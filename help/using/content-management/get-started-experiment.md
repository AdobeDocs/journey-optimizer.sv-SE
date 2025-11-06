---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med innehållsexperiment
description: Läs mer om innehållsexperiment i Journey Optimizer
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: komma igång, börja, innehåll, experimentera
exl-id: 7fe4b24e-f60a-4107-a064-00010b0cbbfc
source-git-commit: efb943e5a6f27becc6e8b6128b776e46d6141823
workflow-type: tm+mt
source-wordcount: '2066'
ht-degree: 0%

---

# Kom igång med innehållsexperiment {#get-started-experiment}

## Vad är ett innehållsexperiment?

Med hjälp av innehållsexperiment kan ni optimera innehåll för åtgärderna i era kampanjer.

Experiment är en uppsättning randomiserade prövningar, som i samband med onlinetestning innebär att vissa slumpmässigt utvalda användare exponeras för en viss variant av ett meddelande och en annan slumpmässigt utvald uppsättning användare för en annan behandling. När du har skickat meddelandet kan du mäta de resultatvärden du är intresserad av, till exempel öppningar av e-postmeddelanden eller klick.

➡️ Ett heltäckande användningsexempel som visar hur du använder innehållsexperiment för att jämföra beslut med den kodbaserade upplevelsekanalen finns i [det här avsnittet](../experience-decisioning/experience-decisioning-uc.md).

## Varför ska du köra Experiment?

![](assets/content_experiment_schema.png)

Experimentera för att isolera de ändringar som leder till förbättringar av mätvärdena. Som framgår av bilden ovan: vissa slumpmässigt utvalda användare exponeras för varje behandlingsgrupp, vilket innebär att grupperna i genomsnitt har samma egenskaper. Skillnader i utfall kan således tolkas som att de beror på skillnader i behandlingarna, dvs. att du kan fastställa ett orsakssamband mellan de ändringar du gjort och de utfall du är intresserad av.

På så sätt kan ni fatta datadrivna beslut för att optimera era era affärsmål.

I Adobe Journey Optimizer kan du testa idéer som:

* **Ämnesrad**: Vilken effekt kan en ändring av tonen eller graden av personalisering av en ämnesrad få?
* **Meddelandeinnehåll**: Kommer en ändring av den visuella layouten för ett e-postmeddelande att resultera i fler klick på e-postmeddelandet?

## Hur fungerar innehållsexperimenten? {#content-experiment-work}

### Slumpmässig tilldelning

Innehållsexperiment i Adobe Journey Optimizer använder en pseudoslumpmässig hash av besöksidentiteten för att slumpmässigt tilldela användare i målgruppen en av de behandlingar som du har definierat. Hash-mekanismen säkerställer att besökarna får samma behandling i scenarier där besökaren går in i en kampanj flera gånger.

MumurHash3 32-bitarsalgoritmen används i detalj för att hash-koda användaridentitetssträngen till en av 10 000 bucket. I ett innehållsexperiment, där 50% av all trafik tilldelas till varje behandling, får användare som hamnar i bucket 1-5 000 den första behandlingen, medan användare i bucketerna 5 001-10 000 får den andra behandlingen. Eftersom pseudoslumpmässiga hashningar används kanske den delade besökaren inte är exakt 50-50, men delningen är ändå statistiskt likvärdig med måldelningsprocenten.

Observera att du måste välja ett identitetsnamnutrymme som userId väljs från för slumpgenereringsalgoritmen när du konfigurerar varje kampanj med ett innehållsexperiment. Detta är oberoende av [körningsadresserna](../configuration/primary-email-addresses.md).

### Datainsamling och -analys

Vid tidpunkten för tilldelningen, dvs. när meddelandet skickas i utgående kanaler, eller när användaren går in i kampanjen i inkommande kanaler, loggas en tilldelningspost i lämplig systemdatauppsättning. Detta registrerar vilken behandling användaren har tilldelats, tillsammans med experiment- och kampanjidentifierare.

