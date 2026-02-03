---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Twilio-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer med Twilio
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: d6f74566-c913-4727-83b9-473a798a0158
source-git-commit: 4278d8c8294b1413788402cd8eac5959996ad3f5
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# Konfigurera Twilio-provider {#sms-configuration-twilio}

Genom att integrera Twilio med Adobe Journey Optimizer kan ni leverera textmeddelanden till era profiler som en del av era resor och kampanjer.

Följ stegen nedan för att konfigurera Twilio som SMS-leverantör:

1. [Skapa API-autentiseringsuppgifter](#api-credential)
1. [Skapa webkrok](sms-webhook.md)
1. [Skapa kanalkonfiguration](sms-configuration-surface.md)
1. [Skapa resa eller kampanj med SMS-kanalsåtgärd](create-sms.md)

## Konfigurera API-autentiseringsuppgifter för SMS/MMS {#api-credential}

Om du vill konfigurera Twilio med Journey Optimizer måste du skapa nya API-autentiseringsuppgifter för Twilio:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** `>` **[!UICONTROL SMS Settings]** och väljer menyn **[!UICONTROL API Credentials]**. Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL SMS vendor]**: Twilio.

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Account SID]** och **[!UICONTROL Auth Token]**: gå till rutan **Kontoinformation** på Twilio Console Dashboard-sidan för att hitta dina autentiseringsuppgifter.

   * **[!UICONTROL Message SID]**: Ange den unika identifierare som tilldelats alla meddelanden som skapats av Twilios API. Läs mer i [Twilio-dokumentation](https://support.twilio.com/hc/en-us/articles/223134387-What-is-a-Message-SID-){target="_blank"}.

   * **[!UICONTROL Inbound Number]**: lägg till ditt unika inkommande nummer. På så sätt kan du använda samma API-autentiseringsuppgifter för olika sandlådor, var och en med ett eget inkommande nummer.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

1. Klicka på bin-ikonen på menyn **[!UICONTROL API Credentials]** för att ta bort dina API-autentiseringsuppgifter.

1. Om du vill ändra befintliga autentiseringsuppgifter letar du reda på de API-autentiseringsuppgifter du vill ha och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

1. Klicka på **[!UICONTROL Verify SMS connection]**, bland dina befintliga API-autentiseringsuppgifter, för att testa och verifiera dina SMS API-autentiseringsuppgifter genom att skicka ett exempelmeddelande till en angiven enhet.

1. Fyll i fälten **Number** och **Message** och klicka på **[!UICONTROL Verify connection]**.

   >[!IMPORTANT]
   >
   >Meddelandet måste vara strukturerat så att det överensstämmer med leverantörens nyttolastformat.

   ![](assets/verify-connection.png)

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalkonfiguration för SMS- och MMS-meddelanden. [Läs mer](sms-configuration-surface.md)

## Konfigurera API-autentiseringsuppgifter för RCS

RCS-meddelanden stöds i Adobe Journey Optimizer via Twilio med funktionen [Anpassad SMS-provider](sms-configuration-custom.md) . På så sätt kan du leverera interaktiva budskap via verifierade affärsprofiler, som innehåller element som karuseller, knappar och multimediematerial.

➡️ [Se hur Twilio stöder RCS i Twilio-dokumentationen ](https://www.twilio.com/docs/rcs)

Om du vill aktivera RCS-meddelanden med Twilio måste nya API-autentiseringsuppgifter konfigureras via en anpassad SMS-provider. Befintliga SMS-autentiseringsuppgifter för Twilio är inte kompatibla eftersom RCS kräver ett distinkt nyttolastformat.

Så här konfigurerar du RCS med Twilio:

1. **Registrera dig för RCS-meddelanden i Twilio**

   Börja med att slutföra RCS-registreringsprocessen på Twilio-plattformen. Detta inkluderar att konfigurera din affärsprofil och aktivera RCS-funktioner för ditt konto.

1. **Skapa en SMS-webkrok**

   [Konfigurera en SMS-webkrok](sms-configuration-custom.md#webhook) som kan ta emot inkommande RCS-meddelanderesvar eller leveransuppdateringar. Den här webkroken måste vara korrekt länkad till din Twilio-konfiguration för tvåvägskommunikation.

1. **Skapa API-autentiseringsuppgifter med anpassad som SMS-leverantör**

   I Journey Optimizer [definierar ](sms-configuration-custom.md#api-credential) nya API-autentiseringsuppgifter specifikt för RCS med&quot;Custom&quot; som SMS-leverantör. Använd lämplig autentiseringsmetod för RCS-slutpunkter, bas-URL och rubriker.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalkonfiguration för dina RCS-meddelanden. [Läs mer](sms-configuration-surface.md)







