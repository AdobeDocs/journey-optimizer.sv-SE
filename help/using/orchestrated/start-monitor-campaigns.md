---
solution: Journey Optimizer
product: journey optimizer
title: Starta och övervaka samordnade kampanjer med Adobe Journey Optimizer
description: Lär dig hur du startar och övervakar samordnade kampanjer med Adobe Journey Optimizer.
hide: true
hidefromtoc: true
exl-id: 5fc2d1d6-75c3-4b45-bb2b-09982b9bd5ed
source-git-commit: e316c3dbbec028f7501990486506779656990c20
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# Starta och övervaka era samordnade kampanjer {#start-monitor}

>[!CONTEXTUALHELP]
>id="ajo_campaign_publication"
>title="Publicera orkestrerad kampanj"
>abstract="Du måste publicera kampanjen för att kunna starta den. Kontrollera att alla varningar är rensade före publiceringen."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/><b>[Starta och övervaka kampanjen](start-monitor-campaigns.md)</b><br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

När du har skapat dina arbetsytor och utformat arbetsytan kan du publicera den och övervaka hur den körs.

Du kan också köra kampanjen i testläge för att kontrollera dess körning och resultatet av de olika aktiviteterna.

## Testa kampanjen innan den publiceras {#test}

Med [!DNL Journey Optimizer] kan du testa samordnade kampanjer innan du publicerar. När en kampanj skapas försätts den i läget **Utkast** som standard. I det här läget kan du köra kampanjen manuellt för att testa flödet.

Alla aktiviteter på arbetsytan körs utom **[!UICONTROL Save audience]** aktiviteter och kanalaktiviteter. Det påverkar inte era data eller er målgrupp.

Så här testar du en kampanj:

1. Öppna den samordnade kampanjen.
2. Klicka på **[!UICONTROL Start]**.

![](assets/campaign-start.png){zoomable="yes"}

Varje aktivitet i kampanjen utförs sekventiellt tills diagrammets slut nås.

Under testet kan du styra kampanjkörningen med åtgärdsfältet på arbetsytan. Därifrån kan man

* **Stoppa** körningen när som helst.
* **Starta** körningen igen.
* **Återuppta** körningen om den tidigare pausats på grund av ett problem.

Om ett fel eller en varning inträffar under körningen visas ett meddelande via ikonen **[!UICONTROL Alerts]** / **[!UICONTROL Warning]** i verktygsfältet på arbetsytan.

![](assets/campaign-warning.png){zoomable="yes"}

Du kan också snabbt identifiera misslyckade aktiviteter med hjälp av de [visuella statusindikatorerna](#activities) som visas direkt i varje aktivitet. Om du vill ha detaljerad felsökning öppnar du loggarna för [kampanjen](#logs-tasks), som innehåller detaljerad information om felet och dess sammanhang.

När kampanjen har validerats kan den publiceras.

## Publicera kampanjen {#publish}

När kampanjen är testad och klar klickar du på **[!UICONTROL Publish]** för att göra den offentlig.

![](assets/campaign-publish.png){zoomable="yes"}

Det visuella flödet startar om och verkliga profiler börjar flöda genom resan i realtid.

Om publiceringsåtgärden misslyckas (t.ex. på grund av att meddelandeinnehåll saknas) får du ett varningsmeddelande och måste åtgärda problemet innan du försöker igen. När publiceringen är klar går kampanjen från **Utkast** till **Live** och börjar köras (omedelbart eller enligt schema).

## Övervaka kampanjkörning {#monitor}

### Visuell flödesövervakning {#flow}

Under körning (i test- eller live-läge) visar det visuella flödet hur profiler rör sig genom resan i realtid. Antalet profiler som övergår mellan uppgifter visas.

![](assets/workflow-execution.png){zoomable="yes"}

Data som transporteras från en aktivitet till en annan genom övergångar lagras i en temporär arbetstabell. Dessa data kan visas för varje övergång. Så här inspekterar du data som passerat mellan aktiviteter:

1. Välj en övergång.
1. Klicka på **[!UICONTROL Preview schema]** i egenskapspanelen för att visa arbetstabellschemat. Välj **[!UICONTROL Preview results]** om du vill visa data som har transporterats.

![](assets/transition.png){zoomable="yes"}

### Indikatorer för utförande av verksamhet {#activities}

Visuella statusindikatorer hjälper dig att förstå hur varje aktivitet fungerar:

| Visuell indikator | Beskrivning |
|-----|------------|
| ![](assets/activity-status-pending.png){zoomable="yes"}{width="70%"} | Aktiviteten körs för närvarande. |
| ![](assets/activity-status-orange.png){zoomable="yes"}{width="70%"} | Aktiviteten kräver din uppmärksamhet. Detta kan inbegripa att bekräfta leveransen eller vidta nödvändiga åtgärder. |
| ![](assets/activity-status-red.png){zoomable="yes"}{width="70%"} | Aktiviteten har påträffat ett fel. Du löser problemet genom att öppna de samordnade kampanjloggarna för mer information. |
| ![](assets/activity-status-green.png){zoomable="yes"}{width="70%"} | Aktiviteten har körts. |

### Loggar och uppgifter {#logs-tasks}

>[!CONTEXTUALHELP]
>id="ajo_campaign_logs"
>title="Loggar och uppgifter"
>abstract="Skärmen **Loggar och uppgifter** innehåller en historik över den samordnade kampanjkörningen, där alla användaråtgärder registreras och fel påträffas."

Övervakning av loggar och uppgifter är ett viktigt steg för att analysera samordnade kampanjer och se till att de körs som de ska. Loggar och uppgifter är tillgängliga från knappen **[!UICONTROL Logs]** som är tillgänglig i både test- och direktläge i verktygsfältet på arbetsytan eller i varje aktivitets egenskapspanel.

Skärmen **[!UICONTROL Logs and tasks]** innehåller en fullständig historik över kampanjkörningen, där alla användaråtgärder och påträffade fel registreras.

![](assets/workflow-logs.png){zoomable="yes"}

Det finns två typer av information:

* Fliken **[!UICONTROL Log]** innehåller den kronologiska historiken för alla åtgärder och fel.
* Fliken **[!UICONTROL Tasks]** innehåller information om aktiviteternas stegvisa körningssekvens.

På båda flikarna kan du välja vilka kolumner som ska visas och i vilken ordning de ska visas, tillämpa filter och använda sökfältet för att snabbt hitta önskad information.