Målsättningsstatistik kan grupperas i två huvudklasser:

* Direktmått, där användaren reagerar direkt på behandlingen, t.ex. öppnar ett e-postmeddelande eller klickar på en länk.
* Indirekt eller &quot;bottenströms&quot;-statistik, som inträffar efter att användaren har exponerats för behandlingen.

För direkta objektiva mätvärden där Adobe Journey Optimizer spårar era meddelanden taggas slutanvändarnas svarshändelser automatiskt med kampanj- och behandlingsidentifierarna, vilket möjliggör direkt koppling av svarsmätningen med en behandling. [Läs mer om spårning](../email/message-tracking.md).

![](assets/technote_2.png)

För mål som rör indirekt eller&quot;bottendel av tratten&quot;, t.ex. inköp, är slutanvändarnas responshändelser inte taggade med kampanj- och behandlingsidentifierare, dvs. en köphändelse inträffar efter exponering för en behandling, det finns inget direkt samband mellan köpet och en tidigare behandlingstilldelning. För dessa mätvärden kopplar Adobe behandlingen till nederdelen av trattkonverteringshändelsen om:

* Användaridentiteten är densamma vid tilldelning och konverteringshändelsetid.
* Omvandlingen sker inom sju dagar efter behandlingstilldelningen.

![](assets/technote_3.png)

Adobe Journey Optimizer använder sedan avancerade &quot;närsomhelst giltiga&quot; statistiska metoder för att tolka denna rådatarapportering, som gör att du kan tolka dina experimentella rapporter. Mer information finns på [den här sidan](../content-management/experiment-calculations.md).

## Tips för att köra Experiment

När du kör Experiment är det viktigt att du följer vissa vedertagna standarder. Här följer några tips för att köra dessa experiment:

+++Isolera de variabler du försöker testa

Formge en hypotes som du tänker testa och begränsa hypotesen till så få ändringar som möjligt för att avgöra vad som har påverkat leveransen.

En bra hypotes kan till exempel vara om personalisering i ämnesrader i e-postmeddelanden ger bättre öppningsfrekvens. Men även om du lägger till en ändring i meddelandeinnehållet eller i bilder kan det leda till en förvirrande slutsats.
+++

+++Kontrollera att du använder rätt mått

Bestäm vilket mätvärde du vill ha som mål och om de ändringar du gör kan ha någon direkt inverkan på det här mätvärdet.

Om du till exempel ändrar innehållet i meddelandetexten påverkas inte öppningsfrekvensen för e-post.
+++

+++Kör testet på rätt målgruppsstorlek eller tillräckligt länge

Om du kör testerna längre kan du upptäcka mindre skillnader i målmåttet mellan behandlingarna. Om baslinjevärdet för målmåttet är litet behöver du större samplingsstorlekar.
Antalet användare som måste ingå i ditt experiment beror på vilken effektstorlek du vill identifiera, variationen eller spridningen av målmåttet samt din tolerans för falska positiva och falska negativa fel. I klassiska experiment kan du använda en [exempelstorlekskalkylator](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=sv-SE){_blank} för att avgöra hur länge du måste köra testet.
+++ 

+++Förstå statistisk osäkerhet

Om du kör ett experiment där 1 000 användare har fått en behandling, och konverteringsgraden är inställd på 5 %. Skulle detta vara den faktiska konverteringsgraden om alla användare inkluderades? Vad skulle vara den faktiska konverteringsgraden?
Statistiska metoder ger oss ett sätt att formalisera den osäkerheten. En av de viktigaste begreppen när du kör onlineexperiment är att de konverteringsgrader som observeras är förenliga med en rad underliggande sanna konverteringsgrader, vilket innebär att du måste vänta tills beräkningarna är tillräckligt exakta innan du försöker dra några slutsatser. Konfidensintervall och Förtroende hjälper oss att kvantifiera denna osäkerhet.
+++

