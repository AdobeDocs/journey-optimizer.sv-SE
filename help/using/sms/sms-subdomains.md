---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera SMS-underdomäner
description: Lär dig konfigurera SMS-underdomäner med Journey Optimizer
role: Admin
level: Intermediate
keywords: SMS, underdomäner, konfiguration
exl-id: 08a546d1-060c-43e8-9eac-4c38945cc3e1
source-git-commit: c823d1a02ca9d24fc13eaeaba2b688249e61f767
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 0%

---

# Konfigurera SMS-underdomäner {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_sms_header"
>title="Delegera en SMS-underdomän"
>abstract="Du kommer att konfigurera din underdomän för SMS-användning. Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en annan underdomän."

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_sms"
>title="Delegera en SMS-underdomän"
>abstract="Du måste konfigurera en underdomän att använda för dina SMS-meddelanden, eftersom du behöver den här underdomänen för att skapa en SMS-yta. Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en ny underdomän."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/sms/sms-configuration.html#message-preset-sms" text="Skapa SMS-ytor"

>[!CONTEXTUALHELP]
>id="ajo_admin_config_sms_subdomain"
>title="Välj en SMS-underdomän"
>abstract="Om du vill kunna skapa en SMS-yta måste du kontrollera att du tidigare har konfigurerat minst en SMS-underdomän att välja från listan över underdomännamn."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/sms/sms-configuration.html#message-preset-sms" text="Skapa SMS-ytor"

För att kunna förkorta URL:er som läggs till i SMS-meddelanden måste du konfigurera den underdomän som du väljer när [skapa en SMS-yta](sms-configuration.md#message-preset-sms).

Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en annan underdomän. Läs mer om hur du delegerar underdomäner till Adobe in [det här avsnittet](../configuration/delegate-subdomain.md).

>[!CAUTION]
>
>SMS-underdomänskonfiguration är vanligt i alla miljöer. Därför:
>
>* Om du vill komma åt och redigera SMS-underdomäner måste du ha **[!UICONTROL Manage SMS Subdomains]** behörighet i produktionssandlådan.
>
> * Eventuella ändringar av en SMS-underdomän påverkar också produktionssandlådorna.


## Använd en befintlig underdomän {#sms-use-existing-subdomain}

Om du vill använda en underdomän som redan har delegerats till Adobe följer du stegen nedan.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL SMS configuration]** > **[!UICONTROL SMS subdomains]**.

   ![](assets/sms_access-subdomains.png)

1. Klicka på **[!UICONTROL Set up subdomain]**.

   ![](assets/sms_set-up-subdomain.png)

1. Välj **[!UICONTROL Use delegated subdomain]** från **[!UICONTROL Configuration type]** -avsnitt.

   ![](assets/sms_use-delegated-subdomain.png)

1. Ange det prefix som ska visas i SMS-URL:en.

   >[!NOTE]
   >
   >Endast alfanumeriska tecken och bindestreck tillåts.

1. Välj en delegerad underdomän i listan.

   >[!NOTE]
   >
   >Du kan inte välja en underdomän som redan används som SMS-underdomän.

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

   ![](assets/sms_prefix-and-subdomain.png)

   <!--Note that you cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your SMS messages, you will not be able to use 'marketing2.yourcompany.com'. However, multi-level subdomains being supported for SMS, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.-->

   >[!CAUTION]
   >
   >Om du väljer en domän som delegerats till Adobe med [CNAME-metod](../configuration/delegate-subdomain.md#cname-subdomain-delegation)måste du skapa DNS-posten på din värdplattform. För att skapa DNS-posten är processen densamma som när du konfigurerar en ny SMS-underdomän. Läs mer i [det här avsnittet](#sms-configure-new-subdomain).

1. Klicka på **[!UICONTROL Submit]**.

1. När den har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](../configuration/about-subdomain-delegation.md#access-delegated-subdomains).<!--Same statuses?-->

   >[!NOTE]
   >
   >Innan du kan använda den underdomänen för att skicka meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 4 timmar.<!--Learn more in [this section](delegate-subdomain.md#subdomain-validation).-->

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att skapa SMS-kanalsytor.

## Konfigurera en ny underdomän {#sms-configure-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_subdomain_dns"
>title="Generera matchande DNS-post"
>abstract="Om du vill konfigurera en ny SMS-underdomän måste du kopiera den Adobe-namnserverinformation som visas i Journey Optimizer-gränssnittet och klistra in den i din domänvärdslösning för att generera den matchande DNS-posten. När kontrollerna är slutförda kan underdomänen användas för att skapa SMS-ytor."

Följ stegen nedan för att konfigurera en ny underdomän.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL SMS configuration]** > **[!UICONTROL SMS subdomains]**.

1. Klicka på **[!UICONTROL Set up subdomain]**.

1. Välj **[!UICONTROL Add your own domain]** från **[!UICONTROL Configuration type]** -avsnitt.

   ![](assets/sms_add-your-own-subdomain.png)

1. Ange den underdomän som ska delegeras.

   >[!CAUTION]
   >
   >Du kan inte använda en befintlig SMS-underdomän.
   >
   >Versaler tillåts inte i underdomäner.

   Det är inte tillåtet att delegera en ogiltig underdomän till Adobe. Se till att du anger en giltig underdomän som ägs av din organisation, till exempel marketing.dincompany.com.

   >[!NOTE]
   >
   >Underdomäner på flera nivåer (av samma överordnade domän) stöds. Du kan till exempel använda sms.marketing.your.com.

1. Posten som ska placeras i dina DNS-servrar visas. Kopiera den här posten eller hämta en CSV-fil och navigera sedan till din värdlösning för domänen för att generera den matchande DNS-posten.

1. Kontrollera att DNS-posten har genererats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan &quot;Jag bekräftar ...&quot; och klickar sedan på **[!UICONTROL Submit]**.

   ![](assets/sms_add-your-own-subdomain-confirm.png)

   >[!NOTE]
   >
   >När du konfigurerar en ny SMS-underdomän pekar den alltid på en CNAME-post.

1. När underdomänsdelegeringen har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](../configuration/about-subdomain-delegation.md#access-delegated-subdomains).<!--Same statuses?-->

   >[!NOTE]
   >
   >Innan du kan använda den underdomänen för att skicka SMS-meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 4 timmar.<!--Learn more in [this section](#subdomain-validation).-->

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att skapa SMS-kanalsytor.

   Observera att underdomänen markeras som **[!UICONTROL Failed]** om du inte skapar valideringsposten i din värdlösning.
