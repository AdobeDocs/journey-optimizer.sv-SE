---
solution: Journey Optimizer
product: journey optimizer
title: Tidig versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
topic: Content Management
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 4e405fe395c8432ed22d64887631b222df83a3e9
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 3%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformationen](release-notes.md).

**Noteringar om tidig version nedan kan ändras utan föregående meddelande till releasedatum**. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformationen](release-notes.md) på releasedatum.

## Februari 25 Information om tidig version {#25-02-rn}

### Nya funktioner {#25-02-features}

De nya funktionerna i den här versionen beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Skapa och hantera affärsregler</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa affärsregler med hjälp av regeluppsättningar. Regeluppsättningar är grupper av regler som hjälper er att begränsa skickade meddelanden inom kampanjer och reseåtgärder över flera kanaler, och att kontrollera profilinmatningar under resor.<p>
<p><ul><li>Skapa kanalregeluppsättningar för att begränsa antalet meddelanden som skickas över en eller flera kanaler. Använd dem på kampanjer eller reseåtgärder för att tillämpa de regler som definieras i regeluppsättningen. Med kanalregeluppsättningen kan du tillämpa regler för appning baserat på kommunikationstyper. Ange till exempel en regeluppsättning som begränsar"kampanjmeddelanden" och en annan för"nyhetsbrev". Använd rätt regeluppsättning i kampanjen eller reseåtgärden beroende på vilken typ av kommunikation du skickar.</li>
<li> Skapa uppsättningar av resegler för att styra profilposter till resor. Begränsa hur ofta en profil kan ta sig in på en resa inom en viss period eller hur många resor en profil kan registreras samtidigt. Använd dessa på resenivå för att säkerställa en korrekt hantering av inträde på arbetsmarknaden.</li></p>
<p>Affärsreglerna fanns tidigare för en uppsättning organisationer (LA) och är nu tillgängliga för alla användare (GA).</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Flerregionalt stöd för SMS</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu hantera SMS-meddelandeleverans från flerregionala slutpunkter genom att åsidosätta leverans-, feedback-, inkommande- och callback-URL:er. För att detta ska fungera har en ny åsidosättnings-URL lagts till i konfigurationen för API-autentiseringsuppgifter. Den här ändringen är endast tillgänglig för SINK-providern.</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Generera landningssidor med AI Assistant</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI Assistant finns nu för leverans av landningssidor, vilket gör att du kan generera text, bilder eller hela sidlayouter.</p>
<!--img src="assets/do-not-localize/ai-lp.gif">
<p>For more information on AI Assistant, refer to the <a href="../email/generative-lp.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Varumärkesriktlinjer (beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni ange egna varumärkesriktlinjer för att definiera varumärkets visuella och verbala identitet. Observera att funktionen Varumärke släpps som en privat betaversion och kommer att finnas tillgänglig för alla kunder i framtida versioner.</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>



<table>
<thead>
<tr>
<th><strong>Flexibel målgruppsutvärdering (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med flexibel målgruppsutvärdering kan ni köra ett segmenteringsjobb på begäran för utvalda målgrupper, vilket säkerställer att ni alltid har de senaste målgruppsdata innan ni inriktar dem på Journey Optimizer resor och kampanjer.</p>
<img src="assets/do-not-localize/flexible-audience.gif">
<p>Mer information finns i den <a href="../audience/about-audiences.md#flexible">detaljerade dokumentationen</a>.</p>
<p> Flexibel målgruppsutvärdering är bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Tillgänglighetsdatum: 28 januari 2025</p>
</tr>
</tbody>
</table>



<table>
<thead>
<tr>
<th><strong>Customer Journey Analytics-mallar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du förbättra dina Journey Optimizer-rapporter genom att använda Customer Journey Analytics-mallar. Med den här nya funktionen kan ni effektivisera rapporteringsprocessen med fördesignade mallar som är anpassade efter era analysbehov.
</p>
<img src="assets/do-not-localize/cja-templates.gif">
<p>Mer information finns i den <a href="../reports/report-cja-manage.md#cja-template">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: från 15 januari 2025</p>
</tr>
</tbody>
</table>




### Förbättringar {#25-02-improvements}

Förbättringarna nedan följer med uppdateringen från februari.

* **Resor** - Nu kan du testa dina anpassade åtgärder genom att skicka API-anrop från administrationsavsnittet. Den här nya funktionen hjälper dig att felsöka anpassade åtgärder innan du har använt dem under en resa.

* **Datauppsättning TTL (Time-to-live)** - Från och med den här månaden kommer ett TTL-skyddsprotokoll att introduceras i Journey Optimizer systemgenererade datauppsättningar i nya sandlådor och nya orgs enligt följande:

   * 90 dagar för data i profilarkivet
   * 13 månader för data i sjön

  Den här ändringen kommer att introduceras i befintliga kundsandlådor i en efterföljande fas.

  Läs mer om den här uppdateringen i [de här dedikerade vanliga frågorna](../data/datasets-ttl.md#frequently-asked-questions).

<!--* **Playbooks** - You can now create and publish your own Use Case Playbooks in Journey Optimizer.-->

* **Direktutskick** - En ny servertyp, Datalandningszon, stöds nu för filroutning i konfigurationen för direktutskick.

**Personalization**

<!--
* The personalization editor has been enhanced with new capabilities such as Auto-complete, Search, and filtering options. You can also show or hide deprecated attributes.-->

* Tillgänglighetsdatum: 29 januari 2025 - nya hjälpfunktioner för datum/tid finns tillgängliga för användning i personaliseringsredigeraren. [Läs mer](../personalization/functions/dates.md)

**E-postkonfiguration** - Tillgänglighetsdatum: 12 feb 2025

* Om du hanterar samtycke utanför Adobe kan du nu ange en anpassad e-postadress för att avbryta prenumerationen och en anpassad URL för att avsluta prenumerationen som en del av inställningarna för e-postkanalen. [Läs mer](../email/list-unsubscribe.md#custom-managed)

  ![](../email/assets/surface-list-unsubscribe-custom.png){width="80%"}

**Beslut** - Tillgänglighetsdatum: 28 januari 2025

* Beslutsfattandet har nu stöd för datatyperna Object när objektkatalogens schema redigeras. [Läs mer](../experience-decisioning/catalogs.md)