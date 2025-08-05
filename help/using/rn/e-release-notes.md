---
solution: Journey Optimizer
product: journey optimizer
title: Förhandsversionsinformation för Journey Optimizer
description: Adobe Journey Optimizer Pre Release Notes
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 2%

---

# Förhandsversionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformationen](release-notes.md).

**Förhandsversionsinformationen nedan kan ändras utan föregående meddelande till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformationen](release-notes.md) på releasedatum.


## 25 förhandsversionsinformation augusti {#25-7-rn}

**Förhandsversionsinformationen nedan kan ändras utan föregående meddelande till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras på releasedatum.

Se även [Förhandsversionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Releasedatum**: 19 augusti 2025


### Nya funktioner {#Aug-25-8-features}

De nya funktionerna i den här versionen beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Pausa och återuppta resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du pausa och återuppta dina resor. Denna förmåga ger resenärerna större kontroll och flexibilitet genom att göra det möjligt att tillfälligt avbryta pågående resor utan att störa kundupplevelsen. När det är pausat skickas ingen kommunikation och profilerna förblir i ett uppehåll tills resan återupptas.</p>
<p>Du kan bara pausa och återuppta en resa, eller utföra grupppausningar och återuppta åtgärder på en grupp resor.</p>
<p>Dessutom kan du använda globala filter på pausade resor för att exkludera profiler baserat på deras attribut.</p>
<img src="assets/do-not-localize/PauseResume.gif">
<p>Den här funktionen fanns tidigare för en begränsad uppsättning kunder (begränsad tillgänglighet) och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Mer information finns i den <a href="../building-journeys/journey-pause.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>



<table>
<thead>
<tr>
<th><strong>Kalendervy</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns en kalendervy tillgänglig i rese- och kampanjlistorna. Ni kan visualisera alla resor och kampanjaktiveringar i respektive lista.</p>
<p>Den här funktionen fanns tidigare i Begränsad tillgänglighet och är nu tillgänglig i alla miljöer. I den här allmänna tillgänglighetsversionen innehåller funktionen:</p>
<ul>
<li>Designförbättringar för navigering i datum</li>
<li>Möjlighet att se utkast till kampanjer om du har angett ett start- och slutdatum</li>
<li>En ny inställning som döljer och visar kalenderobjekt som körs länge</li>
</ul>
<img src="assets/do-not-localize/calendar.gif">
<p>Mer information finns i <a href="../building-journeys/journey-ui.md#journeys-calendar">detaljerad dokumentation</a></p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Mörkt läge i e-post-Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer Email Designer erbjuder nu möjlighet att växla till vyn för mörkt läge, där du kan definiera ytterligare anpassade inställningar som bara ska visas för mottagare som läser deras e-post i mörkt läge.</p>
<p>Observera följande:</p>
<ul>
<li>Den slutliga återgivningen i mörkt läge kan variera och beror på mottagarens e-postklient.</li>
<li>Alla e-postklienter stöder inte anpassat mörkt läge. Vissa e-postklienter använder dessutom bara sitt eget mörka standardläge för alla e-postmeddelanden som tas emot. I båda fallen går det inte att återge de anpassade inställningarna som du har definierat i e-post-Designer.</li>
</ul>
<P>Funktionen finns för närvarande i betaversion och är endast tillgänglig för betatestare. Kontakta din Adobe-representant om du vill delta i betaprogrammet.</p>
<p><img src="assets/do-not-localize/dark-mode.gif"/></p>
<p>Mer information finns i den <a href="../email/dark-mode.md">detaljerade dokumentationen</a>. </p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Optimering av kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer ger er nu de verktyg ni behöver för att leverera personaliserat och optimerat innehåll till er målgrupp, så att ni kan köra innehållsexperiment, skapa regelbaserad målinriktning och använda avancerade kombinationer av båda för att maximera effektiviteten i era kampanjer.</p>
<p>Med optimering kan man</p>
<ul>
<li>Testa olika innehållsvariationer för att identifiera de mest effektiva budskapen.</li>
<li>Leverera personaliserat innehåll baserat på användarattribut och sammanhangsbaserade data.</li>
<li>Kombinera målinriktning och experiment för avancerade kampanjstrategier.</li>
<li>Filtrera bort användare som inte matchar variantvillkor.</li>
<li>Se till att reservmekanismer upprätthåller användarengagemanget.</li>
</ul>
<P>När kampanjen är aktiv utvärderas profiler mot de definierade kriterierna, och baserat på matchningskriterier levereras de med rätt erfarenhet eller innehåll från kampanjen.</p>
<p><img src="assets/do-not-localize/campaign-optimization.gif"/></p>
<!--p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p-->
</td>
</tr>
</tbody>
</table>

### Förbättringar {#Aug-25-8-improv}

Förbättringar i den här versionen visas nedan.