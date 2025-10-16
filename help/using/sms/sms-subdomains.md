---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera underdomäner för textmeddelanden (SMS/MMS)
description: Lär dig konfigurera SMS-underdomäner med Journey Optimizer
role: Admin
feature: SMS, Channel Configuration
level: Intermediate
keywords: SMS, underdomäner, konfiguration
exl-id: 08a546d1-060c-43e8-9eac-4c38945cc3e1
source-git-commit: 7b1be144776fd11cd4aa90aa315eee60b1acc40f
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 0%

---

# Konfigurera SMS-underdomäner {#sms-mms-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_sms_header"
>title="Delegera en SMS/MMS-underdomän"
>abstract="Konfigurera din underdomän för textmeddelanden (SMS/MMS). Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en ny underdomän."

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_sms"
>title="Delegera en SMS/MMS-underdomän"
>abstract="Du måste konfigurera en underdomän att använda för dina textmeddelanden, eftersom du behöver den här underdomänen för att skapa en SMS-konfiguration. Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en ny underdomän."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/sms/configure-sms/sms-configuration-surface" text="Skapa en SMS-konfiguration"

>[!CONTEXTUALHELP]
>id="ajo_admin_config_sms_subdomain"
>title="Välj en SMS/MMS-underdomän"
>abstract="Om du vill kunna skapa en SMS-konfiguration måste du kontrollera att du tidigare har konfigurerat minst en SMS-underdomän att välja från listan över underdomännamn."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/channels/sms/configure-sms/sms-configuration-surface" text="Skapa en SMS-konfiguration"

## Kom igång med SMS-underdomäner {#gs-sms-mms-subdomains}

