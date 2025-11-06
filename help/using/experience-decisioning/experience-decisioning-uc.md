---
title: Användningsfall vid beslut
description: Lär dig hur du skapar beslut och använder dem i innehållsexperiment med den kodbaserade upplevelsekanalen
feature: Decisioning
topic: Integrations
role: User
level: Intermediate, Experienced
exl-id: 09770df2-c514-4217-a71b-e31c248df543
source-git-commit: 5b377982f43902a4549f24c022fa8f4947d896a8
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Använd Beslutsfattandet i en kodbaserad upplevelse med hjälp av innehållsexperimentet {#experience-decisioning-uc}

I det här användningsexemplet beskrivs alla steg som behövs för att använda Decisionering med den kodbaserade kanalen [!DNL Journey Optimizer].

I det här exemplet är du osäker på om en viss rankningsformel fungerar bättre än de förtilldelade prioriteterna. Om du vill mäta vilken som fungerar bäst för målgruppen skapar du en kampanj med [Innehållsexperiment](../content-management/content-experiment.md) där du definierar två leveranssätt:

* I den första behandlingen används **priority** som rangordningsmetod.
* Den andra behandlingen använder **en formel** som rangordningsmetod.

## Skapa urvalsstrategier

Först måste du bygga två urvalsstrategier: en med prioritet som rangordningsmetod och en med en formel som rangordningsmetod.

>[!NOTE]
>
>Du kan också skapa enskilda beslutsobjekt utan att behöva gå igenom en urvalsstrategi. Prioriteten som anges för varje objekt gäller.

### Skapa en strategi med prioritet

Följ stegen nedan för att bygga upp den första urvalsstrategin med prioritet som rangordningsmetod.

1. Skapa ett beslutsobjekt. [Lär dig hur](items.md)

1. Ange **[!UICONTROL Priority]** för beslutsobjektet jämfört med andra. Om en profil kvalificerar för flera objekt ger en högre prioritet objektets prioritet framför andra.

   ![](assets/exd-uc-item-priority.png){width="90%"}

   >[!NOTE]
   >
   >Prioriteten är en heltalsdatatyp. Alla attribut som är heltalsdatatyper ska innehålla heltalsvärden (inga decimaler).

1. Ange berättigandestatus för beslutsobjektet:

   * Definiera målgrupper eller regler för att begränsa objektet till enbart specifika profiler. [Läs mer](items.md#eligibility)

   * Ange regler för begränsning för hur många gånger ett erbjudande får presenteras. [Läs mer](items.md#capping)

1. Om det behövs upprepar du stegen ovan för att skapa ytterligare beslutsobjekt.

1. Skapa en **samling** där dina beslutsobjekt ska inkluderas. [Läs mer](collections.md)

1. Skapa en [urvalsstrategi](selection-strategies.md#create-selection-strategy) och välj den [samling](collections.md) som innehåller de erbjudanden som ska beaktas.

1. [Välj den rangordningsmetod](#select-ranking-method) som du vill använda för att välja det bästa erbjudandet för varje profil. I det här fallet väljer du **[!UICONTROL Offer priority]**: om flera erbjudanden är berättigade för den här strategin använder beslutsmotorn det värde som angetts som **[!UICONTROL Priority]** i erbjudandena. [Läs mer](selection-strategies.md#offer-priority)

   ![](assets/exd-uc-strategy-priority.png){width="90%"}

### Skapa en annan strategi med hjälp av en formel

Om du vill bygga den andra urvalsstrategin med en formel som rangordningsmetod följer du stegen nedan.

1. Skapa ett beslutsobjekt. [Lär dig hur](items.md)

   <!--Do you need to set the same **[!UICONTROL Priority]** as for the first decision item, or it won't be considered at all?-->

1. Ange berättigandestatus för beslutsobjektet:

   * Definiera målgrupper eller regler för att begränsa objektet till enbart specifika profiler. [Läs mer](items.md#eligibility)

   * Ange regler för begränsning för hur många gånger ett erbjudande får presenteras. [Läs mer](items.md#capping)

1. Om det behövs upprepar du stegen ovan för att skapa ytterligare beslutsobjekt.

1. Skapa en **samling** där dina beslutsobjekt ska inkluderas. [Läs mer](collections.md)

1. Skapa en [urvalsstrategi](selection-strategies.md#create-selection-strategy) och välj den [samling](collections.md) som innehåller de erbjudanden som ska beaktas.

1. [Välj den rangordningsmetod](#select-ranking-method) som du vill använda för att välja det bästa erbjudandet för varje profil. I det här fallet väljer du **[!UICONTROL Formula]** om du vill använda ett specifikt beräknat poängvärde för att avgöra vilket kvalificerat erbjudande som ska levereras. [Läs mer](selection-strategies.md#ranking-formula)

   ![](assets/exd-uc-strategy-formula.png){width="90%"}

## Bygg en kodbaserad upplevelsekampanj

<!--To present the best dynamic offer and experience to your visitors on your website or mobile app, add a decision policy to a code-based campaign.

Define two delivery treatments each containing a different decision policy.-->

När du har konfigurerat de två urvalsstrategierna skapar du en kodbaserad upplevelsekampanj där du definierar olika behandlingar för varje strategi, för att jämföra vilken som fungerar bäst.

1. Skapa en kampanj och välj åtgärden **[!UICONTROL Code-base experience]**. [Läs mer](../code-based/create-code-based.md)

1. Klicka på **[!UICONTROL Create experiment]** på kampanjsammanfattningssidan för att konfigurera ditt innehållsexperiment. [Lär dig hur](../content-management/content-experiment.md)

   ![](assets/exd-uc-create-experiment.png){width="90%"}

1. Välj en kodbaserad konfiguration på kampanjsammanfattningssidan och klicka på **[!UICONTROL Edit content]**.

   ![](assets/exd-uc-edit-cbe-content.png){width="90%"}

1. Klicka på **i innehållsutgåvans fönster för att börja personalisera** Behandling A **[!UICONTROL Edit code]**.

   ![](assets/exd-uc-experiment-treatment-a.png){width="90%"}

1. I [kodredigeraren](../code-based/create-code-based.md#edit-code) väljer du **[!UICONTROL Decision policy]**, klickar på **[!UICONTROL Add decision policy]** och fyller i beslutsinformationen. [Läs mer](create-decision.md#add)

   ![](assets/decision-code-based-create.png){width="90%"}

1. Klicka på knappen **[!UICONTROL Strategy sequence]** i avsnittet **[!UICONTROL Add]** och välj **[!UICONTROL Selection strategy]**. [Läs mer](create-decision.md#select)

   ![](assets/decision-code-based-strategy-sequence.png){width="80%"}

   >[!NOTE]
   >
   >Du kan också välja **[!UICONTROL Decision item]** om du vill lägga till enskilda objekt utan att behöva köra igenom en urvalsstrategi. Prioriteten som anges för varje objekt gäller.

1. Välj den första strategin som du skapade - den med prioritet som rangordningsmetod.

   ![](assets/exd-uc-experiment-strategy-priority.png){width="90%"}

1. Spara ändringarna och klicka på **[!UICONTROL Create]**. Det nya beslutet läggs till under **[!UICONTROL Decision policy]**.

1. Klicka på knappen **[!UICONTROL Insert policy]**. Koden som motsvarar beslutspolicyn läggs till. Lägg sedan till alla attribut du vill använda i koden, inklusive profilattribut. [Läs mer](create-decision.md#use-decision-policy)

   ![](assets/exd-uc-experiment-insert-policy.png){width="90%"}

1. Spara ändringarna.

1. Gå tillbaka till innehållsutgåvans fönster, välj plusknappen (+) för att lägga till **Behandling B**, markera den och klicka på **[!UICONTROL Edit code]**.

   ![](assets/exd-uc-experiment-treatment-b.png){width="90%"}

1. Upprepa steg 5 och 6 ovan om du vill skapa en annan beslutsprincip och välja den andra urvalsstrategin som du skapade - den med formeln som rangordningsmetod. <!--Do you need to create exactly the same content to compare only the ranking method?-->

   ![](assets/exd-uc-experiment-strategy-formula.png){width="90%"}

1. Redigera din beslutspolicy som du vill (se steg 8 och 9 ovan).

1. Spara ändringarna och [publicera din kodbaserade upplevelsekampanj](../code-based/publish-code-based.md).

När du har kört experimentet kan du följa upp hur kampanjbehandlingarna fungerar med [rapporten om experimentella kampanjer](../reports/campaign-global-report-cja-experimentation.md).<!-- and [report on decisioning](cja-reporting.md).--> Du kan sedan tolka resultatet av ditt experiment. [Lär dig hur](../content-management/get-started-experiment.md#interpret-results)

Om resultatet är klart:

* Ni kan göra behandlingen med bästa resultat rankad för alla era kunder.
* Du kan också skapa en ny kampanj med hjälp av urvalsstrategin där rankningsmetoden som ger bästa resultat replikeras.