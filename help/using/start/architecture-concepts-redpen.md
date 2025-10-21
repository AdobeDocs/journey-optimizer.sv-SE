---
solution: Journey Optimizer
product: journey optimizer
title: AJO-arkitektur
description: Arkitektur och relation till AEP
feature: Get Started
role: Admin, Developer, User
level: Beginner
redpen-status: PASS_||_2025-04-28_15-13-07
exl-id: f792fdf9-8038-4dd7-a7d5-d931dbf35c3e
hide: true
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 0%

---

# Arkitektur

## The Big Picture: How Adobe Journey Optimizer Passing Together

Adobe Journey Optimizer (AJO) och Adobe Experience Platform (AEP) samarbetar för att möjliggöra datadriven personalisering i stor skala. Detta ekosystem fungerar som ett kontinuerligt flöde där data samlas in, analyseras och används för att skapa personaliserade kundresor.

![](../assets/do-not-localize/get-started-big-picture.png)


### Foundation: Adobe Experience Platform (AEP)

Adobe Experience Platform fungerar som ryggrad och gör det möjligt för varumärken att centralisera kunddata och aktivera dem för personaliserade upplevelser.

- **Dataplattform**: AEP fungerar som ett centralt nav för att samla in, hantera och strukturera kunddata för att säkerställa enhetlighet mellan olika system.
- **Datainmatning (källor)**: Varumärken importerar data från olika system, till exempel CRM-plattformar, webbplatser, mobilappar och molnlagring, med fördefinierade anslutningar. Exempel: en Source Connector importerar data från en e-handelsplattform.
- **Kundprofil i realtid**: Den här funktionen skapar enhetliga profiler genom att sammanfoga data från flera källor. En profil kombinerar till exempel e-postinteraktioner och butiksköp för att ge en fullständig bild av kunden.
- **Styrningslager**: Det här lagret styr dataåtkomst, sekretessefterlevnad och säkerhet. Det säkerställer att varumärken på ett säkert sätt använder kunddata samtidigt som de följer gällande bestämmelser.

### Orchestration Engine: Adobe Journey Optimizer (AJO)

Adobe Journey Optimizer använder data och insikter från AEP för att leverera intelligenta, personaliserade kundupplevelser i olika kanaler.

- **Kundförståelse**: Kundprofiler i realtid möjliggör segmentering i målgrupper för riktade meddelanden. En publik inkluderar till exempel vanliga kunder som identifieras genom inköpshistorik.
- **Innehåll och erbjudanden**:
   - **Innehållshantering**: Den här funktionen innehåller verktyg för att skapa, hantera och personalisera innehåll i olika kanaler. Du kan till exempel skapa ett återanvändbart innehållsfragment för en e-postrubrik för en kampanj.
   - **Beslutshantering**: Det här systemet använder realtidslogik för att välja det bästa erbjudandet eller meddelandet för varje enskild person. En berättigad kund kan till exempel få ett rabatterbjudande baserat på sin webbhistorik.
- **Resurs- och kampanjhantering**: Den här funktionen automatiserar sekvenser av interaktioner (resor) eller schemalägger engångsanpassade meddelanden (kampanjer). En resa utlöser till exempel uppföljning av e-postmeddelanden efter en produktvy.
- **Leverans (anslutningar)**:
   - **Kanaler**: Den här funktionen levererar meddelanden och erbjudanden via kommunikationsplattformar som e-post, SMS, push-meddelanden och direktreklam.
   - **Destinationer**: Den här funktionen exporterar profil- och målgruppsdata till externa system för aktivering eller analys. Målgruppsdata skickas till exempel till en plattform för sociala medier för målgruppsanpassning.
- **Mätning och analys**: Den här funktionen spårar kundengagemang och kampanjresultat med rapporter. Dessa insikter möjliggör kontinuerlig förbättring.

## Kontinuerlig optimeringscykel

Det här ekosystemet fungerar som en kontinuerlig optimeringscykel. Data skapar förståelse för kunderna, vilket ger bättre underlag för personaliserat innehåll och beslut. Dessa är fördelade på resor, levereras över flera kanaler, mäts efter effektivitet och förfinas över tid.

![](../assets/do-not-localize/get-started-flow.png)

## Detaljerad arkitektur

![Adobe Journey Optimizer-arkitektur](assets/ajo-architecture.png)


## Integritet och säkerhet

Adobe Experience Cloud sekretess- och säkerhetspraxis gäller Adobe Journey Optimizer. Dessa åtgärder säkerställer efterlevnad av sekretessbestämmelser, vilket gör det möjligt för varumärken att leverera personaliserade upplevelser samtidigt som kundförtroendet upprätthålls.
