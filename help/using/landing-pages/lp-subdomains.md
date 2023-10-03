---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera underdomäner för landningssidor
description: Lär dig konfigurera underdomäner för landningssidor med Journey Optimizer
role: Admin
level: Intermediate
keywords: landning, landningssida, underdomäner, konfiguration
exl-id: dd1af8dc-3920-46cb-ae4d-a8f4d4c26e89
source-git-commit: ad4bc06d17727c6c8476344f3c1028fd9e717a15
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 0%

---

# Konfigurera underdomäner för landningssidor {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_lp_header"
>title="Delegera en underdomän för landningssida"
>abstract="Du kommer att konfigurera din underdomän för att använda en landningssida. Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en annan underdomän."

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_lp"
>title="Delegera en underdomän för landningssida"
>abstract="Du måste konfigurera en underdomän att använda för dina landningssidor, eftersom du behöver den här underdomänen för att skapa en förinställning för landningssidor. Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en ny underdomän."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/lp-configuration/lp-presets.html#lp-create-preset" text="Skapa förinställningar för landningssidor"

>[!CONTEXTUALHELP]
>id="ajo_admin_config_lp_subdomain"
>title="Skapa en förinställning för landningssida"
>abstract="Om du vill kunna skapa en förinställning för landningssida måste du kontrollera att du tidigare har konfigurerat minst en underdomän för landningssida att välja från listan med underdomännamn."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/lp-configuration/lp-presets.html#lp-create-preset" text="Skapa förinställningar för landningssidor"

För att kunna [skapa förinställningar för landningssidor](lp-presets.md)måste du konfigurera de underdomäner som du ska använda för dina landningssidor.

Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en annan underdomän. Läs mer om hur du delegerar underdomäner till Adobe in [det här avsnittet](../configuration/delegate-subdomain.md).

>[!CAUTION]
>
>Konfigurationen av deldomäner för landningssidor är gemensam för alla miljöer. Därför:
>
>* Om du vill komma åt och redigera underdomäner för landningssidor måste du ha **[!UICONTROL Manage Landing Page Subdomains]** behörighet i produktionssandlådan.
>
> * Alla ändringar av en underdomän för landningssidor påverkar också produktionssandlådorna.

## Använd en befintlig underdomän {#lp-use-existing-subdomain}

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

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

   ![](assets/lp_prefix-and-subdomain.png)

   Observera att du inte kan använda flera delegerade underdomäner för samma överordnade domän. Om till exempel&quot;marketing1.your.company.com&quot; redan har delegerats till Adobe för dina landningssidor kommer du inte att kunna använda&quot;marketing2.your.company.com&quot;. Om det finns stöd för underdomäner på flera nivåer för landningssidor kan du fortsätta med en underdomän till marketing1.yourcompany.com (till exempel email.marketing1.your.com) eller en annan överordnad domän.

   >[!CAUTION]
   >
   >Om du väljer en domän som delegerats till Adobe med [CNAME-metod](../configuration/delegate-subdomain.md#cname-subdomain-delegation)måste du skapa DNS-posten på din värdplattform. För att generera DNS-posten är processen densamma som när du konfigurerar en ny underdomän för landningssida. Läs mer i [det här avsnittet](#lp-configure-new-subdomain).

1. Klicka på **[!UICONTROL Submit]**.

1. När den har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](../configuration/about-subdomain-delegation.md#access-delegated-subdomains).<!--Same statuses?-->

   ![](assets/lp_subdomain-processing.png)

   >[!NOTE]
   >
   >Innan du kan använda den underdomänen för att skicka meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 4 timmar.<!--Learn more in [this section](delegate-subdomain.md#subdomain-validation).-->

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att skapa förinställningar för landningssidor.

## Konfigurera en ny underdomän {#lp-configure-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_lp_subdomain_dns"
>title="Generera matchande DNS-post"
>abstract="Om du vill konfigurera en ny underdomän för landningssidan måste du kopiera den Adobe-namnserverinformation som visas i Journey Optimizer-gränssnittet och klistra in den i din värdlösning för domäner för att generera matchande DNS-post. När kontrollerna är slutförda kan underdomänen användas för att skapa förinställningar för landningssidor."

Följ stegen nedan för att konfigurera en ny underdomän.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL Email configuration]** > **[!UICONTROL Landing page subdomains]**.

1. Klicka på **[!UICONTROL Set up subdomain]**.

1. Välj **[!UICONTROL Add your own domain]** från **[!UICONTROL Configuration type]** -avsnitt.

   ![](assets/lp_add-your-own-subdomain.png)

1. Ange den underdomän som ska delegeras.

   >[!CAUTION]
   >
   >Du kan inte använda en befintlig underdomän för landningssida.
   >
   >Versaler tillåts inte i underdomäner.

   Det är inte tillåtet att delegera en ogiltig underdomän till Adobe. Se till att du anger en giltig underdomän som ägs av din organisation, till exempel marketing.yourcompany.com.

   >[!NOTE]
   >
   >För landningssidor stöds underdomäner på flera nivåer. Du kan till exempel använda&quot;email.marketing.your.com&quot;.

1. Posten som ska placeras i dina DNS-servrar visas. Kopiera den här posten eller hämta en CSV-fil och navigera sedan till din värdlösning för domänen för att generera den matchande DNS-posten.

1. Kontrollera att DNS-posten har genererats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan &quot;Jag bekräftar ...&quot; och klickar sedan på **[!UICONTROL Submit]**.

   ![](assets/lp_add-your-own-subdomain-confirm.png)

   >[!NOTE]
   >
   >När du konfigurerar en ny underdomän för landningssida pekar den alltid på en CNAME-post.

1. När underdomänsdelegeringen har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](../configuration/about-subdomain-delegation.md#access-delegated-subdomains).<!--Same statuses?-->

   >[!NOTE]
   >
   >Innan du kan använda den underdomänen för dina landningssidor måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 4 timmar.<!--Learn more in [this section](#subdomain-validation).-->

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att skapa förinställningar för landningssidor.

   Observera att underdomänen markeras som **[!UICONTROL Failed]** om du inte skapar valideringsposten i din värdlösning.
