---
solution: Journey Optimizer
product: journey optimizer
title: Meddelandeoptimering
description: Använd optimering av meddelanden för att skapa personaliserade och optimerade marknadsföringskampanjer.
role: User
level: Intermediate
keywords: kampanjoptimering, experiment, målinriktning, A/B-testning
source-git-commit: edbe25e0cb341c08e440eb0663fb9b253273f48a
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 0%

---

# Optimering av kampanjer {#message-optimization}

Optimeringen ger er de verktyg ni behöver för att leverera personaliserat och optimerat innehåll till er målgrupp, <!--based on marketer-defined advanced decision configurations. This ensures that the right message reaches the right audience at the right time in order to maximize the effectiveness of your campaigns. (Removed for now as Decisioning is not yet supported)-->vilket ger maximal interaktion och framgång för att skapa högeffektiva <!--customized and -->kampanjer.

Med optimering kan man

* Utnyttja reglerna för [målinriktning](#targeting)
* Kör [innehållsexperiment](#experimentation)
* Använd [avancerade kombinationer](#combination) av både experiment och målinriktning i en enda kampanj

När kampanjen är aktiv utvärderas profiler mot de definierade kriterierna, och baserat på matchningskriterier levereras de med rätt erfarenhet eller innehåll från kampanjen.

Skillnaden mellan experiment och målinriktning kan beskrivas på följande sätt:

* Experimentationen består av en slumpmässig delning av innehållet baserat på &#x200B;.
* Riktad marknadsföring använder deterministiska tekniker för att leverera innehåll baserat på användarprofil, målgruppsmedlemskap eller kontextbaserade regler.

![](assets/msg-optimization-experiment-vs-targeting.png){width="110%" zoomable="yes"}

## Utnyttja målgruppsanpassning {#targeting}

Målinriktning levererar personaliserat innehåll till specifika målgruppssegment baserat på användarprofilattribut eller sammanhangsbaserade attribut.

Till skillnad från experiment, som är en slumpmässig tilldelning av ett budskap, är målinriktning avgörande när det gäller att leverera innehållet till rätt målgrupp.

Med målinriktning kan specifika regler definieras baserat på:

* **Användarprofilattribut**, t.ex. plats (t.ex. geoanpassning), ålder eller önskemål. Användare i USA kan till exempel se en kampanj för&quot;Golden Gate&quot;, medan användare i Frankrike ser en kampanj för&quot;Eiffeltornet&quot;.

* **Sammanhangsberoende data**, t.ex. enhetstyp (t.ex. målgruppsanpassning), tid på dygnet eller sessionsinformation. Datoranvändare får till exempel datoroptimerat innehåll, medan mobilanvändare får mobiloptimerat innehåll.

* **Publiker** som kan användas för att inkludera eller exkludera profiler som har ett visst målgruppsmedlemskap.

Följ stegen nedan för att konfigurera målinriktning i en kampanj.

1. Skapa en kampanj. [Läs mer](../campaigns/create-campaign.md) <!--Add link to API triggered?-->

1. Välj minst en åtgärd på fliken **[!UICONTROL Actions]**.

1. Välj **[!UICONTROL Message Optimization]** i avsnittet **[!UICONTROL Targeting]**.

   ![](assets/msg-optimization-select-targeting.png){width=85%}

1. Använd regelbyggaren för att definiera dina villkor. Definiera t.ex. en regel för amerikanska medborgare, en regel för franska medborgare och en regel för indiska medborgare.

   ![](assets/msg-optimization-create-targeting.png){width=85%}

1. Välj **[!UICONTROL Enable fallback content]** efter behov. Reservinnehåll gör att målgruppen kan få ett standardinnehåll när inga målinriktningsregler är kvalificerade. Om du inte väljer det här alternativet kommer ingen målgrupp som inte är berättigad till en målgruppsregel som definieras ovan inte att få något innehåll.

1. Spara målinriktningsregelinställningarna.

1. Gå tillbaka till fliken **[!UICONTROL Actions]** och välj **[!UICONTROL Edit content]**.

1. Utforma lämpligt innehåll för varje grupp som definieras av målregelinställningarna.

   ![](assets/msg-optimization-targeting-design.png){width=85%}

   I det här exemplet utformar du ett specifikt innehåll för amerikanska medborgare, ett annat innehåll för franska medborgare och ett annat innehåll för indiska medborgare.

1. [Aktivera](review-activate-campaign.md) din kampanj.

När kampanjen är live skickas innehåll som är anpassat för varje mål så att amerikanska medborgare får ett visst meddelande, Frankrike har ett annat budskap och så vidare.

<!--Default content:

* If no targeting rules match, default content can be delivered.

* If default content is not enabled, passthrough behavior ensures lower-priority campaigns are evaluated.-->

## Använd experimenterande {#experimentation}

Experimentation gör att du kan testa flera versioner av innehåll för att avgöra vilken som fungerar bäst baserat på fördefinierade framgångsmått.

Följ stegen nedan för att konfigurera experimentering i en kampanj.

Säg att du vill testa följande kampanjmeddelanden i en kampanj:

* **Behandling A**:&quot;20 % rabatt på ditt nästa köp&quot;
* **Behandling B**:&quot;Fri frakt för beställningar över 50 USD&quot;
* **Behandling C**: &quot;Hämta ditt presentkort på 10 USD&quot;

Följ stegen nedan om du vill konfigurera experimenterande och avgöra vilket meddelande som ger flest inköp.

1. Skapa en kampanj. [Läs mer](../campaigns/create-campaign.md) <!--Add link to API triggered?-->

1. På fliken **[!UICONTROL Actions]** väljer du minst två inkommande åtgärder, till exempel [kodbaserad upplevelse](../code-based/get-started-code-based.md) och [I appen](../in-app/get-started-in-app.md).

1. Välj **[!UICONTROL Message Optimization]** i avsnittet **[!UICONTROL Experimentation]**.

   ![](assets/msg-optimization-select-experiment.png){width=85%}

1. Designa och konfigurera ditt innehållsexperiment som du vill. [Lär dig hur](../content-management/content-experiment.md)

   ![](assets/msg-optimization-create-experiment.png){width=85%}

   När experimentet har definierats gäller det alla åtgärder som har infogats i kampanjen, vilket innebär att samma kunder ser samma erbjudanden på alla ytor.

   >[!NOTE]
   >
   >Du kan välja andra åtgärder: experimentet gäller alla åtgärder som läggs till i kampanjen.

1. [Aktivera](review-activate-campaign.md) din kampanj.

När kampanjen är aktiv tilldelas användarna slumpvis olika innehållsvariationer. [!DNL Journey Optimizer] spårar vilka varianter som driver fler inköp och ger åtgärdbara insikter.

Följ kampanjens framgångar med rapporten [Experimentationskampanj](../reports/campaign-global-report-cja-experimentation.md).

## Kombinera målinriktning och experimenterande {#combination}

Med Journey Optimizer kan ni också kombinera målinriktning och experiment i en enda kampanj för att skapa mer sofistikerade strategier.

Ni kan faktiskt använda målinriktning för att skapa flera olika varianter, och för varje variant kan ni använda experimenterande för att optimera varje innehåll ytterligare. Detta garanterar att experimenten är specifika för varje målinriktningsregel och inte spänner över olika varianter i kampanjen.

Du kan till exempel testa&quot;50 % rabatt&quot; jämfört med ett presentkort på&quot;$50&quot; för kunder i USA och göra ett annat test för kunder i Europa, till exempel&quot;fri frakt på beställningar över €&quot; jämfört med&quot;20 % rabatt på nästa köp&quot;.

Följ stegen nedan för att kombinera både målinriktning och experiment i en kampanj.

1. Skapa en kampanj där ni definierar flera målinriktningsregler. [Lär dig hur](#targeting)

   ![](assets/msg-optimization-create-targeting.png){width=85%}

1. Skapa ett experiment för den första målinriktningsregeln.

1. Designa och konfigurera ditt innehållsexperiment som du vill. [Lär dig hur](../content-management/content-experiment.md)

   ![](assets/msg-optimization-targeting-with-experiment.png){width=85%}

   När experimentet har definierats gäller det bara den första målgruppsregeln.

1. Gå tillbaka till fliken **[!UICONTROL Actions]** och välj **[!UICONTROL Edit content]**.

1. För den grupp som definieras av din första målinriktningsregel kan du definiera ett specifikt innehåll för varje variant av ditt experiment.

   Om ni har lagt till mer än en inkommande åtgärd till er kampanj gäller samma kombination av målinriktning och experiment för varje åtgärd. Du måste dock definiera ett specifikt innehåll för varje variant av varje åtgärd.

   ![](assets/msg-optimization-targeting-experiment-design.png){width=85%}

1. Fortsätt på samma sätt med de andra målinriktningsreglerna och utforma motsvarande innehåll för varje variant.

1. Spara ändringarna och [aktivera](review-activate-campaign.md) kampanjen.

När kampanjen är aktiv tilldelas användare från varje målgrupp slumpvis de olika innehållsvariationerna som definierats för den grupp de tillhör.

<!--
## Reporting on Message optimization

E.g. explaining how a marketer can look at the report to determine which treatment (e.g. which message content) is performing the best for the targeting audience
-->

