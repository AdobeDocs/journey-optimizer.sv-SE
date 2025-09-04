---
solution: Journey Optimizer
product: journey optimizer
title: Villkorsaktivitet
description: Läs mer om villkorsaktivitet
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: aktivitet, villkor, arbetsyta, resa, optimering
badge: label="Begränsad tillgänglighet" type="Informative"
hidefromtoc: true
hide: true
exl-id: f6618de4-7861-488e-90c0-f299ef5897ca
source-git-commit: 27ae100873fee1a790c7e1e757248f9c3af8e24a
workflow-type: tm+mt
source-wordcount: '1142'
ht-degree: 0%

---

# Optimera aktivitet {#journey-path-optimization}

>[!CONTEXTUALHELP]
>id="ajo_journey_optimize"
>title="Optimera aktivitet"
>abstract="Med aktiviteten **Optimera** kan du definiera hur enskilda personer ska gå igenom din resa genom att skapa flera sökvägar baserat på specifika kriterier, inklusive experiment, målinriktning och specifika villkor."

>[!AVAILABILITY]
>
>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

Med aktiviteten **Optimera** kan du definiera hur enskilda personer ska gå igenom din resa genom att skapa flera **sökvägar** baserat på specifika kriterier, inklusive experiment, målgruppsanpassning och specifika villkor, vilket ger ett maximalt engagemang och framgång för att skapa välanpassade och effektiva resor.

En **resesökväg** kan bestå av något av följande:

* sekvensering av kommunikationen,
* tiden mellan dem,
* antal meddelanden,
* eller en kombination av dessa tre variabler.

En sökväg kan till exempel innehålla ett e-postmeddelande, en annan kan innehålla två SMS-meddelanden och en tredje kan innehålla ett e-postmeddelande, en [Wait](wait-activity.md)-nod på två timmar och sedan ett SMS-meddelande.

<!--With this feature, [!DNL Journey Optimizer] empowers you with the tools to deliver personalized and optimized paths to your audience, ensuring maximum engagement and success to create highly customized and effective journeys.-->

Genom aktiviteten **Optimera** kan du:

