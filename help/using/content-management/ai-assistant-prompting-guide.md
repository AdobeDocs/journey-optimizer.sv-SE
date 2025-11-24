---
solution: Journey Optimizer
product: journey optimizer
title: Guiden Fråga om innehåll i AI Assistant
description: Lär dig hur du skapar effektiva uppmaningar för AI-driven innehållsgenerering med hjälp av CO-STAR-ramverket för att skapa varumärkesanpassat, konverterande marknadsföringsmaterial.
role: User
level: Intermediate
source-git-commit: bacfe2e04898e8417308e3f1c889214547e3ea02
workflow-type: tm+mt
source-wordcount: '2088'
ht-degree: 0%

---


# Bästa praxis för AI Assistant-tips {#ai-assistant-prompting-guide}

Den här guiden hjälper er att strukturera era förfrågningar, förmedla avsikter på ett tydligt sätt och se till att AI producerar meddelanden som är anpassade till era varumärkesriktlinjer, målgruppsbehov och kampanjmål.
Lär dig hur du skriver effektiva uppmaningar som gör det möjligt för AI Assistant att generera högkvalitativt marknadsföringsmaterial som är skräddarsytt efter era mål.

## Använda CO-STAR-ramverket {#costar-framework}

För bästa resultat med AI Assistant kan du ordna dina frågor med hjälp av CO-STAR-ramverket. Denna strukturerade strategi säkerställer att AI förstår exakt vad du behöver.

| Komponent | Vad det betyder | Varför det spelar någon roll |
|-|-|-|
| **C - kontext** | Bakgrund om kampanjen, produkten eller situationen | Hjälper AI att förstå helhetsbilden |
| **O - Mål** | Ditt specifika marknadsföringsmål | Skapar det som innehållet ska uppnå |
| **S - Format** | Hur du vill kommunicera | Anger metod |
| **T - Ton** | Rörelsekänsla | Formar hur ditt meddelande känns |
| **A - Målgrupp** | Målgrupp ni riktar er mot | Garanterar att budskapet besvaras av rätt personer |
| **R - Krav** | Specifika begränsningar eller måste-ha | Definierar gränser och viktiga element |

## AI-prompter - grundläggande {#key-takeaways}


### Gör och inte


<table style="table-layout: fixed; width: 100%; border: 0;">
<thead style="border: 0; background-color: #FFFFFF;">
<tr>
<th>Gör</th>
<th>Gör det inte</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<p>Använd CO-STAR-ramverket för strukturen</p>
<p>Var tydlig med aktuellt och befintligt innehåll</p>
<p>Fokusera dokumentanvändning med specifik extraheringsvägledning</p>
<p>Använd listrutor för ton, strategi och språkområde</p>
<p>Matcha marknadsföringsmål med innehållstypfunktioner</p>
<p>Generera flera varianter för A/B-testning</p>
</td>
<td>
<p>Fråga efter strukturändringar, format eller bildredigering i uppmaningar</p>
<p>Ange ton/strategi i uppmaningar om de är tillgängliga i listrutor</p>
<p>Använd vaga mål som"marknadsför vår produkt"</p>
<p>Begär val av villkorliga element</p>
<p>Förvänta dig layoutändringar via uppmaningar</p>
</td>
</tr>
</tbody>
</table>

### Innehåll som inte stöds i uppmaningar

>[!TIP]
>
>Använd **e-postredigeraren** eller **Adobe Express** för visuella ändringar/bildändringar.

Dessa begäranden stöds inte och bör hanteras med andra verktyg:

<table style="table-layout: fixed; border: 0;">
<thead style="border: 0; background-color: #FFFFFF">
<tr>
<th>✕ e-poststrukturändringar</th>
<th>✕ visuella formatändringar</th>
<th>✕ bildredigering</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul>
<li>Markera specifika avsnitt som ska ändras</li>
<li>Ta bort eller klona element</li>
<li>Villkorliga markeringar</li>
<li>Lägga till eller ta bort layoutavsnitt</li>
</ul>
</td>
<td>
<ul>
<li>Textformatering (fet, kursiv, teckensnittsstorlek)</li>
<li>Färgändringar</li>
<li>Layoutstil (kanter, utfyllnad, marginaler)</li>
<li>Visuella effekter (skuggor)</li>
</ul>
</td>
<td>
<ul>
<li>Ändringar i bakgrunden</li>
<li>Lägga till textövertäckningar eller logotyper</li>
<li>Bilders beskärning eller storleksändring</li>
<li>Färgjusteringar</li>
<li>Bildersättning</li>
</ul>
</td>
</tr>
</tbody>
</table>

