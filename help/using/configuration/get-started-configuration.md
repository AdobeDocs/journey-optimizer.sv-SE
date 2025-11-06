---
solution: Journey Optimizer
product: journey optimizer
title: 'Kom igång med kanalkonfigurationen  [!DNL Journey Optimizer] '
description: 'Läs mer om kanalkonfiguration för [!DNL Journey Optimizer] '
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
keywords: konfiguration, konfigurera, meddelanden, kanal, sandlåda, optimerare
source-git-commit: efb943e5a6f27becc6e8b6128b776e46d6141823
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 4%

---


# Kom igång med kanalkonfiguration {#start-optimizer-configuration}

>[!CONTEXTUALHELP]
>id="ajo_channels_rate_controls"
>title="Hastighetskontroller för kanaler"
>abstract="Hastighetskontroller för kanaler"

När du använder [!DNL Journey Optimizer] för första gången tilldelas du en produktionssandlåda och ett visst antal IP-adresser beroende på ditt kontrakt.

För att kunna skicka meddelanden måste du gå igenom konfigurationsstegen som anges nedan:

1. Som [Adobe Journey Optimizer-systemadministratör](../start/path/administrator.md) definierar du dina kanalspecifika konfigurationer. Lär dig hur du konfigurerar dessa konfigurationer på följande sidor:

   <table style="table-layout:fixed"><tr style="border: 0;">
    <td><a href="../email/get-started-email-config.md"><img alt="e-post" src="../channels/assets/do-not-localize/email.png"></a>
    <div align="center"><a href="../email/get-started-email-config.md"><strong>E-post</strong></a></div></td>
    <td><a href="../sms/sms-configuration.md"><img alt="sms" src="../channels/assets/do-not-localize/sms.png"></a>
    <div align="center"><a href="../sms/sms-configuration.md"><strong>SMS</strong></a></div></td>
    <td><a href="../push/push-configuration.md"><img alt="push" src="../channels/assets/do-not-localize/push.png"></a>
    <div align="center"><a href="../push/push-configuration.md"><strong>Push-meddelande</strong></a></div></td>
    <td><a href="../direct-mail/direct-mail-configuration.md"><img alt="direktreklam" src="../channels/assets/do-not-localize/direct-mail.jpg"></a>
    <div align="center"><a href="../direct-mail/direct-mail-configuration.md"><strong>Direktutskick</strong></a></div></td>
    </tr></table>

   <table style="table-layout:fixed"><tr style="border: 0;">
    <td><a href="../in-app/inapp-configuration.md"><img alt="i appen" src="../channels/assets/do-not-localize/inapp.jpg"></a>
    <div align="center"><a href="../in-app/inapp-configuration.md"><strong>I appen</strong></a></div></td>
    <td><a href="../web/web-configuration.md"><img alt="webb" src="../channels/assets/do-not-localize/web.jpg"></a>
    <div align="center"><a href="../web/web-configuration.md"><strong>Webb</strong></a></div></td>
    <td><a href="../code-based/code-based-configuration.md"><img alt="kodbaserad upplevelse" src="../channels/assets/do-not-localize/code.png"></a>
    <div align="center"><a href="../code-based/code-based-configuration.md"><strong>Kodbaserad upplevelse</strong></a></div></td>
    <td><a href="../content-card/content-card-configuration-prereq.md"><img alt="innehållskort" src="../channels/assets/do-not-localize/cards.png"></a>
    <div align="center"><a href="../content-card/content-card-configuration-prereq.md"><strong>Innehållskort</strong></a></div></td>
    </tr></table>

   >[!NOTE]
   >
   >För mobilkanaler underlättar [konfigurationen av den guidade kanalen](set-mobile-config.md) den snabba konfigurationen av marknadsföringskanaler och ser till att alla nödvändiga resurser är tillgängliga inom Experience Platform, Journey Optimizer och datainsamling. På så sätt kan marknadsföringsteamet börja med att skapa kampanjer och resor.

1. När du är klar måste du konfigurera alla tekniska parametrar som krävs för att leverera meddelanden genom att skapa **kanalkonfigurationer**. [Läs mer om kanalkonfigurationer](channel-surfaces.md)

1. Beroende på vilka kanaler du använder, dina miljöer och dina behov måste du också utföra följande steg:

   * Underdomänskonfiguration och delegering för dina kanaler, till exempel [e-post](about-subdomain-delegation.md), [SMS](../sms/sms-subdomains.md), [landningssidor](../landing-pages/lp-subdomains.md) och [webbupplevelser](../web/web-delegated-subdomains.md).

   * Konfigurera IP-warmup-planer för optimal leverans. [Läs mer](ip-warmup-gs.md)

   * Definiera en tillåtelselista för att skicka e-post. [Läs mer](allow-list.md)

   * Hantera det antal dagar som nya försök utförs innan e-postadresser skickas till listan över inaktiveringar. [Läs mer](manage-suppression-list.md)

   * Aktivera alternativet **BCC-e-post** om du vill behålla en kopia av meddelanden som skickas till enskilda personer. [Läs mer](archiving-support.md#enable-bcc)

   * Konfigurera **affärsregler** för att undvika att dina mottagare blir överdrivna. [Läs mer](../conflict-prioritization/rule-sets.md)

   * Avgör vilken e-postadress och/eller vilket telefonnummer som ska användas i prioritetsordning för dina mottagare när flera adresser/nummer är tillgängliga i Adobe Experience Platform. [Läs mer](primary-email-addresses.md)

## Ytterligare resurser

* **[Konfigurera kanalytor](channel-surfaces.md)** - Lär dig hur du konfigurerar och hanterar kanalytor för e-post, push, SMS och andra kanaler.
* **[Delegering via underdomän](delegate-subdomain.md)** - Lär dig hur du delegerar underdomäner till Adobe för e-postleverans och profilering.
* **[IP-värmare](ip-warmup-gs.md)** - Upptäck bästa praxis för IP-adresshämning för att förbättra e-postleveransen och avsändarens anseende.
* **[Hantera undertryckningslista](manage-suppression-list.md)** - Lär dig hur du hanterar undertryckningslistor för att hantera gränser och upprätthålla listhygienen.
* **[Konfigurera mobilappar](set-mobile-config.md)** - Konfigurera mobilappskonfigurationer för push-meddelanden och meddelanden i appen.
* **[Konfigurationsinstruktioner](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/configure-channels){target="_blank"}** - Utforska steg-för-steg-videokurser om kanalkonfiguration och metodtips.
