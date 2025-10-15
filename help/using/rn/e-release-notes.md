---
solution: Journey Optimizer
product: journey optimizer
title: Förhandsversionsinformation för Journey Optimizer
description: Adobe Journey Optimizer Pre Release Notes
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 1a5f6be689c9e91ee0dc0b5f024dbe8020424337
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 0%

---

# Förhandsversionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformationen](release-notes.md).


## 25 förhandsversionsinformation oktober {#25-10-rn}

**Förhandsversionsinformationen nedan kan komma att ändras utan föregående meddelande till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras i versionsinformationen på releasedatum.

Se även [Förhandsversionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Releasedatum**: 21-22 oktober 2025

### Nya funktioner {#oct-25-10-features}

<table>
<thead>
<tr>
<th><strong>Direktreklam, kanal på resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tidigare begränsad till Campaigns finns nu Direct Mail Channel på arbetsytan, vilket gör att du kan lägga in Direct Mail på dina resor. Direktreklam kan nu användas i både batch- och 1:1-resscenarier, med stöd för filextraheringskonfiguration och tidsbaserade frekvensinställningar.</p>
<p> Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nytt API för att hämta åtgärdskampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns ett nytt Journey Optimizer-API, som gör att du kan hämta och inspektera kampanjrelaterade data via programkod, som information, versioner och konfigurationer.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Övervakning och rapportering av anpassade åtgärder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Den här funktionen ger bättre synlighet när det gäller hälsa och utförande av resan, inklusive livscykelstatus och prestandavarningar. Nu kan ni snabbt förstå när, var och varför en onormal situation inträffar i en anpassad åtgärd.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Grundläggande RCS-meddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med det nya RCS Basic-tilläggserbjudandet kan du nu leverera grundläggande RCS-meddelanden (Rich Communication Services) i Journey Optimizer, vilket möjliggör följande förbättrade meddelandefunktioner beroende på leverantör och geografisk support:</p>
<ul>
<li><strong>Varumärkesprofilerat och verifierat avsändarstöd:</strong> Skicka meddelanden med verifierade affärsprofiler med varumärkningselement (logotyp, avsändarnamn osv.).</li>
<li><strong>Information om meddelandeleverans:</strong> Ta emot detaljerade leveransrapporter inklusive meddelandestatusuppdateringar (t.ex. skickade, levererade, lästa).</li>
<li><strong>Länkspårning:</strong> Bädda in och spåra URL:er i RCS-meddelanden för engagemangsanalys.</li>
<li><strong>Återställning till SMS:</strong> Automatisk återgång till SMS när mottagarens enhet inte stöder RCS eller inte kan nås via RCS.</li>
<li><strong>Grundläggande meddelandekomposition:</strong> Skicka grundläggande textbaserade RCS-meddelanden.</li>
</ul>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Direktreklamkanal i samordnade kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Direktreklamkanalen finns nu tillgänglig i samordnade kampanjer. Aktiviteten Direktutskick underlättar direktutskick inom din samordnade kampanj, både för enstaka och återkommande meddelanden. Den automatiserar processen för att generera extraheringsfilen som krävs av direktreklamleverantörer. Ni kan kombinera kanalaktiviteter i den orkestrerade kampanjarbetsytan för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nya källkopplingar för lojalitetsappar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns nya källkopplingar i Adobe Experience Platform för Talon.One, Capillary och Kobie loyalty Apps. Med dessa kopplingar kan ni smidigt strömma lojalitetsdata till Adobe Experience Platform och utnyttja dessa data i Journey Optimizer.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Beslutsstöd i e-postkanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni lägga till beslutsprinciper i e-postresor och -kampanjer. Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för att dynamiskt returnera det bästa innehållet för varje målgruppsmedlem.</p>
<p> Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Stort genomströmningsläge för API-utlösta e-postkampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns det ett nytt högfrekvensläge tillgängligt i API-utlösta kampanjer. Det här läget är utformat för storskaliga meddelanden i realtid (upp till 5 000 transaktioner per sekund) och ger högre tillgänglighet med lägre latens.</p>
<p>Den här funktionen är endast tillgänglig för e-postkanalen, för organisationer som har köpt tillägget Adobe High-through transactional messaging. Kontakta Adobe om du vill ha mer information.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Tysta timmar/tidsbaserade undantag</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med tysta timmar kan du definiera tidsbaserade undantag för e-post-, SMS-, push- och whatsApp-kanaler. De ser till att inga meddelanden skickas under särskilda tidsperioder och hjälper er att följa kundönskemål och krav på regelefterlevnad.</p>
<p>Du kan lägga till tysta timmar genom regeluppsättningar, som kan tilldelas enskilda åtgärder i kampanjer eller resor för exakt kontroll. Genom att effektivisera dessa processer.</p>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Ny hjälpfunktion för körningsmetadata</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny hjälpfunktion för executionMetadata finns i personaliseringsredigeraren. Det gör att du kan lägga till sammanhangsbaserad information till alla inbyggda åtgärder och hämta den i en datauppsättning för export till externa system.</p>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<p>Tillgänglighetsdatum: 13 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Experimentent</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Experimentationsagenten är ett AI-drivet verktyg som moderniserar hur du kan köra och hantera digitala experiment på webbplatser, i e-postmeddelanden, push-meddelanden och program. Experimentationsagenten bygger på Adobe Experience Platform AI-plattformen och experimenteringsverktygen och hjälper dig att köra experiment effektivare, organisera affärsmålen och generera åtgärdbara insikter, framhäva vad som fungerade, vad som inte gjorde det och var du ska experimentera härnäst.</p>
<p>Som en del av den nya Experimentation Accelerator-funktionen levererar agenten:</p>
<ul>
<li><strong>Prestanda:</strong> en tydlig vy av vad som hände i experimentet</li>
<li><strong>Insikter:</strong> - en förklaring av varför resultatet inträffade</li>
<li><strong>Affärsmöjligheter:</strong> vägledning om nästa åtgärd som ska vidtas</li>
</ul>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<p>Tillgänglighetsdatum: 9 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Offentligt API för att hämta resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Det finns nu ett nytt Journey Optimizer-API för att hämta resor och tillhörande objekt som kampanjer och ytor.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<p>Tillgänglighetsdatum: 25 september 2025</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

- **Kampanjer, Experience Decision, Journeys**
   - **Välj återanvändbara regler i mål** - Nu kan du utnyttja regelbyggaren när du använder målregler med meddelandeoptimeringsfunktionen i resor och kampanjer. <!-- [Read more](../FILE.md) -->

- **Kanal - whatsApp**
   - **Körningsfält för WhatsApp-kanal** - Förutom e-post och SMS är det nu möjligt att uppdatera standardkörningsfältet för WhatsApp. Det går också att åsidosätta körningsfältet som angetts globalt i de avancerade parametrarna för WHatsApp-reseaktiviteten eller i konfigurationen för WhatsApp-kanalen. <!-- [Read more](../FILE.md) -->

- **Behörigheter**
   - **Den som skapar en resa/kampanj ska inte kunna godkänna** - ett alternativ lades till när en godkännandeprincip skapades eller ställdes in för att förhindra att den som skapar en resa/kampanj godkänner sina egna objekt. <!-- [Read more](../FILE.md) -->

- **Kanal - tryck**
   - **Mobila Live-aktiviteter - privat beta** - Live-aktiviteter tillhandahåller uppdateringar i realtid och interaktiva upplevelser i mobilappar, så att användarna kan hålla sig informerade om pågående händelser eller uppgifter direkt på enhetens skärm. Den här funktionen förbättrar engagemanget genom att leverera live-information, som förloppsspårning, händelseuppdateringar eller interaktivt innehåll, utan att användarna behöver öppna appen. <!-- [Read more](../FILE.md) -->

- **Resor**
   - **Nya reseaviseringar** - Tillgänglighetsdatum: 14 oktober 2025
Nya förkonfigurerade aviseringar är tillgängliga för resor: Profilborttagningsfrekvensen har överskridits (förhållandet mellan antal ignorerade profiler och angivna profiler under de senaste 5 minuterna har överskridits), felfrekvensen för anpassade åtgärder har överskridits (förhållandet mellan anpassade åtgärdsfel och slutförda HTTP-anrop under de senaste 5 minuterna har överskridits), Profilfelsfrekvensen har överskridits (förhållandet mellan profiler och fel som angetts under de senaste 5 minuterna). <!-- [Read more](../FILE.md) -->

- **Konfiguration**
   - **Stöd för anpassade attribut med en klickning för att avbryta prenumerationen** - Tillgänglighetsdatum: 6 oktober 2025
Med Journey Optimizer kan du, om du hanterar samtycke utanför Adobe, ange en extern anpassad slutpunkt genom att definiera en egen länk för att avbryta prenumerationen i e-postkonfigurationen. När mottagarna klickar på länken för att avbryta prenumerationen lägger Journey Optimizer till vissa standardprofilspecifika parametrar i händelsen för att skicka medgivandeuppdatering. Om du vill anpassa e-postadressen för att avbryta prenumerationen ytterligare kan du nu definiera anpassade attribut som läggs till i medgivandehändelsen. Den här funktionen har redan varit tillgänglig för den anpassade URL:en för ett klick sedan 25 augusti och har nu släppts för alternativet Mailto (unsubscribe) med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst. <!-- [Read more](../FILE.md) -->

- **Kanal - e-post**
   - **PDF-bilagor till e-postmeddelanden** - Tillgänglighetsdatum: 30 september 2025
Du kan nu bifoga en statisk PDF-fil i ett e-postmeddelande som skickas med Journey Optimizer. Du kan skicka upp till 6 meddelanden med en bifogad PDF-fil per profil och år. Den största tillåtna filstorleken för varje bifogad fil är 5 MB. För ytterligare storlekar och volymer kan du köpa tillägget PDF-bilaga. Mer information får du av Adobe.

  >[!AVAILABILITY]
  >
  >Den här förbättringen fanns tidigare i Begränsad tillgänglighet och är nu tillgänglig i alla miljöer (Allmän tillgänglighet).

  <!-- [Read more](../FILE.md) -->

