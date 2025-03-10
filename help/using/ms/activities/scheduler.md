---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Schemaläggaren
description: Lär dig hur du använder aktiviteten Schemaläggaren i en flerstegskampanj
hide: true
hidefromtoc: true
source-git-commit: dfa6c6e11db10f3e843035d32e322b212361548c
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 6%

---

# Schemaläggare {#scheduler}


>[!CONTEXTUALHELP]
>id="ajo_orchestration_scheduler"
>title="Schemaläggaraktivitet"
>abstract="Med aktiviteten **Schemaläggaren** kan du schemalägga när flerstegskampanjen startas. Denna aktivitet bör betraktas som en planerad start. Den kan bara användas som den första aktiviteten i flerstegskampanjen."


Aktiviteten **Schemaläggaren** är en **Flödeskontroll**-aktivitet. Med det kan ni schemalägga när flerstegskampanjen börjar. Denna aktivitet bör betraktas som en planerad start. Den kan bara användas som den första aktiviteten i flerstegskampanjen.

## Bästa praxis{#scheduler-best-practices}

* Schemalägg inte en kampanj i flera steg som körs mer än var 15:e minut eftersom det kan påverka den totala systemprestandan negativt och skapa block i databasen.
* Om du vill skicka en engångsleverans i din flerstegskampanj kan du lägga till en schemaläggningsaktivitet och ställa in den på att köra **En gång**. Du kan också definiera **schemat** i leveransinställningarna.
* Om du vill skicka en återkommande leverans i din flerstegskampanj måste du använda en **schemaläggaraktivitet** och ange körningsfrekvens. Den återkommande leveransaktiviteten tillåter inte att du definierar ett schema.

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

1. Lägg till en **schemaläggaraktivitet** i din flerstegskampanj.

1. Konfigurera **körningsfrekvensen**:

   * **En gång**: Flerstegskampanjen körs en gång.

   * **Dagligen**: Flerstegskampanjen körs vid en viss tidpunkt, en gång om dagen.

   * **Flera gånger om dagen:** Flerstegskampanjen körs regelbundet flera gånger om dagen. Du kan ställa in körningar vid specifika tidpunkter eller med jämna mellanrum.

   * **Veckovis**: Flerstegskampanjen körs vid ett angivet tillfälle, en eller flera gånger i veckan.

   * **Varje månad**: Flerstegskampanjen körs vid ett angivet tillfälle, en eller flera gånger i månaden. Du kan välja månader när du vill att flerstegskampanjen ska köras. Du kan också ställa in körningar på angivna veckodagar i månaden, till exempel den andra tisdagen i månaden.

1. Definiera körningsinformationen utifrån den valda frekvensen.  Detaljfälten kan variera beroende på vilken frekvens som används (tid, repetitionsfrekvens, angivna dagar etc.).

1. Klicka på **Förhandsgranska starttider** för att kontrollera schemat för de kommande tio körningarna av din flerstegskampanj.

1. Definiera giltighetsperioden för schemaläggaren:

   * **Permanent (upphör aldrig)**: Flerstegskampanjen körs enligt den frekvens som anges, utan begränsningar av tidsramen eller antalet iterationer.

   * **Giltighetsperiod**: Flerstegskampanjen körs enligt den frekvens som anges, fram till ett visst datum. Du måste ange start- och slutdatum.

>[!NOTE]
>
>Om du vill starta flerstegskampanjen direkt kan du klicka på **Kör väntande uppgift** i schemaläggarens övre åtgärdsfält. Den här knappen är bara tillgänglig när du har startat flerstegskampanjen.

## Exempel{#scheduler-example}

I följande exempel är aktiviteten konfigurerad så att kampanjen i flera steg körs flera gånger per dag kl. 9 och 12 varje dag i veckan från 1 oktober 2025 till 1 januari 2026.

![](../assets/workflow-scheduler2.png)
