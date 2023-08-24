---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera webbunderdomäner
description: Lär dig hur du konfigurerar webbunderdomäner med Journey Optimizer
role: Admin
level: Intermediate
keywords: webb, underdomäner, konfiguration
exl-id: 6503d9e6-6c6c-4a6d-ad3d-1d81eb3b4698
source-git-commit: 39953bb09a699ed4fd07db26a3f2e54f4e2cacd7
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Konfigurera webbunderdomäner {#web-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web_header"
>title="Delegera en webbunderdomän"
>abstract="Du kommer att konfigurera din underdomän för webbkanalsanvändning. Välj bland de underdomäner som redan har delegerats till Adobe."

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web"
>title="Delegera en webbunderdomän"
>abstract="Om du lägger till innehåll från Adobe Experience Manager Assets Essentials i dina webbupplevelser måste du konfigurera den underdomän som ska användas för att publicera det här innehållet. Välj bland de underdomäner som redan har delegerats till Adobe."

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web_default"
>title="Ange en webbunderdomän"
>abstract="Markera en underdomän i listan över underdomäner som har delegerats till Adobe. Du kan ange den här webbunderdomänen som standardunderdomän, men bara en standardunderdomän i taget kan användas."

Om du lägger till innehåll från [Adobe Experience Manager Assets Essentials](../content-management/assets-essentials.md) måste du konfigurera den underdomän som ska användas för att publicera innehållet.

För att göra det måste du välja i listan över underdomäner som redan har delegerats till Adobe. Läs mer om hur du delegerar underdomäner till Adobe in [det här avsnittet](../configuration/delegate-subdomain.md).

>[!CAUTION]
>
>Konfigurationen av webbunderdomäner är gemensam för alla miljöer. Därför:
>
>* Om du vill komma åt och redigera webbunderdomäner måste du ha **[!UICONTROL Manage Web Subdomains]** behörighet i produktionssandlådan.
>
> * Eventuella ändringar av en webbunderdomän påverkar också produktionssandlådorna.

Du kan skapa flera webbunderdomäner, men bara de **standard** underdomänen kommer att användas. Du kan ändra standardwebbunderdomänen, men bara en åt gången kan användas.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL Web configuration]** > **[!UICONTROL Web subdomains]**.

   ![](assets/web-access-subdomains.png)

1. Klicka på **[!UICONTROL Set up subdomain]**.

1. Välj en delegerad underdomän i listan.

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

1. The **[!UICONTROL Default]** emblem visas bredvid den underdomän som används som standard. Om du vill ändra standardunderdomänen väljer du **[!UICONTROL Set as default]** från **[!UICONTROL More actions]** -knapp intill önskad underdomän.

   ![](assets/web-subdomain-default.png)

   >[!NOTE]
   >
   >Du kan ändra standardwebbunderdomänen, men bara en åt gången kan användas.

   <!--Only a subdomain with the **[!UICONTROL Success]** status can be set as default.

    You cannot delete a subdomain with the **[!UICONTROL Processing]** status.-->