+++Skapa nya hypoteser och testa kontinuerligt

För att få verkliga affärsinsikter bör ni hålla er till bara ett experiment. Följ i stället upp experiment genom att formulera nya hypoteser och köra nya tester med olika förändringar på olika målgrupper och genom att undersöka hur de olika mätvärdena påverkas.
+++

## Tolka resultaten av dina experiment {#interpret-results}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_summary"
>title="Sammanfattningswidget"
>abstract="Widgeten Sammanfattning innehåller en översikt över dina experimentresultat, inklusive om de är slutgiltiga eller inte. Det är ett snabbt och enkelt sätt att förstå resultatet av ditt experiment."

![](assets/experimentation_report_3.png)

I detta avsnitt beskrivs Experimentrapporterna och hur man förstår de olika statistiska mängderna som presenteras.

Här följer några riktlinjer för hur du tolkar resultatet av din Content Experiment.

Observera att en fullständig beskrivning av resultaten bör beakta alla tillgängliga bevis (dvs. urvalsstorlekar, konverteringsgrader, konfidensintervall osv.), och inte bara försäkran om att resultatet är slutgiltigt eller inte. Även om resultatet ännu inte är entydigt kan det ändå finnas övertygande bevis för att en behandling skiljer sig från en annan.

Mer information om statistiska beräkningar finns på [sidan](../content-management/experiment-calculations.md).

### &#x200B;1. Jämför normaliserade värden {#normalized-metrics}

När du jämför prestandan för två behandlingar bör du alltid jämföra normaliserade värden för att ta hänsyn till eventuella skillnader i antalet profiler som exponeras för varje behandling.

Om experimentmålet till exempel är **[!UICONTROL Unique Opens]** och en viss behandling visades till 10 000 profiler med 200 unika öppningar, representerar detta **[!UICONTROL Conversion Rate]** 2 %. För icke-unika mått, t.ex. Öppnar mätvärden, visas det normaliserade måttet som **[!UICONTROL Count per Profile]**, medan det normaliserade måttet visas som **[!UICONTROL Total per Profile]** för kontinuerliga mätvärden som Totalt pris.

### &#x200B;2. Fokus på konfidensintervall {#confidence-intervals}

När du experimenterar med prov på dina profiler, representerar den konverteringsgrad som observerats för en given behandling en uppskattning av den verkliga underliggande konverteringsgraden.

Om till exempel Behandling A har **[!UICONTROL Conversion Rate]** på 3%, medan behandling B har observerats till **[!UICONTROL Conversion Rate]** på 2%, är behandling A en bättre prestation än behandling B? För att svara på detta måste vi först kvantifiera osäkerheten i dessa observerade konverteringsgrader.

Konfidensintervall bidrar till att kvantifiera mängden osäkerhet i de uppskattade konverteringsgraden, men bredare konfidensintervall innebär större osäkerhet. När fler profiler läggs till i experimentet blir intervallen mindre, vilket ger en mer exakt uppskattning. Konfidensintervallet representerar ett intervall av konverteringsgrader som är kompatibla med observerade data.

Om konfidensintervallen för två behandlingar knappt överlappar varandra betyder det att de två behandlingarna har olika konverteringsgrader. Men om det finns mycket överlappning mellan konfidensintervallen för två behandlingar är det mer sannolikt att de två behandlingarna har samma konverteringsgrad.

Adobe använder 95 % Anytime Valid Confidence Intervals, eller Confidence Sequences, vilket innebär att resultatet kan visas när som helst under försöket.

### &#x200B;3. Förstå Lyft {#understand-lift}

Sammanfattningen av experimentrapporten visar **[!UICONTROL Lift over Baseline]**, vilket är ett mått på den procentuella förbättringen av konverteringsgraden för en given behandling över baslinjen. Definierat exakt är det skillnaden i prestanda mellan en given behandling och baslinjen, dividerat med baslinjens prestanda, uttryckt i procent.

