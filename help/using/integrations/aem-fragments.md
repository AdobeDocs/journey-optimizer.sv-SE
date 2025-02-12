---
solution: Journey Optimizer
product: journey optimizer
title: AEM Content Fragments
description: Lär dig hur du kommer åt och hanterar AEM Content Fragments
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 57d7c25f-7e39-46ad-85c1-65e2c18e2686
source-git-commit: ccfc0870a8d59d16c7f5b6b02856785aa28dd307
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Adobe Experience Manager Content Fragments {#aem-fragments}

Genom att integrera Adobe Experience Manager med Adobe Journey Optimizer kan du nu smidigt införliva dina AEM Content Fragments i ditt Journey Optimizer e-postinnehåll. Denna smidiga anslutning förenklar processen att komma åt och utnyttja AEM-innehåll, vilket gör det möjligt att skapa personaliserade och dynamiska kampanjer och resor.

Mer information om AEM Content Fragment finns i [Experience Manager-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/fragments/content-fragments).

## Begränsningar {#limitations}

* Endast tillgängligt för e-postkanalen.

* Användarna kan för närvarande inte växla till den AEM-instans de är anslutna till eftersom varje sandlåda är begränsad till en enda instans.

* Vi rekommenderar att du begränsar antalet användare som kan publicera innehållsfragment för att minska risken för oavsiktliga fel i e-postmeddelanden.

* För flerspråkigt innehåll stöds endast det manuella flödet.

* Varianter stöds för närvarande inte.

* Du måste skapa en tagg speciellt för Journey Optimizer.

+++ Lär dig hur du skapar en Journey Optimizer-tagg

   1. Få åtkomst till din **Experience Manager**-miljö.

   1. Gå till fliken **Allmänt** på menyn **Verktyg** och välj **Taggning**.

   1. Klicka på **Skapa en ny tagg**.

   1. Kontrollera att ID:t följer följande syntax: `ajo-enabled:{AJO-OrgId}/{AJO-SandboxName}`.

   1. Klicka på **Skapa**.

  Nu kan du tilldela den här Journey Optimizer-taggen till dina innehållsfragment.
+++

## Lägg till AEM Content Fragments {#aem-add}

När du har skapat och personaliserat dina [AEM Content Fragments](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/fragments/content-fragments) kan du nu importera det till din kampanj eller resa för att optimera din resa.

1. När du har skapat din [kampanj](../email/create-email.md) eller [resa](../email/create-email.md) med en e-poståtgärd kan du komma åt e-postdesignern och konfigurera e-postinnehållet. [Läs mer](../email/get-started-email-design.md)

1. Klicka inuti ett textblock eller på ämnesraden och välj **[!UICONTROL Add Personalization]** i det sammanhangsberoende verktygsfältet.

   ![](assets/aem_campaign_2.png)

1. Klicka på **[!UICONTROL Open AEM CF selector]** på menyn **[!UICONTROL AEM Content Fragment]** i den vänstra rutan.

   ![](assets/aem_campaign_3.png)

1. Välj en **[!UICONTROL Content Fragment]** i den tillgängliga listan för import till ditt Journey Optimizer-innehåll.

1. Klicka på **[!UICONTROL Show filters]** för att finjustera listan med innehållsfragment.

   Som standard är filtret Innehållsfragment förinställt så att endast godkänt innehåll visas.

   ![](assets/aem_campaign_4.png)

1. När du har valt **[!UICONTROL Content Fragment]** klickar du på **[!UICONTROL Select]** för att öppna den.

   ![](assets/aem_campaign_5.png)

1. Välj önskade fält från din **[!UICONTROL Content Fragment]** som ska läggas till i ditt innehåll. Du kan antingen lägga till ditt innehåll eller kopiera dess värde.

   Observera, att om du väljer att kopiera värdet kommer framtida uppdateringar av **[!UICONTROL Content Fragment]** inte att återspeglas i din kampanj eller resa.

   ![](assets/aem_campaign_6.png)

1. Klicka på **[!UICONTROL Save]** och kontrollera meddelandet i förhandsgranskningen. Du kan nu testa och kontrollera meddelandeinnehållet enligt beskrivningen i [det här avsnittet](../content-management/preview.md).

När du har utfört dina tester och validerat innehållet kan du skicka ditt e-postmeddelande till din publik med din [kampanj](../campaigns/review-activate-campaign.md) eller [resa](../building-journeys/publishing-the-journey.md).
