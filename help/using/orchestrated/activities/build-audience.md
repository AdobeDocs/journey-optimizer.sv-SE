---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Skapa målgrupp
description: Lär dig hur du använder aktiviteten Skapa målgrupp i en orkestrerad kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 3959b5fa-0c47-42a5-828f-4d7ca9b7e72d
source-git-commit: 2935e611bb9682256a324485b28e7dd2552e1dd2
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---

# Bygg målgrupper {#build-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience"
>title="Bygg målgruppsaktivitet"
>abstract="Med aktiviteten **Skapa målgrupp** kan du definiera målgruppen som ska gå in i den orkestrerade kampanjen. När du skickar meddelanden i samband med en orkestrerad kampanj definieras inte meddelandemålgruppen i kanalaktiviteten, utan i aktiviteten **Bygg målgrupp**."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](send-messages.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med Query Modeler](orchestrated-query-modeler.md)<br/><br/>[Skapa din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](activities/and-join.md) - [Skapa målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kombinera](activities/combine.md) - [Ta bort dubbletter](activities/deduplication.md) - [Förbättra](activities/enrichment.md) - [Förena](activities/fork.md) - [Förena{1 ](activities/reconciliation.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/><br/>

Som marknadsförare kan ni enkelt skapa komplexa frågor med ett användarvänligt gränssnitt, så att jag kan segmentera er målgrupp baserat på ett stort antal kriterier och beteenden för att skräddarsy era kampanjer mer effektivt.

Använd målinriktningsaktiviteten **Bygg målgrupp** för att utföra detta. Med den här aktiviteten kan ni definiera målgruppen som ska delta i den orkestrerade kampanjen. När du skickar meddelanden i samband med en orkestrerad kampanj definieras inte meddelandemålgruppen i kanalaktiviteten, utan i aktiviteten **Bygg målgrupp**.

Om du vill definiera målgruppspopulationen kan du:

* Välj en befintlig målgrupp.
* Markera ett fördefinierat filter.
* Bygg en ny målgrupp med frågemodelleraren genom att definiera och kombinera filtervillkor.

>[!NOTE]
>
>Målgrupper som läses in från en fil kan inte anges som mål med en Build-målgruppsaktivitet. För att göra detta måste du använda en **Läs in fil**-aktivitet följt av en **avstämningsaktivitet** .


## Konfigurera aktiviteten Skapa målgrupp {#build-audience-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience_audienceselector"
>title="Målgrupp"
>abstract="Välj målgrupp på samma sätt som du använder en målgrupp när du designar en ny leverans."

Följ de här stegen för att konfigurera aktiviteten **Skapa målgrupp**:

![](../assets/build-audience.png)

1. Lägg till en **Skapa målgruppsaktivitet**.
1. Definiera en etikett.
1. Definiera målgruppstypen: **Skapa din egen** eller **Läs målgrupp**.
1. Konfigurera målgruppen genom att följa stegen som beskrivs på flikarna nedan.


Så här skapar du en egen fråga:

1. Välj **Skapa en egen (fråga)**.
1. Välj **Måldimension**. Med målinriktningsdimensionen kan du definiera målgruppen för operationen: mottagare, mottagare, operatör, prenumeranter osv. Som standard är målet markerat bland mottagarna.
1. Klicka på **Fortsätt**.
1. Använd frågemodelleraren för att definiera frågan. [Läs mer om frågemodelleraren i det här avsnittet](../orchestrated-query-modeler.md)

## Exempel{#build-audience-examples}

Här är ett exempel på en orkestrerad kampanj med två **Build-målgruppsaktiviteter**. Det första riktar sig till pokerspelarna, följt av ett mejlerbjudande. Det andra riktar sig till VIP kunder, följt av SMS-leverans.

![](../assets/workflow-audience-example.png)
