---
title: Skicka e-postkorrektur
description: Lär dig hur du skickar e-postkorrektur.
feature: Preview, Proofs
role: User
level: Beginner
exl-id: e742c04e-2987-4466-84af-bdaf4d714552
source-git-commit: 80935cc31ef88a322c2dd555fc8998935c6e5621
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# Skicka e-postkorrektur {#send-proofs}

Ett korrektur är ett specifikt meddelande som gör att du kan testa ett meddelande innan det skickas till huvudmålgruppen. Mottagarna av beviset ansvarar för att godkänna meddelandet: rendering, innehåll, personaliseringsinställningar, konfiguration.

Observera att [!DNL Journey optimizer] även låter dig testa olika varianter av ditt innehåll genom att förhandsgranska det och skicka korrektur med exempelindata som överförts från en CSV-/JSON-fil, eller läggs till manuellt. [Lär dig hur du testar innehåll med exempelindata](../test-approve/simulate-sample-input.md)

>[!PREREQUISITES]
>
>Om du vill skicka korrektur måste du ha behörighet **Godkänn och publicera** för den specifika resurs (kampanj eller resa) som är associerad med e-postmeddelandet. Om du dessutom vill skicka korrektur på en resa måste du ha behörighet **Publiceringsresa**. [Läs mer om behörigheter](../administration/ootb-permissions.md).


Om du vill skicka e-postkorrektur måste du först välja [testprofiler](test-profiles.md). Följ sedan dessa steg:

1. Klicka på knappen **[!UICONTROL Send proof]** på skärmen **[!UICONTROL Simulate]**.

   ![](../email/assets/send-proof-button.png)

1. I fönstret **[!UICONTROL Send proof]** skriver du in mottagarens e-postadress och klickar på **[!UICONTROL Add]** för att skicka korrekturet till dig själv eller medlemmar i din organisation.

   Observera att du kan lägga till upp till tio mottagare för korrekturleveransen.

   ![](../email/assets/send-proof-add.png)

1. Välj de **Testprofiler** som ska användas för att anpassa meddelandeinnehållet.

   Varje mottagare av korrekturet får lika många meddelanden som antalet valda testprofiler. Om du till exempel har lagt till fem e-postmeddelanden till mottagare och valt tio testprofiler, skickar du femtio korrekturmeddelanden och varje mottagare får tio av dem.

1. Du kan vid behov lägga till ett prefix till korrekturens ämnesrad. Endast alfanumeriska tecken och specialtecken som . - _ ( ) [ ] tillåts som prefix till ämnesraden.

1. Klicka på **[!UICONTROL Send proof]**.

   ![](../email/assets/send-proof-select.png)

1. Klicka på knappen **[!UICONTROL View proofs]** på skärmen **[!UICONTROL Simulate]** för att kontrollera status.

   ![](../email/assets/send-proof-view.png)

Vi rekommenderar att du skickar korrektur efter varje ändring av meddelandeinnehållet.

>[!NOTE]
>
>I det skickade korrekturet är länken till spegelsidan inte aktiv. Den aktiveras endast i de slutliga meddelandena.
