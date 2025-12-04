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
source-git-commit: 38d537eb7a14f926cafd2769fd09821eebb1186a
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# Hantering av avanmälan för textmeddelanden {#sms-opt-out}

I enlighet med branschens standarder och bestämmelser måste alla SMS-marknadsföringsmeddelanden innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. [Läs mer om sekretess- och avanmälningshantering](../privacy/opt-out.md)

>[!IMPORTANT]
>
>Textmeddelandekommunikation kan följa olika lagkrav beroende på vilken typ av meddelanden de gäller, var du skickar dina textmeddelanden och var mottagarna finns. Medan Adobe Journey Optimizer hanterar meddelanden om korta koder, långa koder och avgiftsfria nummer så som beskrivs nedan, bör du kontakta ditt juridiska ombud för att kontrollera att din textmeddelandekommunikation uppfyller alla gällande lagkrav.
>

## Interna inkommande nyckelord {#sms-native-keywords}

>[!NOTE]
>
> Endast Sinch och Infobip har stöd för inbyggda nyckelord när de används med Journey Optimizer.

Som standard hanterar Adobe Journey Optimizer följande vanliga engelskspråkiga svarsmeddelanden för korta koder, avgiftsfria meddelanden och långa kodmeddelanden:

* **Opt-Out**: STOP, QUIT, CANCEL, END, UNSUBSCRIBE, NO.
* **Opt-In**: SUBSCRIBE, YES, UNSTOP, START, FORTSÄTT, RESUME, BEGIN.
* **Hjälp**: HJÄLP.

Dessa nyckelord utlöser vanligtvis ett automatiskt standardsvar från din tredje part-leverantör. Du kan bekräfta detta direkt hos leverantören eller via deras dokumentationswebbplats.

När du använder Infobip måste du se till att Vidarebefordringsåtgärden är inställd på Pull-konfiguration.

Inga steg krävs för att säkerställa att SMS-avanmälningsfunktioner fungerar i Adobe Journey Optimizer när nyckelordssvaren STOP, UNSTOP, START, QUIT, CANCEL, END och UNSUBSCRIBE identifieras automatiskt. Profilernas avanmälningsstatus uppdateras i realtid i Adobe Journey Optimizer.

Om du definierar anpassade avanmälningsnyckelord i dina SMS API-autentiseringsuppgifter åsidosätter de standardvärdena för inkommande nyckelord som listas ovan. Om du vill behålla standardnyckelorden, som STOP, QUIT, CANCEL, END och UNSUBSCRIBE, ska du inkludera dem explicit tillsammans med dina anpassade nyckelord i fältet Avandesnyckelord i din SMS-konfiguration. Annars identifieras bara dina anpassade nyckelord och standardnyckelorden utlöser inte längre avanmälningsåtgärder.

Observera att om en kund svarar STOP på ett textmeddelande blockerar leverantören alla efterföljande SMS från det specifika avsändar-ID:t (kort kod eller långt nummer), inklusive transaktionsmeddelanden. Använd ett separat avsändar-ID som inte tidigare har valts ut för att säkerställa oavbruten leverans av transaktionsmeddelanden.


>[!NOTE]
>
>Om du planerar att använda tvåvägs-SMS (svara med STOP, QUIT, osv.) måste du först skicka minst ett envägs-SMS för att fastställa mappningen mellan telefonnummer och profil. Utgångna eller felkonfigurerade autentiseringsuppgifter för providern förhindrar att inkommande nyckelord uppdaterar användarprofilen, vilket leder till saknade eller fördröjda poster för avanmälan.


## Blockeringslista {#sms-blocklists}

Förutom att Adobe Journey Optimizer stoppar sändning baserat på avanmälningsstatus (för direktintegrering med Twilio, Infobip eller Sinch) har de flesta SMS-gatewayleverantörer också en blockeringslista som säkerställer att SMS-meddelanden inte levereras till en person som har valt att avanmäla sig. Om du använder en annan leverantör än Sinch eller Twilio och skickar ett SMS via [anpassad kanal](../building-journeys/using-custom-actions.md) måste du bekräfta detta hos din leverantör.


## Korta koder {#short-codes}

Som standard hanteras inte nyckelord för deltagande eller hjälp för korta kodnummer av Adobe Journey Optimizer. För att säkerställa att branschens regler och regler för hantering av avanmälan följs är det viktigt att kontrollera att din korta kod följer alla riktlinjer.

Journey Optimizer stöder dock globala avanmälningar baserade på inkommande nyckelord med olika avsändar-ID.

## Avsändarens alfanumeriska ID {#alphanumeric}

De alfanumeriska avsändar-ID:n är endast avsedda för envägsmeddelanden och kan inte ta emot inkommande meddelanden. Därför gäller inte Adobe Journey Optimizer SMS STOP-, START- och HELP-nyckelord för Alpha avsändar-ID:n. Du måste ange andra instruktioner, till exempel skriva till supportteamet, ringa en telefonlinje till supporten eller skicka ett annat telefonnummer eller en annan kod så att användarna kan välja bort meddelanden som skickas via ett alfanumeriskt avsändar-ID.

## Video {#video-sms}

* I videon nedan får du lära dig hur du konfigurerar dubbel anmälan för SMS.

  +++ Se videon

  >[!VIDEO](https://video.tv.adobe.com/v/3427129/?learn=on)

  +++
