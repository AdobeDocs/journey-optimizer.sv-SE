---
title: Konfiguration av landningssida
description: Lär dig hur du konfigurerar miljön för att skapa och använda landningssidor med Journey Optimizer
role: Admin
level: Intermediate
exl-id: 7cf1f083-bef0-40b5-8ddd-920a9d108eca
source-git-commit: 62d8f4b0caa4ed74991e92475392c3278bdf5317
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 1%

---

# Konfigurera landningssidor {#lp-configuration}

## Konfigurera underdomäner för landningssidor {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_config_lp_subdomain"
>title="Skapa en förinställning för landningssida"
>abstract="Om du vill kunna skapa en förinställning för landningssida måste du kontrollera att du tidigare har konfigurerat minst en underdomän för landningssida att välja från listan med underdomännamn."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/lp-configuration.html#lp-create-preset" text="Skapa förinställningar för landningssidor"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_lp"
>title="Delegera en underdomän för landningssida"
>abstract="Du måste konfigurera en underdomän att använda för dina landningssidor, eftersom du behöver den här underdomänen för att skapa en förinställning för landningssidor. Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en ny underdomän."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/lp-configuration.html#lp-create-preset" text="Skapa förinställningar för landningssidor"

För att kunna [skapa förinställningar för landningssidor](#lp-create-preset)måste du konfigurera de underdomäner som du ska använda för dina landningssidor.

Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en annan underdomän. Läs mer om hur du delegerar underdomäner till Adobe in [det här avsnittet](delegate-subdomain.md).

### Använd en befintlig underdomän {#lp-use-existing-subdomain}

Om du vill använda en underdomän som redan har delegerats till Adobe följer du stegen nedan.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL Email configuration]** > **[!UICONTROL Landing page subdomains]**.

   ![](assets/lp_access-subdomains.png)

1. Klicka på **[!UICONTROL Set up subdomain]**.

   ![](assets/lp_set-up-subdomain.png)

1. Välj **[!UICONTROL Use delegated domain]** från **[!UICONTROL Configuration type]** -avsnitt.

   ![](assets/lp_use-delegated-subdomain.png)

1. Ange det prefix som ska visas i landningssidans URL.

   >[!NOTE]
   >
   >Endast alfanumeriska tecken och bindestreck tillåts.

1. Välj en delegerad underdomän i listan.

   >[!NOTE]
   >
   >Du kan inte välja en underdomän som redan används som underdomän för landningssida.

   ![](assets/lp_prefix-and-subdomain.png)

   >[!CAUTION]
   >
   >Om du väljer en domän som delegerats till Adobe med [CNAME-metod](delegate-subdomain.md#cname-subdomain-delegation)måste du skapa DNS-posten på din värdplattform. För att generera DNS-posten är processen densamma som när du konfigurerar en ny underdomän för landningssida. Läs mer i [det här avsnittet](#lp-configure-new-subdomain).

1. Klicka på **[!UICONTROL Submit]**.

1. När den har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](access-subdomains.md).<!--Same statuses?-->

   ![](assets/lp_subdomain-processing.png)

   >[!NOTE]
   >
   >Innan du kan använda den underdomänen för att skicka meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 4 timmar.<!--Learn more in [this section](delegate-subdomain.md#subdomain-validation).-->

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att skapa förinställningar för landningssidor.

### Konfigurera en ny underdomän {#lp-configure-new-subdomain}

Följ stegen nedan för att konfigurera en ny underdomän.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL Email configuration]** > **[!UICONTROL Landing page subdomains]**.

1. Klicka på **[!UICONTROL Set up subdomain]**.

1. Välj **[!UICONTROL Add your own domain]** från **[!UICONTROL Configuration type]** -avsnitt.

   ![](assets/lp_add-your-own-subdomain.png)

1. Ange den underdomän som ska delegeras.

   >[!CAUTION]
   >
   >Du kan inte använda en befintlig underdomän för landningssida.

   Det är inte tillåtet att delegera en ogiltig underdomän till Adobe. Se till att du anger en giltig underdomän som ägs av din organisation, till exempel marketing.dincompany.com.

   Underdomäner på flera nivåer, till exempel &#39;email.marketing.your.com&#39;, stöds för närvarande inte.

