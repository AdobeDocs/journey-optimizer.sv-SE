---
title: Kom igång med innehållsexperiment
description: Läs mer om att experimentera med innehåll i [!DNL Journey Optimizer]
feature: Overview
topic: Content Management, A/B Testing
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 7fe4b24e-f60a-4107-a064-00010b0cbbfc
source-git-commit: 19c52b7c10659305bb729470bf5fa6b9b581bf82
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 0%

---

# Kom igång med innehållsexperiment {#get-started-experiment}

>[!AVAILABILITY]
>
>Funktionen Innehållsexperiment är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

## Vad är en Content Experiment?

Med Content Experiments kan ni optimera innehåll för åtgärderna i era kampanjer.

Experiment är en uppsättning randomiserade prövningar, som i samband med onlinetestning innebär att vissa slumpmässigt utvalda användare exponeras för en viss variant av ett meddelande och en annan slumpmässigt utvald uppsättning användare för en annan behandling. När du har skickat meddelandet kan du mäta de resultatvärden du är intresserad av, t.ex. öppningar av e-postmeddelanden eller klick.

## Varför ska du köra Experiment?

![](assets/content_experiment_schema.png)

Experimentera för att isolera de ändringar som leder till förbättringar av mätvärdena. Se bilden ovan: vissa slumpmässigt utvalda användare exponeras för varje behandlingsgrupp vilket innebär att grupperna i genomsnitt har samma egenskaper. Skillnader i utfall kan således tolkas som att de beror på skillnader i behandlingarna, d.v.s. att du kan fastställa ett orsakssamband mellan de ändringar du gjort och de utfall du är intresserad av.

På så sätt kan ni fatta datadrivna beslut för att optimera era era affärsmål.

För Content Experimentes i Adobe Journey Optimizer kan du testa idéer som:

* **Subject line**: Vilka konsekvenser kan en ändring av tonen eller graden av personalisering av en ämnesrad få?
* **Meddelandeinnehåll**: Kommer en ändring av den visuella layouten för ett e-postmeddelande att resultera i fler klick på e-postmeddelandet?

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
Antalet användare som måste ingå i ditt experiment beror på vilken effektstorlek du vill identifiera, variationen eller spridningen av målmåttet samt din tolerans för falska positiva och falska negativa fel. I klassiska experiment kan du använda en [exempelstorlekskalkylator](https://experienceleague.adobe.com/tools/calculator/testcalculator.html){_blank} för att avgöra hur länge du måste köra testet.
+++

+++Förstå statistisk osäkerhet

Om du kör ett experiment där 1 000 användare har fått en behandling, och konverteringsgraden är inställd på 5 %. Skulle detta vara den faktiska konverteringsgraden om alla användare ingick? Vad skulle vara den faktiska konverteringsgraden?
Statistiska metoder ger oss ett sätt att formalisera den osäkerheten. En av de viktigaste begreppen när du kör onlineexperiment är att de konverteringsgrader som observeras är förenliga med en rad underliggande sanna konverteringsgrader, vilket innebär att du måste vänta tills beräkningarna är tillräckligt exakta innan du försöker dra några slutsatser. Konfidensintervall och Förtroende hjälper oss att kvantifiera denna osäkerhet.
+++

+++Skapa nya hypoteser och testa kontinuerligt

För att få verkliga affärsinsikter bör ni hålla er till bara ett experiment. I stället kan du följa upp experiment genom att formulera nya hypoteser och köra nya tester med olika förändringar, i olika segment och genom att undersöka hur de olika mätvärdena påverkas.
+++

## Tolka resultaten av dina experiment {#interpret-results}

![](assets/experimentation_report_3.png)

I detta avsnitt beskrivs Experimentrapporterna och hur man förstår de olika statistiska mängderna som presenteras.

Här följer några riktlinjer för hur du tolkar resultatet av din Content Experiment.

Observera att en fullständig beskrivning av resultaten bör beakta alla tillgängliga bevis (dvs. urvalsstorlekar, konverteringsgrader, konfidensintervall osv.), och inte bara försäkran om att resultatet är slutgiltigt eller inte. Även om resultatet ännu inte är entydigt kan det ändå finnas övertygande bevis för att en behandling skiljer sig från en annan.

Om du vill förstå statistiska beräkningar kan du läsa detta [page](../campaigns/experiment-calculations.md).

### 1. Jämför normaliserade värden {#normalized-metrics}

När du jämför prestandan för två behandlingar bör du alltid jämföra normaliserade värden för att ta hänsyn till eventuella skillnader i antalet profiler som exponeras för varje behandling.

Om experimentmålet till exempel är inställt på **[!UICONTROL Unique Opens]**, och en viss behandling visades till 10 000 profiler med 200 unika öppningar inspelade, så representerar detta **[!UICONTROL Conversion Rate]** av 2 %. För icke-unika mått, t.ex. opens-metriska, visas det normaliserade måttet som en **[!UICONTROL Count per Profile]**, medan det normaliserade måttet visas som en **[!UICONTROL Total per Profile]**.

### 2. Fokus på konfidensintervall {#confidence-intervals}

När du experimenterar med prov på dina profiler, representerar den konverteringsgrad som observerats för en given behandling en uppskattning av den verkliga underliggande konverteringsgraden.

Om till exempel Behandling A har en **[!UICONTROL Conversion Rate]** 3% medan behandling B har observerats **[!UICONTROL Conversion Rate]** 2 procent, är behandling A bättre än behandling B? För att svara på detta måste vi först kvantifiera osäkerheten i dessa observerade konverteringsgrader.

Konfidensintervall bidrar till att kvantifiera mängden osäkerhet i de uppskattade konverteringsgraden, men bredare konfidensintervall innebär större osäkerhet. När fler profiler läggs till i experimentet blir intervallen mindre, vilket ger en mer exakt uppskattning. Konfidensintervallet representerar ett intervall av konverteringsgrader som är kompatibla med observerade data.

Om konfidensintervallen för två behandlingar knappt överlappar varandra betyder det att de två behandlingarna har olika konverteringsgrader. Men om det finns mycket överlappning mellan konfidensintervallen för två behandlingar är det mer sannolikt att de två behandlingarna har samma konverteringsgrad.

Adobe använder 95 % Anytime Valid Confidence Intervals, eller Confidence Sequences, vilket betyder att resultatet kan visas när som helst under försöket.

### 3. Förstå Lyft {#understand-lift}

Sammanfattningen av expertrapporten visar **[!UICONTROL Lift over Baseline]**, vilket är ett mått på den procentuella förbättringen av konverteringsgraden för en given behandling jämfört med baslinjen. Definierat exakt är det skillnaden i prestanda mellan en given behandling och baslinjen, dividerat med baslinjens prestanda, uttryckt i procent.

### 3. Förstå förtroende {#understand-confidence}

Du bör fokusera på **[!UICONTROL Confidence interval]** För varje behandlingsstart visar Adobe också förtroendet, vilket är ett sannolikhetsmått på hur mycket det finns belägg för att en viss behandling är densamma som ursprungsbehandlingen. Ett högre konfidensintervall tyder på att det inte finns tillräckligt med belägg för antagandet att behandlingar före och efter utgångsvärdet har samma resultat. Mer exakt är den säkerhet som visas en sannolikhet (uttryckt i procent) att vi skulle ha observerat en mindre skillnad i konverteringsgraden mellan en viss behandling och baslinjen, om det i själva verket inte finns någon skillnad i den verkliga underliggande konverteringsgraden. När det gäller p-värden är den konfidensnivå som visas 1 - p-värde.

Adobe använder &quot;Anytime Valid&quot; Confidence, och &quot;Anytime Valid&quot; p-värden som överensstämmer med de Confidence Sequences som beskrivs ovan.

### 4. Statistisk signifikans

Vid användning av Experiment anses ett resultat vara statistiskt signifikant om det var mycket osannolikt att det skulle ha observerats med en nollhypotes om att en viss behandling och baslinjen har identiska verkliga underliggande konverteringsgrader/resultat.

Adobe förklarar att en expert är entydig när förtroendet är över 95 %.

## Så här gör du när du har kört en Experiment

När du har kört din Experiment finns det flera möjliga uppföljningsåtgärder:

* **Skapa vinnande idéer**

   Med ett entydigt resultat kan ni ta fram denna vinnande idé, antingen genom att erbjuda alla era kunder den bästa behandlingen, eller genom att skapa nya kampanjer där strukturen för den bästa behandlingen replikeras.
   </br>Observera att det som fungerar bra på en gång kanske inte fungerar bra senare i en dynamisk miljö.

* **Kör uppföljningstester**

   Ibland kan resultatet av dina försök vara oklart, antingen på grund av att det inte fanns tillräckligt med profiler för att upptäcka skillnader i behandlingar, eller på grund av att behandlingarna du definierade inte var tillräckligt olika.

   Om den hypotes du testade fortfarande är relevant, kan det vara bäst att göra ett uppföljningstest på en större eller annan publik, eller att ändra behandlingarna så att det finns tydligare skillnader.

* **Gör djupare analyser**

   Den behandling som fungerar bra för en viss målgrupp kanske inte är den bästa behandlingen för en annan målgrupp. Detaljerade analyser av hur behandlingar fungerar för olika segment hjälper till att generera idéer för nya tester.

   På samma sätt kan en studie av hur varje behandling fungerar med olika mätvärden också ge en mer heltäckande bild av dina experiment.

   >[!CAUTION]
   >
   >Fler analyser innebär en större risk för att upptäcka en falsk effekt eller falskt positiv.