### Kvalitetskontrolllista {#quality-checklist}

Innan du genererar innehåll bör du kontrollera följande:

&amp;check; **Clear Objective**: Anger tydligt åtgärd, produkt/tjänst, värde och sammanhang.

&amp;check; **Definierad målpublik**: Anger demografi, roll eller segment.

&amp;check; **Justering av innehållstyp**: Målet matchar den valda kanalen eller det valda formatet.

&amp;check; **Listrutor konfigurerade**: Ton, strategi och språkområde har valts, ta inte med dem i uppmaningen.

&amp;check; **Dokumentfokus angiven**: Markerar vilket innehåll eller vilka avsnitt som ska refereras.

&amp;check; **Varumärke används**: Lämpliga varumärkesriktlinjer har valts.

&amp;check; **Realistiskt omfång**: Undvik begäranden om layoutändringar, formatering eller strukturändringar.

## Skriv effektiva marknadsföringsmål {#marketing-objectives}

### Var specifik och handlingsinriktad

När ni utformar marknadsföringsmålen ska ni se till att de är tydliga, användbara och mätbara. Undvik vaga eller generiska programsatser.

**Exempel på bra mål:**

&amp;check;&quot;Drive sign-ups for our free 30 day trial of the new AI-powered analytics dashboard&quot;

&amp;check;&quot;Generera leads för vårt B2B-webbinarium om &#39;Minska molnkostnaderna med 40 %&#39; som inträffar den 15 mars&quot;

&amp;check; &quot;Promote our limited-time 25% semester discount on premium subscriptions, ending December 25th&quot;

**Exempel som ska undvikas:**

✕ &quot;Promote our product&quot; (too vague)

✕&quot;Få människor att köpa saker&quot; (oklart värde)

✕&quot;E-post om nya funktioner&quot; (saknar syfte)

### Strukturera ditt mål

Ange alltid sammanhang och värdeförslag så att AI kan generera relevant innehåll.
Använd den här formeln för att hjälpa dig att skriva effektiva mål: **Åtgärd + produkt/tjänst + värde/förmån + brådskande/kontext**

**Exempel på bra mål:**

&amp;check;&quot;Uppmuntra nedladdningar av vår nya mobilapp som hjälper användarna att spåra hållbara levnadsvanor med personaliserade, miljövänliga rekommendationer&quot;

&amp;check;&quot;Promote registration for our exclusive workshop on advanced data visualization techniques for marketing professionals&quot;

&amp;check;&quot;Driv närvaro vid vår produktlanseringsevent med den revolutionerande AI-skrivassistenten som sparar mer än fem timmar per vecka&quot;

**Exempel som ska undvikas:**

✕ &quot;Announce new app&quot; (värdeförslag och kontext saknas)

✕&quot;Be personer registrera sig för workshop&quot; (saknar specificitet om målgrupp och förmån)

✕ &quot;Promote event&quot; (ingen tydlig åtgärd, värde eller trängning)

## Skapa nytt innehåll kontra ändra befintligt innehåll {#new-vs-modify}

Ange tydligt om din begäran inbegriper generering av nytt innehåll eller uppdatering av befintligt material. Skillnaden är viktig eftersom den vägleder AI vid valet av lämplig metod och ger ett mer exakt och användbart resultat.

### Skapa nytt innehåll

Använd den här strategin när ni lanserar marknadsföringskampanjer, presenterar nya produkter eller initierar någon form av uppdaterad eller uppdaterad kommunikation. Det ser till att ert budskap börjar starkt och anpassar sig efter era mål.

**Fråga** ➤ När du skapar nytt innehåll ska du fokusera på ditt marknadsföringsmål utan att referera till befintligt innehåll.

>[!BEGINSHADEBOX]

**Exempel:**

* **Testversion av SaaS**:&quot;Starta vår nya CRM-programvara för småföretagare, markera 50 % tidsbesparingar, 90 % snabbare leads och erbjuda en 30-dagars kostnadsfri testversion med personlig introduktion&quot;
* **Funktionsmeddelande**:&quot;Nya API-integreringsfunktioner som minskar utvecklingstiden med 60 % för företagskunder, med inriktning på tekniska beslutsfattare&quot;
* **Evenemangskampanj**:&quot;Kör registreringar för vårt webbinarium om Digital Marketing Trends 2024&quot; med experter från Google, Meta och Adobe, som betonar åtgärdbara insikter och begränsade licenser (max 500)&quot;

>[!ENDSHADEBOX]

### Ändra befintligt innehåll