### &#x200B;3. Förstå förtroende {#understand-confidence}

Även om du i första hand bör fokusera på **[!UICONTROL Confidence interval]** för utförandet av varje behandling, så visar Adobe även förtroendet, vilket är ett sannolikhetsmått på hur mycket det finns belägg för att en viss behandling är densamma som basbehandlingen. Ett högre konfidensintervall tyder på att det inte finns tillräckligt med belägg för antagandet att behandlingar före och efter utgångsvärdet har samma resultat. Mer exakt är den säkerhet som visas en sannolikhet (uttryckt i procent) att vi skulle ha observerat en mindre skillnad i konverteringsgraden mellan en viss behandling och baslinjen, om det i själva verket inte finns någon skillnad i den verkliga underliggande konverteringsgraden. När det gäller p-värden är den konfidensnivå som visas 1 - p-värde.

Adobe använder &quot;Anytime Valid&quot; Confidence, och &quot;Anytime Valid&quot; p-värden som överensstämmer med de Confidence Sequences som beskrivs ovan.

### &#x200B;4. Statistisk betydelse

Vid användning av Experiment anses ett resultat vara statistiskt signifikant om det var mycket osannolikt att det skulle ha observerats med en nollhypotes om att en viss behandling och baslinjen har identiska verkliga underliggande konverteringsgrader/resultat.

Adobe förklarar att en expert är entydig när förtroendet är över 95 %.

## Så här gör du när du har kört en Experiment

När du har kört din Experiment finns det flera möjliga uppföljningsåtgärder:

* **Distribuera vinnande idéer**

  Med ett entydigt resultat kan ni ta fram denna vinnande idé, antingen genom att erbjuda alla era kunder den bästa behandlingen, eller genom att skapa nya kampanjer där strukturen för den bästa behandlingen replikeras.
  </br>Observera att det som fungerar bra på en gång kanske inte fungerar bra senare i en dynamisk miljö.

* **Kör uppföljningstester**

  Ibland kan resultatet av dina försök vara oklart, antingen på grund av att det inte fanns tillräckligt med profiler för att upptäcka skillnader i behandlingar, eller på grund av att behandlingarna du definierade inte var tillräckligt olika.

  Om den hypotes du testade fortfarande är relevant, kan det vara bäst att göra ett uppföljningstest på en större eller annan publik, eller att ändra behandlingarna så att det finns tydligare skillnader.

* **Gör djupgående analyser**

  Den behandling som fungerar bra för en viss målgrupp kanske inte är den bästa behandlingen för en annan målgrupp. Genom att göra djupare analyser av hur behandlingar fungerar för olika målgrupper kan du generera idéer för nya tester.

  På samma sätt kan en studie av hur varje behandling fungerar med olika mätvärden också ge en mer heltäckande bild av dina experiment.

  >[!CAUTION]
  >
  >Fler analyser innebär en större risk för att upptäcka en falsk effekt eller falskt positiv.

## Ytterligare resurser

* **[Skapa innehållsexperiment](content-experiment.md)** - Lär dig hur du utformar och konfigurerar A/B-tester för att optimera meddelandeprestanda.
* **[Experimentera beräkningar](experiment-calculations.md)** - Förstå de statistiska metoder och mätvärden som används i experimentella analyser.
* **[Flerarmad bandit kontra A/B-testning](mab-vs-ab.md)** - Jämför olika experimenteringsmetoder och när varje metod ska användas.
* **[Experimentaccelerator](experiment-accelerator-gs.md)** - Upptäck hur du kan snabba upp experimenterandet med AI-driven optimering.
* **[Experimentera med rapportberäkningar](experiment-report-calculations.md)** - Lär dig hur du tolkar experimentresultat och statistisk signifikans.
* **[Experimenteringsjälvstudiekurser](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/content-management/experimentation-overview){target="_blank"}** - Utforska stegvisa videokurser om innehållsexperiment och metodtips.
