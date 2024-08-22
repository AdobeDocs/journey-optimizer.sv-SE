---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med  [!DNL Journey Optimizer] konfiguration
description: Läs mer om  [!DNL Journey Optimizer] konfiguration
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
keywords: konfiguration, konfigurera, meddelanden, kanal, sandlåda, optimerare
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 10%

---


# Kom igång med konfigurationen [!DNL Journey Optimizer] {#start-optimizer-configuration}

När du använder [!DNL Journey Optimizer] för första gången tilldelas du en produktionssandlåda och ett visst antal IP-adresser beroende på ditt kontrakt.

För att kunna skapa dina resor och skicka meddelanden måste du gå igenom konfigurationsstegen nedan.

## Konfigurera meddelanden och kanaler

1. För att kunna skapa och skicka meddelanden måste du utföra specifika konfigurationer beroende på kanalen.

   * För kanalen **Email** måste du delegera underdomäner till Adobe och skapa IP-pooler för att gruppera IP-adresser. [Läs mer](../email/get-started-email-config.md)

   * För kanalen **Push** måste du definiera inställningar för push-meddelanden i både [!DNL Adobe Experience Platform] och [!DNL Adobe Experience Platform Launch]. [Läs mer](../push/push-configuration.md)

   * För **SMS**-kanalen måste du konfigurera instansen för att skicka SMS, inklusive att integrera providerinställningarna med [!DNL Journey Optimizer]. [Läs mer](../sms/sms-configuration.md)

1. När du är klar måste du skapa **kanalkonfigurationer** för att konfigurera alla tekniska parametrar som krävs för att leverera meddelanden. [Läs mer](channel-surfaces.md)

1. Du kan även:

   * Hantera det antal dagar som nya försök utförs innan e-postadresser skickas till listan över inaktiveringar. [Läs mer](manage-suppression-list.md)

   * Aktivera alternativet **BBC-e-post** om du vill behålla en kopia av meddelanden som skickas till enskilda personer. [Läs mer](archiving-support.md#enable-bcc)

   * Konfigurera **affärsregler** för att undvika att dina mottagare blir överdrivna. [Läs mer](frequency-rules.md)

   * Avgör vilken e-postadress och/eller vilket telefonnummer som ska användas i prioritetsordning för dina mottagare när flera adresser/nummer är tillgängliga i Adobe Experience Platform. [Läs mer](primary-email-addresses.md)

<!--* Understand the push notification flow. [Learn more](../push/push-gs.md)-->

>[!NOTE]
>
>Dessa steg måste utföras av en [Adobe Journey Optimizer-systemadministratör](../start/path/administrator.md).

## Konfigurera resor

För att kunna skapa resor måste du konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**. [Läs mer](about-data-sources-events-actions.md)

![](assets/admin-menu.png)

* Med konfigurationen för **datakälla** kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas på dina resor. [Läs mer](../datasource/about-data-sources.md)

* **Med händelser** kan du utlösa dina resor åt gången för att skicka meddelanden i realtid till den person som flyger in på resan. I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobes upplevelsedatamodell (XDM). Händelser kommer från API:er för direktuppspelning av inmatning för autentiserade och oautentiserade händelser (som Adobe Mobile SDK-händelser). [Läs mer](../event/about-events.md)

* [!DNL Journey Optimizer] har inbyggda meddelandefunktioner som gör att du kan utforma och skicka ditt innehåll. Om du använder ett tredjepartssystem för att skicka meddelanden skapar du en **anpassad åtgärd**. [Läs mer](../action/action.md)