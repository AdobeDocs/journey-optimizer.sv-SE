---
title: Delegera underdomäner
description: Lär dig hur du delegerar dina underdomäner
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 311eb2d1-e445-43e6-bc2c-c6288b637f47
source-git-commit: bbc2adabac63ffb813ea2630f29aec552fc3f4df
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 27%

---

# Lägga till en Google TXT-post i en underdomän {#google-txt-record}

TXT-poster är en typ av DNS-poster som används för att tillhandahålla textinformation om en domän som kan läsas av externa källor.

För att säkerställa god levererbarhet och framgångsrik leverans av e-post till Gmail-adresser, [!DNL Journey Optimizer] I kan du lägga till särskilda TXT-poster för verifiering av Google-webbplatser i dina underdomäner för att säkerställa att de verifieras.

>[!CAUTION]
>
> Den här åtgärden kan bara utföras när en underdomän har **[!UICONTROL Success]** status. Mer information om underdomänernas status finns i [det här avsnittet](access-subdomains.md).

Så här lägger du till en Google TXT-post i din underdomän:

1. Öppna underdomänen från **[!UICONTROL Channels]** / **[!UICONTROL Subdomains]** -menyn.

1. I **[!UICONTROL Google txt record]** anger du verifieringskoden som genereras från [Google Workspace](https://support.google.com/a/answer/183895){target=&quot;_blank&quot;}<!--G Suite Admin tools-->och sedan klicka **[!UICONTROL Save]**.

   ![](../assets/subdomain-google-txt.png)

1. När TXT-posten har lagts till måste den verifieras av Google. Navigera till [Google Workspace](https://support.google.com/a/answer/183895){target=&quot;_blank&quot;}<!--G Suite Admin tools-->startar du sedan verifieringssteget.
