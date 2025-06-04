---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Dela
description: Lär dig hur du använder aktiviteten Dela i en iscensatt kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 986bc566-123a-451d-a4a6-bbf5a2798849
source-git-commit: c46c202d68613f08e2d2b23ea882fb6561669b08
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 0%

---

# Dela {#split}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split"
>title="Delad aktivitet"
>abstract="Med aktiviteten **Dela** kan du segmentera inkommande populationer i flera deluppsättningar baserat på olika urvalskriterier, t.ex. filtreringsregler eller populationsstorlek."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-query-modeler.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](/deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena&lbrace;1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/><br/>

Aktiviteten **Dela** är en **målaktivitet** som gör att du kan segmentera inkommande populationer i flera deluppsättningar baserat på olika urvalskriterier, till exempel filtreringsregler eller populationsstorlek.

## Konfigurera aktiviteten Dela {#split-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_segments"
>title="Segment för delad aktivitet"
>abstract="Lägg till så många delmängder som du vill för att segmentera den inkommande populationen.<br/></br>När aktiviteten **Dela** körs segmenteras populationen mellan de olika delmängderna i den ordning som de läggs till i aktiviteten. Innan du påbörjar din samordnade kampanj måste du se till att du har beställt delmängderna i den ordning som passar dina behov med pilknapparna."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_filter"
>title="Dela aktivitetsfilter"
>abstract="Om du vill använda ett filtreringsvillkor för delmängden klickar du på **[!UICONTROL Create filter]** och konfigurerar den önskade filtreringsregeln med frågemodelleraren. Ta till exempel med profiler från den inkommande populationen vars e-postadress finns i databasen."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_limit"
>title="Gräns för delad aktivitet"
>abstract="Om du vill begränsa antalet profiler som markeras av delmängden aktiverar du alternativet **[!UICONTROL Enable limit]** och anger antalet eller procentsatserna för den population som ska inkluderas."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_sorting"
>title="Sortering av delad aktivitet"
>abstract="När du anger en populationsgräns för en delmängd kan du rangordna de valda profilerna baserat på ett visst profilattribut i stigande eller fallande ordning. Aktivera alternativet **Aktivera sortering** om du vill göra det. Du kan till exempel begränsa en delmängd så att den endast innehåller de 50 översta profilerna med det högsta inköpspriset."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_complement"
>title="Delad generering av komplementfärg"
>abstract="När du har konfigurerat alla deluppsättningar kan du välja den återstående populationen som inte matchade någon av deluppsättningarna och inkludera dem i en ytterligare utgående övergång. Aktivera alternativet **Generera komplement** om du vill göra det."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_generatesubsets"
>title="Generera alla delmängder i samma tabell"
>abstract="Växla till det här alternativet om du vill gruppera alla delmängder i en enda utdataövergång."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_emptytransition"
>title="Hoppa över tom övergång"
>abstract="Aktivera alternativet **[!UICONTROL Skip empty transition]** om du vill inaktivera utdataövergången för den här delmängden om den inkommande populationen är tom."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_split_enable_overlapping"
>title="Aktivera överlappning av utdatapopulationer"
>abstract=" Med alternativet **[!UICONTROL Enable overlapping of output populations]** kan du hantera populationer som tillhör flera delmängder. När rutan inte är markerad ser delningsaktiviteten till att en mottagare inte kan finnas i flera utdataövergångar, även om den uppfyller villkoren för flera delmängder. De kommer att vara i målet för den första fliken med matchande villkor. När rutan är markerad kan mottagarna hittas i flera delmängder om de uppfyller filtervillkoren."

Följ de här stegen för att konfigurera aktiviteten **Dela**:

1. Lägg till en **delad**-aktivitet i din samordnade kampanj.

1. Aktivitetskonfigurationsrutan öppnas med en standarddelmängd. Klicka på knappen **Lägg till segment** om du vill lägga till så många delmängder som behövs för att segmentera den inkommande populationen.

   ![](../assets/workflow-split.png)

   >[!IMPORTANT]
   >
   >När aktiviteten **Dela** körs segmenteras populationen över de olika delmängderna i den ordning som de läggs till i aktiviteten. Om till exempel den första delmängden återställer 70 % av den ursprungliga populationen, kommer nästa tillagda delmängd endast att tillämpa sina urvalskriterier på de återstående 30 %, och så vidare.
   >
   >Innan du påbörjar en strukturerad kampanj måste du se till att du har beställt delmängderna i den ordning som passar dina behov. Det gör du genom att använda pilknapparna för att ändra positionen för en delmängd.

1. När deluppsättningar har lagts till visar aktiviteten så många utdataövergångar som det finns deluppsättningar. Vi rekommenderar starkt att du ändrar etiketten för varje delmängd för att enkelt identifiera dem i den orkestrerade kampanjarbetsytan.

1. Konfigurera hur varje delmängd ska filtrera den inkommande populationen. Följ dessa steg för att göra detta:

   1. Öppna delmängden för att visa dess egenskaper.

   1. Om du vill använda ett filtreringsvillkor för delmängden klickar du på **[!UICONTROL Create filter]** och konfigurerar den önskade filtreringsregeln med frågemodelleraren. Ta till exempel med profiler från den inkommande populationen vars e-postadress finns i databasen.

   1. Om du vill begränsa antalet profiler som markeras av delmängden aktiverar du alternativet **[!UICONTROL Enable limit]** och anger antalet eller procentsatserna för den population som ska inkluderas.

   1. Om du vill inaktivera en övergång om den inkommande populationen är tom aktiverar du alternativet **[!UICONTROL Skip empty transition]**. Om ingen profil matchar delmängden kommer den orkestrerade kampanjen inte att övergå till nästa aktivitet.

      ![](../assets/workflow-split-subset.png)

1. När du har konfigurerat alla deluppsättningar kan du välja den återstående populationen som inte matchade någon av deluppsättningarna och inkludera dem i en ytterligare utgående övergång. Aktivera alternativet **[!UICONTROL Generate complement]** om du vill göra det.

   ![](../assets/workflow-split-complement.png)

   >[!NOTE]
   >
   >Med alternativet **[!UICONTROL Generate all subsets in the same table]** kan du gruppera alla delmängder till en enda utdataövergång.

1. Med alternativet **[!UICONTROL Enable overlapping of output populations]** kan du hantera populationer som tillhör flera delmängder:

   * När rutan inte är markerad ser delningsaktiviteten till att en mottagare inte kan finnas i flera utdataövergångar, även om den uppfyller villkoren för flera delmängder. De kommer att vara i målet för den första fliken med matchande villkor.
   * När rutan är markerad kan mottagarna hittas i flera delmängder om de uppfyller filtervillkoren. Det bästa sättet är att använda exklusiva kriterier.

Aktiviteten är nu konfigurerad. Vid genomförande av samordnade kampanjer kommer populationen att segmenteras i olika delmängder, i den ordning som de har lagts till i aktiviteten.

## Exempel{#split-example}

I följande exempel används aktiviteten **[!UICONTROL Split]** för att segmentera en målgrupp i distinkta delmängder baserat på kommunikationskanalen som vi vill använda:

* **Delmängd 1 &quot;push&quot;**: Den här delmängden innehåller alla profiler som har installerat vårt mobilprogram.
* **Delmängd 2 &quot;sms&quot;**: Användare av mobiltelefoner: För den återstående populationen som inte ingick i delmängd 1 tillämpar delmängd 2 en filtreringsregel för att välja profiler med mobiltelefoner i databasen.
* **Kompletteringsövergång**: Den här övergången fångar alla återstående profiler som inte matchade delmängd 1 eller delmängd 2. Det omfattar profiler som varken har installerat mobilappen eller en mobiltelefon, till exempel användare som inte har installerat mobilappen eller saknar ett registrerat mobilnummer.

![](../assets/workflow-split-example.png)
