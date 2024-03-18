---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
topic: Content Management
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 4f7a62cdfbd90b2d33341342f6fba769e8bf0132
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 6%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation mars 2024 {#e-2024}

**Releasedatum**: 19-20 mars 2024

### Ny funktion {#e-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Kodbaserade upplevelser</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med den nya kodbaserade upplevelsekanalen kan du med Adobe Journey Optimizer utföra avancerad personalisering och testning för alla dina inkommande egenskaper, vilket möjliggör smidig leverans av skräddarsydda upplevelser över olika kontaktytor som webbappar, mobilappar, datorprogram, videokonsoler, tv-anslutna enheter, smarta tv-apparater, kioskdatorer, ATM-enheter, IoT-enheter med mera.</p>
<P>Viktiga funktioner:</p>
<ul><li> Universell personalisering: utöka personaliserade upplevelser över alla kontaktytor för att säkerställa en sammanhängande och skräddarsydd användarresa</li>
<li>Detaljerad redigeringsprecision: redigera specifikt innehåll på enskilda platser i dina program eller webbsidor</li>
<li>Mångsidig implementering: stöd för implementeringsmetoder på serversidan, API-baserade eller SDK-baserade, för smidig integrering med utvecklingsmiljön.</li></ul></p>
<p>Mer information finns i den <a href="../code-based/get-started-code-based.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/code-based.gif">
</tr>
</tbody>
</table>

### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Innehållsmallar**

* **Miniatyrbild** - A **miniatyrbildsvisning** är nu tillgängligt för innehållsmallar och fragment för förbättrad visuell åtkomst. [Läs mer](../content-management/content-templates.md#template-thumbnails)

**Resor**

Nya mellanliggande statusvärden har lagts till i reseutvecklingscykeln:

* **Publicering** status mellan **Utkast** status och **Live** status
* **Stoppar** status mellan **Live** status och **Stoppad** status
* **Aktiverar testläge** eller **Inaktiverar testläge** statusvärden mellan **Utkast** status och **Utkast (test)** status

När en resa befinner sig i ett mellanliggande tillstånd är den skrivskyddad.