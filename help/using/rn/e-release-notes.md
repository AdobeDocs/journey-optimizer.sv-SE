---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 570f50a86288378c26f967f4861f19b9da9f96cf
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 4%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation januari 2024 {#e-2024}

**Releasedatum**: 20-31 januari 2024

### Nya funktioner{#e-features}

Den här versionen innehåller de nya funktionerna som listas nedan.


<table>
<thead>
<tr>
<th><strong>Uppdateringar om leveransbarhet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer stöder nu tekniken för DMARC-autentisering.</p>
<p>Från och med 1 februari 2024, Google och Yahoo! kommer att kräva att du har en DMARC-post för alla domäner som du använder för att skicka e-post till dem. Se till att du har ställt in DMARC-posten för alla underdomäner som du har delegerat eller delegerat till Adobe i Journey Optimizer.</p>
<!--img src="assets/channel-reports.png"/-->
<p>Mer information finns i den <a href="../configuration/dmarc-record.md">detaljerade dokumentationen</a>.</p>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Använd fallspelningsböcker</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Använd en katalog med branschspecifika fallspelningsböcker i Real-Time CDP och Journey Optimizer för att hantera vanliga användningsområden som du kan använda Adobe Experience Platform och Adobe Journey Optimiser.</p><p>När du har valt den spelbok som bäst passar dina behov kan du aktivera den för att generera de resurser som behövs för att stödja ditt användningssätt, som resor, meddelanden, scheman eller segment, och anpassa dem till ditt schema för snabbare time-to-value.</p>
<br/><img src="assets/do-not-localize/playbooks.gif"/>
<!--<p>For more information, refer to the <a href="../start/playbooks.md">detailed documentation</a>.</p>-->
</tr>
</tbody>
</table>

### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Rapporter**

* **Nya domänbaserade uppdelningswidgetar** - Nya widgetar har lagts till för att förbättra kampanjrapporten och reserapporten. The **Studsa orsaker efter domän**, **Skickat och levererat av domäner**, **Öppnar och klickar per domän** och **Studsa och fel efter domän** widgetar ger en detaljerad beskrivning på domännivå för viktiga e-postleveranser och spårningsvärden. [Läs mer](../reports/channel-report.md)

**SMS-kanal**

* **Dubbel anmälan** - Arbetsflödet för dubbel anmälan för SMS garanterar att användare uttryckligen väljer att ta emot meddelanden när begäran initieras från sin enhet. Användarna initierar godkännandeprocessen genom att skicka ett inkommande SMS-meddelande. När de har bekräftat sitt samtycke skickas ett uppföljningsmeddelande med en begäran om slutlig verifiering. Om en användarprofil inte finns skapas den när den har bekräftats. [Läs mer](../sms/sms-configuration.md#create-api)

  Observera att detta endast gäller SMS-leverantörer för Sinch och Infobip.

**Resor**

* **Varaktighet för reaktionshändelser** - Den maximala varaktighet som du kan definiera i **Reaktionshändelser** är nu 29 dagar i stället för 30. [Läs mer](../building-journeys/reaction-events.md)

<!--* **Date filters** - You can now use custom dates to filter the journeys inventory, in addition to the existing predefined date filters. This allows you to refine the list by displaying journeys published on a specific date, within a particular month, throughout an entire year, or within specified time ranges. [Learn more](../building-journeys/journey-gs.md#filter)-->

* **Läsa målgrupper**  - Aktiviteten Läs målgrupp bygger nu på datamängden med profilögonblicksbilder för gruppsegment, som bara genereras en gång om dagen efter att det schemalagda dagliga batchjobbet har körts, och därför kommer data att uppdateras till det senaste batchjobbet.

* **Fältgrupper** - Åtgärdade ett problem som innebar att fältgrupper blockerades för att sparas i vissa fall.

**Frekvensregler**

* **Frekvensbegränsning varje vecka och dag** - Du kan nu ange maximalt antal meddelanden som skickas till en kundprofil under en vecka eller en dag, utöver månaden. Frekvensbegränsningen baseras på den valda kalenderperioden och återställs i början av motsvarande tidsram. [Läs mer](../configuration/frequency-rules.md#create-new-rule)

**Beslutsledning**

* **Frekvensbegränsning på Edge** - Räknaren för frekvensbegränsning har nu uppdaterats och är tillgänglig i ett beslut av Edge Decisioning API på mindre än 3 sekunder.