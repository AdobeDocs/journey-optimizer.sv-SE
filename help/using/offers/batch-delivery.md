---
title: Gruppbeslut
description: Lär dig hur ni kan leverera offertbeslut till alla profiler inom en viss Adobe Experience Platform-publik.
Feature: Offers
Level: Intermediate
exl-id: 810c05b3-2bae-4368-bf12-3ea8c2f31c01
source-git-commit: 3f96cc0037b5bcdb2ce94e2721b02ba13b3cff36
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 0%

---

# Gruppbeslut {#deliver}

## Kom igång med batchbeslut {#start}

Med Journey Optimizer kan ni leverera offertbeslut till alla profiler inom en viss Adobe Experience Platform-publik.

För att göra detta måste ni skapa en jobbförfrågan i Journey Optimizer som innehåller information om målgruppen och vilket beslut som ska fattas om erbjudandet. Erbjudandeinnehållet för varje profil i målgruppen placeras sedan i en Adobe Experience Platform-datauppsättning där det är tillgängligt för anpassade grupparbetsflöden.

Batchleverans kan också utföras med API:er. Mer information finns i [API-dokumentation för batchbeslut](api-reference/offer-delivery-api/batch-decisioning-api.md).

## Förutsättningar {#prerequisites}

Innan du konfigurerar en jobbförfrågan bör du kontrollera att du har skapat:

* **En datauppsättning** i Adobe Experience Platform. Den här datauppsättningen används för att lagra beslutsresultatet med ODE-schema för beslutshändelser. Läs mer i [Dokumentation för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html).

* **En publik** i Adobe Experience Platform. Publiken bör utvärderas och sedan uppdateras. Lär dig hur du uppdaterar utvärdering av medlemskap för målgrupper i [Dokumentation för segmenteringstjänst](http://www.adobe.com/go/segmentation-overview-en)

  >[!NOTE]
  >
  >Ett batchjobb tar bort profilögonblicksbilden som inträffar en gång om dagen. Vid gruppbeslut avbryts frekvensen och profiler läses alltid in från den senaste ögonblicksbilden. Förvänta dig att vänta upp till 24 timmar efter att du har skapat en målgrupp innan du provar API:t för gruppbeslut.

* **Ett beslut** i Adobe Journey Optimizer. [Lär dig hur du skapar ett beslut](offer-activities/create-offer-activities.md)

<!-- in API doc, remove these info and add ref here-->

## Skapa en jobbförfrågan

Följ stegen nedan för att skapa en ny jobbförfrågan.

1. I **[!UICONTROL Offers]** -menyn, öppna **[!UICONTROL Batch decisioning]** klicka sedan på **[!UICONTROL Create request]**.

   ![](assets/batch-create.png)

1. Namnge din jobbförfrågan och välj sedan den datauppsättning som jobbdata ska skickas till.

1. Välj målgrupp för Adobe Experience Platform.

1. Välj en eller flera beslutsmöjligheter för erbjudanden som du vill använda för att leverera erbjudanden till målgruppen:
   1. Välj en placering i listan.
   1. Vilka beslut som är tillgängliga för den valda placeringsskärmen. Välj önskat beslut och klicka på **[!UICONTROL Add]**.
   1. Upprepa åtgärden för att lägga till så många beslutsomfattningar som du vill.

   ![](assets/batch-decision.png)

1. Som standard returneras ett erbjudande i beslutsomfånget för varje profil. Du kan justera antalet returnerade erbjudanden med **[!UICONTROL Request offer per profile]** alternativ. Om du till exempel väljer 2 visas de två bästa erbjudandena för det valda beslutsområdet.

   >[!NOTE]
   >
   >Du kan begära upp till 30 erbjudanden per beslutsomfattning.

1. Om du vill inkludera erbjudandeinnehållet i datauppsättningen växlar du **[!UICONTROL Include content]** på. Det här alternativet är inaktiverat som standard.

1. Klicka **[!UICONTROL Create]** för att köra jobbbegäran.

## Övervaka batchjobb

Alla begärda batchjobb är tillgängliga från **[!UICONTROL Batch decisioning]** -fliken. Dessutom finns det sök- och filtreringsverktyg som hjälper dig att förfina listan.

![](assets/batch-list.png)

### Status för jobbförfrågningar

När en jobbförfrågan har skapats, går batchjobbet igenom flera statusvärden:

>[!NOTE]
>
>Om du vill vara säker på att du får den senaste informationen om jobbbegärans status använder du ellipsknappen bredvid jobbet för att uppdatera det.

1. **[!UICONTROL Queued]**: Jobbbegäran har skapats och har öppnats i behandlingskön. Upp till 5 batchjobb kan köras åt gången per datauppsättning. Alla andra gruppförfrågningar med samma utdatamängd läggs till i kön. Ett jobb i kö plockas upp för bearbetning när det föregående jobbet har slutförts.
1. **[!UICONTROL Processing]**: Jobbbegäran bearbetas
1. **[!UICONTROL Ingesting]**: Jobbbegäran har körts, resultatdata hämtas i den valda datauppsättningen,
1. **[!UICONTROL Completed]**: Jobbbegäran har körts och resultatdata lagras nu i den valda datauppsättningen.

   >[!NOTE]
   >
   >Du kan komma åt datauppsättningen där resultaten av ett jobb lagras genom att klicka på dess namn i jobblistan.

Om ett fel inträffar när jobbbegäran körs, får den **[!UICONTROL Error]** status. Försök att duplicera batchjobbet för att skapa en ny begäran. [Lär dig duplicera ett batchjobb](#duplicate)

### Bearbetningstid för batchjobb

Sluttiden för varje batchjobb är tiden från den tidpunkt då arbetsbelastningen skapas till den tidpunkt då beslutsresultatet är tillgängligt i utdatauppsättningen.

Målgruppsstorleken är den viktigaste faktorn som påverkar den kompletta batchbeslutstiden. Om det valbara erbjudandet har ett globalt frekvenstak aktiverat tar batchbeslutet ytterligare tid att slutföra. Nedan visas några uppskattningar av total bearbetningstid för respektive målgrupp, både med och utan frekvensbegränsning för berättigade erbjudanden:

Med frekvensbegränsning aktiverad för berättigade erbjudanden:

| Målgruppsstorlek | Tid för hela processen |
|--------------|----------------------------|
| 10 000 profiler eller mindre | 7 minuter |
| 1 miljon profiler eller mindre | 30 minuter |
| 15 miljoner profiler eller mindre | 50 minuter |

Utan frekvensbegränsning för berättigade erbjudanden:

| Målgruppsstorlek | Tid för hela processen |
|--------------|----------------------------|
| 10 000 profiler eller mindre | 6 minuter |
| 1 miljon profiler eller mindre | 8 minuter |
| 15 miljoner profiler eller mindre | 16 minuter |

## Duplicera en jobbförfrågan {#duplicate}

Du kan återanvända information om ett befintligt jobb för att skapa en ny begäran.

Om du vill göra det klickar du på ikonen Duplicera, redigerar jobbinformationen om det behövs och klickar sedan på **[!UICONTROL Create]** för att skapa den nya begäran.

![](assets/batch-duplicate.png)
