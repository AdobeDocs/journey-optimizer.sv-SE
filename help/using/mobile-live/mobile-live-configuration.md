---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera aktivitetskanalen Live
description: Lär dig hur du konfigurerar miljön för att skicka Live-aktiviteter med Journey Optimizer
feature: Channel Configuration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: db85a563-9630-4d87-bf10-9f2515fe8a45
source-git-commit: 6b4e3a6c32d24861f1ea8df54fc2e4fbb19d0ce7
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 1%

---

# Kom igång med Live-aktivitetskonfiguration {#mobile-live-config}

Innan du skickar din Live-aktivitet måste du konfigurera din Adobe Journey Optimizer-miljö. Så här gör du:

## Steg 1: Lägg till dina push-inloggningsuppgifter för appar i Journey Optimizer (valfritt){#push-credentials-launch}

Registrering av push-autentiseringsuppgifter krävs för mobilappen för att godkänna att Adobe skickar push-meddelanden åt dig.

Steg 1 är valfritt om dina push-autentiseringsuppgifter redan har konfigurerats, eftersom de kan återanvändas för kanalkonfigurationen för Live Activity. Om inga autentiseringsuppgifter har definierats måste du skapa nya push-autentiseringsuppgifter för din app. Se stegen nedan:

1. Gå till **[!UICONTROL Channels]** > **[!UICONTROL Push settings]** > **[!UICONTROL Push credentials]**-menyn.

1. Klicka på **[!UICONTROL Create push credential]**.

   ![](assets/credential-1.png)

1. I listrutan **[!UICONTROL Platform]** väljer du Operativsystemet:

1. Ange mobilappen **[!UICONTROL App ID]**.

   ![](assets/credential-2.png)

1. Aktivera alternativet **[!UICONTROL Apply to all sandboxes]** om du vill att de här push-autentiseringsuppgifterna ska vara tillgängliga i alla sandlådor. Om en specifik sandlåda har egna autentiseringsuppgifter för samma Platform- och App ID-par har dessa sandlådespecifika autentiseringsuppgifter företräde.

1. Växlade på knappen **[!UICONTROL Manually enter push Credentials]** för att lägga till dina autentiseringsuppgifter.

1. Dra och släpp .p8-filen Apple Push Notification Authentication Key. Den här nyckeln kan hämtas från sidan **Certifikat**, **Identifierare** och **Profiler**.

1. Ange **nyckel-ID**. Detta är en 10-teckensträng som tilldelas när en p8-autentiseringsnyckel skapas. Den finns på fliken **Tangenter** på sidan **Certifikat**, **Identifierare** och **Profiler** .

1. Ange **Team-ID**. Detta är ett strängvärde som finns under fliken Medlemskap.

1. Klicka på **[!UICONTROL Submit]** om du vill skapa appkonfigurationen.

## Steg 2: Skapa din konfiguration för Live-aktivitet {#config-live-activity}

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]**. Klicka på knappen **[!UICONTROL Create channel configuration]**.

   ![](assets/config-1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen och välj sedan WhatsApp-kanalen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Välj **[!DNL Live activity]** som kanal.

   ![](assets/config-2.png)

1. Välj **[!UICONTROL Marketing action(s)]** om du vill associera medgivandeprinciper till meddelanden med den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. Läs mer

1. Välj iOS som **[!UICONTROL Platform]**.

1. I listrutan väljer du samma **[!UICONTROL App id]** som för de [push-autentiseringsuppgifter](#push-credentials-launch) som är konfigurerade ovan eller en befintlig.

   ![](assets/config-3.png)

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalkonfigurationen som utkast och återuppta konfigurationen senare.

1. När kanalkonfigurationen har skapats visas den i listan med statusen **[!UICONTROL Processing]**.

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om möjliga felorsaker i [det här avsnittet](../configuration/channel-surfaces.md).

1. När kontrollerna har slutförts får kanalkonfigurationen statusen **[!UICONTROL Active]**. Den är klar att användas för att leverera meddelanden.

Nu kan du börja integrera med Adobe Experience Platform Mobile SDK för att aktivera dynamiska uppdateringar i realtid på låsskärmen och Dynamic Island.

➡️ [Läs mer om Adobe Experience Platform Mobile SDK-integrering](mobile-live-configuration-sdk.md)