Om du vill kunna förkorta URL:er som läggs till i dina SMS/MMS-meddelanden måste du konfigurera den underdomän du väljer när du [skapar en SMS-konfiguration](sms-configuration.md#message-preset-sms).

Du kan antingen använda en underdomän som redan har delegerats till Adobe eller konfigurera en annan underdomän. Läs mer om hur du delegerar underdomäner till Adobe i [det här avsnittet](../configuration/delegate-subdomain.md).

SMS-underdomänskonfigurationen **delas mellan alla miljöer**. Därför påverkar alla ändringar av en SMS-underdomän även andra produktionssandlådor.

Om du vill komma åt och redigera SMS-underdomäner måste du ha behörigheten **[!UICONTROL Manage SMS Subdomains]** i produktionssandlådan. Läs mer om behörigheter i [det här avsnittet](../administration/high-low-permissions.md).

## Använd en befintlig underdomän {#sms-use-existing-subdomain}

Om du vill använda en underdomän som redan har delegerats till Adobe följer du stegen nedan.

1. Bläddra till menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och välj **[!UICONTROL SMS settings]** > **[!UICONTROL SMS subdomains]**.

1. Klicka på **[!UICONTROL Set up subdomain]**.

   ![](assets/sms_set-up-subdomain.png)

1. Välj **[!UICONTROL Use delegated subdomain]** i avsnittet **[!UICONTROL Configuration type]**.

   ![](assets/sms_use-delegated-subdomain.png)

1. Ange det prefix som ska visas i SMS-URL:en.

   Endast alfanumeriska tecken och bindestreck tillåts.

   >[!CAUTION]
   >
   >Använd inte prefix av typen `cdn` eller `data` eftersom dessa är reserverade för internt bruk. Andra begränsade eller reserverade prefix som `dmarc` eller `spf` bör också undvikas.

1. Välj en delegerad underdomän i listan.

   Du kan inte välja en underdomän som redan används som SMS-underdomän.

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

   ![](assets/sms_prefix-and-subdomain.png)

   <!--Note that you cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your SMS messages, you will not be able to use 'marketing2.yourcompany.com'. However, multi-level subdomains being supported for SMS, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.-->

   >[!CAUTION]
   >
   >Om du väljer en domän som delegerats till Adobe med metoden [CNAME](../configuration/delegate-subdomain.md#cname-subdomain-setup) måste du skapa DNS-posten på din värdplattform. För att skapa DNS-posten är processen densamma som när du konfigurerar en ny SMS-underdomän. Lär dig hur i [det här avsnittet](#sms-configure-new-subdomain).

1. Klicka på **[!UICONTROL Submit]**.

1. När den har skickats visas underdomänen i listan med statusen **[!UICONTROL Processing]**. Mer information om underdomäners status finns i [det här avsnittet](../configuration/delegate-subdomain.md#access-delegated-subdomains).<!--Same statuses?-->

   Innan du kan använda den underdomänen för att skicka meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta **upp till 4 timmar**.<!--Learn more in [this section](delegate-subdomain.md#subdomain-validation).-->

1. När kontrollerna har slutförts får underdomänen statusen **[!UICONTROL Success]**. Det är klart att användas för att skapa SMS-kanalkonfigurationer.

## Konfigurera en ny underdomän {#sms-configure-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_subdomain_dns"
>title="Generera matchande DNS-post"
>abstract="Om du vill konfigurera en ny SMS-underdomän måste du kopiera den Adobe-namnserverinformation som visas i Journey Optimizer-gränssnittet och klistra in den i din domänvärdslösning för att generera den matchande DNS-posten. När kontrollerna är slutförda kan underdomänen användas för att skapa SMS-konfigurationer."

Följ stegen nedan för att konfigurera en ny underdomän.

1. Bläddra till menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och välj sedan **[!UICONTROL SMS settings]** > **[!UICONTROL SMS subdomains]**.

1. Klicka på **[!UICONTROL Set up subdomain]**.

   ![](assets/sms_set-up-subdomain.png)

1. Välj **[!UICONTROL Add your own domain]** i avsnittet **[!UICONTROL Configuration type]**.

   ![](assets/sms_add-your-own-subdomain.png)

1. Ange den underdomän som ska delegeras.

   >[!CAUTION]
   >
   >* Du kan inte använda en befintlig SMS-underdomän.
   >
   >* Versaler tillåts inte i underdomäner.

   Det är inte tillåtet att delegera en ogiltig underdomän till Adobe. Se till att du anger en giltig underdomän som ägs av din organisation, till exempel marketing.yourcompany.com.

   Underdomäner på flera nivåer (av samma överordnade domän) stöds. Du kan till exempel använda sms.marketing.your.com.

1. Posten som ska placeras i dina DNS-servrar visas. Kopiera den här posten eller hämta en CSV-fil och navigera sedan till din värdlösning för domänen för att generera den matchande DNS-posten.

1. Kontrollera att DNS-posten har genererats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan Jag bekräftar.. och klickar sedan på **[!UICONTROL Submit]**.

   ![](assets/sms_add-your-own-subdomain-confirm.png)

   När du konfigurerar en ny SMS-underdomän pekar den alltid på en CNAME-post.

1. När underdomänsdelegeringen har skickats visas underdomänen med statusen **[!UICONTROL Processing]** i listan. Mer information om underdomäners status finns i [det här avsnittet](../configuration/delegate-subdomain.md#access-delegated-subdomains).<!--Same statuses?-->

Innan du använder en underdomän för att skicka SMS-meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 4 timmar.<!--Learn more in [this section](#subdomain-validation).--> När kontrollerna har slutförts får underdomänen statusen **[!UICONTROL Success]**. Det är klart att användas för att skapa SMS-kanalkonfigurationer.

Observera att underdomänen markeras som **[!UICONTROL Failed]** om du inte kan skapa valideringsposten i din värdlösning.

## Guardrails {#guardrails}

Användargränssnittet [!DNL Journey Optimizer] stöder för närvarande inte borttagning eller avdelegering av SMS-underdomäner när de har konfigurerats.

När du testar funktioner i [!DNL Journey Optimizer] kan det dock vara nödvändigt att skapa en SMS-underdomän. När testningen är klar kan detta leda till klumpiga miljöer med onödiga konfigurationer eftersom användargränssnittet inte tillåter borttagning eller avdelegering av SMS-underdomäner.

Här följer några rekommenderade steg och överväganden:

<!--As an alternative action, create a new SMS subdomain for future use cases and avoid using the existing one if it is no longer needed.-->

* Det bästa sättet är att underhålla en snygg miljö genom att bara skapa nödvändiga komponenter och konfigurationer.
* I situationer där det kan påverka ditt företag ska du kontakta din Adobe-representant som kan hjälpa dig med borttagningen/avdelegeringen av SMS-underdomänen. [Läs mer](#undelegate-subdomain)
* Om mer hjälp behövs kan du kontakta Adobe för att få hjälp med hur du hanterar instansen effektivt.

## Avdelegera en underdomän {#undelegate-subdomain}

Om du inte längre vill delegera en SMS-underdomän kan du kontakta din Adobe-representant med den underdomän som du vill avdelegera.

Om SMS-underdomänen pekar på en CNAME-post kan du ta bort den CNAME DNS-post som du skapade för SMS-underdomänen från din värdlösning (men ta inte bort den ursprungliga e-postunderdomänen om det finns någon).

>[!NOTE]
>
>En SMS-underdomän kan peka på en CNAME-post eftersom den antingen var en [befintlig underdomän](#sms-use-existing-subdomain) som delegerats till Adobe med [CNAME-metoden](../configuration/delegate-subdomain.md#cname-subdomain-setup) eller en [ny SMS-underdomän](#sms-configure-new-subdomain) som du konfigurerade.

När din begäran har hanterats av Adobe visas inte längre den odelegerade domänen på underdomänens lagersida.
