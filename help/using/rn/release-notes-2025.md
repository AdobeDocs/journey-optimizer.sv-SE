---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation 2025
description: Versionsinformation om Journey Optimizer 2025
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: aa8c74de-748b-4947-a972-14703f6ab4a7
source-git-commit: 9d87d133bb580ebed94a265beded5895f7fd0301
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 7%

---

# Versionsinformation för 2025 {#release-notes-2025}

På den här sidan visas alla funktioner och förbättringar för [!DNL Journey Optimizer] som släpptes 2025.

## Versionsinformation 25 februari {#25-02-rn}

**Releasedatum**: 18-19 februari 2025


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
<li> Skapa uppsättningar av resegler för att styra profilposter till resor. Begränsa hur ofta en profil kan ta sig in på en resa inom en viss period eller hur många resor en profil kan registreras samtidigt. Använd dessa på resenivå för att säkerställa en korrekt hantering av inträde på arbetsmarknaden.</li></ul></p>
<p>Affärsreglerna fanns tidigare för en uppsättning organisationer (LA) och är nu tillgängliga för alla användare (GA). Affärsreglerna för resedomäner är fortfarande bara tillgängliga för ett begränsat antal organisationer (LA).</p>
<p>Mer information finns i den <a href="../configuration/rule-sets.md">detaljerade dokumentationen</a>.</p>
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
<p>Med hjälp av AI Assistant kan du nu skapa övertygande innehåll för landningssidor, inklusive helsidesdesign, skräddarsydd text och anpassade bilder.</p>
<img src="assets/do-not-localize/ai-lp.gif">
<p>Mer information finns i den <a href="../content-management/generative-lp.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Varumärken med AI Assistant (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni skapa egna varumärken för att definiera ert varumärkes visuella och verbala identitet. </p>
<p>Den här funktionen lanseras som en privat betaversion för en begränsad uppsättning kunder. Den kommer att finnas tillgänglig successivt för alla kunder i framtida versioner.</p>
<p>Mer information finns i den <a href="../content-management/brands.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Felsöka anpassade åtgärder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du validera en anpassad åtgärdskonfiguration genom att göra riktiga API-anrop direkt från Adobe Journey Optimizer. Den här nya funktionen hjälper dig att felsöka anpassade åtgärder före eller efter det att du har använt dem under en resa. </p>
<p>Mer information finns i den <a href="../action/troubleshoot-custom-action.md">detaljerade dokumentationen</a>.</p>
<!--p> This capability is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Flexibel utvärdering av målgruppen (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med flexibel målgruppsutvärdering kan ni köra ett segmenteringsjobb på begäran för utvalda målgrupper, vilket säkerställer att ni alltid har de senaste målgruppsdata innan ni inriktar dem på Journey Optimizer resor och kampanjer.</p>
<img src="assets/do-not-localize/flexible-audience.gif">
<p>Mer information finns i den <a href="../audience/creating-a-segment-definition.md#flexible">detaljerade dokumentationen</a>.</p>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Tillgänglighetsdatum: 28 januari 2025</p>
</tr>
</tbody>
</table>
</table>


### Förbättringar {#25-02-improvements}

Förbättringarna nedan följer med uppdateringen från februari.

* **Datauppsättning TTL (Time-to-live)** - Från och med den här månaden kommer ett TTL-skyddsprotokoll att introduceras i Journey Optimizer systemgenererade datauppsättningar i nya sandlådor och nya orgs enligt följande:

   * 90 dagar för data i profilarkivet
   * 13 månader för data i sjön

  Den här ändringen kommer att introduceras i befintliga kundsandlådor i en efterföljande fas.

  Läs mer om den här uppdateringen i [de dedikerade vanliga frågorna](../data/datasets-ttl.md#frequently-asked-questions).

<!--* **Playbooks** - You can now create and publish your own Use Case Playbooks in Journey Optimizer.-->

* **Direktutskick** - En ny servertyp, Datalandningszon, stöds nu för filroutning i konfigurationen för direktutskick. [Läs mer](../direct-mail/direct-mail-configuration.md#file-routing-configuration)

* **SMS** - Nu kan du hantera SMS-meddelandeleverans från flerregionala slutpunkter genom att åsidosätta URL:er för leverans, feedback, inkommande och återanrop. För att detta ska fungera har en ny åsidosättnings-URL lagts till i konfigurationen för API-autentiseringsuppgifter. Den här ändringen är endast tillgänglig för SINK-providern. [Läs mer](../sms/sms-configuration-sinch.md)

* **Personalization** (Tillgänglighetsdatum: 29 januari 2025) - Det finns nya hjälpfunktioner för datum/tid som kan användas i personaliseringsredigeraren. [Läs mer](../personalization/functions/dates.md)


<!--
* The personalization editor has been enhanced with new capabilities such as Auto-complete, Search, and filtering options. You can also show or hide deprecated attributes.-->


* **E-postkonfiguration** - Om du hanterar samtycke utanför Adobe kan du nu ange en anpassad e-postadress för att avbryta prenumerationen och en anpassad URL för att avbryta prenumerationen som en del av konfigurationsinställningarna för e-postkanalen. [Läs mer](../email/list-unsubscribe.md#custom-managed)

  ![](../email/assets/surface-list-unsubscribe-custom.png){width="80%"}

* **Beslut** (Tillgänglighetsdatum: 28 januari 2025) - Beslut stöder nu objekttyper när objektkatalogens schema redigeras. [Läs mer](../experience-decisioning/catalogs.md)
