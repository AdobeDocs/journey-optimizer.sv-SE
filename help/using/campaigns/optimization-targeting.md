---
solution: Journey Optimizer
product: journey optimizer
title: Använd målgruppsanpassning i meddelandeoptimering
description: Lär dig hur ni kan utnyttja regler för målinriktning för att leverera personaliserat innehåll till specifika målgruppssegment.
role: User
level: Intermediate
keywords: målgruppsanpassning, optimering, målgrupp, personalisering, regler
source-git-commit: fec72c63d41a41adce5107082c50a68a7b8c0af2
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Använd målinriktning {#targeting}

>[!CONTEXTUALHELP]
>id="ajo_content_targeting_fallback"
>title="Vad är reservinnehåll?"
>abstract="Reservinnehåll gör att målgruppen kan få ett standardinnehåll när ingen målinriktningsregel är kvalificerad.</br>Om du inte väljer det här alternativet kommer ingen målgrupp som inte är kvalificerad för en målregel som definieras ovan inte att få något innehåll."

Målinriktning levererar personaliserat innehåll till specifika målgruppssegment baserat på användarprofilattribut eller sammanhangsbaserade attribut.

Till skillnad från experiment, som är en slumpmässig tilldelning av ett budskap, är målinriktning avgörande när det gäller att leverera innehållet till rätt målgrupp.

Med målinriktning kan specifika regler definieras baserat på:

* **Användarprofilattribut**, t.ex. plats (t.ex. geoanpassning), ålder eller önskemål. Användare i USA kan till exempel se en kampanj för&quot;Golden Gate&quot;, medan användare i Frankrike ser en kampanj för&quot;Eiffeltornet&quot;.

* **Sammanhangsberoende data**, t.ex. enhetstyp (t.ex. målgruppsanpassning), tid på dygnet eller sessionsinformation. Datoranvändare får till exempel datoroptimerat innehåll, medan mobilanvändare får mobiloptimerat innehåll.

* **Publiker** som kan användas för att inkludera eller exkludera profiler som har ett visst målgruppsmedlemskap.

Följ stegen nedan för att konfigurera målinriktning.

1. Skapa en [resa](../building-journeys/journey-gs.md#jo-build) eller en [kampanj](../campaigns/create-campaign.md).

   >[!NOTE]
   >
   >Om du befinner dig på en resa lägger du till en **[!UICONTROL Action]**-aktivitet, väljer en kanalaktivitet och sedan **[!UICONTROL Configure action]**. [Läs mer](../building-journeys/journey-action.md#add-action)

1. Välj minst en åtgärd på fliken **[!UICONTROL Actions]**.

1. Välj **[!UICONTROL Optimization]** i avsnittet **[!UICONTROL Create targeting rule]**.

   ![](assets/msg-optimization-select-targeting.png){width=85%}

1. Klicka på **[!UICONTROL Create rule]** > **[!UICONTROL Create new]** och använd regelbyggaren för att definiera dina villkor oavsett var du är.

   ![](assets/msg-optimization-create-rule.png){width=100%}

   Definiera t.ex. en regel för amerikanska medborgare, en regel för franska medborgare och en regel för indiska medborgare.

   ![](assets/msg-optimization-create-targeting.png){width=85%}

1. Du kan också klicka på **[!UICONTROL Create rule]** > **[!UICONTROL Select rule]** för att välja en befintlig målinriktningsregel som har skapats på menyn **[!UICONTROL Rules]**. [Läs mer](../experience-decisioning/rules.md)

   ![](assets/msg-optimization-select-rule.png){width=70%}

   I det här fallet kopieras formeln som utgör regeln helt enkelt till resan eller kampanjen. Eventuella senare ändringar av den regeln från menyn **[!UICONTROL Rules]** påverkar inte resan eller kampanjens kopia.

   >[!AVAILABILITY]
   >
   >[Det går för närvarande att skapa målgruppsregler](../experience-decisioning/rules.md#create) från den dedikerade [!DNL Journey Optimizer]-menyn för organisationer som har köpt erbjudandet om tillägg till beslut, och de är tillgängliga på begäran för andra organisationer (begränsad tillgänglighet).
   >
   >Denna kapacitet kommer att successivt lanseras för alla kunder. Under tiden kontaktar du Adobe för att få åtkomst.

1. När du har lagt till en regel kan du fortfarande ändra den. Välj **[!UICONTROL Edit inline]** om du vill uppdatera den när du är i farten med regelverktyget eller **[!UICONTROL Select rule]** om du vill hämta en annan befintlig regel.

   ![](assets/msg-optimization-modify-rule.png){width=100%}

   >[!NOTE]
   >
   >När du redigerar en infogad regel påverkas inte den befintliga regel som den härstammar från.

1. Välj alternativet **[!UICONTROL Enable fallback content]** efter behov. Reservinnehåll gör att målgruppen kan få ett standardinnehåll när inga målinriktningsregler är kvalificerade.

   >[!NOTE]
   >
   >Om du inte väljer det här alternativet kommer ingen målgrupp som inte är berättigad till en målgruppsregel som definieras ovan inte att få något innehåll.

1. Spara målinriktningsregelinställningarna.

1. Gå tillbaka till fliken **[!UICONTROL Actions]** och välj **[!UICONTROL Edit content]**.

1. Utforma lämpligt innehåll för varje grupp som definieras av målregelinställningarna.

   ![](assets/msg-optimization-targeting-design.png){width=85%}

   I det här exemplet utformar du ett specifikt innehåll för amerikanska medborgare, ett annat innehåll för franska medborgare och ett annat innehåll för indiska medborgare.

1. [Aktivera](review-activate-campaign.md) din resa eller kampanj.

När resan/kampanjen är live skickas innehåll som är skräddarsytt för varje mål så att amerikanska medborgare får ett specifikt meddelande, Frankrike har ett annat budskap och så vidare.

<!--Default content:

* If no targeting rules match, default content can be delivered.

* If default content is not enabled, passthrough behavior ensures lower-priority campaigns are evaluated.-->

