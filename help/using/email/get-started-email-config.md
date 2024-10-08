---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med e-postkonfiguration
description: Läs mer om e-postkonfigurationen i  [!DNL Journey Optimizer]
role: Admin
level: Experienced
feature: Channel Configuration, Email
topic: Administration
keywords: e-post, konfiguration, yta, underdomäner
exl-id: 1fc9a4f6-6c34-4414-b400-aac6bda9ee25
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 7%

---

# Kom igång med e-postkonfiguration {#get-starte-email-config}

Om du vill kunna skicka e-post via resor och kampanjer i [!DNL Journey Optimizer] måste du gå igenom ett antal konfigurationssteg.

1. För att säkerställa optimal leverans och skydda ditt rykte börjar du med att delegera till Adobe de underdomäner som du tänker använda för att skicka e-postmeddelanden med [!DNL Journey Optimizer]. Dessa underdomäner avgör element som webbsidor som ska spåras och URL:er för spegelsidor. [Läs mer](../configuration/about-subdomain-delegation.md)

   ![](../configuration/assets/subdomain-list.png)

1. Förbättra e-postleveransen och anseendet genom att gruppera IP-adresser som tillhandahålls med din instans. [Läs mer](../configuration/ip-pools.md)

   ![](../configuration/assets/ip-pool-create.png)

1. Skapa kanalkonfigurationer och välj kanalen **[!UICONTROL Email]**. [Läs mer](../configuration/channel-surfaces.md)


   ![](../configuration/assets/preset-general.png)

1. Konfigurera alla tekniska parametrar som krävs för att leverera e-postmeddelanden i varje e-postkanalskonfiguration. [Läs mer](email-settings.md)

   * Här väljer du den underdomän som ska användas för att skicka e-postmeddelanden och de IP-pooler som ska associeras med konfigurationen. [Läs mer](email-settings.md#subdomains-and-ip-pools)

   ![](assets/surface-subdomain-ip-pool.png)

   * **[!UICONTROL Sender email]**- och **[!UICONTROL Error email]**-adresserna måste använda den valda delegerade underdomänen. [Läs mer](email-settings.md#email-header)

   ![](assets/preset-header.png)

1. Avgör vilken e-postadress som ska användas i prioritetsordning för mottagarna när det finns flera tillgängliga adresser i Adobe Experience Platform. [Läs mer](../configuration/primary-email-addresses.md)

   ![](../configuration/assets/primary-address-execution-fields.png)

1. Hantera det antal dagar som nya försök utförs innan e-postadresser skickas till listan över inaktiveringar. [Läs mer](../configuration/manage-suppression-list.md)

   ![](../configuration/assets/suppression-list-edit-retries.png)
