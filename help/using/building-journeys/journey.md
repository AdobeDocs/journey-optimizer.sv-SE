---
solution: Journey Optimizer
product: journey optimizer
title: Allmän princip
description: Allmän princip
feature: Journeys
topic: Content Management
role: User
level: Beginner
exl-id: 73cfd48b-72e6-4b72-bbdf-700a32a34bda
source-git-commit: f04454860ebe597d3306e62b58de5f32e08342ee
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 2%

---


# Allmän princip{#jo-general-principle}

Använd [!DNL Journey Optimizer] för att skapa realtidssamordning med hjälp av kontextuella data som lagras i händelser eller datakällor.

Utforma avancerade scenarier i flera steg med följande funktioner:

* Skicka i realtid **enhetlig leverans** aktiveras när en händelse tas emot, eller **i batch** med Adobe Experience Platform-segment.

* Utnyttja **kontextuella data** från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part.

* Använd **inbyggda funktionsmakron** för att skicka meddelanden som [!DNL Journey Optimizer] eller skapa **anpassade åtgärder** om du använder ett tredjepartssystem för att skicka meddelanden.

* Med **resedesigner** bygg upp flerstegstillämpningar: enkelt dra och släppa en tävlingshändelse eller en aktivitet i ett lässegment, lägga till villkor och skicka personaliserade meddelanden.

## Steg för att skapa en resa{#steps-journey}

Adobe Journey Optimizer har en flerkanalig orkestreringsyta som gör att marknadsförarna kan harmonisera marknadsföringen med ett-till-ett-kundengagemang. Med användargränssnittet kan du enkelt dra och släppa aktiviteter från paletten till arbetsytan för att skapa din resa. Observera att du även kan dubbelklicka på en aktivitet för att lägga till den på arbetsytan i nästa tillgängliga steg.

Lär dig hur du påbörjar och skapar din första resa på [den här sidan](journey-gs.md).

Lär dig använda resedesignern och kombinera aktiviteter för att skapa kraftfulla flerkanalsresor i [det här avsnittet](using-the-journey-designer.md).

Som datatekniker kan du lära dig hur du konfigurerar dina resor, inklusive datakällor, händelser och åtgärder i [det här avsnittet](../configuration/about-data-sources-events-actions.md).


## Användningsfall{#uc-journey}

Upptäck följande kompletta användningsexempel för att utnyttja
* Användningsexempel
   * [Skicka flerkanalsmeddelanden](journeys-uc.md)
   * [Skicka ett meddelande med Campaign v7/v8](campaign-classic-use-case.md)
   * [Skicka ett meddelande till prenumeranter](message-to-subscribers-uc.md)

* Tekniska användningsfall
   * [Skicka samlingar dynamiskt med anpassade åtgärder](collections.md)
   * [Rita upp leveranser](ramp-up-deliveries-uc.md)
   * [Begränsa genomströmning med externa datakällor och anpassade åtgärder](limit-throughput.md)

## Reseversioner{#journey-versions}

I reselistan visas alla reseversioner med versionsnumret. Läs [den här sidan](../building-journeys/using-the-journey-designer.md).

När du söker efter en resa visas de senaste versionerna högst upp i listan första gången programmet öppnas. Sedan kan du definiera den sortering som du vill ha så att programmet behåller den som en användarinställning. Färdens version visas också överst i reseupplagans gränssnitt, ovanför arbetsytan.

![](assets/journeyversions1.png)

>[!NOTE]
>
>I de flesta fall kan en profil inte finnas flera gånger på samma resa samtidigt. Om återinträde är aktiverat kan en profil återansluta en resa, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt. [Läs mer](end-journey.md).

Om du behöver ändra till en direktresa skapar du en ny version av din resa.

1. Öppna den senaste versionen av din liveresa och klicka **[!UICONTROL Create a new version]** och bekräfta.

   ![](assets/journeyversions2.png)

   >[!NOTE]
   >
   >Du kan bara skapa en ny version av den senaste versionen av en resa.

1. Gör ändringarna genom att klicka **[!UICONTROL Publish]** och bekräfta.

   ![](assets/journeyversions3.png)

Från det att resan har publicerats kommer individerna att börja flöda in i den senaste versionen av resan. Personer som redan har gått in i en tidigare version stannar kvar tills de är klara med resan. Om de senare återgår till samma resa, kommer de att gå till den senaste versionen.

Reseversioner kan stoppas individuellt. Alla versioner av resor har samma namn.

När du publicerar en ny version av en resa upphör den tidigare versionen automatiskt och växlar till **Stängd** status. Ingen inträde på resan kan ske. Även om du stoppar den senaste versionen förblir den tidigare versionen stängd.

>[!NOTE]
>
>Läs mer om säkerhetsregler och begränsningar för olika reseversioner i [den här sidan](../start/guardrails.md#journey-versions-limitations)