* Kör [sökvägsexperiment](#experimentation)
* Utnyttja [målinriktningsreglerna](#targeting) i varje resesökväg
* Använd [villkor](#conditions) på dina sökvägar

![](assets/journey-optimize.png)

När resan är live utvärderas profiler mot de definierade kriterierna, och baserat på matchningskriterier skickas de vidare längs lämplig väg från resan.

## Använd experimenterande {#experimentation}

Experimentation gör att du kan testa olika banor baserat på en slumpmässig delning för att avgöra vilken som fungerar bäst baserat på fördefinierade framgångsmått.

Följ stegen nedan för att konfigurera sökvägsexperiment under en resa.

Låt oss säga att du vill jämföra tre banor:

* en sökväg med ett e-postmeddelande,
* en andra sökväg med en **[!UICONTROL Wait]**-nod på två dagar och ett e-postmeddelande,
* en tredje sökväg med ett e-postmeddelande och sedan ett SMS-meddelande.

1. Dra och släpp **[!UICONTROL Orchestration]**-aktiviteten från avsnittet **[!UICONTROL Optimize]** till arbetsytan för resan.

1. Lägg till en valfri etikett, som kan vara användbar för att identifiera aktiviteten i loggar för rapportering och testläge.

1. Välj **[!UICONTROL Experiment]** i listrutan **[!UICONTROL Method]**.

   ![](assets/journey-optimize-experiment.png){width=75%}

1. Klicka på **[!UICONTROL Create experiment]**.

1. Välj den **[!UICONTROL Success metric]** som du vill ange för ditt experiment.

   <!--Need to have the list of all default metrics + a description for each.
    Explain why the metric selection is important.
    Are there custom metrics? If so explain.
    If possible, add best practices and examples for each metrics (could even be a dedicated section).
    Consider adding an example in this step: For this example, select this metric to test xxx.
    -->

   ![](assets/journey-optimize-experiment-metrics.png){width=70%}

<!--1. Change the **[!UICONTROL Title]** of your treatment to better differentiate them.-->

1. Du kan lägga till en **[!UICONTROL Holdout]**-grupp i leveransen. Den här gruppen kommer inte att få något innehåll från det här experimentet.

   >[!NOTE]
   >
   >Om du aktiverar alternativfältet tar det automatiskt 10 % av din befolkning. Du kan justera procentandelen om det behövs.

   <!--
    [!IMPORTANT]
    >
    >DOES THIS APPLY TO PATH EXPERIMENT? When a holdout group is used in an action for path experimentation, the holdout assignment only applies to that specific action. After the action is completed, profiles in the holdout group will continue down the journey path and can receive messages from other actions. Therefore, ensure that any subsequent messages do not rely on the receipt of a message by a profile that might be in a holdout group. If they do, you may need to remove the holdout assignment.-->

1. Du kan tilldela en exakt procentandel till varje **[!UICONTROL Treatment]**, eller bara växla på **[!UICONTROL Distribute evenly]**-växlingsfältet.

   ![](assets/journey-optimize-experiment-treatments.png){width=80%}

1. Klicka på **[!UICONTROL Create]**.

1. Definiera elementen som du vill ha för varje gren som är resultatet av Experiment, till exempel:

   * Dra och släpp en [e-post](../email/create-email.md)-aktivitet till den första grenen (**Behandling A**).

   * Dra och släpp en [Wait](wait-activity.md)-aktivitet på två dagar till den första grenen, följt av en [Email](../email/create-email.md)-aktivitet (**Treatment B**).

   * Dra och släpp en [e-post](../email/create-email.md)-aktivitet till den tredje grenen, följt av en [SMS](../sms/create-sms.md)-aktivitet (**Behandling C**).

   ![](assets/journey-optimize-experiment-ex.png){width=100%}

1. Du kan också använda **[!UICONTROL Add an alternative path in case of a timeout or an error]** för att definiera en reservåtgärd. [Läs mer](using-the-journey-designer.md#paths)

1. Välj en kanalåtgärd och använd knappen **[!UICONTROL Edit content]** för att komma åt designverktygen.

   ![](assets/journey-optimize-experiment-edit-content.png){width=70%}

1. Därifrån kan du i den vänstra rutan navigera mellan olika innehåll för varje åtgärd i ditt experiment. Designa allt innehåll efter behov.

   ![](assets/journey-optimize-experiment-content.png){width=100%}

1. [Publicera](publishing-the-journey.md) din resa.

När resan är live tilldelas användarna slumpvis olika vägar. [!DNL Journey Optimizer] spårar vilken sökväg som fungerar bäst och ger åtgärdbara insikter.

Följ upp din resa med rapporten Optimera/Experimentera [för resan](../reports/journey-global-report-cja.md). <!--Need a doc page on reporting specific to path experimentation in journey - [Path experimentation journey report](../xxx) such as what we have for [Experimentation campaign report](../reports/campaign-global-report-cja-experimentation.md)-->

### Exempel på användningsområden {#uc-experiment}

I följande exempel visas hur du använder aktiviteten **[!UICONTROL Optimize]** med metoden **[!UICONTROL Experiment]** för att avgöra vilken sökväg som fungerar bäst generellt.

+++Kanaleffektivitet

Testa om det första meddelandet skickas via e-post eller SMS leder till högre konverteringar.

* Använd konverteringsgraden som optimeringsmått (till exempel inköp, registreringar).

<!--![](assets/journey-optimize-experiment-uc.png)-->

+++

+++Meddelandefrekvens

Kör ett experiment för att kontrollera om ett e-postmeddelande eller tre e-postmeddelanden under en vecka leder till fler inköp.

* Använd köp eller avbeställningsfrekvensen som optimeringsmått.

+++

+++Väntetid mellan kommunikation

Jämför en 24-timmars väntan jämfört med en 72-timmars väntan före en uppföljning för att avgöra vilken tidpunkt som maximerar engagemanget.

* Använd klickfrekvensen eller intäkterna som optimeringsmått.

+++

## Utnyttja målgruppsanpassning {#targeting}

Med målgruppsanpassning kan du fastställa specifika regler eller kvalifikationer som måste uppfyllas för att en kund ska vara berättigad att ange en av kundresan, baserat på specifika målgruppssegment <!-- depending on profile attributes or contextual attributes-->.

Till skillnad från experiment, som är en slumpmässig tilldelning av en viss bana, är målinriktning avgörande för att säkerställa att rätt målgrupp eller profil kommer in på den angivna banan.

<!--With targeting, specific rules can be defined based on:

* **User profile attributes** such as location (eg. geo-targeting), age, or preferences. For example, users in the US receive a "Golden Gate" promotion, while users in France receive an "Eiffel Tower" promotion.

* **Contextual data** such as device type (eg. device-targeting), time of day, or session details. For example, desktop users receive desktop-optimized content, while mobile users receive mobile-optimized content.

* **Audiences** which can be used to include or exclude profiles that have a particular audience membership.-->

Följ stegen nedan för att konfigurera målinriktning på en resa.

1. Dra och släpp **[!UICONTROL Orchestration]**-aktiviteten från avsnittet **[!UICONTROL Optimize]** till arbetsytan för resan.

1. Lägg till en valfri etikett, som kan vara användbar för att identifiera aktiviteten i loggar för rapportering och testläge.

1. Välj **[!UICONTROL Targeting rule]** i listrutan **[!UICONTROL Method]**.

   ![](assets/journey-optimize-targeting.png){width=75%}

1. Klicka på **[!UICONTROL Create targeting rule]**.

1. Använd regelbyggaren för att definiera dina villkor. Du kan till exempel definiera en regel för Guldmedlemmar i bonusprogrammet (`loyalty.status.equals("Gold", false)`) och en regel för de andra medlemmarna (`loyalty.status.notEqualTo("Gold", false)`).

   ![](assets/journey-targeting-rule.png)

1. Välj **[!UICONTROL Enable fallback content]** efter behov. Reservinnehåll gör att målgruppen kan få ett standardinnehåll när inga målinriktningsregler är kvalificerade. Om du inte markerar det här alternativet kommer målgrupper som inte är kvalificerade för en målregel som definieras ovan inte att ange en reservsökväg.

1. Spara målinriktningsregelinställningarna.

1. Tillbaka på resan, släpp specifika åtgärder för att anpassa varje bana. Skapa till exempel ett e-postmeddelande med personliga erbjudanden för Gold Loyalty-medlemmar och en SMS-påminnelse för alla andra medlemmar.

   ![](assets/journey-targeting-paths.png)

1. Du kan också använda **[!UICONTROL Add an alternative path in case of a timeout or an error]** för att definiera en reservåtgärd. [Läs mer](using-the-journey-designer.md#paths)

1. Utforma lämpligt innehåll för varje åtgärd som motsvarar en grupp som definieras av målarregelinställningarna. Du kan smidigt navigera mellan olika innehåll för varje åtgärd.

   ![](assets/journey-targeting-design.png)

   I det här exemplet skapar du ett e-postmeddelande med specialerbjudanden för guldmedlemmar och en SMS-påminnelse för de andra medlemmarna.

1. [Publicera](publishing-the-journey.md) din resa.

När resan är live behandlas den sökväg som anges för varje segment så att Guld-medlemmar anger sökvägen med e-posterbjudandena, medan de andra medlemmarna anger sökvägen med SMS-påminnelsen.

### Riktade användningsfall {#uc-targeting}

I följande exempel visas hur du använder aktiviteten **[!UICONTROL Optimize]** med metoden **[!UICONTROL Targeting]** för att anpassa sökvägar för olika undergrupper.

+++Segmentspecifika kanaler

Gold-status som lojalitetsmedlemmar kan få personaliserade erbjudanden via e-post, medan alla andra medlemmar dirigeras till SMS-påminnelser.

* Använd intäkten per profil eller konverteringsgrad som optimeringsmått.

<!--![](assets/journey-optimize-targeting-uc.png)-->

+++

+++Beteendebaserad målinriktning

Kunder som har öppnat ett e-postmeddelande men inte klickat kan få ett push-meddelande, medan de som inte öppnat alls får ett SMS.

* Använd genomklickningsfrekvensen eller nedströmskonverteringar som optimeringsmått.

+++

+++Målinriktning mot inköpshistorik

Kunder som nyligen har köpt kan gå in på en kort&quot;Tack + Korsförsäljning&quot;-väg, medan kunder som inte har någon köphistorik går in på en längre vårdsresa.

* Använd den upprepade inköpstakten eller engagemangsfrekvensen som optimeringsmått.

+++

## Lägg till ett villkor {#conditions}

Du kan lägga till ett villkor för att definiera hur enskilda personer ska gå igenom din resa genom att skapa flera banor som baseras på specifika kriterier. Du kan också konfigurera en alternativ sökväg för att hantera timeout eller fel, vilket ger en smidig upplevelse.

![](assets/journey-condition.png)

Lär dig definiera ett villkor i [det här avsnittet](conditions.md).

Följande typer av villkor är tillgängliga:

* [Source-villkor för data](condition-activity.md#data_source_condition)
* [Tidsvillkor](condition-activity.md#time_condition)
* [Procentandel av delning](condition-activity.md#percentage_split)
* [Datumvillkor](condition-activity.md#date_condition)
* [Profilände](condition-activity.md#profile_cap)
