---
title: Kom igång med [!DNL Journey Optimizer] konfiguration
description: Läs mer om [!DNL Journey Optimizer] konfiguration
role: Admin
level: Intermediate
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 11%

---


# Kom igång med [!DNL Journey Optimizer] konfiguration {#start-optimizer-configuration}

Vid åtkomst [!DNL Journey Optimizer] För första gången tilldelas du en produktionssandlåda och ett visst antal IP-adresser beroende på ditt kontrakt.

För att kunna skapa dina resor och skicka meddelanden måste du gå igenom följande konfigurationssteg:

1. **Konfigurera meddelanden och kanaler**: definiera kanalytor, anpassa och anpassa meddelandena.

   * Skapa kanalytor för att konfigurera alla tekniska parametrar som krävs för att leverera meddelanden. [Läs mer](message-presets.md)

   * Avgör vilken e-postadress som ska användas i prioritetsordning för mottagarna när det finns flera tillgängliga adresser i Adobe Experience Platform. [Läs mer](primary-email-addresses.md)

   * Hantera det antal dagar som nya försök utförs innan e-postadresser skickas till listan över inaktiveringar. [Läs mer](manage-suppression-list.md)

   * Definiera inställningar för push-meddelanden i båda [!DNL Adobe Experience Platform] och [!DNL Adobe Experience Platform Launch]. [Läs mer](../configuration/push-gs.md)

   <!--* Understand the push notification flow. [Learn more](../configuration/push-gs.md)-->

   * Konfigurera instansen för att skicka SMS (för närvarande endast tillgängligt för en uppsättning organisationer - begränsad tillgänglighet). [Läs mer](sms-configuration.md)


1. **Delegera underdomäner**: för alla nya underdomäner som ska användas i Journey Optimizer är det första steget att delegera den. [Läs mer](about-subdomain-delegation.md)

   ![](assets/subdomain.png)

1. **Skapa IP-pooler**: förbättra e-postleveransen och ditt anseende genom att gruppera IP-adresser som har etablerats med din instans. [Läs mer](ip-pools.md)

   ![](assets/ip-pool.png)

1. **Konfigurera resor**: för att kunna bygga resor måste ni konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**. [Läs mer](about-data-sources-events-actions.md)

   ![](assets/admin-menu.png)

   * The **datakälla** kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas på dina resor. [Läs mer](../datasource/about-data-sources.md)

   * **Händelser** gör det möjligt för er att utlösa era resor helt och hållet för att skicka meddelanden i realtid till den person som kommer in på resan. I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobe Experience Data Model (XDM). Händelser kommer från API för strömningsinmatning för autentiserade och ej autentiserade händelser (till exempel händelser i Adobe Mobile SDK). [Läs mer](../event/about-events.md)

   * [!DNL Journey Optimizer] innehåller inbyggda meddelandefunktioner som gör att du kan designa och skicka innehåll. Om du använder ett tredjepartssystem för att skicka meddelanden skapar du en **anpassad åtgärd**. [Läs mer](../action/action.md)