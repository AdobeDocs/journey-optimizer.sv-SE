---
solution: Journey Optimizer
product: journey optimizer
title: Nytt resegränssnitt
feature: Release Notes
topic: Content Management
description: Nytt resegränssnitt
hide: true
hidefromtoc: true
source-git-commit: 81d54c026c52fe78b1b725d67da15505907b8bb9
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Nytt resegränssnitt {#new-canvas}

>[!CONTEXTUALHELP]
>id="ajo_new_canvas"
>title="Nyheter?"
>abstract="Ny arbetsyta"

Vi har arbetat på en förenkling av resemodellen som syftar till att underlätta vissa interna processer. Den här modelländringen är i sig transparent för dig, förutom att vi tog tillfället i akt att introducera nya funktioner tillsammans:

* En ny arbetsyta i Journey
* Live-rapportering på arbetsytan Resa
* Förbättra läsbarheten på arbetsytan och gör aktivitetsdesignen mer skalbar så att vi kan ge mer information på aktivitetsnivå för aktuella och framtida förbättringar.

## Uppdateringar av resemodellen

Den nya resemodellen kommer att leva tillsammans med den befintliga, vilket innebär att det kommer att finnas resor med två olika modeller:

* Den gamla, med namnet &quot;v1&quot;
* Och den nya som kallas &quot;v2&quot;

Alla resor i v1 stannar i v1. Du kan fortfarande redigera, testa och publicera dem. Alla nya versioner som skapas från en v1 behålls i v1. Det finns inga funktionella förändringar runt v1-resor.

Du ser att en resa är i v1 med arbetsytedesignen:

[SCREENSHOT]

Om den innehåller runda aktiviteter är det en v1.

Men när du ska skapa en ny resa eller duplicera en befintlig, blir det en v2-resa. På grund av detta förväntar vi oss att vi ska se färre och färre v1-resor över tiden. Se till att vi fortfarande kommer att stödja befintliga resor live v1.

Som vi nämnde är den nya modellen transparent för användarna, förutom en begränsning: det går inte att kopiera och klistra in aktiviteter från en v1-resa till en v2 och vice versa. Vi rekommenderar att du duplicerar din v1-resa så att du automatiskt får en v2-resa.

Du ser att en resa är i v2 med den nya arbetsytedesignen (se nedan):

[SCREENSHOT]

Alla nya funktioner runt arbetsytan (inklusive Live Reporting) kommer att finnas tillgängliga exklusivt på v2-resor.

## Ny arbetsyta i Journey

Med den nya resemodellen introducerar vi en omdesignad researbetsyta som passar smidigt in i Adobe Experience Cloud lösningar och ekosystem av appar, vilket ger en intuitiv och effektiv användarupplevelse. Alla resor i v2-stacken kommer att finnas i den nya designen.

[SCREENSHOT]

Aktiviteter visas nu i fyrkantiga rutor med:

* Den första raden som representerar aktivitetstypen, som ofta skrivs över av mer sammanhangsberoende information (t.ex.: på Läser målgrupper innehåller den namnet på den valda målgruppen), eller av en anpassad etikett om du definierar en sådan.
* Den andra live-versionen representerar alltid aktivitetstypen.

[SCREENSHOT]

Den här nya designen förbättrar läsbarheten på arbetsytan genom att ...

Det är också mer skalbart så att vi kan ge mer information på aktivitetsnivå, som vi började med direktrapportering.

[SCREENSHOT]

Förvänta dig att nya ändringar kommer inom några månader runt den nya designen!

## Live Reporting

* GIF
* live-rapportering