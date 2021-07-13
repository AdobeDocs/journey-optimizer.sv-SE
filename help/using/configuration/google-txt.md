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
feature: Applikationsinställningar
topic: Administrering
role: Admin
level: Intermediate
source-git-commit: 63de381ea3a87b9a77bc6f1643272597b50ed575
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 26%

---


# Lägga till en Google TXT-post i en underdomän

TXT-poster är en typ av DNS-poster som används för att tillhandahålla textinformation om en domän som kan läsas av externa källor.

För att säkerställa god levererbarhet och framgångsrik leverans av e-post till Gmail-adresser kan du med Customer Journeys Management lägga till särskilda TXT-poster för Google Site verification i dina underdomäner för att säkerställa att de verifieras.

>[!NOTE]
>
> Den här åtgärden kan bara utföras när en underdomän har statusen **[!UICONTROL Success]**. Mer information om underdomäners status finns i [det här avsnittet](access-subdomains.md).

Så här lägger du till en Google TXT-post till din underdomän:

1. Öppna underdomänen från menyn **[!UICONTROL Channels]** / **[!UICONTROL Subdomains]**.

1. I avsnittet Google-post anger du den verifieringskod som genererats i [G Suite Admin tools](https://support.google.com/a/answer/183895) och klickar sedan på **[!UICONTROL Save]**.

   ![](../assets/subdomain-google-txt.png)

1. När TXT-posten har lagts till måste den verifieras av Google. Navigera till administrationsverktygen för G Suite och starta sedan verifieringssteget.
