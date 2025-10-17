---
solution: Journey Optimizer
product: journey optimizer
title: Förhandsversionsinformation för Journey Optimizer
description: Adobe Journey Optimizer Pre Release Notes
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 1ecf54bbcb2cc62b5f13434cfbf1e369cd145d93
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 1%

---

# Förhandsversionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformationen](release-notes.md).


## 25 förhandsversionsinformation oktober {#oct-25-10-rn}

**Förhandsversionsinformationen nedan kan komma att ändras utan föregående meddelande till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras i versionsinformationen på releasedatum.

Se även [Förhandsversionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Releasedatum**: 22 oktober 2025

### Nya funktioner {#oct-25-10-features}



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

<!--table>
<thead>
<tr>
<th><strong>RCS Basic Messaging</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>With the new RCS Basic add-on offering, you can now deliver basic Rich Communication Services (RCS) messaging in Journey Optimizer, enabling the following enhanced messaging capabilities subject to provider and geographical support:</p>
<ul>
<li><strong>Branded and verified sender support:</strong> Send messages using verified business profiles with branding elements (logo, sender name, etc.).</li>
<li><strong>Message delivery insights:</strong> Receive detailed delivery reports including message status updates (e.g., sent, delivered, read).</li>
<li><strong>Link tracking:</strong> Embed and track URLs within RCS messages for engagement analytics.</li>
<li><strong>Fallback to SMS:</strong> Automatic fallback to SMS when the recipient's device does not support RCS or is temporarily unreachable via RCS.</li>
<li><strong>Basic message composition:</strong> Send basic text-based RCS messages.</li>
</ul>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Direct mail channel in Orchestrated campaigns</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Direct mail channel is now available in orchestrated campaigns. The Direct mail activity facilitates direct mail sending within your Orchestrated campaign, for both one-time and recurring messages. It serves to automate the process of generating the extraction file required by direct mail providers. You can combine channel activities into the Orchestrated campaign canvas to create cross-channel campaigns that can trigger actions based on customer behavior and data.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Direct Mail channel in journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Previously limited to Campaigns, Direct Mail channel is now available on the journey canvas, enabling you to incorporate Direct Mail into your journeys. Direct Mail can now be used in both batch and 1:1 journey scenarios, with support for file extraction configuration and time-based frequency settings.</p>
<p> Previously released in Limited Availability, this capability is now available to all environments (General Availability).</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

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
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
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
<th><strong>Återanvändbara målinriktningsregler</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Journey Optimizer kan ni nu skapa regler från en dedikerad användargränssnittsmeny och utnyttja dem när ni bygger målinriktning, antingen som en del av optimeringen av innehåll i en kampanj eller en resa, antingen i optimeringsprocessen.</p>
<p>Målreglerna är för närvarande begränsade. Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Observera att den här funktionen endast är tillgänglig för organisationer som har köpt tilläggserbjudandet för beslut. Den kommer att successivt lanseras för alla kunder.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Teman i e-post-Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni snabbt tillämpa förgodkända teman för att säkerställa ett enhetligt varumärke i alla e-postmeddelanden, snabba upp kampanjprocessen och oberoende producera högkvalitativa e-postmeddelanden samtidigt som ni minskar beroendet av designteam.</p>
<p>Tidigare släppt i betaversion är den här funktionen nu tillgänglig för ett antal organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<img src="assets/do-not-localize/themes.gif">
<p>Mer information finns i den <a href="../email/apply-email-themes.md">detaljerade dokumentationen</a>.</p>
<!--p>Availability date: October 22, 2025</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nya reseaviseringar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Det finns nya förkonfigurerade aviseringar som kan övervaka din resa:</p>
<ul><li><a href="../reports/alerts.md#alert-discard-rate">Frekvensen för ignorerade profiler överskreds</a>: Profilförhållandet mellan ignorerade profiler och angivna profiler under de senaste 5 minuterna överskred tröskelvärdet</li>
<li><a href="../reports/alerts.md#alert-custom-action-error-rate">Felfrekvens för anpassad åtgärd överskreds</a>: Förhållandet mellan anpassade åtgärdsfel och lyckade HTTP-anrop under de senaste 5 minuterna överskred tröskelvärdet</li>
<li><a href="../reports/alerts.md#alert-profile-error-rate">Profilens felfrekvens har överskridits</a>: Profilernas felförhållande till de angivna profilerna under de senaste 5 minuterna överskred tröskelvärdet.</li></ul> <p>Du kan ändra tröskelvärden och prenumerera på enskilda varningar på resenivå jämfört med globalt.</p>
<p>Mer information finns i <a href="../reports/alerts.md">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 14 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Hjälp för körningsmetadata</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny hjälpfunktion, executeMetadata, är tillgänglig i personaliseringsredigeraren. Det gör att du kan lägga till sammanhangsbaserad information till alla inbyggda åtgärder och hämta den i en datauppsättning för export till externa system.</p>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Mer information finns i <a href="../personalization/functions/helpers.md#execution-metadata">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 13 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Experimentationsagenten är här!</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Experimenteringsagenten tillhandahålls av <a href="https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator.html" target="_blank">Adobe Experience Platform Agent Orchestrator</a> och är tillgänglig i Journey Optimizer. </p>
<p>Experimentationsagenten är ett AI-drivet verktyg som moderniserar hur du kan köra och hantera digitala experiment på webbplatser, i e-postmeddelanden, push-meddelanden och program. Det hjälper er att köra experiment effektivare, organisera affärsmålen och generera åtgärdbara insikter, framhäv vad som fungerade, vad som inte gjorde det och var ni ska experimentera härnäst.</p>
<p>Mer information finns i <a href="https://experienceleague.adobe.com/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-experiment.html?lang=sv-SE" target="_blank">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 10 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>PDF bilagor till e-postmeddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu bifoga en statisk PDF-fil i ett e-postmeddelande som skickas med Journey Optimizer.</p>
<ul>
<li>Du kan skicka upp till 6 meddelanden med en PDF-bilaga per profil och år.</li>
<li>Den största tillåtna filstorleken för varje bifogad fil är 5 MB.</li>
<li>För ytterligare storlekar och volymer kan du köpa tillägget PDF-bilagor. Mer information får du av Adobe.</li>
</ul>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p><img src="assets/do-not-localize/pdf-attachments.gif"/></p>
<p>Mer information finns i <a href="../email/pdf-attachments.md">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 30 september 2025</p>
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
<p>Mer information finns i <a href="https://developer.adobe.com/journey-optimizer-apis/references/journeys-retrieve/">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 25 september 2025</p>
</td>
</tr>
</tbody>
</table>


### Förbättringar

**Körningsfält för WhatsApp-kanal**

Förutom E-post och SMS kan du även uppdatera standardkörningsfältet för dina WhatsApp-leveranser på sandlådenivå. Det går också att åsidosätta körningsfältet som angetts globalt genom att ändra det i de avancerade parametrarna för whatsApp-reseaktiviteten eller i konfigurationen för WhatsApp-kanalen. <!-- [Read more](../FILE.md) -->

**Stöd för anpassade attribut för adressen Mailto (unsubscribe)**

Med Journey Optimizer kan du, om du hanterar samtycke utanför Adobe, ange externa anpassade slutpunkter genom att definiera en egen länk för att avbryta prenumerationen och en anpassad e-postadress för att avbryta prenumerationen i e-postkonfigurationen. När mottagarna klickar på länken för att avbryta prenumerationen lägger Journey Optimizer till vissa standardprofilspecifika parametrar i händelsen för att skicka medgivandeuppdatering.

Om du vill anpassa dina anpassade slutpunkter ytterligare kan du nu definiera anpassade attribut som också läggs till i medgivandehändelsen. [Läs mer](../email/list-unsubscribe.md#custom-attributes)

>[!AVAILABILITY]
>
>Den här funktionen har redan varit tillgänglig för den anpassade **[!UICONTROL One-click Unsubscribe URL]** sedan 25 augusti och har nu släppts för alternativet **[!UICONTROL Mailto (unsubscribe)]** med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

Tillgänglighetsdatum: 6 oktober 2025