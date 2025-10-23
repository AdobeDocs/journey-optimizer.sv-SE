---
solution: Journey Optimizer
product: journey optimizer
title: Definiera API-utlösta kampanjegenskaper
description: Lär dig hur du definierar API-utlösta kampanjegenskaper.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
exl-id: bda7e337-a246-4f01-b935-4a234d4c4baa
source-git-commit: d93b7ce225294257f49caee6ac08cfb575611a93
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Definiera API-utlösta kampanjegenskaper {#api-properties}

Så här skapar du en ny API-utlöst kampanj:

1. Bläddra till menyn **[!UICONTROL Campaigns]** och välj fliken **[!UICONTROL API triggered]**.

1. Klicka på knappen **[!UICONTROL Create campaign]** och välj kampanjtyp:

   * **[!UICONTROL API triggered - Marketing]** - Välj den här typen av API-utlösta kampanj för att skicka personaliserad marknadsföringskommunikation till målgrupper.

   * **[!UICONTROL API triggered - Transactional]** - Transaktionskampanjer syftar till att skicka transaktionsmeddelanden, d.v.s. meddelanden som skickas ut efter en åtgärd som har utförts av en individ: lösenordsåterställning, kundvagn osv.

     +++Läge med hög genomströmning

     Du kan aktivera läget **[!UICONTROL High Throughput]** för transaktions-API-utlösta kampanjer. Det här läget är utformat för storskaliga meddelanden i realtid (upp till 5 000 transaktioner per sekund) och ger högre tillgänglighet med lägre latens. [Lär dig hur du arbetar med högdagerläge](../campaigns/api-triggered-high-throughput.md)

     >[!AVAILABILITY]
     >
     >För närvarande är läget High Throput bara tillgängligt för e-postkanalen och i USA-regionen.
     >
     >Den här funktionen är bara tillgänglig för organisationer som har köpt tillägget **Transactional Messaging med hög genomströmning** för Adobe. Kontakta Adobe om du vill ha mer information.

     +++

   ![](assets/api-triggered-modal.png)

1. Ange ett namn och en beskrivning för kampanjen på fliken **[!UICONTROL Properties]**.

   ![](assets/create-campaign-properties.png)

1. Använd fältet **Taggar** för att tilldela enhetliga Adobe Experience Platform-taggar till kampanjen. På så sätt kan ni enkelt klassificera dem och förbättra sökningen från kampanjlistan. [Lär dig arbeta med taggar](../start/search-filter-categorize.md#tags).

1. Du kan begränsa åtkomsten till den här kampanjen baserat på åtkomstetiketter. Om du vill lägga till en åtkomstbegränsning bläddrar du till knappen **[!UICONTROL Manage access]** högst upp på sidan. Se till att endast markera etiketter som du har behörighet för. [Läs mer om åtkomstkontroll på objektnivå](../administration/object-based-access.md).

## Nästa steg {#next}

När kampanjens konfiguration och innehåll är klart kan du konfigurera dess åtgärd. [Läs mer](api-triggered-campaign-action.md)
