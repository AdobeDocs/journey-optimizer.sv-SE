---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera webbunderdomäner
description: Lär dig hur du konfigurerar webbunderdomäner med Journey Optimizer
role: Admin
feature: Web Channel, Subdomains
level: Experienced
keywords: webb, underdomäner, konfiguration
exl-id: 6e00466d-4ce5-4d80-89ff-c7331a5ab158
source-git-commit: bfb9e797757a96b1e39736f532ee9308f87bb71f
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 0%

---

# Konfigurera webbunderdomäner {#web-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web_header"
>title="Delegera en webbunderdomän"
>abstract="Du kommer att konfigurera din underdomän för webbkanalsanvändning. Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en annan underdomän."

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web"
>title="Delegera en webbunderdomän"
>abstract="Om du lägger till innehåll från Adobe Experience Manager Assets i dina webbupplevelser måste du konfigurera den underdomän som ska användas för att publicera det här innehållet. Välj bland de underdomäner som redan har delegerats till Adobe eller konfigurera en ny underdomän."

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web_default"
>title="Ange en webbunderdomän"
>abstract="Markera en underdomän i listan över underdomäner som har delegerats till Adobe. Du kan ange den här webbunderdomänen som standardunderdomän, men bara en standardunderdomän i taget kan användas."

Om du lägger till innehåll från [Adobe Experience Manager Assets](../content-management/assets.md) måste du konfigurera den underdomän som ska användas för att publicera innehållet.

Du kan använda en underdomän som redan har delegerats till Adobe eller konfigurera en annan underdomän. Läs mer om hur du delegerar underdomäner till Adobe in [det här avsnittet](../configuration/delegate-subdomain.md).

>[!CAUTION]
>
>Konfigurationen av webbunderdomäner är gemensam för alla miljöer. Därför:
>
>* Om du vill komma åt och redigera webbunderdomäner måste du ha **[!UICONTROL Manage Web Subdomains]** behörighet i produktionssandlådan.
>
> * Eventuella ändringar av en webbunderdomän påverkar också produktionssandlådorna.

Du kan skapa flera webbunderdomäner, men bara de **standard** underdomänen kommer att användas. Du kan ändra standardwebbunderdomänen, men bara en åt gången kan användas.

## Få åtkomst till och hantera webbunderdomäner {#access-web-subdomains}

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL Web configuration]** > **[!UICONTROL Web subdomains]**. Alla underdomäner som har konfigurerats med den aktuella sandlådan visas.

   ![](assets/web-access-subdomains.png)

1. Du kan filtrera efter användare som delegerat varje underdomän eller en av delegeringsstatusen (**[!UICONTROL Draft]**, **[!UICONTROL Processing]**, **[!UICONTROL Success]** eller **[!UICONTROL Failed]**).

   ![](assets/web-filter-subdomains.png)

1. The **[!UICONTROL Default]** emblem visas bredvid den underdomän som används som standard. Om du vill ändra standardunderdomänen väljer du **[!UICONTROL Set as default]** från **[!UICONTROL More actions]** -knapp intill önskad underdomän.

   ![](assets/web-subdomain-default.png)

   >[!NOTE]
   >
   >Du kan ändra standardwebbunderdomänen, men bara en åt gången kan användas.

## Använd en befintlig underdomän {#web-use-existing-subdomain}

Om du vill använda en underdomän som redan har delegerats till Adobe följer du stegen nedan.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL Web configuration]** > **[!UICONTROL Web subdomains]**.

1. Klicka på **[!UICONTROL Set up subdomain]**.

1. Välj **[!UICONTROL Use delegated subdomain]** från **[!UICONTROL Configuration type]** och välj en delegerad underdomän i listan.

   ![](assets/web-subdomain-details.png)

   >[!NOTE]
   >
   >Du kan inte välja en underdomän som redan används som webbunderdomän.

1. Det prefix som ska visas i webb-URL:en läggs automatiskt till. Du kan inte ändra den.

1. Om du vill ange den här underdomänen som standard väljer du motsvarande alternativ.

   ![](assets/web-subdomain-details-default.png)

   >[!NOTE]
   >
   >Endast **standard** underdomänen kommer att användas.

1. Klicka på **[!UICONTROL Submit]**. Underdomänen får **[!UICONTROL Success]** status. Det är klart att användas för era webbupplevelser.

   >[!NOTE]
   >
   >I mycket sällsynta fall kan en underdomänskonfiguration misslyckas. I det här fallet kan du ta bort **[!UICONTROL Failed]** för att rensa listan med **[!UICONTROL Delete]** från **[!UICONTROL More actions]** -ikon.

## Konfigurera en ny underdomän {#web-configure-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_web_subdomain_dns"
>title="Generera matchande DNS-post"
>abstract="Om du vill konfigurera en ny webbunderdomän måste du kopiera den Adobe-namnserverinformation som visas i Journey Optimizer-gränssnittet och klistra in den i din domänvärdslösning för att generera den matchande DNS-posten. När kontrollen är klar kan underdomänen användas för att publicera innehåll som kommer från Adobe Experience Manager Assets-biblioteket."

Följ stegen nedan för att konfigurera en ny underdomän.

>[!NOTE]
>
>Som standard [!DNL Journey Optimizer] Med kan du delegera upp till 10 underdomäner totalt (som omfattar både e-post och webbkanaler). Beroende på ditt licensavtal kan du dock delegera upp till 100 underdomäner. Kontakta Adobe och läs mer om hur många underdomäner du har rätt till.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL web configuration]** > **[!UICONTROL web subdomains]**.

1. Klicka på **[!UICONTROL Set up subdomain]**.

1. Välj **[!UICONTROL Add your own domain]** från **[!UICONTROL Configuration type]** -avsnitt.

1. Ange den underdomän som ska delegeras.

   >[!CAUTION]
   >
   >Du kan inte använda en befintlig webbunderdomän.
   >
   >Versaler tillåts inte i underdomäner.

   ![](assets/web-add-your-own-domain.png)

   Det är inte tillåtet att delegera en ogiltig underdomän till Adobe. Se till att du anger en giltig underdomän som ägs av din organisation, till exempel marketing.yourcompany.com.

   >[!NOTE]
   >
   >Underdomäner på flera nivåer (av samma överordnade domän) stöds. Du kan till exempel använda &#39;web.marketing.your.com&#39;.

1. Om du vill ange den här underdomänen som standard väljer du motsvarande alternativ.

   >[!NOTE]
   >
   >Endast **standard** underdomänen kommer att användas.

1. Posten som ska placeras i dina DNS-servrar visas. Kopiera den här posten eller hämta en CSV-fil och navigera sedan till din värdlösning för domänen för att generera den matchande DNS-posten.

1. Kontrollera att DNS-posten har genererats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan &quot;Jag bekräftar ...&quot; och klickar sedan på **[!UICONTROL Submit]**.

   ![](assets/web-add-your-own-domain-confirm.png)

   >[!NOTE]
   >
   >När du konfigurerar en ny webbunderdomän pekar den alltid på en CNAME-post.

1. När underdomänsdelegeringen har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](../configuration/about-subdomain-delegation.md#access-delegated-subdomains).<!--Same statuses?-->

   >[!NOTE]
   >
   >Innan du kan använda den underdomänen för att skicka webbmeddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 4 timmar.

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att skapa webbkanalsytor.

   Observera att underdomänen markeras som **[!UICONTROL Failed]** om du inte skapar valideringsposten i din värdlösning.

<!--
Only a subdomain with the **[!UICONTROL Success]** status can be set as default.
You cannot delete a subdomain with the **[!UICONTROL Processing]** status.
-->
