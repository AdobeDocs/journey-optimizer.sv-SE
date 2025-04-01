---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera WhatsApp-kanalen
description: Lär dig hur du konfigurerar miljön för att skicka meddelanden i whatsApp med Journey Optimizer
feature: Whatsapp, Channel Configuration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta" type="Informative"
exl-id: d1f40cd8-f311-4df6-b401-8858095cef3e
source-git-commit: 87931614150d6f764f565f683f83db4f63d88ee0
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 2%

---

# Kom igång med konfigurationen för whatsApp {#whatsapp-config}

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* [Kom igång med whatsApp-meddelanden](get-started-whatsapp.md)
* **[Kom igång med whatsApp-konfiguration](whatsapp-configuration.md)**
* [Skapa ett WhatsApp-meddelande](create-whatsapp.md)
* [Kontrollera och skicka dina meddelanden om whatsApp](send-whatsapp.md)

>[!ENDSHADEBOX]

Innan du skickar ett WhatsApp-meddelande måste du konfigurera din Adobe Journey Optimizer-miljö och associera med ditt WhatsApp-konto. Så här gör du:

1. [Skapa dina API-autentiseringsuppgifter för WhatsApp](#WhatsApp-credentials)
1. [Skapa din whatsApp-konfiguration](#WhatsApp-configuration)

Dessa steg måste utföras av en Adobe Journey Optimizer [systemadministratör](../start/path/administrator.md).

## Skapa API-autentiseringsuppgifter för whatsApp {#whatsapp-credentials}

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** och väljer menyn **[!UICONTROL API Credentials]** . Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera dina API-autentiseringsuppgifter enligt nedanstående:

   * **API-token**: Ange din API-token. Läs mer i [Metadatadokumentation](https://developers.facebook.com/docs/facebook-login/guides/access-tokens/)
   * **Konto-ID**: Ange det unika nummer som hör till din företagsportfölj. Läs mer i [Metadatadokumentation](https://www.facebook.com/business/help/1181250022022158?id=180505742745347).

   ![](assets/whatsapp-api.png)

1. Klicka på **[!UICONTROL Continue]**.

1. Välj det **företagskonto** som du vill ansluta till dina API-autentiseringsuppgifter för WhatsApp.

   ![](assets/whatsapp-api-2.png)

1. Välj det **telefonnummer** som ska användas för att skicka meddelanden från din whatsApp.

1. Dina telefonnummerinställningar fylls i automatiskt:

   * **Kvalitetsklassificering**: Återger kundens feedback på meddelanden som skickats de senaste 24 timmarna.
      * Grön: Hög kvalitet
      * Gul: Medium-kvalitet
      * Röd: Låg kvalitet

     Läs mer om [Kvalitetsklassificering](https://www.facebook.com/business/help/766346674749731#)

   * **Genomflöde**: anger den hastighet med vilken ditt telefonnummer kan skicka meddelanden.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat dina API-autentiseringsuppgifter måste du nu skapa en kanalkonfiguration för WhatsApp-meddelanden. [Läs mer](#whatsapp-configuration)

## Skapa whatsApp-konfiguration {#whatsapp-configuration}

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]**. Klicka på knappen **[!UICONTROL Create channel configuration]**.

   ![](assets/whatsapp-config-1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen och välj sedan WhatsApp-kanalen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Välj **[!DNL WhatsApp]** som kanal.

   ![](assets/whatsapp-config-2.png)

1. Välj **[!UICONTROL Marketing action(s)]** om du vill associera medgivandeprinciper till meddelanden med den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. Läs mer

1. Markera tidigare skapade **[!UICONTROL WhatsApp API configuration]**.

   ![](assets/whatsapp-config-3.png)

1. Ange den **[!UICONTROL Sender number]**-&#x200B; som du vill använda för kommunikationen.

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalkonfigurationen som utkast och återuppta konfigurationen senare.

1. När kanalkonfigurationen har skapats visas den i listan med statusen **[!UICONTROL Processing]**.

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om möjliga felorsaker i [det här avsnittet](../configuration/channel-surfaces.md).

1. När kontrollerna har slutförts får kanalkonfigurationen statusen **[!UICONTROL Active]**. Den är klar att användas för att leverera meddelanden.

Du kan nu skicka meddelanden om whatsApp med Journey Optimizer.
