---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Twilio-provider
description: Lär dig konfigurera din miljö för att skicka textmeddelanden med Journey Optimizer med Twilio
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: d6f74566-c913-4727-83b9-473a798a0158
source-git-commit: c9a35c2950c061318f673cdd53d0a5fd08063c27
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---

# Konfigurera Twilio-provider {#sms-configuration-twilio}

Om du vill konfigurera Twilio med Journey Optimizer måste du skapa en ny API-inloggningsuppgift som används för Twilio:

1. Bläddra till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** `>` **[!UICONTROL SMS Settings]** i den vänstra listen och välj menyn **[!UICONTROL API Credentials]**. Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera dina SMS API-uppgifter enligt beskrivningen nedan:

   * **[!UICONTROL SMS vendor]**: Twilio.

   * **[!UICONTROL Name]**: Välj ett namn på din API-uppgift.

   * **[!UICONTROL Account SID]** och **[!UICONTROL Auth Token]**: Gå till rutan **Kontoinformation** på Twilio Consoles instrumentpanel för att hitta dina autentiseringsuppgifter.

   * **[!UICONTROL Message SID]**: Ange den unika identifierare som tilldelas varje meddelande som skapas av Twilios API. Läs mer i [Twilio-dokumentation](https://support.twilio.com/hc/en-us/articles/223134387-What-is-a-Message-SID-){target="_blank"}.

   * **[!UICONTROL Inbound Number]**: Lägg till ditt unika inkommande nummer. Detta gör att du kan använda samma API-uppgifter i olika sandlådor, där var och en har sitt eget inkommande nummer.

1. Klicka på **[!UICONTROL Submit]** när du har slutfört konfigurationen av dina API-uppgifter.

1. Klicka på papperskorgen på menyn **[!UICONTROL API Credentials]** för att ta bort dina API-uppgifter.

1. Om du vill ändra befintliga inloggningsuppgifter letar du upp önskade API-inloggningsuppgifter och klickar på alternativet **[!UICONTROL Edit]** för att göra nödvändiga ändringar.

När du har skapat och konfigurerat dina API-inloggningsuppgifter måste du nu skapa en kanalkonfiguration för SMS- och MMS-meddelanden. [Läs mer](sms-configuration-surface.md)
