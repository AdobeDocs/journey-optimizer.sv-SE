---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med kampanjer
description: Läs mer om kampanjer i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Intermediate
keywords: kampanj, hur, starta, optimera
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 8b1bf0b0469c1efc5194dae56ddddd9f05dbf722
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---

# Kom igång med kampanjer {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="Kampanjer"
>abstract="Skapa kampanjer för att leverera engångsinnehåll till ett specifikt segment i olika kanaler. Innan du skapar din kampanj måste du se till att du har en kanalyta (t.ex. en meddelandeförinställning) och ett Adobe Experience Platform-segment som är klart att användas."

Använd Journey Optimizer kampanjer för att leverera engångsinnehåll till ett visst segment via olika kanaler. När du använder resor utförs åtgärderna i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema.

Du kan skapa två typer av kampanjer:

* **Schemalagda kampanjer** möjliggör enkel ad hoc-batchkommunikation för marknadsföringsfall som reklamerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar.
* **API-utlösta kampanjer** möjliggör enkla transaktions-/driftsmeddelanden med REST API:er (lösenordsåterställning, övergivna varukorgar osv.), där behovet kan innebära personalisering med hjälp av profilattribut och sammanhangsbaserade data från nyttolast.

De viktigaste stegen för att skapa en kampanj är följande:

![](assets/create-campaign-process.png)

➡️ [Upptäck den här funktionen i en video](#video)

## Före start {#campaign-prerequisites}

Kontrollera följande innan du börjar skapa din första kampanj i Journey Optimizer:

1. **Du behöver rätt behörigheter**. Kampanjer är bara tillgängliga för användare med tillgång till en kampanjrelaterad **[!UICONTROL Product profile]** som Campaign-administratör, Campaign-godkännare, Campaign-chef och/eller Campaign-visningsprogram.

   Om du inte kan komma åt kampanjer måste din behörighet utökas. Om du har åtkomst till [Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"} för din organisation, följ stegen nedan. Om inte, kontakta Journey Optimizer-administratören.

   +++Lär dig hur du tilldelar kampanjbehörigheter

   Tilldela motsvarande **[!UICONTROL Product profile]** till användarna:

   1. Från [Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}väljer du [!DNL Adobe Experience Platform] produkt.

   1. Bläddra till **[!UICONTROL Product profile]** väljer du en av de inbyggda kampanjrelaterade **[!UICONTROL Product profile]**: Kampanjadministratör, Kampanjgodkännare, Kampanjhanterare eller Kampanjvisningsprogram.

      Mer information om Journey Optimizer kampanj **[!UICONTROL Product profiles]** och **[!UICONTROL Permissions]**, [hänvisa till denna sida](../administration/ootb-product-profiles.md).

      ![](assets/do-not-localize/admin_1.png)

   1. Klicka **[!UICONTROL Add user]** för att tilldela användaren det valda **[!UICONTROL Product profile]**.

      ![](assets/do-not-localize/admin_2.png)

   1. Ange användarens namn, grupp eller e-postadress och klicka på **[!UICONTROL Save]**.
   Användaren har nu åtkomst **[!UICONTROL Campaigns]**.

+++

1. **Ni behöver en målgrupp**. Målgruppssegment måste vara tillgängliga innan kampanjen kan skapas. Läs mer om målgruppsframtagning [på den här sidan](../segment/about-segments.md).
1. **Du behöver en kanalyta**. Om du vill kunna markera en kanal måste du ha motsvarande kanalyta (dvs. förinställning) skapad och tillgänglig. Läs mer om kanalytor [på den här sidan](../configuration/channel-surfaces.md).

## Instruktionsvideo {#video}

Lär dig hur du skapar din första kampanj.

>[!VIDEO](https://video.tv.adobe.com/v/346680?quality=12)
