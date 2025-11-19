---
solution: Journey Optimizer
product: journey optimizer
title: Bästa praxis för SMS för kostnadsoptimering
description: Lär dig hur du kan optimera kostnaderna för SMS-meddelanden genom att hantera teckenbegränsningar, kodning och personalisering i Journey Optimizer
feature: SMS
topic: Content Management
role: User
level: Intermediate
source-git-commit: 13b3c8aa7fce85029167ef31feb7272e4877b7b0
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---

# Bästa tillvägagångssätt för SMS-kostnadsoptimering {#sms-cost-optimization}

SMS-meddelanden faktureras vanligtvis av leverantörer baserat på en gräns på 160 tecken per meddelande. Att skicka SMS-meddelanden kan medföra extrakostnader om meddelandena delas upp i flera delar.

Följ de här riktlinjerna för att optimera er strategi för meddelanden och minska kostnaderna.

## Håll meddelandena korta {#keep-messages-short}

Journey Optimizer tillåter upp till 1 500 tecken i ett SMS-meddelande. En varning visas när du överskrider den här gränsen och meddelanden som överskrider den här tröskeln kommer att utlösa ett fel.

De flesta SMS-leverantörer stöder GSM 7-bitars kodning, där ett enda SMS kan innehålla upp till 160 tecken. Meddelanden som överskrider den här längden delas automatiskt upp i flera SMS-delar (sammanfogning):

* **Färre än 160 tecken**: 1 SMS-del
* **161-306 tecken**: 2 SMS-delar
* **307-459 tecken**: 3 SMS-delar

**Om du vill minimera kostnaderna** bör du hålla meddelanden på under 160 tecken så att de faktureras som en enskild SMS-del.

Ett 1 600-teckenmeddelande kan till exempel förbruka 10 SMS-krediter, även om det visas som ett enda meddelande i Journey Optimizer.

## Undvik specialtecken som ökar längden {#avoid-special-characters}

Vissa tecken, till exempel `| ^ € { } [ ] ~ \`, räknas som två tecken i GSM-kodning. Om du tar med de här tecknen kan det hända att ditt meddelande överskrider gränsen på **160 tecken** snabbare.

## Förhindra UCS-2-kodning {#prevent-ucs2-encoding}

Om meddelandet innehåller icke-GSM-tecken, t.ex. kinesisk eller arabisk text, varumärkessymboler eller hårda radbrytningar från formateringsverktyg, kommer meddelandet att kodas av leverantören med UCS-2, som endast stöder 70 tecken per SMS.

UCS-2-kodning kan öka antalet tecken och därmed påverka meddelandefaktureringen med tjänsteleverantören.

Ett Unicode-meddelande med 200 tecken kommer till exempel att levereras i tre SMS-delar.

## Bästa tillvägagångssätt {#authoring-best-practices}

Skriv det slutliga SMS-meddelandet direkt i Journey Optimizer eller klistra in det från vanliga textprogram.

Undvik att använda RTF-program eftersom de kan medföra dolda tecken eller radbrytningar som utlöser UCS-2-kodning, vilket kan öka både antalet SMS-delar och därmed sammanhängande kostnader.

## Kontrollera antalet tecken innan det skickas {#check-character-count}

Använd program med oformaterad text eller Journey Optimizer **[!UICONTROL Simulate content]**-menyn för att verifiera antalet tecken.

När Journey Optimizer visar ett antal tecken, inklusive mellanslag, under innehållssimulering bör du tänka på följande:

* Det innehåller **inte** tecken som genererats via dynamisk anpassning eller vissa specialtecken.

* **x/1500 count** fungerar som en visuell indikator på den tekniska nyttolastgränsen, inte gränsen per meddelande, till exempel gränsen på 160 tecken för GSM 7 bitar.

* Adobe stöder UTF-8-kodning i redigeraren, som skiljer sig från GSM-7-bitars kodning.

## Förstå rapportering {#understanding-reporting}

**Journey Optimizer-rapportering** räknar det fullständiga meddelandet som en sändning, oavsett SMS-delar.

**Leverantörsrapportering** återspeglar det faktiska antalet SMS-meddelandedelar som används för leverans och bör refereras till för att bekräfta fakturering och eventuella overages. Om Adobe är din SMS-leverantör via Sinch får du faktureringsrapporten separat varje månad.

## Personalization att tänka på {#personalization-considerations}

Dynamisk personalisering kan öka längden på ett meddelande. Om du till exempel ersätter en variabel med ett långt förnamn kan ytterligare tecken läggas till.

## Ytterligare resurser {#additional-resources}

Granska tecken som stöds och kodningsregler i [stödguiden för singch-tecken](https://developers.sinch.com/docs/sms/resources/message-info/character-support/)

