---
solution: Journey Optimizer
product: journey optimizer
title: Utforma tillgängligt innehåll
description: Lär dig hur du utformar tillgängligt innehåll för e-postmeddelanden och landningssidor i Journey Optimizer
feature: Email Design, Landing Pages
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: e-post, design, tillgänglighet
exl-id: 78011ec0-a3b6-4d4e-ab4b-9da032c283a2
source-git-commit: a5dd21377a26debb0aa3174fafb29c0532562c63
workflow-type: tm+mt
source-wordcount: '1627'
ht-degree: 0%

---

# Utforma tillgängligt innehåll {#accessible-content}

Den [europeiska tillgänglighetslagen](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32019L0882){target="_blank"} är ett direktiv som är utformat för att förbättra den inre marknaden för tillgängliga produkter och tjänster genom att eliminera hinder som orsakas av olika nationella regler i medlemsstaterna.

I den här förordningen anges att all digital kommunikation, inklusive e-post, nyhetsbrev, PDF-filer och hämtningsbart innehåll, bör vara tillgänglig. När du skapar innehåll för dina mottagare måste du därför följa särskilda riktlinjer, t.ex. använda hjälpmedelsanpassade teckensnitt, läsbara format och tillhandahålla alternativ text för bilder.

Med [!DNL Journey Optimizer] [Email Designer](content-from-scratch.md), som gör det möjligt för marknadsförare att skapa innehåll både för **e-post** och **landningssidor**, kan du enkelt följa det här direktivet, baserat på Web Content Accessibility Guidelines (WCAG) 2.1, nivå AA.

I enlighet med detta listas de bästa sätten att utforma hjälpmedelsanpassat innehåll med [!DNL Journey Optimizer] nedan.

>[!NOTE]
>
>Den här sidan handlar om att göra ditt innehåll tillgängligt för alla dina mottagare, så att personer med funktionshinder kan läsa, förstå och interagera med dina e-postmeddelanden och landningssidor som är utformade med [!DNL Journey Optimizer].
>
>Å andra sidan är hjälpmedelsfunktionerna för gränssnittet [!DNL Journey Optimizer] detaljerade i [det här avsnittet](../start/accessibility.md).

## Säkra textläsbarhet {#text-readability}

