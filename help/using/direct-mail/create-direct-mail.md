---
title: Skapa ett direktutskick
description: Lär dig hur du skapar ett direktutskick i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: direktreklam, meddelande, kampanj
exl-id: 6b438268-d983-4ab8-9276-c4b7de74e6bd
source-git-commit: d8ae894cc303237f5b2257afd8da5b2d0cf1b7a6
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 4%

---

# Skapa ett direktutskick {#create-direct}

>[!CONTEXTUALHELP]
>id="ajo_direct_mail"
>title="Skapa direktreklam"
>abstract="Skapa direktreklam i schemalagda kampanjer och utforma de extraheringsfiler som direktreklamleverantörer behöver för att skicka e-post till era kunder."

Skapa en schemalagd kampanj och konfigurera extraheringsfilen om du vill skapa direktutskick. Den här filen krävs av direktreklamleverantörer för att skicka e-post till dina kunder.

>[!IMPORTANT]
>
>Kontrollera att du har konfigurerat innan du skapar ett direktmeddelandemeddelande:
>
>1. A [konfiguration för filroutning](../direct-mail/direct-mail-configuration.md#file-routing-configuration) som anger den server där extraheringsfilen ska överföras och lagras,
>1. A [meddelandeyta för direktreklam](../direct-mail/direct-mail-configuration.md#direct-mail-surface) som refererar till filroutningskonfigurationen.


## Skapa en kampanj för direktreklam{#create-dm-campaign}

Så här skapar du en direktreklamkampanj:

1. Skapa en ny schemalagd kampanj och välj **[!UICONTROL Direct mail]** som åtgärden.

1. Välj **[!UICONTROL Direct mail surface]** använda och klicka **[!UICONTROL Create]**. [Lär dig hur du skapar en direktreklamyta](direct-mail-configuration.md#direct-mail-surface).

   ![](assets/direct-mail-campaign.png){width="800" align="center"}

1. I **[!UICONTROL Properties]** redigerar du Campaigns **[!UICONTROL Title]** och **[!UICONTROL Description]**.

1. Definiera målgruppen genom att klicka på **[!UICONTROL Select audience]** och välj bland de tillgängliga Adobe Experience Platform-målgrupperna. [Läs mer](../audience/about-audiences.md).

   >[!IMPORTANT]
   >
   >För närvarande är valet av målgrupp begränsat till 3 miljoner profiler. Denna begränsning kan hävas på begäran av Adobe.

1. I **[!UICONTROL Identity namespace]** markerar du lämpligt namnutrymme för att identifiera personer inom den valda målgruppen. [Läs mer](../event/about-creating.md#select-the-namespace).

   ![](assets/direct-mail-campaign-properties.png){width="800" align="center"}

1. Kampanjer kan schemaläggas för ett specifikt datum eller ställas in så att de återkommer med regelbundna intervall. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** av kampanjen i [det här avsnittet](../campaigns/create-campaign.md#schedule).

Nu kan du börja konfigurera extraheringsfilen som ska skickas till din direktmeddelandeleverantör.

## Konfigurera extraheringsfilen {#extraction-file}

Extraheringsfilen krävs av direktreklamleverantörer för att skicka e-post till dina kunder. Så här definierar du extraheringsfilens konfiguration:

1. På skärmen för kampanjkonfiguration klickar du på **[!UICONTROL Edit content]** för att konfigurera extraheringsfilens innehåll.

1. Justera extraheringsfilens egenskaper:

   1. Ange önskat **[!UICONTROL Filename]** för extraheringsfilen.

   1. Om du vill kan du aktivera **[!UICONTROL Append timestamp to export filename]** om du vill lägga till en automatisk tidsstämpel till det angivna filnamnet.

   1. Ibland kan du behöva lägga till information i början eller slutet av extraheringsfilen.  Använd **[!UICONTROL Notes]** anger du sedan om du vill ta med anteckningen som sidhuvud eller sidfot.

      ![](assets/direct-mail-properties.png){width="800" align="center"}

1. Konfigurera kolumnerna och den information som ska visas i extraheringsfilen:

   1. Klicka på **[!UICONTROL Add]** för att skapa en ny kolumn.

   1. The **[!UICONTROL Formatting]** visas till höger så att du kan ställa in den markerade kolumnen. Ange en **[!UICONTROL Label]** för kolumnen.

   1. I **[!UICONTROL Data]** väljer du de profilattribut som ska visas med [Uttrycksredigeraren](../personalization/personalization-build-expressions.md).

   1. Om du vill sortera extraheringsfilen med en kolumn markerar du kolumnen och växlar på **[!UICONTROL Sort by]** alternativ. The **[!UICONTROL Sort By]** visas bredvid kolumnens etikett i dialogrutan **[!UICONTROL Data Fields]** -avsnitt.

      ![](assets/direct-mail-content.png){width="800" align="center"}

   1. Upprepa dessa steg om du vill lägga till så många kolumner som behövs för extraheringsfilen. Observera att du kan lägga till upp till 50 kolumner.

      Om du vill ändra en kolumns position drar och släpper du den till önskad plats i dialogrutan **[!UICONTROL Data field]** -avsnitt. Om du vill ta bort en kolumn markerar du den och klickar på **[!UICONTROL Remove]** knappen i **[!UICONTROL Formatting]** fönster.

Nu kan du testa ditt direktutskick och skicka det till din publik. [Lär dig hur du testar och skickar direktreklam](test-send-direct-mail.md)
