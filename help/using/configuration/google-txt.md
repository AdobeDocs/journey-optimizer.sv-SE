---
title: Lägga till en Google TXT-post i en underdomän
description: Lär dig hur du lägger till en Google TXT-post i en underdomän
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 311eb2d1-e445-43e6-bc2c-c6288b637f47
source-git-commit: d568480005d9b4aad5982c26184a5add0be6c83a
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 21%

---

# Lägga till en Google TXT-post i en underdomän {#google-txt-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_google"
>title="Google TXT-poster"
>abstract="För att e-post ska kunna levereras till Gmail-adresser kan du lägga till särskilda TXT-poster för verifiering av Google-webbplatser i din underdomän för att se till att den är verifierad."

TXT-poster är en typ av DNS-poster som används för att tillhandahålla textinformation om en domän som kan läsas av externa källor.

För att säkerställa optimal leverans och framgångsrik leverans av e-post till Gmail-adresser, [!DNL Journey Optimizer] Med kan du lägga till särskilda TXT-poster för verifiering av Google-webbplatser i din underdomän för att kontrollera att den är verifierad.

>[!CAUTION]
>
> Den här åtgärden kan bara utföras när en underdomän har **[!UICONTROL Success]** status. Mer information om underdomänernas status finns i [det här avsnittet](access-subdomains.md).

Så här lägger du till en Google TXT-post i din underdomän:

1. Öppna underdomänen från **[!UICONTROL Channels]** / **[!UICONTROL Subdomains]** -menyn.

1. I **[!UICONTROL Google txt record]** anger du verifieringskoden som genereras från [Google Workspace](https://support.google.com/a/answer/183895){target=&quot;_blank&quot;}<!--G Suite Admin tools-->och sedan klicka **[!UICONTROL Save]**.

   ![](assets/subdomain-google-txt.png)

1. När TXT-posten har lagts till måste den verifieras av Google. Navigera till [Google Workspace](https://support.google.com/a/answer/183895){target=&quot;_blank&quot;}<!--G Suite Admin tools-->startar du sedan verifieringssteget.
