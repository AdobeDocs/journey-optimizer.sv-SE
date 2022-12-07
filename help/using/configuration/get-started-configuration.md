---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med [!DNL Journey Optimizer] konfiguration
description: Läs mer om [!DNL Journey Optimizer] konfiguration
role: Admin
level: Intermediate
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 15%

---


# Kom igång med [!DNL Journey Optimizer] konfiguration {#start-optimizer-configuration}

Vid åtkomst [!DNL Journey Optimizer] För första gången tilldelas du en produktionssandlåda och ett visst antal IP-adresser beroende på ditt kontrakt.

För att kunna skapa dina resor och skicka meddelanden måste du gå igenom konfigurationsstegen nedan.

## Konfigurera meddelanden och kanaler

Definiera kanalytor, anpassa och anpassa meddelandena.

* [Delegera till underdomänerna Adobe](about-subdomain-delegation.md) du vill använda för att skicka e-post och [skapa IP-pooler](ip-pools.md) för att gruppera IP-adresser som har etablerats med din instans.

* Hantera det antal dagar som nya försök utförs innan e-postadresser skickas till listan över inaktiveringar. [Läs mer](manage-suppression-list.md)

* Definiera inställningar för push-meddelanden i båda [!DNL Adobe Experience Platform] och [!DNL Adobe Experience Platform Launch]. [Läs mer](../push/push-gs.md)

   <!--* Understand the push notification flow. [Learn more](../push/push-gs.md)-->

* Konfigurera instansen för att skicka SMS (för närvarande endast tillgängligt för en uppsättning organisationer - begränsad tillgänglighet). [Läs mer](../sms/sms-configuration.md)

* Skapa kanalytor för att konfigurera alla tekniska parametrar som krävs för att leverera meddelanden. [Läs mer](channel-surfaces.md)

* Avgör vilken e-postadress och/eller vilket telefonnummer som ska användas i prioritetsordning för dina mottagare när flera adresser/nummer är tillgängliga i Adobe Experience Platform. [Läs mer](primary-email-addresses.md)

## Konfigurera resor

För att kunna bygga resor måste du konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**. [Läs mer](about-data-sources-events-actions.md)

![](assets/admin-menu.png)

* The **datakälla** kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas på dina resor. [Läs mer](../datasource/about-data-sources.md)

* **Händelser** gör det möjligt för er att utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som kommer in på resan. I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobes upplevelsedatamodell (XDM). Händelser kommer från API för strömningsinmatning för autentiserade och ej autentiserade händelser (till exempel händelser i Adobe Mobile SDK). [Läs mer](../event/about-events.md)

* [!DNL Journey Optimizer] innehåller inbyggda meddelandefunktioner som gör att du kan designa och skicka innehåll. Om du använder ett tredjepartssystem för att skicka meddelanden skapar du en **anpassad åtgärd**. [Läs mer](../action/action.md)