>[!TIP]
>
>Använd funktionen **Förfina** i stället för att skriva anpassade uppmaningar för standardändringar som att bearbeta, sammanfatta eller förenkla. [Läs mer](generative-uc.md##refine)

Använd detta när ni behöver uppdatera, uppdatera eller anpassa era aktuella marknadsföringskampanjer. Den här metoden har stöd för stegvisa förbättringar som säkerställer att ditt meddelande förblir relevant utan att börja om från början.

**Fråga** ➤ Ange tydligt vad du vill ändra och hur det ska ändras när du ändrar befintligt innehåll.

>[!BEGINSHADEBOX]

**Exempel:**

* **Kampanjuppdatering**:&quot;Ändra e-postmeddelandet om produktlansering så att det fokuserar på företagssäkerhetsfunktioner i stället för allmänna produktivitetsfördelar, så att IT-beslutsfattare med efterlevnadscertifieringar kan målinriktas&quot;
* **Målgruppsinfo**:&quot;Anpassa vår demoinbjudan till programvaror så att den riktar sig till hälso- och sjukvården specifikt och ersätta generiska exempel med vårdärenden och efterlevnadsfördelar inom HIPAA&quot;
* **Säsongsuppdatering**:&quot;Uppdatera vår kampanj Q3 för semester i Q4, ändra fokus från skolstart till semester med snabb betoning på frakt&quot;

>[!ENDSHADEBOX]

## Förbättra prompten med avancerade inställningar {#personalize-prompt}

### Typ av kommunikationsstrategi

>[!TIP]
>
>Använd listrutan Kommunikationsstrategi på menyn Textinställningar i stället för att ange den i prompten för specialbearbetning.

Er kommunikationsstrategi avgör hur ni förmedlar ert budskap för att maximera effekten. Olika strategier fungerar bättre för olika mål, oavsett om du skapar trängsel, skapar förtroende eller driver omedelbara åtgärder. Välj den strategi som bäst passar era kampanjmål och målgruppsinsikter.

| **Strategi** | **Bäst för** | **Meddelandeformat** | **Exempel** |
|--------------|--------------|------------------------|--------------|
| **Brådskande** | Tidskänsliga erbjudanden, leveranstider, omedelbar åtgärd | Skapar ett omedelbart tryck med ett tidsbaserat språk | &quot;Slå till nu: Erbjudandet gäller till midnatt&quot; <br> &quot;Registrera dig idag innan fläckarna fylls&quot; <br> &quot;48-timmars blixtförsäljning börjar nu&quot; |
| **FOMO (rädsla för att saknas)** | Begränsade erbjudanden, evenemang, exklusiv åtkomst | Använder tidsåtgång, knapphet och ledtrådar | &quot;Bara 24 timmar kvar! Begränsat lager med 40 % rabatt&quot; <br>&quot;Sista chansen: Sista chansen: Sista chansen med tidig fågelprissättning upphör imorgon&quot; <br>&quot;Endast 100 betapunkter återstår&quot; |
| **Socialt korrektur** | Pålitlighetsuppbyggnad, utlåtanden, populära produkter | Utnyttjar andras upplevelser och validering | &quot;Gå med i 50 000 fler nöjda kunder&quot; <br> &quot;Betygsatta 4,9/5 stjärnor av branschfolk&quot; <br> &quot;Betrodda av Fortune 500-företag&quot; |
| **Scharlakans** | Begränsat lager, exklusiva releaser, efterfrågade artiklar | Framhäver begränsad tillgänglighet och exklusivitet | &quot;Endast 5 kvar i lager&quot; <br> &quot;Begränsad version: 100 enheter tillgänglig&quot; <br> &quot;Exklusiv version: först till kvarn&quot; |
| **Incentive** | Erbjudanden, belöningsprogram, specialerbjudanden | Visar påtagliga fördelar och belöningar | &quot;Få 20 % rabatt på din första beställning&quot; <br> &quot;Få dubbla poäng i helgen&quot; <br> &quot;Fri frakt på beställningar över 50 dollar&quot; |
| **Exklusivitet** | Premiumprodukter, VIP-upplevelser, erbjudanden som endast är för medlemmar | Använder premiumpositionering och specialåtkomstspråk | &quot;Exklusiv inbjudan till vår privata förhandsgranskning&quot; <br> &quot;Elitmedlemskapet låser upp avancerade analyser&quot; <br> &quot;Gå med i utvalda Fortune 500-företag som redan använder oss&quot; |
| **Gamification** | Engagerande kampanjer, lojalitetsprogram, interaktivt innehåll | Använder spelmekanik och målgruppsspråk | &quot;Lås upp din nästa belöningsnivå&quot; <br> &quot;Slutför utmanar att vinna brickor&quot; <br> &quot;Klättra på resultatlistan för exklusiva priser&quot; |
| **Informativ** | Utbildning, forskning, komplexa produkter, tankeledarskap | Fakta, data, insikter och förklaringar används | &quot;5 insikter från analys av 10 000+ interaktioner&quot; <br> &quot;Ny forskning avslöjar tre banbrytande strategier&quot; <br> &quot;Fullständig guide till implementering av AI i marknadsföring&quot; |
| **Utbildning och insikter** | Utbildningsinnehåll, branschtrender, bästa praxis | Ger värdefull kunskap och användbara arbetsmetoder | &quot;Lär dig mer om avancerade tekniker med vår expertguide&quot; <br> &quot;Upptäck sju strategier som marknadsförarna använder&quot; <br> &quot;Lär dig hur du optimerar ditt arbetsflöde i fem steg&quot; |

### Ange rätt ton {#tone}

>[!TIP]
>
>Använd listrutan Ton på menyn Textinställningar i stället för att ange den i uppmaningen.

Tone formar hur publiken upplever och svarar på ert budskap. Välj alltid en ton som är anpassad efter ert varumärkestrotal och det stadium som profilresan tar.

Använd tabellen nedan för att utforska varje ton i detalj, inklusive när den fungerar bäst och exempel på innehåll som passar varje format.

| Tonalitet | Bäst för | Exempel på innehåll |
|-|-|-|
| Professional | B2B-kommunikation, formella meddelanden | &quot;Vi har nöjet att meddela vårt strategiska partnerskap ...&quot; |
| Empatetisk | Kundsupport, känsliga ämnen | &quot;Vi förstår hur frustrerande det här måste vara för dig..&quot; |
| Humoristisk | Engagerande kampanjer, lättanvänt innehåll | &quot;Varning: Kan orsaka stora produktivitetsvinster!&quot; |
| Spännande | Produktlanseringar, eventkampanjer | &quot;Det här är ögonblicket du har väntat på!&quot; |
| Inspirerande | Motivationskampanjer, varumärkessyfte | &quot;Tillsammans kan vi göra skillnad i världen..&quot; |
| Engagerande | Försäljningskampanjer, konverteringar | &quot;Missa inte denna tidsbegränsade möjlighet att ...&quot; |
| Egen | Kundengagemang, välkomstmeddelanden | &quot;Vi är så glada att du är här med oss!&quot; |
| Formell | Juridiska meddelanden, officiella meddelanden | &quot;Vi meddelar dig härmed om följande ändringar..&quot; |
| Apologetisk | Återställning av tjänster, problemlösning | &quot;Vi ber om ursäkt för eventuella olägenheter..&quot; |
| Assertiv | Ledarinnehåll, auktoritativa meddelanden | &quot;Det här måste du göra nu..&quot; |
| saga | Varumärkesberättelser, känslomässiga kopplingar | &quot;Allt började med en enkel fråga..&quot; |
| Konversationslayout | Strukturkampanjer, relationsskapande | &quot;Låt oss prata om hur det här kan hjälpa dig ...&quot; |

### Optimera ert varumärkesmaterial {#brand-assets}

>[!TIP]
>
>Om du redan har överfört en varumärkesresurs via menyn **Varumärke-Assets** behöver du inte referera till den i uppmaningen. Alla valda dokument används automatiskt.

Varumärkesresurser ger faktainformation som berikar ert genererade innehåll med specifika, korrekta detaljer.
När du överför breda dokument, t.ex. produktbroschyrer, ska du lägga till vilka delar du ska fokusera på:

* **I stället för** _&quot;Använd produktbroschyren&quot;_ **bör du använda** _&quot;Fokusera på de avancerade säkerhetsfunktionerna och kompatibilitetscertifieringarna, särskilt SOC 2-kompatibilitet och datakryptering&quot;_

* **I stället för** _&quot;Referera fallstudierna&quot;_ **ska du använda** _&quot;Resultat av räntabilitet från vårdklienter, närmare bestämt 40-procentig kostnadsminskning på Regional Medical Center&quot;_

* **I stället för** _&quot;Inkludera teknisk information&quot;_ **ska du använda** _&quot;Fokusera API-integreringsfunktioner och utvecklarfördelar, med fokus på REST API-slutpunkter och 99,9 % aktiv SLA&quot;_

### Innehållsförbättring

>[!TIP]
>
>Använd funktionen Förfina i stället för att fråga när du vill bearbeta, sammanfatta, förenkla, ändra ton eller översätta befintligt innehåll. [Läs mer](generative-uc.md#refine)

När innehållet har genererats kan du använda funktionen **Förfina** för att iterera och förbättra det med följande alternativ:

| **Åtgärd** | **Använd skiftläge** | **Fråga exempel** |
|-|-|-|
| **Samarbeta** | Lägg in djup och detaljer i innehållet | &quot;Samarbeta om de tekniska fördelarna med våra säkerhetsfunktioner&quot; |
| **Sammanfattning** | Komprimera långt innehåll för olika format | &quot;Sammanfatta den här produktöversikten för inlägg i sociala medier&quot; |
| **Förenkla** | Göra komplext innehåll tillgängligare | &quot;Förenkla denna tekniska förklaring för en allmän publik&quot; |
| **Ändra ton** | Anpassa innehåll för olika målgrupper | &quot;Ändra tonen till mer vardaglig för yngre demografiska förändringar&quot; |
| **Omskapa** | Kulturell anpassning bortom översättning | &quot;Skapa denna kampanj för den japanska marknaden&quot; |

## Scenariobaserade frågeexempel

### Baserat på innehållstyp {#content-type-practices}

<table style="table-layout: fixed; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Kanal</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>E-post</strong></td>
<td>"Ge storföretag en skjuts framåt genom att presentera tre framgångsberättelser med detaljerade avkastningsmått (IBM: 45 % kostnadsminskning, Accenture: 200 % ökning, Microsoft: 60 % tidsbesparing), riktade IT-chefer på företag med över 1 000 anställda"</td>
</tr>
<tr>
<td><strong>SMS</strong></td>
<td>"Meddela VIP-kunder om 4-timmars blixtförsäljning på premiumelektronik med 40 % rabatt, begränsad till de första 100 kunderna"</td>
</tr>
<tr>
<td><strong>Push-meddelanden</strong></td>
<td>"Engagera användare som inte har öppnat appen på 7 dagar igen med personaliserade innehållsrekommendationer baserade på läshistoriken"</td>
</tr>
<tr>
<td><strong>Landningssidor</strong></td>
<td>"Konvertera B2B-besökare till kvalificerade leads genom att visa hur vår säkerhetslösning förhindrar 99,9 % av cyberattackerna, med Fortune 500-utlåtanden och kostnadsfri säkerhetsrevision"</td>
</tr>
</tbody>
</table>

### Baserat på branschspecifika metoder {#industry-approaches}

<table style="table-layout: fixed; border-collapse: collapse; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Bransch</th>
<th>Exempelfråga</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>B2B-teknik</strong></td>
<td>"Uppvisa ROI och tekniska specifikationer samtidigt som ni tar itu med säkerhetsfrågor för IT-beslutsfattare som utvärderar vår molninfrastrukturslösning, med betoning på 99,9 % drifttid för SLA, SOC 2-kompatibilitet och 40 % kostnadsbesparingar."</td>
</tr>
<tr>
<td><strong>E-handel</strong></td>
<td>"Skapa ett trängande tempo kring tidsbegränsade semesterprodukter och framhäv samtidigt fri frakt och enkel retur för sista minuten-kunder, med betoning på begränsade mängder (mindre än 50 kvar) och 24 timmars leveransstopp."</td>
</tr>
<tr>
<td><strong>Finansiella tjänster</strong></td>
<td>"Undervisa kunderna om strategier för diversifiering av investeringsportföljer samtidigt som man upprätthåller regelefterlevnad, med certifierade insikter från finansiella rådgivare och riskfriskrivningar."</td>
</tr>
<tr>
<td><strong>Hälso- och sjukvård</strong></td>
<td>"Främja förebyggande vårdförmåner och årliga hälsokontroller samtidigt som man bevarar medicinsk precision, med bräddarsydda läkarrekommendationer och patientsekretessgarantier."</td>
</tr>
<tr>
<td><strong>Utbildning</strong></td>
<td>"Framhäv karriärutvecklingsresultat och branschcertifieringar och visa upp lärarexpertis, som visar upp 92-procentig jobbplacering och projektbaserad kursplan."</td>
</tr>
<tr>
<td><strong>SaaS-plattformar</strong></td>
<td>"Spara tid och automatisera med specifika mätvärden och ta itu med integreringsproblemen, med genomsnittliga tidsbesparingar under 25 timmar per vecka och integrering med över 200 populära verktyg."</td>
</tr>
</tbody>
</table>
