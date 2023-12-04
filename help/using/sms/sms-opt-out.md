---
solution: Journey Optimizer
product: journey optimizer
title: Hantering av avanmälan för textmeddelanden
description: Lär dig hantera avanmälan med SMS/MMS-meddelanden
feature: SMS
topic: Content Management
role: User
level: Intermediate
exl-id: 59ea67d9-e90c-4ad0-afb9-d0e0fd868855
source-git-commit: 31c3ed854b38e287850895176f8416bc62739cb0
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Hantering av avanmälan för textmeddelanden {#sms-opt-out}

I enlighet med branschens standarder och bestämmelser måste alla SMS-marknadsföringsmeddelanden innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. [Läs mer om sekretess- och avanmälningshantering](../privacy/opt-out.md)

>[!IMPORTANT]
>
>Textmeddelandekommunikation kan följa olika lagkrav beroende på vilken typ av meddelanden det gäller, var du skickar dina textmeddelanden och var mottagarna finns. Medan Adobe Journey Optimizer hanterar meddelandena om korta koder, långa koder och avgiftsfria nummer enligt beskrivningen nedan, bör du kontakta ditt juridiska ombud för att kontrollera att din textmeddelandekommunikation uppfyller alla gällande lagkrav.
>

## Interna inkommande nyckelord {#sms-native-keywords}

Som standard hanterar Adobe Journey Optimizer följande engelskspråkiga standardsvarsmeddelanden för korta koder, avgiftsfria meddelanden och långa kodmeddelanden: STOP, UNSTOP, START, QUIT, CANCEL, END och UNSUBSCRIBE. Observera att endast Sinch och Infobip har stöd för inbyggda nyckelord när de används med Journey Optimizer.

Dessa nyckelord utlöser vanligtvis ett automatiskt standardsvar från din tredje part-leverantör. Du kan bekräfta detta direkt hos leverantören eller via deras dokumentationswebbplats.

Inga steg krävs för att säkerställa att SMS-avanmälningsfunktioner fungerar i Adobe Journey Optimizer när nyckelordssvaren STOP, UNSTOP, START, QUIT, CANCEL, END och UNSUBSCRIBE identifieras automatiskt. Profilernas avanmälningsstatus uppdateras i realtid i Adobe Journey Optimizer.


## Blockeringslista {#sms-blocklists}

Förutom att Adobe Journey Optimizer stoppar sändningen baserat på avanmälningsstatus (för direktintegrering med Twilio eller Sinch) har de flesta SMS-gatewayleverantörer också en blockeringslista som säkerställer att du inte får något SMS-meddelande till en person som har valt att avanmäla sig. Om du använder en annan leverantör än Sinch eller Twilio och skickar ett SMS via [anpassad kanal](../building-journeys/using-custom-actions.md)måste du bekräfta detta med din leverantör.


## Korta koder {#short-codes}

Som standard hanteras inte nyckelord för deltagande eller hjälp för korta kodnummer av Adobe Journey Optimizer. För att säkerställa att branschens regler och regler för hantering av avanmälan följs är det viktigt att kontrollera att din korta kod följer alla riktlinjer.

Journey Optimizer stöder dock globala avanmälningar baserade på inkommande nyckelord med olika avsändar-ID.

## Avsändarens alfanumeriska ID {#alphanumeric}

De alfanumeriska avsändar-ID:n är endast avsedda för envägsmeddelanden och kan inte ta emot inkommande meddelanden. Därför gäller Adobe Journey Optimizer SMS STOP-, START- och HELP-nyckelord inte för Alpha avsändar-ID:n. Du måste ange andra instruktioner, till exempel skriva till supportteamet, ringa en telefonlinje till supporten eller skicka ett annat telefonnummer eller en annan kod så att användarna kan välja bort meddelanden som skickas via ett alfanumeriskt avsändar-ID.

## Video {#video-sms}

Mer information om hur inbyggt stöd för inkommande nyckelord (START, STOP och UNSTOP) fungerar för SMS finns i följande video:

>[!VIDEO](https://video.tv.adobe.com/v/344026?quality=12)
