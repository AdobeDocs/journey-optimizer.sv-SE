---
title: Skapa reserverbjudanden
description: Lär dig hur du skapar reserverbjudanden för kunder som inte är berättigade till något erbjudande
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
exl-id: 9ba16ad9-a5e7-4ce7-8ed6-7707d37178c6
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 2%

---

# Skapa reserverbjudanden {#create-fallback-offers}

Reserverbjudandet skickas till kunderna om de inte är berättigade till andra erbjudanden. Stegen för att skapa ett reserverbjudande består av att skapa en eller flera representationer, som när du skapar ett erbjudande.

➡️ [Upptäck den här funktionen i videon](#video)

Listan över reserverbjudanden finns på menyn **[!UICONTROL Offers]**.

![](../assets/offers_list.png)

Så här skapar du ett reserverbjudande:

>[!NOTE]
>
>Observera, att till skillnad från personaliserade erbjudanden saknar reserverbjudanden regler och begränsningsparametrar eftersom de presenteras för kunderna som sista utväg utan villkor.

1. Klicka på **[!UICONTROL Create offer]** och välj sedan **[!UICONTROL Fallback offer]**.

   ![](../assets/create_fallback.png)

1. Ange erbjudandets namn. Du kan också koppla en eller flera befintliga samlingskvalificerare (som tidigare kallats taggar) till den, så att du enklare kan söka efter och ordna erbjudandebiblioteket.

   ![](../assets/fallback_details.png)

1. Välj **[!UICONTROL Manage access]** om du vill tilldela etiketter för anpassad eller viktig dataanvändning till erbjudandet. [Läs mer om OLAC (Object Level Access Control)](../../administration/object-based-access.md)

1. Skapa en eller flera representationer för reserverbjudandet. Det gör du genom att dra och släppa praktik från den vänstra rutan, som när du skapar ett personaliserat erbjudande. Se [Skapa anpassade erbjudanden](../offer-library/creating-personalized-offers.md).

   ![](../assets/fallback_content.png)

1. När reserverbjudandets representationer har lagts till visas en sammanfattning. Om allt är korrekt konfigurerat och ditt reserverbjudande är klart att presenteras för kunderna klickar du på **[!UICONTROL Finish]** och väljer sedan **[!UICONTROL Save and approve]**.

   Du kan också spara reserverbjudandet som ett utkast för att redigera och godkänna det senare.

   ![](../assets/fallback_review.png)

1. Reserverbjudandet visas i listan med statusen **[!UICONTROL Live]** eller **[!UICONTROL Draft]**, beroende på om du godkände det eller inte i föregående steg.

   Den är nu klar att levereras till kunderna. Du kan markera den för att visa dess egenskaper och redigera den. <!-- no suppression? -->

   ![](../assets/fallback_created.png)

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329383?quality=12)

