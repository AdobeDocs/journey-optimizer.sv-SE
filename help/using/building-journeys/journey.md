---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med resor
description: Kom igång med resor
feature: Journeys, Get Started, Overview
role: User
level: Beginner, Intermediate
keywords: resa, upptäckt, komma igång
exl-id: 73cfd48b-72e6-4b72-bbdf-700a32a34bda
source-git-commit: 7f21098d5ae157f1c0d3de3aa584564c6f73310a
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---


# Kom igång med resor{#jo-general-principle}

Använd [!DNL Journey Optimizer] för att skapa användningsfall för realtidssamordning med hjälp av kontextuella data som lagras i händelser eller datakällor.

Utforma avancerade scenarier i flera steg med följande funktioner:

* Skicka **enhetsleverans** i realtid när en händelse tas emot, eller **i batch** med Adobe Experience Platform-målgrupper.

* Utnyttja **sammanhangsbaserade data** från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part.

* Använd de **inbyggda åtgärderna** för att skicka meddelanden som är utformade i [!DNL Journey Optimizer] eller skapa **anpassade åtgärder** om du använder ett tredjepartssystem för att skicka meddelanden.

* Med **resedesignern** kan du skapa dina flerstegsfall: enkelt dra och släppa en anmälningshändelse eller en läsningsaktivitet, lägga till villkor och skicka personaliserade meddelanden.

>[!NOTE]
>
>Reservoarer och begränsningar för resan finns på [den här sidan](../start/guardrails.md)

## Steg för att skapa en resa{#steps-journey}

Använd Adobe Journey Optimizer för att utforma och samordna personaliserade resor från en arbetsyta. De viktigaste stegen för att skapa en resa är följande:

![](assets/journey-creation-process.png)

➡️ [Upptäck den här funktionen i videon](#video)

Adobe Journey Optimizer har en flerkanalig orkestreringsyta som gör att marknadsförarna kan harmonisera marknadsföringen med ett-till-ett-kundengagemang. Med användargränssnittet kan du enkelt dra och släppa aktiviteter från paletten till arbetsytan för att skapa din resa.

![](assets/interface-journeys.png)

Lär dig hur du startar och skapar din första resa på [den här sidan](journey-gs.md).

Flerkanalsdesignern hjälper er att skapa flerstegsresor med riktade målgrupper, uppdateringar baserade på kundinteraktioner eller affärsinteraktioner i realtid och flerkanalsmeddelanden med ett intuitivt dra-och-släpp-gränssnitt.

![](assets/journey38.png)

Läs mer i [det här avsnittet](using-the-journey-designer.md).

Som datatekniker beskrivs stegen för att konfigurera dina resor, inklusive datakällor, händelser och åtgärder i [det här avsnittet](../configuration/about-data-sources-events-actions.md).


## Användningsfall{#uc-journey}

Lär dig hur du bygger resor i följande situationer:

Affärsexempel:

* [Skicka flerkanalsmeddelanden](journeys-uc.md)
* [Skicka ett meddelande med Campaign v7/v8](ajo-ac.md)
* [Skicka ett meddelande till prenumeranter](message-to-subscribers-uc.md)

Tekniska användningsfall:

* [Skicka samlingar dynamiskt med anpassade åtgärder](collections.md)
* [Begränsa genomströmning med externa datakällor och anpassade åtgärder](limit-throughput.md)

## Reseversioner{#journey-versions}

I reselistan visas alla reseversioner med versionsnumret. Läs [den här sidan](../building-journeys/using-the-journey-designer.md).

När du söker efter en resa visas de senaste versionerna högst upp i listan första gången programmet öppnas. Sedan kan du definiera den sortering som du vill ha så att programmet behåller den som en användarinställning. Färdens version visas också överst i reseupplagans gränssnitt, ovanför arbetsytan.

![](assets/journeyversions1.png)

>[!NOTE]
>
>Vanligtvis kan en profil inte finnas flera gånger på samma resa samtidigt. Om återinträde är aktiverat kan en profil återansluta en resa, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt. [Läs mer](end-journey.md).

Om du behöver ändra till en direktresa skapar du en ny version av din resa.

1. Öppna den senaste versionen av din liveresa, klicka på **[!UICONTROL Create a new version]** och bekräfta.

   ![](assets/journeyversions2.png)

   >[!NOTE]
   >
   >Du kan bara skapa en ny version av den senaste versionen av en resa.

1. Gör ändringarna, klicka på **[!UICONTROL Publish]** och bekräfta.

Från det att resan har publicerats kommer individerna att börja flöda in i den senaste versionen av resan. Personer som redan har gått in i en tidigare version stannar kvar tills de är klara med resan. Om de senare kommer in på samma resa igen kommer de att gå in i den senaste versionen.

Reseversioner kan stoppas individuellt. Alla versioner av resor har samma namn.

När du publicerar en ny version av en resa avslutas den tidigare versionen automatiskt och ändras till statusen **Stängd** . Ingen inträde på resan kan ske. Även om du stoppar den senaste versionen förblir den tidigare versionen stängd.

## Instruktionsvideo {#video}

Identifiera komponenterna i en resa och förstå grunderna för hur man bygger en resa på arbetsytan.

>[!VIDEO](https://video.tv.adobe.com/v/3424996?quality=12)