Utnyttja fliken **[!UICONTROL Styles]** i komponenten **[!UICONTROL Text]** för att säkerställa att texten är läsbar, till exempel genom att använda rätt färgkontrast och enkla teckensnitt. [Läs mer](content-components.md#text)

![](assets/accessible-text-styles.png){width="80%"}

För teckensnitt och text måste du följa riktlinjerna nedan:

**Val av teckensnitt**

* Använd sans-serif-teckensnitt som Arial, Verdana, Tahoma, Helvetica eller Open Sans.
* Undvik serif-, cursive- och dekorativa teckensnitt i brödtextinnehållet.
* Behåll en begränsad teckensnittsuppsättning för konsekvens och reservteckensnitt (till exempel: `font-family: Arial, Helvetica, sans-serif;`).

**Teckensnittsstorlek**

* Se till att teckensnittsstorleken är minst 16px för brödtext.
* Använd rätt hierarki för rubriker.

**Färgkontrast**

* Behåll ett kontrastförhållande på minst 4,5:1 mellan text och bakgrund.
* För stor text (≥24px eller fet 18px) måste du se till att kontrasten är minst 3:1.
* Undvik ljusgrå eller pastelltext på vita bakgrunder.
* Förlita dig inte på enbart färg för att förmedla innebörden, utan använd i stället understrykningar, ikoner osv.

**Texttillgänglighet**

* Undvik text i bilder.
* Använd inte versaler i brödtexten.
* Se till att texten kan zoomas upp till 200 % utan att layouten bryts.

## Säkerställ visuell tillgänglighet {#visual-accessibility}

Följ de bästa metoderna nedan för att se till att ditt innehåll är synligt:

* Undvik att använda färgbara indikatorer för viktig information.
* Använd textetiketter och ikoner för att säkerställa tydlighet.
* Optimera designen för mobil och responsiv layout och se till att knapparna är stora och har rätt avstånd.
* Testa regelbundet olika enheter och skärmstorlekar för att bevara tillgängligheten.

I [!DNL Journey Optimizer] kan storleken och mellanrummet för de olika elementen i ditt innehåll förfinas ytterligare med formatparametrarna och attributen i e-postrutan för Designer **[!UICONTROL Styles]**. [Lär dig hur](get-started-email-style.md)

Du kan till exempel uppdatera [bakgrunden](backgrounds.md) eller ändra marginalerna, utfyllnaden och justeringen för att förbättra innehållets visuella tillgänglighet. [Läs mer](alignment-and-padding.md)

![](assets/accessible-styles.png){width="80%"}

Dessutom kan du förhandsgranska och optimera designen för olika enheter och skärmstorlekar med e-post [!DNL Journey Optimizer] från Designer. Du kan när som helst **[!UICONTROL Switch to live view]** för att kontrollera hur ditt innehåll kan återges på olika enhetsstorlekar.

![](assets/accessible-live-view.png){width="80%"}

>[!CAUTION]
>
>Live-vyn är en allmän förhandsvisning som är utformad för att jämföra hur återgivningen kan se ut på olika enhetsstorlekar. Den slutliga återgivningen kan variera beroende på mottagarens e-postklient.

## Använd alternativ text för bilder {#alt-text}

Använd komponenten **[!UICONTROL Image]** för att ange alternativ text för bilder. [Lär dig hur](content-components.md#image)

![](assets/accessible-alt-text.png){width="90%"}

För effektiv alternativ text i digitala produkter, följ riktlinjerna nedan:

* Beskriv syftet med bilden kortfattat och i sitt sammanhang.
* Undvik överflödiga fraser som &quot;Bild av ...&quot; och använd tom alt-text för dekorativa bilder.
* För ikoner med betydelse, ange meningsfulla etiketter och för komplexa bilder använder du en kort alternativ text plus en längre beskrivning någon annanstans.

## Använd läsbart format {#readable-format}

Använd den relevanta strukturen för e-postprogrammet för Designer och [innehållskomponenter](content-components.md), samt alternativen i rutan **[!UICONTROL Styles]**, för att ordna ditt innehåll på ett tydligt, logiskt och koncist sätt som är tillgängligt för alla.

![](assets/accessible-components.png){width="100%"}

* Använd strukturerad, semantisk HTML med rätt rubriker, stycken, listor och tabeller.
* Se till att innehållet följer ett logiskt flöde från vänster till höger, uppifrån och ned.
* Använd klart och koncist språk.
* Ange alternativa format för PDF:er och infografik.
* Tillåt storleksändring och omformning av text och se till att typografin är läsbar med tillräcklig färgkontrast i alla format.

## Säkerställ läsbarhet {#readability}

För att innehållet ska vara läsbart måste det vara klart, välstrukturerat och användbart för alla, även för personer med visuella, kognitiva eller läsrelaterade problem och för dem som använder hjälpmedelstekniker. Några saker du bör tänka på när du skapar hjälpmedelsanpassat innehåll är:

* Behålla meningar till omkring 20 ord eller mindre.
* Redigera kopian så att den blir direkt och direkt.
* Använd aktiv röst för att förenkla meningsbyggnaden.
* Undvik slang, jargon och regionala ord som vissa kanske inte känner till.

Om du vill utvärdera läsbarheten för e-post kan du använda det populära [Flesch Reading Ease-testet](https://support.microsoft.com/en-us/office/get-your-document-s-readability-and-level-statistics-85b4969e-e80a-4777-8dd3-f7fc3c8b3fd2){target="_blank"} som finns i Microsoft Word och som beräknar hur enkelt innehållet är att läsa på en skala från 0 till 100.

## Testa innehållet {#test}

Om du vill verifiera innehållets tillgänglighet kan du använda testfunktionerna i [!DNL Journey Optimizer]. De är inte särskilt utformade för att kontrollera om ditt innehåll är fullt tillgängligt, men de kan tillhandahålla en första verifieringsnivå.

* Förhandsgranska innehållet med testprofiler. [Lär dig hur](../content-management/preview.md)

* Använd alternativet [Återgivning via e-post](../content-management/rendering.md) som använder Litmus för att simulera dina designer för de vanligaste e-postklienterna (Apple Mail, Gmail, Outlook) och se om text, färger och bilder gör ditt innehåll tillgängligt. <!--Litmus includes accessibility testing-->

* Skicka korrektur för att testa återgivningen av materialet innan det skickas till den verkliga målgruppen. [Lär dig hur](../content-management/proofs.md)

![](assets/accessible-simulate.png){width="90%"}

Om du vill kontrollera på ett mer konsekvent sätt om innehållet är tillgängligt kan du gå till särskilda externa verktyg som:

* Kontrastkontrollen [WebAim](https://webaim.org/resources/contrastchecker/){target="_blank"} och verktyget [WAVE för utvärdering av webbtillgänglighet](https://wave.webaim.org/){target="_blank"} för utvärdering av kontrast och efterlevnad.

* Hjälpmedelstekniker som skärmläsare (till exempel: [NVDA](https://www.nvaccess.org/download/){target="_blank"} eller [VoiceOver](https://support.apple.com/en-ie/guide/iphone/iph3e2e415f/ios){target="_blank"} på iPhone) för att få e-post från synskadade användare.

## Använd mörkt läge {#dark-mode}

Mörkt läge förbättrar den visuella tillgängligheten för användare med ljuskänslighet eller synnedsättning, vilket ger en bättre visningsupplevelse.

Med e-post-Designer kan du växla till **[!UICONTROL Dark mode]**-vyn och definiera specifika anpassade inställningar som ska visas av de e-postklienter som stöder e-post. [Lär dig hur](dark-mode.md)

![](assets/accessible-dark-mode.png){width="90%"}

Bland de bästa sätten att utforma innehåll i mörkt läge bör du använda genomskinliga PNG- eller SVG-filer, ställa in lämpliga metataggar och CSS och ge hjälpmedelsanpassad grundformatering om mörkt läge inte stöds. Slutligen måste du se till att dina e-postmeddelanden återges korrekt i mörkt läge genom att testa allt e-postinnehåll och alla gränssnittselement i både ljust och mörkt läge.

Detaljerade metodtips som är specifika för mörkt läge, inklusive riktlinjer för att säkerställa tillgänglighet, finns i [det här avsnittet](dark-mode.md#best-practices). <!--KEEP dark mode accessibility best practices IN ONE SINGLE LOCATION - for now listed on the Dark mode page.-->

## Använd specifika attribut för tillgänglighet {#attributes}

### Språkattribut {#language}

När du skapar designer inkluderar du attributen `lang` (språk) och `dir` (textorientering) i innehållets brödtext. Dessa attribut hjälper hjälpmedelstekniker som skärmläsare att tolka och presentera innehållet på rätt sätt.

* Attributet `lang` anger språket i e-postmeddelandet som ska användas till hjälpmedelstekniker, vilket säkerställer att orden uttalas korrekt.

  +++Exempel

  Exempel på engelska:

  ```
  <body lang="en">
  ```

  Exempel för franska:

  ```
  <body lang="fr">
  ```

  +++

* Attributet `dir` anger textriktningen. De flesta språk, inklusive engelska och franska, läses från vänster till höger (ltr), medan språk som arabiska och hebreiska läses från höger till vänster (rtl).

  +++Exempel

  Exempel för engelska (vänster till höger):

  ```
  <body lang="en" dir="ltr">
  ```

  Exempel för arabiska (höger till vänster):

  ```
  <body lang="ar" dir="rtl">
  ```

  +++

Skärmläsare förlitar sig på attributet `lang` för att använda rätt uttydningsregler, medan textriktning garanterar att innehållet flödar naturligt för språk som läses från vänster till höger eller från höger till vänster. Utan dessa attribut kan användare uppleva förvirrande läsordning eller feluttal. Därför ska du alltid radbryta din e-postbrödtext med rätt `lang`- och `dir`-attribut.

>[!TIP]
>
>Om e-postmeddelandet innehåller flera språk tilldelar du lämpliga språkattribut till specifika avsnitt (t.ex. `<table>` eller `<td>` block) för att säkerställa att varje del läses korrekt.

### Tabeller {#tables}

I HTML används ofta tabeller för layout. Som standard behandlar skärmläsare varje `<table>` som en datatabell, där rader, kolumner och struktur presenteras. Detta kan vara förvirrande om tabellen bara används för formatering.

Lägg till `role="presentation"` (eller `role="none"`) i layouttabeller för att säkerställa att hjälpmedelstekniker hoppar över sin struktur och bara fokuserar på det faktiska innehållet.

+++Exempel - Layouttabell (med `role="presentation"`)

```
<table role="presentation" border="0" cellpadding="0" cellspacing="0" width="100%"> 

  <tr> 

    <td align="center"> 

      <h1>Hello World</h1> 

      <p>Welcome to our newsletter</p> 

    </td> 

  </tr> 

</table>
```

Skärmläsarna läser:
&quot;Hello World. Välkommen till vårt nyhetsbrev.&quot; *(Ingen uppgift om rader, kolumner eller tabell)*

+++

+++Exempel - Datatabell (utan `role="presentation"`)

```
<table border="1" cellpadding="5" cellspacing="0"> 

  <tr> 

    <th scope="col">Name</th> 

    <th scope="col">Score</th> 

  </tr> 

  <tr> 

    <td>Alice</td> 

    <td>95</td> 

  </tr> 

  <tr> 

    <td>Bob</td> 

    <td>88</td> 

  </tr> 

</table> 
```

Skärmläsarna läser:
&quot;Tabell med 2 kolumner och 3 rader.&quot;

&quot;Namn, Alice. Score, 95.&quot;

&quot;Namn, Bob. Poäng, 88.&quot;

+++

>[!TIP]
>
>Använd `role="presentation"` exklusivt för layouttabeller. Behåll den semantiska `<table>`-strukturen för datatabeller så att skärmläsare kan meddela rubriker och relationer korrekt.

### Text för länkar {#links}

Skärmläsare läser upp länkar med sin text. Om en länk endast heter&quot;Klicka här&quot; eller&quot;Läs mer&quot; kommer användare av hjälpmedelstekniker inte att känna till målet. För att säkerställa tillgänglighet behöver de beskrivande text som tydligt anger målet eller åtgärden.

Använd e-post-Designer för att [lägga till en länk](message-tracking.md#insert-links) i ditt innehåll och redigera etiketten för att göra den identifierbar (synlig) och beskrivande (tydlig om syftet). Undvik otydliga etiketter som &quot;here&quot; eller &quot;more&quot;.

![](assets/accessible-link.png){width="70%"}

+++Exempel - Bra länk (beskrivande): 

```
<p>Learn more in the  

<a href="https://adobe.com/release-notes">August release notes</a>. 

</p>
```

Skärmläsarna läser:
&quot;Link, August release notes.&quot;

+++

+++Exempel - felaktig länk (inte beskrivande)

```
<p>Learn more about our new features.  

  <a href="https://adobe.com/release-notes">Click here</a>. 

</p>
```

Skärmläsarna läser:
&quot;Länk, klicka här.&quot; *(Ingen kontext ligger utanför läsordningen)*

+++

<!--
>[!TIP]
>
>Always ensure link text is discernible (visible) and descriptive (clear about purpose). Avoid vague labels like 'here' or 'more'.-->

## Stöd för tangentbordsnavigering och fokus {#keyboard}

<!--for landing pages-->

Med stöd för tangentbordsnavigering och -fokus kan personer som inte kan använda en mus få full tillgång till och interagera med innehållet. Det förbättrar också den övergripande användbarheten genom att ge alla användare ett tydligt och konsekvent sätt att gå igenom informationen.

* Fokusera via tangentbordet

   * Kontrollera att alla interaktiva element (till exempel knappar, kryssrutor och länkar) har `tabindex="0"` så att de inkluderas i den naturliga tabbordningen.

   * Tillåt navigering med tabb- och piltangenterna ( ↑ ↓ →), som ska markera det fokuserade elementet synligt.

* Anpassad fokusstil

   * Använd tydliga och urskiljbara format för att fokusera på åtgärdbara element:

     +++Exempel (CSS)

     ```
     [tabindex="0"] : focus { 
     
     outline: 2px solid #00AEEF;  /* Cyan border */ 
     
     background-color: #20CEFF;   /* Optional background */ 
     
     }
     ```

     +++

   * Kontrollera att fokusindikatorerna uppfyller WCAG 2.2-standarder för fokusutseende, inklusive:

      * Minimiområde: 2 CSS pixeltjock kontur.

      * Kontrastförhållande: ≥ 3:1 mellan fokuserat och ofokuserat läge.

* Stöd för tangentbordsaktivering

   * Se till att kryssrutor och knappar svarar på tangenterna Enter och Space.

   * Validera interaktion med enbart tangentbordet:

      * Använd Enter eller Space för att växla mellan kryssrutorna.

      * Enter eller Space ska utlösa knappar.
