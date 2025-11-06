---
title: Kontrollera och skicka meddelanden i appen
description: Lär dig hur du kontrollerar och skickar ett meddelande i appen i Journey Optimizer
feature: In App
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, skapa, börja
exl-id: 9e9c235a-b78c-4669-af82-822b6f1e6fca
source-git-commit: 4847415fa33ebf1c21622ebf4faecafd4decc8d3
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 3%

---

# Kontrollera och skicka meddelanden i appen {#create-in-app}

## Förhandsgranska på enhet {#preview-device}

Om du vill få en smygtitt på meddelandet i appen innan det publiceras för alla användare kan du förhandsgranska det på en viss enhet. Med den här funktionen kan du säkerställa att meddelandet ser ut och fungerar som det ska på den valda enheten, vilket ger en bättre användarupplevelse för din målgrupp.

Gör så här:

1. Klicka på **[!UICONTROL Preview on device]**.

   ![](assets/in_app_create_6.png)

1. Klicka på **[!UICONTROL Connect to device]** i fönstret **[!UICONTROL Start]**.

1. Ange **[!UICONTROL Base URL]** för programmet och klicka på **[!UICONTROL Next]**.

   ![](assets/in_app_create_7.png)

1. Skanna QR-koden med enheten och ange den PIN-kod som visas.

Ditt meddelande i appen kan nu utlösas direkt på din enhet så att du kan förhandsgranska och granska meddelandet på en faktisk enhet.

## Förhandsgranska med testprofiler {#simulate}

När ditt meddelande i appen har definierats kan du använda testprofiler för att förhandsgranska det. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet med hjälp av testprofildata.

Det gör du genom att klicka på **[!UICONTROL Simulate content]** och sedan lägga till en testprofil för att kontrollera meddelandet med hjälp av testprofildata.

Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehåll finns i avsnittet [Innehållshantering](../content-management/preview-test.md).

## Granska och aktivera meddelanden i appen{#in-app-review}

>[!IMPORTANT]
>
> Om din kampanj omfattas av en godkännandeprincip måste du begära godkännande för att kunna skicka meddelanden i appen. [Läs mer](../test-approve/gs-approval.md)

När ditt meddelande i appen har skapats och dess innehåll har definierats och anpassats kan du granska och aktivera det.

Gör så här:

1. Använd knappen **[!UICONTROL Review to activate]** för att visa en sammanfattning av meddelandet.

   Sammanfattningen gör att du kan ändra kampanjen om det behövs och kontrollera om någon parameter är felaktig eller saknas.

   ![](assets/in_app_create_5.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]**.

Din kampanj är nu aktiverad. Det meddelande i appen som konfigurerats i kampanjen skickas omedelbart, eller på det angivna datumet.

När ni har skickat dem kan ni mäta effekten av era meddelanden i appen i kampanjrapporten eller reserapporten. Mer information om rapportering finns i [det här avsnittet](../reports/campaign-global-report-cja-inapp.md).

**Relaterade ämnen:**

* [Skapa ett meddelande i appen](create-in-app.md)
* [Design In-app-meddelande](design-in-app.md)
* [Rapport i appen](../reports/campaign-global-report-cja-inapp.md)
* [Konfiguration i appen](inapp-configuration.md)
