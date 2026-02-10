---
solution: Journey Optimizer
product: journey optimizer
title: Lista över undantag
description: Läs mer om undantag under sändning
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: a34ba1a8-87d5-4f9c-a181-2f49e74e8f09
source-git-commit: 8ced9477edf8a7129e974d007755e132f3079943
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 7%

---

# Uteslutningsorsaker {#exclusion-list}

## Hur undantag räknas i kampanjrapporter

Observera att måttet *Undantag* beräknas så här när kampanjrapporter visas:

**Undantag = unika undantag + dubblerade undantagshändelser**

Det innebär att om en profil utesluts flera gånger (t.ex. på grund av flera undantagshändelser för samma profil) räknas varje händelse in i summan för uteslutningar. Därför kan summan av *Levererade* och *Undantag* överstiga den ursprungliga målgruppsstorleken. Detta beteende förväntas och återspeglar hur undantagshändelser spåras i systemet.

**Exempel:**

- Målgrupp: 94 000 profiler
- Levererat: 69 000
- Undantag: 37 000 (inkluderar dubblerade exclude-händelser)
- Totalt (levererat + Uteslutning): 106 000

Summan överskrider målgruppen eftersom dubblerade undantagshändelser ingår i antalet undantag.

Mer information om de specifika exkluderingsorsakerna finns i tabellen nedan.

## Lista över orsaker till undantag

| Uteslutningsorsak | Felkod | Kanal | Förklaring |
|-|-|-|-|
| RuntimeDispatchError | 050301 | Alla kanaler | Allmän undantagshändelse för alla körningsfel. |
| RuntimeRenderingError | 050302 | Alla kanaler | Allmän undantagshändelse för alla återgivningsfel vid körning. |
| NamespaceErrorForExperimentation | 050017 | Alla kanaler | En undantagshändelse genereras när Namnutrymme i Experiment skiljer sig från profilens namnutrymme. |
| ExperimentationHoldoutExclusion | 050018 | Alla kanaler | Denna exkluderingshändelse inträffar när den kvalificerade behandlingen för en expert är&quot; Holdout&quot;. |
| ExkluderadeFörKontrollRegler | 050002 | Alla kanaler | Den här undantagshändelsen genereras när leveransen av det aktuella meddelandet bryter mot kontrollreglerna, t.ex. antalet e-postmeddelanden som tillåts under en månad. |
| DirectMailNoVariantDefined | 050062 | DirectMail | En undantagshändelse genereras när ingen direktmeddelandevariant har definierats. |
| DirectMailNoMessageHittadesFörBehandling | 050061 | DirectMail | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| EmailNoConsent | 050101 | E-post | En undantagshändelse genereras när användaren har valt att inte ta emot marknadsföring via e-post. |
| Undertryckt | 050107 | E-post | Uteslutning på grund av en av anledningarna till uteslutning. |
| EmailSuppressed | 050102 | E-post | En undantagshändelse genereras när målets e-post ignoreras. |
| DomainSuppressed | 050105 | E-post | En undantagshändelse genereras när domänen för måle-postmeddelandet ignoreras. |
| NotAllowed | 050108 | E-post | En undantagshändelse genereras när tillåtelselista är aktiverat och målmeddelandet är exkluderat från tillåtelselista. |
| EmailNotAllowed | 050103 | E-post | En undantagshändelse genereras när tillåtelselista är aktiverat och målmeddelandet är exkluderat från tillåtelselista. |
| DomänTillåtenInte | 050106 | E-post | En undantagshändelse genereras när tillåtelselista är aktiverat och domänen för måle-postmeddelandet är exkluderad från tillåtelselista. |
| EmailNoSubscriberIdFoundInProfile | 050025 | E-post | En undantagshändelse genereras när subscriberId inte hittas i profilen för ett prenumerationsmeddelande. |
| EmailNoAddressFoundInProfile | 050020 | E-post | En undantagshändelse genereras när e-postadressen inte hittas i körningsadressen. |
| EmailNoAddressDefinedInPreset | 050021 | E-post | En undantagshändelse genereras när körningsadressen inte har definierats i konfigurationen. |
| EmailNoVariantDefined | 050026 | E-post | En undantagshändelse genereras när ingen variant har definierats i e-postmeddelandet. |
| EmailNoMessageFoundForTreatment | 050027 | E-post | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| EmailMalformedAddress | 050024 | E-post | En undantagshändelse genereras när e-postmeddelandet innehåller en felformaterad adress. |
| UnsubscribeLinkNotValid | 050081 | E-post | En undantagshändelse genereras när längden för List-Unsubscribe mailTo-objektet är större än RFC-gränsen på 998 tecken. |
| InAppNoVariantDefined | 050041 | InApp | En undantagshändelse genereras när ingen variant har definierats för InApp-meddelandet. |
| InAppNoMessageFoundForTreatment | 050042 | InApp | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| PushNoTokenFoundInProfile | 050030 | Push | En undantagshändelse genereras när profilen inte har push-tokens. |
| PushNoValidTokenFoundForApps | 050031 | Push | En undantagshändelse genereras när ingen giltig token hittas för målprogrammen i konfigurationen. **Viktigt!** När du använder ett produktionscertifikat måste attributet `pushNotificationDetails.platform` i användarprofilen anges till `apns`. Om du använder ett sandlådecertifikat anger du det till `apnsSandbox`. Ett matchningsfel mellan plattformsattributet och certifikattypen utlöser detta undantag. |
| PushMalformedProfile | 050034 | Push | En undantagshändelse genereras när pushNotificationDetails i profilen har fel format. |
| PushNoConsent | 050111 | Push | En undantagshändelse genereras när användaren har valt bort push-meddelanden för marknadsföring. |
| PushNoApplicationDefinedInPreset | 050033 | Push | En undantagshändelse genereras när konfigurationen inte innehåller något program att rikta sig till. |
| PushNoVariantDefined | 050035 | Push | En undantagshändelse genereras när ingen variant har definierats. |
| PushNoMessageFoundForTreatment | 050036 | Push | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| SMSNoSamtycke | 050104 | SMS | En undantagshändelse genereras när användaren har valt att inte längre använda SMS för marknadsföring. |
| SMSFromNumberNotDefinedInPreset | 050152 | SMS | En undantagshändelse genereras när&quot;FromNumber&quot; inte har definierats i konfigurationen. |
| SMSNoToNumberDefinedInProfile | 050153 | SMS | En undantagshändelse genereras när &quot;ToNumber&quot; inte har definierats i konfigurationen. |
| SMSNoVariantDefined | 050154 | SMS | En undantagshändelse genereras när ingen variant har definierats. |
| SMSNoMessageFoundForTreatment | 050155 | SMS | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| WebNoVariantDefined | 050041 | Webb | En undantagshändelse genereras när ingen variant har definierats för ett webbmeddelande. |
| WebNoMessageFoundForTreatment | 050042 | Webb | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
