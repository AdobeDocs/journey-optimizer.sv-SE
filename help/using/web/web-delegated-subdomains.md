---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera webbunderdomäner
description: Lär dig hur du konfigurerar webbunderdomäner med Journey Optimizer
role: Admin
level: Intermediate
keywords: webb, underdomäner, konfiguration
exl-id: 6503d9e6-6c6c-4a6d-ad3d-1d81eb3b4698
source-git-commit: b05c7e88c223af44cd2f7d10ea76c39359662cbd
workflow-type: tm+mt
source-wordcount: '357'
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

Om du lägger till innehåll från [Adobe Experience Manager Assets Essentials](../email/assets-essentials.md) måste du konfigurera den underdomän som ska användas för att publicera innehållet.

Du måste välja i listan över underdomäner som redan har delegerats till Adobe. Läs mer om hur du delegerar underdomäner till Adobe in [det här avsnittet](../configuration/delegate-subdomain.md).

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

1. Det prefix som ska visas i webb-URL:en läggs automatiskt till.

1. Om du vill ange den här underdomänen som standard väljer du motsvarande alternativ.

   ![](assets/web-subdomain-details-default.png)

   >[!NOTE]
   >
   >Endast **standard** underdomänen kommer att användas.

1. Klicka på **[!UICONTROL Submit]**. Underdomänen får **[!UICONTROL Success]** status. Det är klart att användas för era webbupplevelser.

1. The **[!UICONTROL Default]** emblem visas bredvid den underdomän som används som standard. Om du vill ändra standardunderdomänen väljer du **[!UICONTROL Set as default]** från **[!UICONTROL More actions]** -knapp bredvid önskad underdomän.

   >[!NOTE]
   >
   >Du kan ändra standardwebbunderdomänen, men bara en åt gången kan användas.

   ![](assets/web-subdomain-default.png)

   <!--Only a subdomain with the **[!UICONTROL Success]** status can be set as default.

    You can only delete a **[!UICONTROL Failed]** subdomain to clean up the list. To do so, select **[!UICONTROL Delete]** from the **[!UICONTROL More actions]** button next to the desired subdomain.

    You cannot delete a subdomain with the **[!UICONTROL Processing]** status.-->
