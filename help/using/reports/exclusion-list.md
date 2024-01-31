---
solution: Journey Optimizer
product: journey optimizer
title: Lista över undantag
description: Läs mer om undantag som inträffar när du skickar
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: a34ba1a8-87d5-4f9c-a181-2f49e74e8f09
source-git-commit: d26dbebaf36241d0e91c36c95f83ce6cf712ecee
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 9%

---

# Uteslutningsorsaker {#exclusion-list}

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
| EmailNoAddressDefinedInPreset | 050021 | E-post | En undantagshändelse genereras när körningsadressen inte har definierats i ytan. |
| EmailNoVariantDefined | 050026 | E-post | En undantagshändelse genereras när ingen variant har definierats i e-postmeddelandet. |
| EmailNoMessageFoundForTreatment | 050027 | E-post | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| EmailMalformedAddress | 050024 | E-post | En undantagshändelse genereras när e-postmeddelandet innehåller en felformaterad adress. |
| InAppNoVariantDefined | 050041 | InApp | En undantagshändelse genereras när ingen variant har definierats för InApp-meddelandet. |
| InAppNoMessageFoundForTreatment | 050042 | InApp | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| PushNoTokenFoundInProfile | 050030 | Push | En undantagshändelse genereras när profilen inte har push-tokens. |
| PushNoValidTokenFoundForApps | 050031 | Push | En undantagshändelse genereras när ingen giltig token hittas för målprogrammen i ytan. |
| PushMalformedProfile | 050034 | Push | En undantagshändelse genereras när pushNotificationDetails i profilen har fel format. |
| PushNoConsent | 050111 | Push | En undantagshändelse genereras när användaren har valt bort push-meddelanden för marknadsföring. |
| PushNoApplicationDefinedInPreset | 050033 | Push | En undantagshändelse genereras när ytan inte innehåller något program att rikta sig till. |
| PushNoVariantDefined | 050035 | Push | En undantagshändelse genereras när ingen variant har definierats. |
| PushNoMessageFoundForTreatment | 050036 | Push | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| SMSNoSamtycke | 050104 | SMS | En undantagshändelse genereras när användaren har valt att inte längre använda SMS för marknadsföring. |
| SMSFromNumberNotDefinedInPreset | 050152 | SMS | En undantagshändelse genereras när&quot;FromNumber&quot; inte har definierats i ytan. |
| SMSNoToNumberDefinedInProfile | 050153 | SMS | En undantagshändelse genereras när&quot;ToNumber&quot; inte har definierats i ytan. |
| SMSNoVariantDefined | 050154 | SMS | En undantagshändelse genereras när ingen variant har definierats. |
| SMSNoMessageFoundForTreatment | 050155 | SMS | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
| WebNoVariantDefined | 050041 | Webb | En undantagshändelse genereras när ingen variant har definierats för ett webbmeddelande. |
| WebNoMessageFoundForTreatment | 050042 | Webb | En undantagshändelse genereras när experimentet aktiveras för meddelandet och inget meddelande hittas för den kvalificerade behandlingen. |
