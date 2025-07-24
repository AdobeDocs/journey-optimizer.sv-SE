---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med samordnade kampanjer
description: Lär dig hur du börjar med samordnade kampanjer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 611dd06d-aa18-4fa3-a477-8a910cec21d8
source-git-commit: 15f5fdfde0e9f7c93739a624918838dbd6787833
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 0%

---

# Kom igång med samordnade kampanjer {#orchestrated-camp}

>[!CONTEXTUALHELP]
>id="campaigns_overview_orchestrated"
>title="Samordnade kampanjer"
>abstract="**Kampanjsamordning**<br/> Dela, kombinera, berika och hantera relationsdatauppsättningar för att definiera er målgrupp<br/><br/>"

**Utnyttja data för flera enheter**<br/> Lär dig hur samordnade kampanjer kan utnyttja relationsdatauppsättningar för att förbättra data för segmentering och personalisering <br/><br/>**Ad-hoc-segmentering och exakt räkning**<br/> Bygg ditt segment steg för steg med exakt antal <br/><br/>**Tillgängliga kanaler**<br/> E-post, SMS, push-meddelanden, direktreklam&quot;

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| <b>[Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)</b><br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](gs-schemas.md)</li><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Kampanjsamordning i [!DNL Adobe Journey Optimizer] driver avancerade, varumärkesinitierade marknadsföringskampanjer över alla kanaler, vilket hjälper er att öka engagemanget, intäkterna och kundlojaliteten i stor skala.

Flerkanalsmarknadsföring är avgörande, men samordnade kampanjer gör den sömlös. Med ett visuellt dra-och-släpp-gränssnitt kan ni utforma och automatisera komplexa marknadsföringsarbetsflöden, från segmentering till meddelandeleverans, i flera kanaler. Allt sker i en intuitiv miljö som är byggd för snabbhet, kontroll och effektivitet.

![](assets/canvas-example-diagram.png){zoomable="yes"}

## Kärnfunktioner

Kampanjsamordning bygger på fyra huvudpelare:

<table style="table-layout:auto">
<tr style="border: 0;">
<td><img alt="On-demand-målgrupper" src="assets/do-not-localize/icon-audience.svg" width="50px"></a></td><td><b>On-Demand-målgrupper</b><br/>Frågar direkt mellan datauppsättningar för att skapa målgruppssegment med valfri kombination av datatyper och dimensioner.</td></tr>
<tr style="border: 0;">
<td><img alt="Segmentering och sändning av flera enheter" src="assets/do-not-localize/icon-entity.svg" width="50px"></a></td><td><b>Segmentering och sändning av flera enheter</b><br/>Gå steget längre än personbaserade kampanjer - använd entiteter som produktkataloger, butiksplatser eller tjänstdata för att måla med precision.</td></tr>
<tr style="border: 0;">
<td><img alt="Synlighet och precision före sändning" src="assets/do-not-localize/icon-visibility.svg" width="50px"></a></td><td><b>Synlighet och precision före sändning</b><br/>Få exakt segmenteringsantal och fullständigt kampanjomfång före lansering för att säkerställa precision och förtroende.</td></tr>
<tr style="border: 0;">
<td><img alt="Arbetsflöden för kampanjer i flera steg" src="assets/do-not-localize/icon-multistep.svg" width="50px"></a></td><td><b>Flerstegskampanjer</b><br/>Utforma kampanjer i flera steg, från dagliga meddelanden till komplexa kampanjer som säsongskampanjer eller större produktlanseringar.</td></tr>
</table>

## Samordnade kampanjer och resor

Även om visualiseringen av samordnade kampanjer liknar resor, löser den olika syften och användningsområden:

* **Resor** - 1 till 1 arbetsyta där varje profil förflyttar sig genom de olika stegen i sin egen takt. Tillståndet för varje kund upprätthålls i sitt sammanhang för att aktivera realtidsåtgärder.

* **Samordnade kampanjer** - Till skillnad från resor använder orkestrerade kampanjer en batcharbetsyta som beräknar segment. Alla profiler bearbetas samtidigt.

## Förhandskrav

Innan du arbetar med samordnade kampanjer är det viktigt att du har rätt behörigheter. Åtkomsten till samordnade kampanjer är begränsad till användare som är tilldelade en relevant **[!UICONTROL Product Profile]**, till exempel en Orchestrated Campaign Administrator, Orchestrated Campaign Approver, Orchestrated Campaign Manager eller Orchestrated Campaign Viewer.

Om du inte kan komma åt orkestrerade kampanjfunktioner kontaktar du administratören för att få den behörighet som krävs.

➡️ [Läs mer om produktprofiler för orkestrerade kampanjer](../administration/ootb-product-profiles.md)

## Låt oss dyka djupare

Nu när ni har en förståelse för vad flerkanalskampanjer är, är det dags att gå djupare in i dessa dokumentationsavsnitt för att börja arbeta med funktionen.

<table><tr style="border: 0; text-align: center;">
<td>
<a href="gs-campaign-creation.md">
<img alt="Få åtkomst till och hantera arbetsflöden" src="assets/do-not-localize/workflow-access.jpeg">
</a>
<div>
<a href="gs-campaign-creation.md"><strong>Konfigurationssteg</strong></a>
</div>
<p>
</td>
<td>
<a href="create-orchestrated-campaign.md">
<img alt="Lead" src="assets/do-not-localize/workflow-create.jpeg">
</a>
<div><a href="create-orchestrated-campaign.md"><strong>Skapa en orkestrerad kampanj</strong>
</div>
<p>
</td>
<td>
<a href="activities/about-activities.md">
<img alt="Sällan" src="assets/do-not-localize/workflow-activities.jpeg">
</a>
<div>
<a href="activities/about-activities.md"><strong>Arbeta med aktiviteter</strong></a>
</div>
<p></td>
</tr></table>
