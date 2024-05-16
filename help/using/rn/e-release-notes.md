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
source-git-commit: b5e073ef1d0c579f430913d60442d7d4cfa620a3
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 5%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation maj 2024 {#e-2024}

**Releasedatum**: 21-22 maj 2024

### Nya funktioner {#e-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.


<table>
<thead>
<tr>
<th><strong>Experience Decision - begränsad tillgänglighet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Experience Decision förenklar personaliseringen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas beslutsposter och en sofistikerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person.</p>
<p>Dessa beslutsobjekt integreras smidigt i ett stort antal inkommande ytor via den nya kodbaserade upplevelsekanalen, som nu är tillgänglig inom Journey Optimizer-kampanjer. Policy för Experience Decision-beslut är endast tillgängliga för kodbaserade upplevelsekampanjer.</p>
<p>Experience Decision är för närvarande bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<img src="assets/do-not-localize/gif-exd.gif"/>
<p>Mer information finns i den <a href="../experience-decisioning/gs-experience-decisioning.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Arbetsflöde för IP-förstärkning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Om du skickar e-post till en helt ny IP-adress kan du nu enkelt utföra arbetsflöden för IP-värmare direkt från användargränssnittet. Adobe Journey Optimizer erbjuder ett standardiserat och effektivt sätt att värma upp era IP-adresser som följer de bästa metoderna för optimal leverans.</p>
<p>Mer information finns i den <a href="../configuration/ip-warmup-gs.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Affärsregler - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa regler för exakt frekvensbegränsning och tillämpa dem på olika typer av marknadsföringskommunikation via regeluppsättningar. Med den här nya funktionen kan ni styra hur ofta era målgrupper får ett meddelande genom att ställa in flerkanalsregler som automatiskt utesluter överbegärda profiler från meddelanden och åtgärder.</p>
<p>Funktionen för affärsregler är för närvarande endast tillgänglig som en betaversion.</p>
<p>Mer information finns i den <a href="../configuration/business-rules.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Utökade personaliseringsdata - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du söka efter och hämta datavärden i Adobe Experience Platform datamängder och använda dessa värden för att skapa villkor i Adobe Journey Optimizer. Du kan utnyttja data från en uppslagsdatauppsättning när en relation har definierats med ett attribut inuti en objektmatris. Du kan ange datauppsättningar som inte är profilaktiverade för sökning. När det är aktiverat kan du använda ett profilattribut som en kopplingsnyckel till den angivna datauppsättningen för att hämta ytterligare data för personalisering.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Experience Decision**

Från betaversion till den här versionen har följande förbättringar lagts till:

* **Experience Decision + Code-based experiences (LA)** - Nu kan ni utnyttja beslutsfunktionen i Experience för att använda beslutsobjekt i era kodbaserade kampanjer. Obs! Den kodbaserade upplevelsekanalen och Experience Decision är inte tillgängliga för organisationer som har köpt Adobe Healthcare Shield och tillägg till Privacy and Security Shield. [Läs mer](../code-based/get-started-code-based.md)
* **Kontextdata** - Nu kan du utnyttja kontextdata från Adobe Experience Platform i dina regler för beslutsfattande och rangordningsformler. [Läs mer](../experience-decisioning/context-data.md)
* **Ny behörighet** - Det finns nu en ny behörighet för att hantera Experience Decision Management-resursen. Det gör att ni kan hantera rättigheter för Experience Decision. [Läs mer](../experience-decisioning/gs-experience-decisioning.md)
* **Begränsningsregler** - Du kan nu lägga till flera regler för att sätta stopp för ett visst beslutsobjekt i Experience Decisioning. På så sätt kan ni öka kontrollen över hur erbjudandena skickas. [Läs mer](../experience-decisioning/items.md#capping)
* **Rapportering** - Nu kan du skapa anpassade rapportinstrumentpaneler för Experience Decision-kampanjer med [!DNL Customer Journey Analytics]. [Läs mer](../experience-decisioning/cja-reporting.md)


**Beslutshantering**

* **Stöd för flera regler** - Du kan nu lägga till upp till 10 regler om begränsning av ett visst erbjudande i Beslutshantering. På så sätt kan ni öka kontrollen över hur erbjudandena skickas.
* **Granskningar** - **Ändra logg** så att du kan se alla ändringar som har gjorts i ett erbjudande eller ett beslut har tagits bort. Ändringar som rör erbjudanden och beslut kan nu ses i **Granskningar** -menyn.


**E-postkanal**

* **List-unsubscribe** - Efter de senaste Gmail- och Yahoo-meddelandena om bulkavsändare stöder Journey Optimizer alternativet&quot;post/1-click&quot; List-Unsubscribe.
* **Skräddarsy poäng** (Beta) - Nu kan du kontrollera ditt innehåll som skräppost i en dedikerad skräppostrapport. Med SpamAssassin kan Adobe Journey Optimizer nu testa ditt e-postinnehåll och ge det ett poängvärde som anger om internetleverantörer kommer att betrakta det som skräppost eller inte. [Läs mer](../content-management/spam-report.md)


**Publiker**

* Målgrupper och attribut från målgruppssammansättning och anpassad uppladdning (CSV-fil) kan nu användas med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.

**Personalisering**

* **Uttrycksfragment** - Uttrycksfragment är nu tillgängliga för **Kanal i appen**. [Läs mer](../personalization/use-expression-fragments.md)

**Resor**

* **Sammanfoga profiler** (Begränsad tillgänglighet) - Sammanslagningsprinciper som används av en resa är nu synliga och konsekventa under hela resan.
* **Stöd för mTLS** - mTLS-protokollet stöds nu i Journey Optimizer API:er och anpassade åtgärder.
* **Sök tabeller i händelser** - Du kan nu utnyttja data från en uppslagsdatauppsättning när en relation har definierats med ett attribut inuti en objektmatris. Uppslagsvärdena är tillgängliga i resor (villkor, anpassade åtgärder osv.) och personalisering av meddelanden.
