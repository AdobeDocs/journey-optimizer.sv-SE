---
solution: Journey Optimizer
product: journey optimizer
title: Skapa den första resan
description: Viktiga steg för att skapa din första resa med Adobe Journey Optimizer
feature: Journeys, Get Started
topic: Content Management
role: User
level: Intermediate
keywords: resa, första, start, snabbstart, målgrupp, händelse, åtgärd
exl-id: d940191e-8f37-4956-8482-d2df0c4274aa
source-git-commit: fec6b15db9f8e6b2a07b55bc9e8fc4d9cb0d73d7
workflow-type: tm+mt
source-wordcount: '1215'
ht-degree: 7%

---

# Skapa den första resan{#jo-quick-start}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card2"
>title="Skapa resor"
>abstract="Använd **Adobe Journey Optimizer** för att skapa användningsfall för realtidssamordning med hjälp av kontextuella data lagrade i händelser eller datakällor."


## Förhandskrav{#start-prerequisites}

För att kunna skicka meddelanden med resor krävs följande konfigurationer:

1. **Konfigurera en händelse**: Om du vill utlösa dina resor tills när en händelse tas emot måste du konfigurera en händelse. Du definierar den förväntade informationen och hur den ska behandlas. Det här steget utförs av en **teknisk användare**. [Läs mer](../event/about-events.md).

   ![](assets/jo-event7bis.png)

1. **Skapa en målgrupp**: resan kan även avlyssna Adobe Experience Platform målgrupper för att skicka meddelanden i grupp till en viss uppsättning profiler. Därför måste ni skapa målgrupper. [Läs mer](../audience/about-audiences.md).

   ![](assets/segment2.png)

1. **Konfigurera datakällan**: du kan definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel under dina förhållanden. En inbyggd datakälla i Adobe Experience Platform konfigureras även vid tidpunkten för etablering. Det här steget är inte nödvändigt om du bara utnyttjar data från händelserna under din resa. Det här steget utförs av en **teknisk användare**. [Läs mer](../datasource/about-data-sources.md)

   ![](assets/jo-datasource.png)

1. **Konfigurera en åtgärd**: Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. Läs mer om detta [section](../action/action.md). Det här steget utförs av en **teknisk användare**. Om du använder Journey Optimizer inbyggda meddelandefunktioner behöver du bara lägga till en kanalåtgärd på kundresan och utforma innehållet.

   ![](assets/custom2.png)

## Åtkomstresor {#journey-access}

>[!CONTEXTUALHELP]
>id="ajo_journey_create"
>title="Resor"
>abstract="Utforma kundresor för att leverera personaliserade, sammanhangsbaserade upplevelser. Med Journey Optimizer kan du skapa användningsfall för realtidssamordning med kontextuella data som lagras i händelser eller datakällor. The **Ökning** visas en instrumentpanel med nyckelvärden för dina resor. The **Bläddra** -fliken visar en lista över befintliga resor."

### Viktiga mätvärden och reselista {#access-metrics}

Klicka på **[!UICONTROL Journeys]**. Det finns två flikar:

**Ökning**: den här fliken visar en instrumentpanel med viktiga mått för dina resor:

* **Bearbetade profiler**: totalt antal profiler som har bearbetats under de senaste 24 timmarna
* **Direktresor**: Totalt antal levande resor med trafik under de senaste 24 timmarna. Livesändningar omfattar **Enhetsresor** (händelsebaserad) och **Batchresor** (läsare).
* **Felfrekvens**: förhållandet mellan alla felaktiga profiler och det totala antalet profiler som har angetts under de senaste 24 timmarna.
* **Ignorera frekvens**: förhållandet mellan alla ignorerade profiler och totalt antal profiler som har angetts under de senaste 24 timmarna. En ignorerad profil representerar en person som inte är berättigad att delta i resan, till exempel på grund av ett felaktigt namnutrymme eller på grund av regler för återinträde.

>[!NOTE]
>
>På denna kontrollpanel beaktas trafiken under de senaste 24 timmarna. Endast de resor du har åtkomst till visas. Mätvärdena uppdateras var 30:e minut och endast när nya data är tillgängliga.

![](assets/journeys-dashboard.png)

