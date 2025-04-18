---
solution: Journey Optimizer
product: journey optimizer
title: Schemalägg och starta samordnade kampanjer med Adobe Journey Optimizer
description: Lär dig schemalägga och starta samordnade kampanjer med Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: 5fc2d1d6-75c3-4b45-bb2b-09982b9bd5ed
source-git-commit: bdc584c1aae0c735d81dfc95e11f96f755bea26a
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 2%

---

# Schemalägg och starta samordnade kampanjer {#start-monitor}



>[!CONTEXTUALHELP]
>id="ajo_campaign_publication"
>title="Publicera orkestrerad kampanj"
>abstract="Du måste publicera kampanjen för att kunna starta den. Kontrollera att alla varningar är rensade före publiceringen."

När du har skapat dina arbetsytor och utformat arbetsytan kan du publicera den och övervaka hur den körs.

## Schemaläggningsalternativ

>[!CONTEXTUALHELP]
>id="ajo_orchestration_scheduler"
>title="Schemaläggaraktivitet"
>abstract="Med kampanjen **Schemaläggaren** kan du schemalägga när den orkestrerade kampanjen startas. Denna aktivitet bör betraktas som en planerad start. Den kan bara användas som den första aktiviteten i den orkestrerade kampanjen."

Som kampanjansvarig kan ni schemalägga kampanjer att startas automatiskt vid specifika tidpunkter, vilket ger exakt timing och korrekta målgruppsdata för marknadsföringskommunikation.

### Bästa praxis {#scheduler-best-practices}

* Schemalägg inte att en orkestrerad kampanj ska köras mer än var femtonde minut eftersom det kan påverka den totala systemprestandan negativt och skapa block i databasen.
* Om du vill skicka ett enbildsmeddelande i din orkestrerade kampanj kan du ange att det ska köras **En gång**.
* Om du vill skicka ett återkommande meddelande i din samordnade kampanj måste du använda alternativen **Schemaläggning** och ange körningsfrekvens. Den återkommande leveransaktiviteten tillåter inte att du definierar ett schema.

### Konfigurera kampanjschemat {#scheduler-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_schedule_validity"
>title="Schemaläggarens giltighet"
>abstract="Du kan definiera en giltighetsperiod för schemaläggaren. Den kan vara permanent (standard) eller giltig till ett visst datum."


>[!CONTEXTUALHELP]
>id="ajo_orchestration_schedule_options"
>title="Alternativ för schemaläggare"
>abstract="Definiera frekvensen för schemaläggaren. Den kan köras vid ett specifikt tillfälle, en eller flera gånger per dag, vecka eller månad."

![Schemaläggarskärmen med månatliga alternativ](assets/scheduler-screen.png)

Följ de här stegen för att konfigurera det **samordnade kampanjschemat**:

1. Välj knappen **Så snart som möjligt** högst upp på arbetsytan för orkestrerade kampanjer.

1. Konfigurera **körningsfrekvensen**:

   * **En gång**: Den orkestrerade kampanjen körs en gång.

   * **Dagligen**: Den orkestrerade kampanjen körs vid en viss tidpunkt, en gång om dagen.

   * **Flera gånger om dagen:** Den samordnade kampanjen körs regelbundet flera gånger om dagen. Du kan ställa in körningar vid specifika tidpunkter eller med jämna mellanrum.

   * **Veckovis**: Den orkestrerade kampanjen körs vid ett angivet tillfälle, en eller flera gånger i veckan.

   * **Månadsvis**: Den samordnade kampanjen körs vid ett angivet tillfälle, en eller flera gånger i månaden. Du kan välja månader när du vill att den samordnade kampanjen ska köras. Du kan också ställa in körningar på angivna veckodagar i månaden, till exempel den andra tisdagen i månaden.

     ![Schemaläggarskärmen med dagligt körningsexempel](assets/scheduler-daily-sample.png){width="50%" align="left"}

1. Definiera körningsinformationen utifrån den valda frekvensen.  Detaljfälten varierar beroende på vilken frekvens som används (tid, repetitionsfrekvens, angivna dagar osv.).

1. Klicka på **Förhandsgranska starttider** för att kontrollera schemat för de kommande tio körningarna av din samordnade kampanj.

1. Definiera giltighetsperioden för schemaläggaren:

   * **Permanent (upphör aldrig att gälla)**: Den orkestrerade kampanjen körs enligt den angivna frekvensen, utan några begränsningar för tidsramen eller antalet iterationer.

   * **Giltighetsperiod**: Den orkestrerade kampanjen körs enligt den angivna frekvensen, fram till ett visst datum. Du måste ange start- och slutdatum.

1. Välj **Bekräfta** om du vill spara inställningarna. Körningsfrekvensen visas ovanför arbetsytan för den orkestrerade kampanjen.

