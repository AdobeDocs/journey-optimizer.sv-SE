---
title: Förhandsgranska ditt innehåll
description: Lär dig hur du förhandsgranskar innehåll.
feature: Preview, Proofs
role: User
level: Beginner
exl-id: 6477270c-0309-411a-8254-c7ffc4419492
source-git-commit: bf0a6fa496a08348be16896a7f2313882eb97c06
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 2%

---

# Förhandsgranska innehåll med testprofiler {#preview}

<!--## Preview your content {#preview-content}-->

När [testprofiler](test-profiles.md) har definierats kan du förhandsgranska innehållet.

>[!NOTE]
>
>I [!DNL Journey optimizer] kan du också testa olika varianter av ditt innehåll genom att förhandsgranska det och skicka korrektur med exempelindata som har överförts från en CSV-/JSON-fil, eller lagts till manuellt. [Lär dig hur du testar innehåll med exempelindata](../test-approve/simulate-sample-input.md)

Så här förhandsgranskar du ditt innehåll med testprofiler:

1. Klicka på knappen **[!UICONTROL Simulate content]** på skärmen Redigera innehåll i ditt meddelande eller i e-post-Designer.

1. Välj en testprofil. Du kan kontrollera de värden som är tillgängliga i kolumnerna. Använd höger-/vänsterpilarna för att bläddra bland data.

   ![](../email/assets/preview-select-profile.png)

   >[!NOTE]
   >
   >Om du vill lägga till fler testprofiler väljer du **[!UICONTROL Manage test profiles]**. [Läs mer](test-profiles.md)

1. Klicka på ikonen **[!UICONTROL Select data]** ovanför listan för att lägga till eller ta bort kolumner.

   I slutet av listan visas personaliseringsfält som är specifika för det aktuella meddelandet. I det här exemplet är profilens ort, förnamn och efternamn. Markera de fälten och se till att dessa värden är ifyllda i testprofilerna.

   ![](../email/assets/preview-select-data.png)

1. I meddelandeförhandsgranskningen ersätts anpassade element med de valda testprofildata. För det här meddelandet är till exempel både e-postinnehåll och e-postämne personliga:

   ![](../email/assets/preview-test-profile.png)

1. Välj andra testprofiler om du vill förhandsgranska din e-post för varje variant av meddelandet.

>[!NOTE]
>
>Om det finns ett fel i konfigurationsinformationen klickar du på knappen **[!UICONTROL View configuration details]**. [Läs mer](../email/surface-personalization.md#check-configuration)

När ni skapar kodbaserade upplevelser kan ni förhandsgranska ert personaliserade innehåll direkt i webbläsaren eller på era mobila enheter för att få en simulering i verkligheten. [Läs mer](../code-based/test-code-based.md#preview-on-device)

