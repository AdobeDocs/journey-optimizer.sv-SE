---
solution: Journey Optimizer
product: journey optimizer
title: E-postfeltyper
description: Få åtkomst till listan över alla möjliga e-postfel när du skickar leveranser med Journey Optimizer.
feature: Deliverability, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: återförsök, studsa, mjuk, ignorerad, hård, optimering, fel
hide: true
hidefromtoc: true
exl-id: a8908b11-2288-4d53-897c-3f99cb5ceab4
source-git-commit: 0cb73489981659c3f231b9def40e0e483ed3aef8
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 4%

---

# E-postfeltyper {#email-error-types}

Möjliga orsaker till leveransfel är flera. Tabellen nedan beskriver alla fel som kan inträffa när e-postleveranser skickas med [!DNL Journey Optimizer], tillsammans med deras beskrivning och feltyp.

Dessa fel finns i [AJO Message Feedback Event Dataset](../data/datasets-query-examples.md#message-feedback-event-dataset) som innehåller meddelandeleveransloggarna, inklusive information om all meddelandeleverans från [!DNL Journey Optimizer] och feedbackposter från e-postleverantörerna på domän.

| Feletikett | Feltyp | Tekniskt värde | Beskrivning |
| --- | --- | --- | --- |
| **Obestämt** | Ignorerad | 1 | Det går inte att klassificera SMTP-studsmeddelandet som tagits emot från Internet-leverantören. |
| **Ogiltig mottagare** | Hård studs | 10 | Mottagarens adress är ogiltig. |
| **Mottagaren har nekats** | Hård studs | 15 | Mottagarens Internet-leverantör har avböjt meddelandet och Internet-leverantören kan blockera avsändaren om mottagaren inte är undertryckt. |
| **Mjuk studs** | Mjuk studs | 20 | Meddelandet orsakade ett tillfälligt fel. Det kan lyckas i framtida försök. |
| **DNS-fel** | Mjuk studs | 21 | Ett tillfälligt DNS-fel uppstod vid meddelandeleveransen. Det kan lyckas i framtida försök. |
| **Postlådan är full** | Mjuk studs | 22 | Meddelandet fick ett tillfälligt leveransfel eftersom mottagarens postlåda var full. |
| **För stor** | Ignorerad | 23 | Meddelandet orsakade ett tillfälligt leveransfel eftersom meddelandestorleken överskred mottagarens gräns. |
| **Timeout** | Ignorerad | 24 | Meddelandeleveransen misslyckades antingen på grund av att meddelandets giltighet gick ut eller att det tog för lång tid att skicka till Internet. |
| **Administratörsfel** | Administratör | 25 | Leveransen misslyckades på grund av en principkonfiguration i e-postsändningsinfrastrukturen. |
| **Allmänt studs: INGEN RCPT** | Ignorerad | 30 | Det gick inte att leverera meddelandet eftersom mottagaren inte identifierades. |
| **Allmänt studs** | Ignorerad | 40 | Meddelandet orsakade ett tillfälligt leveransfel av ospecificerade orsaker. |
| **E-postblock** | Ignorerad | 50 | Leveransen orsakade ett tillfälligt fel på grund av höga volymer eller hastighetsbegränsningar från Internet-leverantören. |
| **Skräppostblock** | Ignorerad | 51 | Leveransen orsakade ett tillfälligt fel eftersom Internet-leverantören ansåg att avsändarens domäner eller IP-adresser är en känd skräppostkälla. |
| **Skräppostinnehåll** | Ignorerad | 52 | Leveransen orsakade ett tillfälligt fel eftersom Internet-leverantören klassificerade e-postens innehåll som skräppost. |
| **Återkommande nekad** | Mjuk studs | 54 | Det gick inte att acceptera meddelandet eftersom måldomänen inte tillåts för återutläggning. |
| **Autosvar** | Ignorerad | 60 | Dessa meddelanden ignoreras av [!DNL Journey Optimizer] vid mottagning om inte vidarebefordran är aktiverat. |
| **Övergående fel** | Ignorerad | 70 | Leveransen provas på nytt med begränsad hastighet eller kan skjutas upp om den avbryts. |
| **Problem-svar** | Mjuk studs | 100 | Leveransen kan misslyckas permanent eftersom [!DNL Journey Optimizer] inte har stöd för en autentiseringsmekanism för utmaning-svar. |
