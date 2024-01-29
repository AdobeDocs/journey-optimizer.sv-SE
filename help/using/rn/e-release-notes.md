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
source-git-commit: fd6f83019aa9cd5b4d6561007f5e0068256bb211
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 3%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation januari 2024 {#oct-jan-2024}

**Releasedatum**: 30-31 januari 2024

### Nya funktioner{#jan-2024-features}

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
<p>Mer information finns i den <a href="../configuration/dmarc-record-update.md">detaljerade dokumentationen</a>.</p>
</tr>
</tbody>
</table>



### Förbättringar {#jan-2024-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Rapporter**

* **Nya domänbaserade uppdelningswidgetar** - Nya widgetar har lagts till för att förbättra kampanjrapporten och reserapporten. The **Studsa orsaker efter domän**, **Skickat och levererat av domäner**, **Öppnar och klickar per domän** och **Studsa och fel efter domän** widgetar ger en detaljerad beskrivning på domännivå för viktiga e-postleveranser och spårningsvärden.

**SMS-kanal**

* **Dubbel anmälan** - Arbetsflödet för dubbel anmälan för SMS garanterar att användare uttryckligen väljer att ta emot meddelanden när begäran initieras från sin enhet. Användarna initierar godkännandeprocessen genom att skicka ett inkommande SMS-meddelande. När de har bekräftat sitt samtycke skickas ett uppföljningsmeddelande med en begäran om slutlig verifiering. Om en användarprofil inte finns skapas den när den har bekräftats.

  Observera att detta endast gäller SMS-leverantörer för Sinch och Infobip.

**Resor**

* **Varaktighet för reaktionshändelser** - Den maximala varaktighet som du kan definiera i **Reaktionshändelser** är nu 29 dagar i stället för 30.

* **Datumfilter** - Du kan nu använda anpassade datum för att filtrera reselagret, utöver de befintliga fördefinierade datumfiltren. På så sätt kan du förfina listan genom att visa resor som publicerats ett visst datum, inom en viss månad, under ett helt år eller inom angivna tidsintervall.

* **Läsa målgrupper**  - Aktiviteten Läs målgrupp är nu beroende av data om profilögonblicksbilder för gruppsegment, som bara genereras en gång om dagen efter att det schemalagda dagliga batchjobbet har körts.

**Frekvensregler**

* **Frekvensbegränsning varje vecka och dag** - Du kan nu ange maximalt antal meddelanden som skickas till en kundprofil under en vecka eller en dag, utöver månaden. Frekvensbegränsningen baseras på den valda kalenderperioden och återställs i början av motsvarande tidsram.


**Beslutsledning**

* **Frekvensbegränsning på Edge** - Räknaren för frekvensbegränsning har nu uppdaterats och är tillgänglig i ett beslut av Edge Decisioning API på mindre än 3 sekunder.