>[!TIP]
>
>Om du vill starta den orkestrerade kampanjen med en gång ska du behålla standardvärdet **Så snart som möjligt**.

## Exempel {#scheduler-example}

I följande exempel är aktiviteten konfigurerad så att den samordnade kampanjen körs två gånger per dag kl. 9 och 12 varje dag i veckan från 1 oktober 2025 till 1 januari 2026.

![Schemaläggaren har konfigurerats att köra kampanjen två gånger om dagen kl. 9 och 12:00](assets/scheduler-sample.png){width="50%" align="left"}


## Starta en orkestrerad kampanj {#start}

Om du vill starta en strukturerad kampanj går du till fliken **[!UICONTROL Orchestration]** på menyn **[!UICONTROL Campaigns]** och väljer den kampanj som ska startas. Klicka sedan på knappen **[!UICONTROL Play]** i det övre högra hörnet av arbetsytan.

När den orkestrerade kampanjen körs, utförs varje aktivitet på arbetsytan i sekventiell ordning tills slutet på den orkestrerade kampanjen nås.

Du kan spåra förloppet för målprofiler i realtid med ett visuellt flöde. På så sätt kan du snabbt identifiera status för varje aktivitet och antalet profiler som övergår mellan dem.

![](assets/workflow-execution.png){zoomable="yes"}

## Samordnade kampanjövergångar {#transitions}

I samordnade kampanjer lagras data som transporteras från en aktivitet till en annan via övergångar i en tillfällig arbetstabell. Dessa data kan visas för varje övergång. Det gör du genom att markera en övergång och öppna dess egenskaper till höger på skärmen.

* Klicka på **[!UICONTROL Preview schema]** för att visa arbetstabellens schema.
* Klicka på **[!UICONTROL Preview results]** om du vill visa de data som har transporterats i den valda övergången.

![](assets/transition.png){zoomable="yes"}

## Körning av övervakningsaktivitet {#activities}

Med visuella indikatorer i det övre högra hörnet av varje aktivitetsruta kan du kontrollera deras körning:

| Visuell indikator | Beskrivning |
|-----|------------|
| ![](assets/activity-status-pending.png){zoomable="yes"}{width="70%"} | Aktiviteten körs för närvarande. |
| ![](assets/activity-status-orange.png){zoomable="yes"}{width="70%"} | Aktiviteten kräver din uppmärksamhet. Detta kan inbegripa att bekräfta leveransen eller vidta nödvändiga åtgärder. |
| ![](assets/activity-status-red.png){zoomable="yes"}{width="70%"} | Aktiviteten har påträffat ett fel. Du löser problemet genom att öppna de samordnade kampanjloggarna för mer information. |
| ![](assets/activity-status-green.png){zoomable="yes"}{width="70%"} | Aktiviteten har körts. |

## Övervaka loggar och uppgifter {#logs-tasks}

Övervakning av arbetsflöden, loggar och uppgifter är ett viktigt steg för att analysera era samordnade kampanjer och se till att de körs som de ska. De är tillgängliga från ikonen **[!UICONTROL Logs]** som är tillgänglig i åtgärdsverktygsfältet och i egenskapsrutan för varje aktivitet.

Menyn **[!UICONTROL Logs and tasks]** innehåller en historik över den orkestrerade kampanjkörningen, där alla användaråtgärder och påträffade fel registreras.
![](assets/workflow-logs.png){zoomable="yes"}

Det finns två typer av information:

* Fliken **[!UICONTROL Log]** innehåller körningshistoriken för alla orkestrerade kampanjaktiviteter. Den indexerar de åtgärder som utförts och körningsfel i kronologisk ordning.
* Fliken **[!UICONTROL Tasks]** innehåller information om körningssekvensen för aktiviteterna.

På båda flikarna kan du välja vilka kolumner som ska visas och i vilken ordning de ska visas, tillämpa filter och använda sökfältet för att snabbt hitta önskad information.

## Samordnade kommandon för kampanjkörning {#execution-commands}

Åtgärdsfältet i det övre högra hörnet innehåller kommandon som gör att du kan hantera den samordnade kampanjkörningen. Du kan:

* **[!UICONTROL Start]** / **[!UICONTROL Resume]** körningen av   iscensatt kampanj, som sedan får statusen Pågår. Om den samordnade kampanjen pausades återupptas den, annars startas den och de inledande aktiviteterna aktiveras sedan.

* **[!UICONTROL Pause]** körningen av den orkestrerade kampanjen, som sedan får statusen Pausad. Inga nya aktiviteter kommer att aktiveras förrän de återupptas, men pågående åtgärder avbryts inte.

* **[!UICONTROL Stop]** är en iscensatt kampanj som körs och som sedan får statusen Slutförd. De pågående åtgärderna avbryts om möjligt. Du kan inte återuppta den orkestrerade kampanjen från samma plats som den stoppades.
