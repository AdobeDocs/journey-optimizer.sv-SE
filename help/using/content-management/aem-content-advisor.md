---
solution: Journey Optimizer
product: journey optimizer
title: Öppna Adobe Experience Manager Content Advisor
description: Lär dig hur du får tillgång till och använder Adobe Experience Manager Content Advisor för att identifiera resurser och innehållsfragment med hjälp av AI-baserad semantisk sökning i Adobe Journey Optimizer.
role: User
level: Beginner, Intermediate
hide: true
hidefromtoc: true
source-git-commit: 58b6300dd00cc4475397d117a705fe88deab1796
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---


# Arbeta med Adobe Experience Manager Content Advisor {#aem-content-advisor}

>[!AVAILABILITY]
>
>Adobe Experience Manager Content Advisor är endast tillgängligt i kanalutvecklingsarbetsflöden.

Adobe Experience Manager Content Advisor ersätter deterministisk upptäckt med standardiserad intent-driven identifiering från en enhetlig yta. Det möjliggör en enhetlig, AI-driven identifiering av Assets- och Content Fragments direkt i Journey Optimizer arbetsflöden, vilket förbättrar marknadsföringens produktivitet och kampanjeffektivitet.

## Tillgängliga funktioner

### För Assets {#asset-features}

Adobe Experience Manager Content Advisor innehåller följande resursfunktioner:

* 
  +++ AI-semantisk sökning

  Sök efter resurser på ett naturligt språk i stället för med exakta nyckelord eller filnamn. Beskriv vad du behöver på ett enkelt språk, till exempel&quot;kaffe i bergen&quot;, så hittar AI sammanhangsberoende resurser baserat på innebörd och innehåll, inte bara textmatchningar.

  ![](assets/content-advisor-2.png){zoomable="yes"}

  +++

* 
  +++ Historik för senaste sökningar

  Kom åt dina senaste sökningar och återanvänd nyckelord och kontexter. Detta sparar tid när ni arbetar med liknande kampanjer eller behöver förfina tidigare sökningar.

  ![](assets/content-advisor-4.png){zoomable="yes"}

  +++ 

* 
  +++ Överför i korthet

  Ladda upp ett kort marknadsföringsdokument för att automatiskt visa resurser som är anpassade till ert kampanjsammanhang. AI analyserar sammanfattningen och föreslår relevanta resurser baserat på innehållet och kraven som beskrivs i dokumentet.

  ![](assets/content-advisor-5.png){zoomable="yes"}

  +++

* 
  +++ Panelen Resursinformation

  Visa detaljerade metadata och egenskaper för alla resurser med hjälp av ikonen **Info** . Detta inkluderar resursdimensioner, filstorlek, datum när de skapades, taggar och annan relevant information som hjälper dig att fatta välgrundade beslut.

  ![](assets/content-advisor-6.png){zoomable="yes"}

  +++

* 
  +++ Panelen Dynamiska media

  Få tillgång till dynamiska renderingar, smarta beskärningar och snabba ändringar baserat på databaskonfigurationen.

  ![](assets/content-advisor-1.png){zoomable="yes"}

  Panelen Dynamic Media ger tillgång till dynamiska renderingar, smarta beskärningar och ändringar direkt. Du kan ange modifierare direkt på panelen för att skapa anpassade återgivningar.

  **Tillgänglighet**

  Tillgängligheten för dynamiska media beror på din databaskonfiguration:

   * **Scene7**: Tillgängligt för publicerade resurser (utom Video och PDF). [Läs mer om modifierare i Dynamic Media Scene7](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/r-is-http-modifiers.html){target="_blank"}

   * **OpenAPI**: Tillgängligt för godkända resurser (utom video). [Läs mer om Dynamic Media med OpenAPI-modifierare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/dynamicmedia/image-profiles.html){target="_blank"}

   * **Både Scene7 och OpenAPI**: Tillgängligt när båda konfigurationerna finns och resursen uppfyller villkoren.

  **Gruppmarkering**

  Vilka knappar du ser beror på din databaskonfiguration:

   * **Scene7-knappen är bara**: Databasen har Scene7-konfiguration och resursen publiceras till Dynamic Media.
   * **Endast OpenAPI-knappen**: Databasen har OpenAPI-konfiguration och resursen har godkänts.
   * **Båda knapparna**: Databasen har både konfigurationer och resursen är både publicerad och godkänd.
  +++

### För innehållsfragment {#content-fragment-features}

Adobe Experience Manager Content Advisor innehåller följande funktioner för innehållsfragment:

* 
  +++ Mallvylista 

  Växla mellan miniatyr- och tabellvyer för att bläddra bland innehållsfragment i det format som passar ditt arbetsflöde bäst. Miniatyrbildsvyn ger visuell kontext medan tabellvyn visar detaljerad information i ett strukturerat format.

  ![](assets/content-advisor-7.png){zoomable="yes"}

  +++

* 
  +++ Informationspanelen 

  Klicka på ikonen **[!UICONTROL Info]** för att öppna en högerpanel med fragmentvariationer, egenskaper och **[!UICONTROL Referenced By]** information. Avsnittet **[!UICONTROL Referenced By]** visar alla Adobe Experience Manager-entiteter där fragmentet används, med länkar för att visa dessa referenser direkt i Adobe Experience Manager.

  ![](assets/content-advisor-8.png){zoomable="yes"}

  +++

* 
  +++ Öppna i Adobe Experience Manager

  Öppna snabbt ett innehållsfragment direkt i Adobe Experience Manager för redigering med ikonen bredvid titeln. Denna smidiga integrering gör att du kan växla mellan Journey Optimizer och Adobe Experience Manager utan att tappa sitt sammanhang.

  ![](assets/content-advisor-9.png){zoomable="yes"}

  +++

* 
  +++ JSON-förhandsgranskning

  Förhandsgranska JSON-strukturen för innehållsfragment i ett rent, organiserat tabellformat. Detta hjälper er att förstå fragmentets datastruktur och verifiera innehåll innan ni använder det i era kampanjer.

  ![](assets/content-advisor-10.png){zoomable="yes"}

  +++

## Öppna Adobe Experience Manager Content Advisor {#access}

Gör så här för att få tillgång till Adobe Experience Manager Content Advisor i Journey Optimizer:

1. Skapa en kampanj i Adobe Journey Optimizer och lägg till en kanalåtgärd, till exempel E-post.

1. Klicka på **[!UICONTROL Edit Content]** och sedan på **[!UICONTROL Edit Email Body]** för att öppna innehållsredigeraren.

1. Dra och släpp en HTML- eller Text-komponent i e-postinnehållet.

1. Håll pekaren över komponenten och klicka på **[!UICONTROL Show the source code]** (för HTML-komponenter) eller **[!UICONTROL Add Personalization]** (för Text-komponenter).

1. I Personalization Editor väljer du innehållets startpunkt:

   * Om du vill lägga till en resurs klickar du på **[!UICONTROL Assets]** och sedan på **[!UICONTROL Open Asset Selector]**.

     ![](assets/content-advisor-11.png){zoomable="yes"}

   * Om du vill lägga till ett Adobe Experience Manager-innehållsfragment klickar du på **[!UICONTROL AEM Content Fragment]** och sedan på **[!UICONTROL Open AEM CF Selector]**.

     ![](assets/content-advisor-12.png){zoomable="yes"}

1. Välj Adobe Experience Manager-databas.

   ![](assets/content-advisor-13.png){zoomable="yes"}

1. Bläddra och markera resursen eller innehållsfragmentet som du vill använda och infoga det sedan i innehållet.