**Bläddra**: den här fliken visar en lista över befintliga resor. Du kan söka efter resor, använda filter och utföra grundläggande åtgärder för varje element. Du kan till exempel duplicera eller ta bort ett objekt. Mer information hittar du i [det här avsnittet](../start/user-interface.md#filter-lists).

![](assets/journeys-browse.png)

### Filtrera resor {#filter}

I listan över resor kan du använda olika filter för att förfina listan över resor för bättre läsbarhet.

![](assets/filter-journeys.png)

Här är de olika filtreringsåtgärderna som du kan utföra:

Filtrera resor efter status, typ, version och tilldelade taggar från **[!UICONTROL Status and version filters]**.

Typen kan vara: **[!UICONTROL Unitary event]**, **[!UICONTROL Audience qualification]**, **[!UICONTROL Read audience]** eller **[!UICONTROL Business event]**.

Status kan vara:

* **Stängd**: resan har avslutats med **Nära nya ingångar** -knappen. Resan slutar med att nya individer kan komma in på resan. Personer som redan är på resan kan slutföra resan normalt.
* **Utkast**: resan befinner sig i sitt första skede. Den har inte publicerats än.
* **Utkast (test)**: testläget har aktiverats med **Testläge** -knappen.
* **Slutförd**: resan automatiskt övergår till denna status efter 91-dagarsperioden [global timeout](journey-properties.md#global_timeout). Profiler som redan finns på resan slutför normalt. Nya profiler kan inte längre komma in på resan.
* **Live**: resan har publicerats med **Publicera** -knappen.
* **Stoppad**: resan har stängts av med **Stoppa** -knappen. Alla individer lämnar resan direkt.

>[!NOTE]
>
>Reseutvecklingscykeln innehåller också en uppsättning mellanliggande statusvärden som inte är tillgängliga för filtrering: &quot;Publicera&quot; (mellan &quot;Utkast&quot; och &quot;Live&quot;), &quot;Aktivera testläge&quot; eller &quot;Inaktivera testläge&quot; (mellan &quot;Utkast&quot; och &quot;Utkast (test)&quot;) och &quot;Stoppar&quot; (mellan &quot;Live&quot; och &quot;Stoppad&quot;). När en resa befinner sig i ett mellanliggande tillstånd är den skrivskyddad.

Använd **[!UICONTROL Creation filters]** för att filtrera resorna efter när de skapades eller efter den användare som skapade dem.

Visa resor som använder en specifik händelse, fältgrupp eller åtgärd från **[!UICONTROL Activity filters]** och **[!UICONTROL Data filters]**.

Använd **[!UICONTROL Publication filters]** för att välja ett publiceringsdatum eller en användare. Du kan till exempel välja att visa de senaste versionerna av direktresor som publicerades igår.

Om du vill filtrera resor baserat på ett visst datumintervall väljer du **[!UICONTROL Custom]** från **[!UICONTROL Published]** listruta.

I konfigurationspanelerna Händelse, Datakälla och Åtgärd visas dessutom **[!UICONTROL Used in]** fältet visar antalet resor som använder den aktuella händelsen, fältgruppen eller åtgärden. Du kan klicka på knappen **[!UICONTROL View journeys]** för att visa en lista över motsvarande resor.

![](assets/journey3bis.png)

## Bygg upp din resa {#jo-build}

Designa resor för att leverera personaliserade, sammanhangsbaserade upplevelser. [!DNL Journey Optimizer] gör att du kan skapa användningsfall för realtidssamordning med kontextuella data lagrade i händelser eller datakällor. Utforma avancerade scenarier i flera steg med följande funktioner:

* Skicka i realtid **enhetlig leverans** aktiveras när en händelse tas emot, eller **i batch** med Adobe Experience Platform målgrupper.

* Utnyttja **kontextuella data** från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part.

* Använd **inbyggda kanalåtgärder** (E-post, SMS, push, InApp) för att skicka meddelanden som är utformade i [!DNL Journey Optimizer] eller skapa **anpassade åtgärder** om du använder ett tredjepartssystem för att skicka meddelanden.

* Med **resedesigner** bygg upp era flerstegssituationer: dra och släpp enkelt en anmälningshändelse eller en läs målgruppsaktivitet, lägg till villkor och skicka personaliserade meddelanden.

➡️ [Upptäck den här funktionen i video](journey.md#video)

Steg för att skicka meddelanden via resor listas nedan.

1. Från **Bläddra** flik, klicka **[!UICONTROL Create Journey]** för att skapa en ny resa.

1. Redigera resans egenskaper i konfigurationsrutan som visas till höger. Lär dig hur du ställer in resans egenskaper i detta [den här sidan](journey-properties.md).

   ![](assets/jo-properties.png)

1. Börja med att dra och släppa en händelse eller en **Läs målgrupp** från paletten till arbetsytan. Mer information om resedesign finns i [det här avsnittet](using-the-journey-designer.md).

   ![](assets/read-segment.png)

1. Dra och släpp nästa steg som personen kommer att följa. Du kan till exempel lägga till ett villkor följt av en kanalåtgärd. Mer information om aktiviteter finns i [det här avsnittet](using-the-journey-designer.md).

1. Testa din resa med testprofiler. Läs mer om detta [section](testing-the-journey.md)

1. Publicera resan för att aktivera den. Läs mer om detta [section](publishing-the-journey.md).

   ![](assets/jo-journeyuc2_32bis.png)

1. Övervaka din resa med de dedikerade rapportverktygen för att mäta hur effektiv din resa är. Läs mer om detta [section](../reports/live-report.md).

   ![](assets/jo-dynamic_report_journey_12.png)


## Duplicera en resa {#duplicate-a-journey}

Du kan duplicera en befintlig resa från **Bläddra** -fliken. Alla objekt och inställningar dupliceras till kopian av resan.

Gör så här:

1. Navigera till den resa du vill kopiera och klicka på **Fler åtgärder** -ikonen (de tre punkterna bredvid resans namn).
1. Välj **Duplicera**.

   ![Duplicera en resa](assets/duplicate-jo.png)

1. Ange namnet på resan och bekräfta. Du kan också ändra namnet på skärmen för reseegenskaper. Som standard anges namnet på följande sätt: `[JOURNEY-NAME]_copy`

   ![](assets/duplicate-jo2.png)

1. Den nya resan skapas och är tillgänglig i reselistan.
