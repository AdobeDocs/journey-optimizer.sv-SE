---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Schemaläggaren
description: Lär dig använda aktiviteten Schemaläggaren i en orkestrerad kampanj
hide: true
hidefromtoc: true
exl-id: da77a0bf-7b17-40fc-b2cb-2f0940152e64
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 6%

---

# Schemaläggare {#scheduler}


>[!CONTEXTUALHELP]
>id="ajo_orchestration_scheduler"
>title="Schemaläggaraktivitet"
>abstract="Med aktiviteten **Schemaläggaren** kan du schemalägga när den orkestrerade kampanjen startas. Denna aktivitet bör betraktas som en planerad start. Den kan bara användas som den första aktiviteten i den orkestrerade kampanjen."


Aktiviteten **Schemaläggaren** är en **Flödeskontroll**-aktivitet. Med den kan ni schemalägga när den orkestrerade kampanjen börjar. Denna aktivitet bör betraktas som en planerad start. Den kan bara användas som den första aktiviteten i den orkestrerade kampanjen.

## Bästa praxis{#scheduler-best-practices}

* Schemalägg inte att en orkestrerad kampanj ska köras mer än var femtonde minut eftersom det kan påverka den totala systemprestandan negativt och skapa block i databasen.
* Om du vill skicka en engångsleverans i din samordnade kampanj kan du lägga till en schemaläggningsaktivitet och ställa in den på att köra **En gång**. Du kan också definiera **schemat** i leveransinställningarna.
* Om du vill skicka en återkommande leverans i din samordnade kampanj måste du använda en **schemaläggaraktivitet** och ange körningsfrekvens. Den återkommande leveransaktiviteten tillåter inte att du definierar ett schema.

## Konfigurera aktiviteten Schemaläggaren {#scheduler-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_schedule_validity"
>title="Schemaläggarens giltighet"
>abstract="Du kan definiera en giltighetsperiod för schemaläggaren. Den kan vara permanent (standard) eller giltig till ett visst datum."


>[!CONTEXTUALHELP]
>id="ajo_orchestration_schedule_options"
>title="Alternativ för schemaläggare"
>abstract="Definiera frekvensen för schemaläggaren. Den kan köras vid ett specifikt tillfälle, en eller flera gånger per dag, vecka eller månad."

Följ de här stegen för att konfigurera aktiviteten **Schemaläggaren**:

![](../assets/workflow-scheduler.png)

1. Lägg till en **schemaläggaraktivitet** i den orkestrerade kampanjen.

1. Konfigurera **körningsfrekvensen**:

   * **En gång**: Den orkestrerade kampanjen körs en gång.

   * **Dagligen**: Den orkestrerade kampanjen körs vid en viss tidpunkt, en gång om dagen.

   * **Flera gånger om dagen:** Den samordnade kampanjen körs regelbundet flera gånger om dagen. Du kan ställa in körningar vid specifika tidpunkter eller med jämna mellanrum.

   * **Veckovis**: Den orkestrerade kampanjen körs vid ett angivet tillfälle, en eller flera gånger i veckan.

   * **Månadsvis**: Den samordnade kampanjen körs vid ett angivet tillfälle, en eller flera gånger i månaden. Du kan välja månader när du vill att den samordnade kampanjen ska köras. Du kan också ställa in körningar på angivna veckodagar i månaden, till exempel den andra tisdagen i månaden.

1. Definiera körningsinformationen utifrån den valda frekvensen.  Detaljfälten kan variera beroende på vilken frekvens som används (tid, repetitionsfrekvens, angivna dagar etc.).

1. Klicka på **Förhandsgranska starttider** för att kontrollera schemat för de kommande tio körningarna av din samordnade kampanj.

1. Definiera giltighetsperioden för schemaläggaren:

   * **Permanent (upphör aldrig att gälla)**: Den orkestrerade kampanjen körs enligt den angivna frekvensen, utan några begränsningar för tidsramen eller antalet iterationer.

   * **Giltighetsperiod**: Den orkestrerade kampanjen körs enligt den angivna frekvensen, fram till ett visst datum. Du måste ange start- och slutdatum.

>[!NOTE]
>
>Om du vill starta den orkestrerade kampanjen direkt kan du klicka på **Kör väntande uppgift** i schemaläggarens övre åtgärdsfält. Den här knappen är bara tillgänglig när du har startat den orkestrerade kampanjen.

## Exempel{#scheduler-example}

I följande exempel är aktiviteten konfigurerad så att den samordnade kampanjen körs flera gånger per dag kl. 9 och 12 varje dag i veckan från 1 oktober 2025 till 1 januari 2026.

![](../assets/workflow-scheduler2.png)
