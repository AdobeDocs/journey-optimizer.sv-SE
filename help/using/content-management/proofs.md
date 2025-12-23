---
title: Skicka e-postkorrektur
description: Lär dig hur du skickar e-postkorrektur.
feature: Preview, Proofs
role: User
level: Beginner
exl-id: e742c04e-2987-4466-84af-bdaf4d714552
source-git-commit: f874456748a8bd7fce69c7ad2a7e69380d5336a6
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# Skicka korrektur med testprofildata {#send-proofs}

Ett korrektur är ett specifikt meddelande som gör att du kan testa ett meddelande innan det skickas till huvudmålgruppen. Mottagarna av beviset ansvarar för att godkänna meddelandet: rendering, innehåll, personaliseringsinställningar, konfiguration.

>[!NOTE]
>
>I [!DNL Journey Optimizer] kan du också testa olika varianter av ditt innehåll genom att förhandsgranska det och skicka korrektur med exempelindata som har överförts från en CSV-/JSON-fil, eller lagts till manuellt. [Lär dig hur du simulerar innehållsvariationer](../test-approve/simulate-sample-input.md)

## Måste läsas {#must-read}

**Regler för frekvensbegränsning** - Alla befintliga regler för frekvensbegränsning gäller för korrektur. Om du har angett [regler för frekvensbegränsning](../conflict-prioritization/channel-capping.md) (t.ex. högsta antal tillåtna överföringar per profil) gäller dessa gränser även när du skickar korrektur. Om en testprofil redan har nått gränsvärdet för frekvens visas korrektur som färdigt, men inget e-postmeddelande skickas. Vid upprepad testning bör du överväga att använda unika testprofiler eller justera frekvenshöljen för korrekturscenarier efter behov.

**Spegelsida** - I det skickade korrekturet är länken till spegelsidan inte aktiv. Den aktiveras endast i de slutliga meddelandena.

**Assets** - Assets och bilder har särskilda tillgänglighetsregler:

* Assets/Bilder är tillgängliga i levererat innehåll eller korrekturinnehåll i upp till 2 år (730 dagar) sedan de publicerades första gången i ett fragment- eller textbundet meddelande.
* Återpublicering krävs efter denna förfalloperiod (när som helst efter 730 dagar) för att hålla dem tillgängliga i ytterligare två år.
* Om publiceringen görs inom 730 dagar efter den första publikationen kommer inte förfallodagen för mediefiler/bilder att förlängas till de kommande 730 dagarna.

## Skicka korrektur {#send-proofs-steps}

Om du vill skicka e-postkorrektur med testprofildata måste du först välja [testprofiler](test-profiles.md). Följ sedan dessa steg:

1. Klicka på knappen **[!UICONTROL Simulate]** på skärmen **[!UICONTROL Send proof]**.

   ![Skicka korrekturknapp på simuleringsskärmen](../email/assets/send-proof-button.png)

1. I fönstret **[!UICONTROL Send proof]** skriver du in mottagarens e-postadress och klickar på **[!UICONTROL Add]** för att skicka korrekturet till dig själv eller medlemmar i organisationen.

   Observera att du kan lägga till upp till tio mottagare för korrekturleveransen.

   ![Lägg till mottagare i korrekturleveransen](../email/assets/send-proof-add.png)

1. Välj de **Testprofiler** som ska användas för att anpassa meddelandeinnehållet.

   Varje mottagare av korrekturet får lika många meddelanden som antalet valda testprofiler. Om du till exempel har lagt till fem e-postmeddelanden till mottagare och valt tio testprofiler, kommer du att skicka femtio korrekturmeddelanden. Varje mottagare får tio av dem.

1. Du kan vid behov lägga till ett prefix till korrekturens ämnesrad. Endast alfanumeriska tecken och specialtecken som . - _ ( ) [ ] tillåts som prefix till ämnesraden.

1. Klicka på **[!UICONTROL Send proof]**.

   ![Välj testprofiler och skicka korrekturet](../email/assets/send-proof-select.png)

1. Klicka på knappen **[!UICONTROL Simulate]** på skärmen **[!UICONTROL View proofs]** för att kontrollera status.

   ![Visa korrekturknappen för att kontrollera leveransstatus](../email/assets/send-proof-view.png)

Vi rekommenderar att du skickar korrektur efter varje ändring av meddelandeinnehållet.