1. Posten som ska placeras i dina DNS-servrar visas. Kopiera den här posten eller hämta en CSV-fil och navigera sedan till din värdlösning för domänen för att generera den matchande DNS-posten.

1. Kontrollera att DNS-posten har genererats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan &quot;Jag bekräftar ...&quot; och klickar sedan på **[!UICONTROL Submit]**.

   ![](assets/lp_add-your-own-subdomain-confirm.png)

   >[!NOTE]
   >
   >När du konfigurerar en ny underdomän för landningssida pekar den alltid på en CNAME-post.

1. När underdomänsdelegeringen har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](access-subdomains.md).<!--Same statuses?-->

   >[!NOTE]
   >
   >Innan du kan använda den underdomänen för att skicka meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 4 timmar.<!--Learn more in [this section](#subdomain-validation).-->

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att skapa förinställningar för landningssidor.

   Observera att underdomänen markeras som **[!UICONTROL Failed]** om du inte skapar valideringsposten i din värdlösning.

## Definiera förinställningar för landningssidor {#lp-define-preset}

När [skapa en landningssida](../landing-pages/create-lp.md#create-a-lp)måste du välja en förinställning för landningssidan för att kunna bygga landningssidan och använda den **[!DNL Journey Optimizer]**.

### Åtkomst till förinställningar för landningssidor {#lp-presets}

Följ stegen nedan för att få tillgång till förinställningarna för landningssidan.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** -menyn.

1. Välj **[!UICONTROL Branding]** > **[!UICONTROL Landing page presets]**.

   ![](assets/lp_presets-access.png)

1. Klicka på en förinställd etikett för att komma åt förinställningsinformationen för landningssidan.

   ![](assets/lp_preset-details.png)

### Skapa en förinställning för landningssida {#lp-create-preset}

Följ stegen nedan för att skapa en förinställning för landningssidan.

>[!NOTE]
>
>För att kunna skapa en förinställning måste du kontrollera att du tidigare har konfigurerat minst en underdomän för landningssida. [Lär dig mer](#lp-subdomains)

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL Branding]** > **[!UICONTROL Landing page presets]**.

1. Välj **[!UICONTROL Create landing page preset]**.

   ![](assets/lp_create-preset-temp.png)

1. Ange ett namn och en beskrivning för förinställningen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

1. Välj en underdomän för landningssida i listrutan.

   ![](assets/lp_preset-subdomain.png)

   >[!NOTE]
   >
   >Om du vill kunna välja en underdomän kontrollerar du att du tidigare har konfigurerat minst en underdomän för landningssida. [Lär dig mer](#lp-subdomains)

   De inställningar som motsvarar den valda underdomänens visning.

1. Om du vill välja landningssidans underdomän som spårnings-URL kontrollerar du **[!UICONTROL Same as landing page subdomain]** alternativ. [Läs mer om spårning](../design/message-tracking.md)

   ![](assets/lp_preset-subdomain-settings-same.png)

   Om till exempel landningssidans URL är pages.mail.luma.com och spårnings-URL:en är data.mail.luma.com kan du välja pages.mail.luma.com som ska användas som spårningsunderdomän.

1. Klicka **[!UICONTROL Submit]** för att bekräfta att förinställningen för landningssidan har skapats. Du kan också spara förinställningen som utkast och återuppta konfigurationen senare.

   ![](assets/lp_preset-subdomain-settings-submit.png)

1. När förinställningen för landningssidan har skapats visas den i listan med **[!UICONTROL Active]** status. Den är klar att användas för dina landningssidor.

   ![](assets/lp-preset-active-temp.png)

Du är nu redo att [skapa landningssidor](../landing-pages/create-lp.md) in [!DNL Journey Optimizer].

>[!NOTE]
>
>Lär dig hur du skapar meddelandeförinställningar för push-meddelanden och e-postmeddelanden i [det här avsnittet](message-presets.md).

**Relaterade ämnen**:

* [Kom igång med landningssidor](../landing-pages/get-started-lp.md)
* [Skapa en landningssida](../landing-pages/create-lp.md#create-a-lp)
