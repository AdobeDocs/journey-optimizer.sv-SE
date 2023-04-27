---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera webbunderdomäner
description: Lär dig hur du konfigurerar webbunderdomäner med Journey Optimizer
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
keywords: webb, underdomäner, konfiguration
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '366'
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
>title="Ange en standardunderdomän"
>abstract="Du kan skapa flera webbunderdomäner, men bara standardunderdomänen används. Du kan ändra standardwebbunderdomänen, men bara en åt gången kan användas."

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

1. Om du vill ange den här underdomänen som standard väljer du motsvarande alternativ.

   ![](assets/web-subdomain-details-default.png)

   >[!NOTE]
   >
   >Endast **standard** underdomänen kommer att användas. Du kan ändra standardwebbunderdomänen, men bara en åt gången kan användas.

1. Klicka på **[!UICONTROL Submit]**. Underdomänen får **[!UICONTROL Success]** status. Det är klart att användas för era webbupplevelser.

1. The **[!UICONTROL Default]** emblem visas bredvid den underdomän som används som standard. Om du vill ändra standardunderdomänen väljer du **[!UICONTROL Set as default]** från **[!UICONTROL More actions]** -knapp bredvid önskad underdomän.

   ![](assets/web-subdomain-default.png)

   <!--Only a subdomain with the **[!UICONTROL Success]** status can be set as default.-->

1. Du kan bara ta bort en **[!UICONTROL Failed]** underdomän för att rensa listan. Om du vill göra det väljer du **[!UICONTROL Delete]** från **[!UICONTROL More actions]** -knapp bredvid önskad underdomän.

<!--You cannot delete a subdomain with the **[!UICONTROL Processing]** status.-->

