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
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 24%

---

# Lägga till en Google TXT-post i en underdomän

TXT-poster är en typ av DNS-poster som används för att tillhandahålla textinformation om en domän som kan läsas av externa källor.

För att säkerställa att e-post kan levereras och levereras till Gmail-adresser kan du med Customer Journeys Management lägga till särskilda TXT-poster för Google platsverifiering i dina underdomäner för att säkerställa att den verifieras.

>[!NOTE]
>
> Den här åtgärden kan bara utföras när en underdomän har **[!UICONTROL Success]** status. Mer information om underdomänernas status finns i [det här avsnittet](access-subdomains.md).

Så här lägger du till en Google TXT-post i din underdomän:

1. Öppna underdomänen från **[!UICONTROL Channels]** / **[!UICONTROL Subdomains]** -menyn.

1. Ange verifieringskoden som genererats i avsnittet Txt-post i Google [Administrationsverktyg för G Suite](https://support.google.com/a/answer/183895)och sedan klicka **[!UICONTROL Save]**.

   ![](../assets/subdomain-google-txt.png)

1. När TXT-posten har lagts till måste den verifieras av Google. Navigera till administrationsverktygen för G Suite och starta sedan verifieringssteget.
