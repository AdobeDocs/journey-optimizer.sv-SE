---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Infobip-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden och MMS med Journey Optimizer med Infobip
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 7b6dc89a-1a81-49c2-b2a7-bf24b9d215e3
source-git-commit: 4278d8c8294b1413788402cd8eac5959996ad3f5
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 0%

---

# Konfigurera Infobip-provider {#sms-configuration-infobip}

>[!BEGINSHADEBOX]

Om nyckelord för anmälan eller avanmälan inte anges används standardmeddelanden för godkännande för att respektera användarens integritet. Om du lägger till anpassade nyckelord åsidosätts standardvärdena automatiskt.

**Standardnyckelord:**

* **Opt-In**: SUBSCRIBE, YES, UNSTOP, START, FORTSÄTT, RESUME, BEGIN
* **Opt-Out**: STOP, QUIT, CANCEL, END, UNSUBSCRIBE, NO
* **Hjälp**: HJÄLP

>[!ENDSHADEBOX]

Genom att integrera Infobip med Adobe Journey Optimizer kan ni leverera textmeddelanden till era profiler som en del av era resor och kampanjer.

Följ stegen nedan för att konfigurera InfoBitp som din SMS-leverantör:

1. [Skapa API-autentiseringsuppgifter](#api-credential)
1. [Skapa webkrok](sms-webhook.md)
1. [Skapa kanalkonfiguration](sms-configuration-surface.md)
1. [Skapa resa eller kampanj med SMS-kanalsåtgärd](create-sms.md)

## Konfigurera API-autentiseringsuppgifter för SMS {#api-credential}

Så här konfigurerar du Infobip med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** och väljer menyn **[!UICONTROL API Credentials]** . Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   +++ Lista över SMS-autentiseringsuppgifter för konfiguration

   | Konfigurationsfält | Beskrivning |
   |---|---|    
   | SMS-leverantör | Infobip |
   | Namn | Välj ett namn för API-autentiseringsuppgifterna. |
   | API-bas-URL och API-nyckel | Gå till webbgränssnittets hemsida eller API-nyckelhanteringssidan för att hitta dina autentiseringsuppgifter. För regionala eller alternativa domänslutpunkter, t.ex. `api-ny2.infobip.com`, anger du den fullständiga bas-URL:en och verifierar din auktoriseringstoken med Infobip-stöd. </br>Läs mer i [Infobip-dokumentation](https://www.infobip.com/docs/api){target="_blank"} |
   | Nyckelord för deltagande | **Använd menyn [Webhooks](sms-webhook.md) för att konfigurera medgivandenyckelord för nya SMS-konfigurationer. Befintliga konfigurationer kan fortsätta med hjälp av medgivandenyckelord i det här avsnittet.** </br>Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt meddelande om anmälan. Använd kommaseparerade värden för flera nyckelord. |
   | Opt-in-meddelande | **Använd menyn [Webhooks](sms-webhook.md) för att konfigurera medgivandenyckelord för nya SMS-konfigurationer. Befintliga konfigurationer kan fortsätta med hjälp av medgivandenyckelord i det här avsnittet.** </br> Ange det anpassade svar som automatiskt skickas som ditt meddelande. |
   | Avanmäl nyckelord | **Använd menyn [Webhooks](sms-webhook.md) för att konfigurera medgivandenyckelord för nya SMS-konfigurationer. Befintliga konfigurationer kan fortsätta med hjälp av medgivandenyckelord i det här avsnittet.** </br> Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt avanmälningsmeddelande. Använd kommaseparerade värden för flera nyckelord. |
   | Avanmäl meddelande | **Använd menyn [Webhooks](sms-webhook.md) för att konfigurera medgivandenyckelord för nya SMS-konfigurationer. Befintliga konfigurationer kan fortsätta med hjälp av medgivandenyckelord i det här avsnittet.** </br>Ange det anpassade svar som automatiskt skickas som ditt meddelande. |
   | Hjälpnyckelord | **Använd menyn [Webhooks](sms-webhook.md) för att konfigurera medgivandenyckelord för nya SMS-konfigurationer. Befintliga konfigurationer kan fortsätta med hjälp av medgivandenyckelord i det här avsnittet.** </br>Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt **hjälpmeddelande**. Använd kommaseparerade värden för flera nyckelord. |
   | Hjälpmeddelande | **Använd menyn [Webhooks](sms-webhook.md) för att konfigurera medgivandenyckelord för nya SMS-konfigurationer. Befintliga konfigurationer kan fortsätta med hjälp av medgivandenyckelord i det här avsnittet.** </br>Ange det anpassade svar som automatiskt skickas som **hjälpmeddelande**. |
   | Nyckelord för dubbel anmälan | **Använd menyn [Webhooks](sms-webhook.md) för att konfigurera medgivandenyckelord för nya SMS-konfigurationer. Befintliga konfigurationer kan fortsätta med hjälp av medgivandenyckelord i det här avsnittet.** </br>Ange de nyckelord som utlöser processen för dubbel anmälan. Om en användarprofil inte finns skapas den när den har bekräftats. Använd kommaseparerade värden för flera nyckelord. [Läs mer om SMS-dubbelanmälan](https://video.tv.adobe.com/v/3427129/?learn=on). |
   | Dubbelt meddelande om anmälan | **Använd menyn [Webhooks](sms-webhook.md) för att konfigurera medgivandenyckelord för nya SMS-konfigurationer. Befintliga konfigurationer kan fortsätta med hjälp av medgivandenyckelord i det här avsnittet.** </br>Ange det anpassade svar som skickas automatiskt som svar på bekräftelsen av dubbel anmälan. |
   | Huvudenhets-ID | Ange ditt tilldelade enhets-ID för DLT-huvudnamn. |
   | Innehållsmall-ID | Ange ditt registrerade ID för DLT-innehållsmall. |
   | Giltighetsperiod | Ange meddelandets giltighetsperiod i timmar. Om det inte går att leverera meddelanden inom den här tidsramen gör systemet ytterligare försök att skicka dem igen. Standardgiltighetsperioden är inställd på 48 timmar. |
   | Återkallningsdata | Ange ytterligare klientdata som ska skickas på Notify URL. |
   | Ingående nummer | Lägg till ditt unika inkommande nummer. På så sätt kan du använda samma API-autentiseringsuppgifter för olika sandlådor, var och en med ett eget inkommande nummer. |
   | Anpassade inkommande nyckelord | Definiera unika nyckelord utan medgivande för batchbaserade åtgärder, t.ex. RABATT, ERBJUDANDEN, REGISTRERING. Dessa nyckelord fångas in och lagras som attribut i profilen, vilket gör att du kan aktivera en gruppbaserad segmentkvalificering under resan och leverera ett anpassat svar eller en anpassad åtgärd. |
   | Standardsvarsmeddelande för inkommande trafik | Ange standardsvaret som skickas när en slutanvändare skickar ett inkommande SMS som inte matchar något av de definierade nyckelorden. |

   +++

1. Aktivera alternativet **[!UICONTROL Fuzzy Opt-out]** för att identifiera meddelanden som liknar nyckelord för avanmälan (t.ex. &quot;CANCIL&quot;) och anpassa bekräftelsemeddelandet i fältet **[!UICONTROL Fuzzy Auto Reply]**.

   **[!UICONTROL Fuzzy Opt-out]** identifierar SMS-meddelanden som anger att en användare vill avbryta prenumerationen, även om meddelandet inte exakt matchar ett definierat avanmälningsnyckelord. Det kan identifiera vanliga avanmälningsfraser och vissa stötande termer, vilket kan säkerställa att era kampanjer respekterar användarnas preferenser och följer de gällande reglerna.

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

RCS-meddelanden stöds i Adobe Journey Optimizer via Infobip med funktionen [Anpassad SMS-provider](sms-configuration-custom.md) . På så sätt kan du leverera interaktiva budskap via verifierade affärsprofiler, som innehåller element som karuseller, knappar och multimediematerial.

➡️ [Se hur Infobip stöder RCS i Infobip-dokumentationen ](https://www.infobip.com/docs/api/channels/rcs)

Om du vill aktivera RCS-meddelanden med Infobip måste nya API-autentiseringsuppgifter konfigureras via en anpassad SMS-provider. Befintliga SMS-autentiseringsuppgifter för Infobip är inte kompatibla eftersom RCS kräver ett distinkt nyttolastformat.

Så här konfigurerar du RCS med Infobip:

1. **Registrera ditt företag för RCS via Infobip**

   Börja med att slutföra RCS-introduktionen och registreringsprocessen på Infobip-plattformen. Detta innebär att du konfigurerar din RCS-avsändarprofil och ser till att ditt konto är RCS-aktiverat. Läs mer i [Infobip-dokumentation](https://www.infobip.com/docs/rcs/get-started)

1. **Skapa en SMS-webkrok**

   [Konfigurera en anpassad SMS-webkrok](sms-configuration-custom.md#webhook) i Journey Optimizer. Den här webkroken hanterar leveranskvitton, inkommande RCS-meddelanden och statusuppdateringar från Infobips plattform.

1. **Skapa API-autentiseringsuppgifter med anpassad som SMS-leverantör**

   [Skapa en ny API-autentiseringsuppgift](sms-configuration-custom.md#api-credential) i Journey Optimizer och välj Anpassad som SMS-provider. Använd lämplig autentiseringsmetod för RCS-slutpunkter, bas-URL och rubriker.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa [din webkrok](sms-webhook.md) och en kanalkonfiguration för dina RCS-meddelanden. [Läs mer](sms-configuration-surface.md)
