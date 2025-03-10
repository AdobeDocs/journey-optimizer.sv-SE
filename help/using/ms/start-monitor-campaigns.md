---
solution: Journey Optimizer
product: journey optimizer
title: Starta och övervaka flerstegskampanjer med Adobe Journey Optimizer
description: Lär dig hur du startar och övervakar flerstegskampanjer med Adobe Journey Optimizer
hide: true
hidefromtoc: true
source-git-commit: f73d847c1d335260a0198e844d237a652e346729
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Starta och övervaka era flerstegskampanjer {#start-monitor}

När du har skapat arbetsflödet och utformat de uppgifter som ska utföras på arbetsytan kan du starta det och övervaka hur det körs.

## Starta en kampanj i flera steg {#start}

Om du vill starta en kampanj i flera steg går du till fliken **[!UICONTROL Multi-step]** på menyn **[!UICONTROL Campaign]** och väljer den kampanj som ska startas. Klicka sedan på knappen **[!UICONTROL Start]** i det övre högra hörnet av arbetsytan.

När flerstegskampanjen körs utförs varje aktivitet på arbetsytan i sekventiell ordning tills slutet på flerstegskampanjen nås.

Du kan spåra förloppet för målprofiler i realtid med ett visuellt flöde. På så sätt kan du snabbt identifiera status för varje aktivitet och antalet profiler som övergår mellan dem.

![](assets/workflow-execution.png){zoomable="yes"}

## Flerstegskampanjsövergångar {#transitions}

I flerstegskampanjer lagras data som transporteras från en aktivitet till en annan via övergångar i en tillfällig arbetstabell. Dessa data kan visas för varje övergång. Det gör du genom att markera en övergång och öppna dess egenskaper till höger på skärmen.

* Klicka på **[!UICONTROL Preview schema]** för att visa arbetstabellens schema.
* Klicka på **[!UICONTROL Preview results]** om du vill visa de data som har transporterats i den valda övergången.

![](assets/transition.png){zoomable="yes"}

## Körning av övervakningsaktivitet {#activities}

Med visuella indikatorer i det övre högra hörnet av varje aktivitetsruta kan du kontrollera deras körning:

| Visuell indikator | Beskrivning |
|-----|------------|
| ![](assets/activity-status-pending.png){zoomable="yes"}{width="70%"} | Aktiviteten körs för närvarande. |
| ![](assets/activity-status-orange.png){zoomable="yes"}{width="70%"} | Aktiviteten kräver din uppmärksamhet. Detta kan inbegripa att bekräfta leveransen eller vidta nödvändiga åtgärder. |
| ![](assets/activity-status-red.png){zoomable="yes"}{width="70%"} | Aktiviteten har påträffat ett fel. Du löser problemet genom att öppna loggarna för flerstegskampanjer för mer information. |
| ![](assets/activity-status-green.png){zoomable="yes"}{width="70%"} | Aktiviteten har körts. |

## Övervaka loggar och uppgifter {#logs-tasks}

Övervakning av arbetsflöden, loggar och uppgifter är ett viktigt steg för att analysera era flerstegskampanjer och se till att de körs som de ska. De är tillgängliga från ikonen **[!UICONTROL Logs]** som är tillgänglig i åtgärdsverktygsfältet och i egenskapsrutan för varje aktivitet.

Menyn **[!UICONTROL Logs and tasks]** innehåller en historik över kampanjkörningen i flera steg, där alla användaråtgärder och påträffade fel registreras.
![](assets/workflow-logs.png){zoomable="yes"}

Det finns två typer av information:

* Fliken **[!UICONTROL Log]** innehåller körningshistoriken för alla kampanjaktiviteter i flera steg. Den indexerar de åtgärder som utförts och körningsfel i kronologisk ordning.
* Fliken **[!UICONTROL Tasks]** innehåller information om körningssekvensen för aktiviteterna.

På båda flikarna kan du välja vilka kolumner som ska visas och i vilken ordning de ska visas, tillämpa filter och använda sökfältet för att snabbt hitta önskad information.

## Kommandon för kampanjkörning i flera steg {#execution-commands}

Åtgärdsfältet i det övre högra hörnet innehåller kommandon som gör att du kan hantera körningen av en kampanj i flera steg. Du kan:

* **[!UICONTROL Start]** / **[!UICONTROL Resume]** körningen av   kampanj i flera steg, som sedan får statusen Pågår. Om flerstegskampanjen pausades återupptas den, annars startas den och de inledande aktiviteterna aktiveras sedan.

* **[!UICONTROL Pause]** körningen av flerstegskampanjen, som sedan får statusen Pausad. Inga nya aktiviteter kommer att aktiveras förrän de återupptas, men pågående åtgärder avbryts inte.

* **[!UICONTROL Stop]** är en kampanj i flera steg som körs och som sedan får statusen Slutförd. De pågående åtgärderna avbryts om möjligt. Du kan inte återuppta flerstegskampanjen från samma ställe som den stoppades.
