---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med arbetsytan
description: Lär dig arbeta med arbetsytan
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 3eb9466e-9d88-4470-a22f-5e24a29923ae
badge: label="Beta" type="Informative"
source-git-commit: 242fd8dbb04d62b9ec838655985add4ea0d7b377
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 0%

---

# Arbeta med arbetsytan {#composition-canvas}

>[!BEGINSHADEBOX]

Vad du hittar i den här dokumentationen:

* [Kom igång med målgruppsmaterial](get-started-audience-orchestration.md)
* [Skapa ditt första dispositionsarbetsflöde](create-compositions.md)
* **[Arbeta med arbetsytan](composition-canvas.md)**
* [Få åtkomst till och hantera målgrupper](access-audiences.md)

>[!ENDSHADEBOX]

Målgruppsdisposition är en visuell arbetsyta som gör att du kan skapa målgrupper och använda olika aktiviteter (dela, berika osv.).

Stegen för att komponera en målgrupp på arbetsytan är följande:

1. [Definiera era startmålgrupper](#starting-audience)
1. [Lägg till en eller flera aktiviteter](#action-activities)
1. [Spara resultaten till en ny målgrupp](#save)

## Välj den inledande målgruppen {#starting-audience}

Det första steget för att skapa en komposition är att välja en eller flera befintliga målgrupper som grund för din komposition.

1. Välj **[!UICONTROL Audience]** aktiviteten anger sedan en etikett för aktiviteten.

1. Välj målgrupp:

   * Klicka på **[!UICONTROL Add audience]** knapp för att välja en eller flera befintliga målgrupper,
   * Klicka på **[!UICONTROL Build rule]** för att skapa en ny segmentdefinition med [Segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/audiences-choose-audience.png)

1. Om du väljer flera målgrupper anger du hur profilerna för dessa målgrupper ska sammanfogas:

* **[!UICONTROL Union]**: inkludera alla profiler från de valda målgrupperna,
* **[!UICONTROL Intersection]**: innehåller profiler som är gemensamma för alla valda målgrupper,
* **[!UICONTROL Exclude overlap]**: innehåller profiler som bara tillhör en av målgrupperna. Profiler som tillhör fler än en publik inkluderas inte.

I det här exemplet vill vi inrikta oss på alla profiler som tillhör publikerna guld och silver.

![](assets/audiences-starting-audience.png)

När målgrupper har valts visas det uppskattade antalet profiler längst ned i aktiviteten.

## Lägg till aktiviteter {#action-activities}

Lägg till aktiviteter efter att du har valt den första målgruppen för att förfina urvalet.

Det gör du genom att klicka på plusknappen (+) på kompositionsbanan och sedan välja önskad aktivitet. Den högra rutan öppnas och du kan konfigurera den nyligen tillagda aktiviteten.

![](assets/audiences-select-activity.png)

Tillgängliga aktiviteter är:

* [Målgrupp](#audience): innehålla ytterligare profiler som tillhör en eller flera befintliga målgrupper,
* [Exkludera](#exclude): utesluta profiler som tillhör en befintlig målgrupp eller utesluta profiler som bygger på specifika attribut,
* [Förfina](#enrich): berika er målgrupp med ytterligare attribut från Adobe Experience Platform datauppsättningar,
* [Rankning](#rank): rangordna profiler baserat på ett specifikt attribut, ange antalet profiler som ska behållas och inkluderas i din komposition,
* [Dela](#split): dela upp kompositionen i flera banor baserat på slumpmässiga procentsatser eller attribut.

Du kan lägga till så många **[!UICONTROL Audience]** och **[!UICONTROL Exclude]** aktiviteter efter behov i din komposition. Inga ytterligare aktiviteter kan dock läggas till efter **[!UICONTROL Rank]** och **[!UICONTROL Split]** aktiviteter.

Du kan ta bort en aktivitet från arbetsytan när som helst genom att klicka på knappen Ta bort i den högra rutan.  Om aktiviteten som du vill ta bort är överordnad andra aktiviteter i kompositionen visas ett meddelande, som du kan använda för att ange om du bara vill ta bort den markerade aktiviteten eller alla dess underordnade aktiviteter.

### Målgruppsaktivitet {#audience}

>[!CONTEXTUALHELP]
>id="ajo_ao_audience"
>title="Målgruppsaktivitet"
>abstract="Med hjälp av Audience-aktiviteten kan du i din komposition inkludera ytterligare profiler som tillhör en befintlig målgrupp."

>[!CONTEXTUALHELP]
>id="ajo_ao_merge_types"
>title="Sammanfoga typer"
>abstract="Ange hur profilerna för de valda målgrupperna ska sammanfogas."

The **[!UICONTROL Audience]** kan du i din komposition inkludera ytterligare profiler som tillhör en befintlig målgrupp.

Konfigurationen för den här aktiviteten är identisk med startvärdet [Målgruppsaktivitet](#starting-audience).

### Exkludera aktivitet {#exclude}

>[!CONTEXTUALHELP]
>id="ajo_ao_exclude_type"
>title="Uteslut typ"
>abstract="Använd typen Uteslut målgrupp för att exkludera profiler som tillhör en befintlig målgrupp. Med attributtypen Uteslut med kan du exkludera profiler baserat på ett specifikt attribut."

>[!CONTEXTUALHELP]
>id="ajo_ao_exclude"
>title="Exkludera aktivitet"
>abstract="Med aktiviteten Uteslut kan du utesluta profiler från kompositionen genom att välja en befintlig målgrupp eller använda en regel."

The **[!UICONTROL Exclude]** kan du utesluta profiler från din komposition. Det finns två typer av undantag:

* **[!UICONTROL Exclude Audience]**: Uteslut profiler som tillhör en befintlig målgrupp.

   Klicka på **[!UICONTROL Add audience]** och sedan välja den målgrupp som ska uteslutas.

   ![](assets/audiences-exclude-audience.png)

* **[!UICONTROL Exclude using attribute]**: Uteslut profiler baserade på ett specifikt attribut.

   Välj det attribut som ska slås upp och ange sedan vilket värde som ska uteslutas. I det här exemplet utesluts vi från dispositionsprofiler vars hemadress är i Japan.

   ![](assets/audiences-exclude-attribute.png)

### Förfina {#enrich}

>[!CONTEXTUALHELP]
>id="ajo_ao_enrich"
>title="Berika aktivitet"
>abstract="Använd aktiviteten Enrich för att exkludera profiler som tillhör en befintlig målgrupp. Med attributtypen Uteslut med kan du exkludera profiler baserat på ett specifikt attribut."

>[!CONTEXTUALHELP]
>id="ajo_ao_enrich_dataset"
>title="Datauppsättning för berikning"
>abstract="Välj den datauppsättning för berikning som innehåller de data som du vill koppla till målgruppen."

>[!CONTEXTUALHELP]
>id="ajo_ao_enrich_criteria"
>title="Anrikningskriterier"
>abstract="Välj de fält som ska användas som avstämningsnyckel mellan källdatauppsättningen, dvs. målgruppen, och datauppsättningen för anrikning."

>[!CONTEXTUALHELP]
>id="ajo_ao_enrich_attributes"
>title="Attribut för berikning"
>abstract="Välj ett eller flera attribut från datauppsättningen för anrikning som ska kopplas till målgruppen. När kompositionen har publicerats kopplas dessa attribut till publiken och kan utnyttjas i kampanjer för att personalisera leveranser."

The **[!UICONTROL Enrich]** Med hjälp av aktivitet kan ni berika er målgrupp med ytterligare attribut från Adobe Experience Platform datamängder. Du kan t.ex. lägga till information om den köpta produkten, som namn, pris eller tillverkare-ID, och använda dessa uppgifter för att anpassa de leveranser som skickas till målgruppen.

>[!IMPORTANT]
>
>För närvarande sprids inte etiketter på datauppsättningen, antingen på datauppsättningsnivå eller på fältnivå, till den nya målgruppen. Detta kan påverka åtkomstkontroll och/eller datastyrning för den slutliga målgruppen. Därför bör du endast använda testdata när du komponerar målgrupper.

Så här konfigurerar du aktiviteten:

1. Välj **[!UICONTROL Enrichment dataset]** som innehåller de data som du vill associera med målgruppen.

1. I **[!UICONTROL Enrichment criteria]** väljer du de fält som ska användas som avstämningsnyckel mellan källdatauppsättningen, dvs. målgruppen, och anrikningsdatauppsättningen. I det här exemplet använder vi ID:t för den köpta produkten som avstämningsnyckel.

1. Klicka på **[!UICONTROL Add atttributes]** väljer du sedan ett eller flera attribut från anrikningsdatauppsättningen som ska kopplas till målgruppen.

   ![](assets/audiences-enrich-activity.png)

När kompositionen har publicerats kopplas de valda attributen till målgruppen och kan utnyttjas i kampanjer för att personalisera leveranser.

### Rankningsaktivitet {#rank}

>[!CONTEXTUALHELP]
>id="ajo_ao_ranking"
>title="Rankningsaktivitet"
>abstract="Med aktiviteten Rankning kan du rangordna profiler baserat på ett specifikt attribut och inkludera dem i din komposition. Ta till exempel med de 50 profilerna med det största antalet förmånspoäng."

>[!CONTEXTUALHELP]
>id="ajo_ao_rank_profilelimit_text"
>title="Lägg till profilgräns"
>abstract="Aktivera det här alternativet om du vill ange ett maximalt antal profiler som ska ingå i kompositionen."

The **[!UICONTROL Rank]** Med -aktivitet kan du rangordna profiler baserat på ett specifikt attribut och inkludera dem i din komposition. Du kan till exempel inkludera de 50 profilerna med det största antalet förmånspoäng.

1. Markera det attribut som du vill söka efter och ange en rangordningsordning (stigande eller fallande).

   >[!NOTE]
   >
   >Du kan välja attribut med följande datatyper: heltal, tal, kort <!--(other?)-->

1. Växla **[!UICONTROL Add profile limit]** på och ange ett maximalt antal profiler som ska ingå i kompositionen.

   ![](assets/audiences-rank.png)

### Delad aktivitet {#split}

<!-- [!CONTEXTUALHELP]
>id="ajo_ao_control_group_text"
>title="Control Group"
>abstract="Use control groups to isolate a portion of the profiles. This allows you to measure the impact of a marketing activity and make a comparison with the behavior of the rest of the population."-->

>[!CONTEXTUALHELP]
>id="ajo_ao_split"
>title="Delad aktivitet"
>abstract="Med aktiviteten Dela kan du dela upp kompositionen i flera banor. När kompositionen publiceras sparas en publik i Adobe Experience Platform för varje bana."

>[!CONTEXTUALHELP]
>id="ajo_ao_split_type"
>title="Delad text"
>abstract="Använd delningstypen Procent för att slumpmässigt dela upp profiler i flera banor. Med attributdelningstypen kan du dela profiler baserat på ett specifikt attribut."

>[!CONTEXTUALHELP]
>id="ajo_ao_split_otherprofiles_text"
>title="Andra profiler"
>abstract="Aktivera det här alternativet om du vill skapa en ytterligare sökväg med de återstående profilerna som inte matchar något av villkoren som anges i de andra sökvägarna."

The **[!UICONTROL Split]** kan du dela upp kompositionen i flera banor.

Den här åtgärden lägger automatiskt till en **[!UICONTROL Save]** i slutet av varje bana. När kompositionen publiceras sparas en publik i Adobe Experience Platform för varje bana.

Det finns två typer av delade åtgärder:

* **[!UICONTROL Percent split]**: dela upp profiler slumpmässigt i två eller flera banor. Du kan till exempel dela upp profilerna i två olika banor med 50 % vardera. <!--and add an additional path for control group.-->

   ![](assets/audiences-split-percentage.png)

* **[!UICONTROL Attribute split]**: delade profiler baserade på ett specifikt attribut. I det här exemplet delar vi upp profiler baserat på deras rumstypsinställningar.

   ![](assets/audiences-split.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Other profiles]** kan du skapa ytterligare en sökväg med de återstående profilerna som inte matchar något av villkoren som anges i de andra sökvägarna.

## Spara era målgrupper {#save}

Konfigurera de målgrupper som ska sparas i Adobe Experience Platform.

Om du vill göra det väljer du **[!UICONTROL Save audience]** i slutet av varje bana anger du namnet på den nya målgruppen som ska skapas.

![](assets/audiences-publish.png)

När kompositionen är klar kan du publicera den. [Lär dig hur du skapar kompositioner](create-compositions.md)
