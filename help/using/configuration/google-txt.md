---
solution: Journey Optimizer
product: journey optimizer
title: Lägga till en Google TXT-post i en underdomän
description: Lär dig hur du lägger till en Google TXT-post i en underdomän
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: subdomain, google, txt, record, gmail, deliverability
exl-id: 311eb2d1-e445-43e6-bc2c-c6288b637f47
source-git-commit: e89bec74f597185065b274d22740324a09e9319e
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 6%

---

# Lägga till en Google TXT-post i en underdomän {#google-txt-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_google"
>title="Google TXT-poster"
>abstract="För att e-post ska kunna levereras till Gmail-adresser kan du lägga till särskilda TXT-poster för verifiering av Google-webbplatser i din underdomän för att se till att den är verifierad."

TXT-poster är en typ av DNS-post som används för att tillhandahålla textinformation om en domän, som kan läsas av externa källor.

För att säkerställa optimal leverans och korrekt leverans av e-post till Gmail-adresser kan du med [!DNL Journey Optimizer] lägga till särskilda TXT-poster för verifiering av Google-webbplatser i din underdomän för att se till att den är verifierad.

>[!CAUTION]
>
> Den här åtgärden kan bara utföras när en underdomän har statusen **[!UICONTROL Success]**. Mer information om underdomäners status finns i [det här avsnittet](delegate-subdomain.md#access-delegated-subdomains).

Så här lägger du till en Google TXT-post i din underdomän:

1. Öppna underdomänen från menyn **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** > **[!UICONTROL Subdomains]**.

1. I avsnittet **[!UICONTROL Google txt record]** anger du den verifieringskod som har genererats från [Google Workspace](https://support.google.com/a/answer/183895){target="_blank"}<!--G Suite Admin tools--> och klickar sedan på **[!UICONTROL Save]**.

   ![](assets/subdomain-google-txt.png)

1. När TXT-posten har lagts till måste den verifieras av Google. Navigera till [Google Workspace](https://support.google.com/a/answer/183895){target="_blank"}<!--G Suite Admin tools--> och starta sedan verifieringssteget.

## Uppdatera en Google TXT-post {#update-google-txt-record}

Så här uppdaterar du en befintlig Google TXT-post:

1. Öppna underdomänen från menyn **[!UICONTROL Subdomains]**.

1. Rensa det befintliga värdet i fältet **[!UICONTROL Google txt record]** och klicka på **[!UICONTROL Save]**. Det här steget ersätter det tidigare Google TXT-postvärdet med en tom sträng.

1. Öppna nu samma underdomän igen och ange den nya verifieringskoden.

1. Klicka på **[!UICONTROL Save]** igen.

1. Verifiera den uppdaterade posten genom [Google Workspace](https://support.google.com/a/answer/183895){target="_blank"}.
