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
source-git-commit: ba870af16a92ffd5aae2bb4e0abb8f0cdbb8dc80
workflow-type: tm+mt
source-wordcount: '1737'
ht-degree: 5%

---

# Skapa den första resan{#jo-quick-start}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card2"
>title="Skapa resor"
>abstract="Använd **Adobe Journey Optimizer** för att skapa användningsfall för realtidssamordning med hjälp av kontextuella data lagrade i händelser eller datakällor."

## Förutsättningar{#start-prerequisites}

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

I listan över resor kan du filtrera resorna efter status, typ och version från **[!UICONTROL Status and version filters]**. Typen kan vara: **[!UICONTROL Unitary event]**, **[!UICONTROL Audience qualification]**, **[!UICONTROL Read audience]**, **[!UICONTROL Business event]** eller **[!UICONTROL Burst]**.

Du kan välja att endast visa resor som använder en specifik händelse, fältgrupp eller åtgärd från **[!UICONTROL Activity filters]** och **[!UICONTROL Data filters]**. Dessutom kan du **[!UICONTROL Publication filters]** gör att du kan välja ett publiceringsdatum eller en användare. Du kan till exempel välja att visa de senaste versionerna av direktresor som publicerades igår. [Läs mer](../building-journeys/using-the-journey-designer.md).

![](assets/filter-journeys.png)

Använd **[!UICONTROL Last update]** och **[!UICONTROL Last update by]** kolumner för att kontrollera när den senaste uppdateringen av dina resor gjordes och vem som sparade den.

I konfigurationsrutorna Händelse, Datakälla och Åtgärd visas **[!UICONTROL Used in]** fältet visar antalet resor som använder den aktuella händelsen, fältgruppen eller åtgärden. Du kan klicka på knappen **[!UICONTROL View journeys]** för att visa en lista över motsvarande resor.

![](assets/journey3bis.png)

## Bygg upp din resa{#jo-build}

Det här steget utförs av **företagsanvändare**. Här skapar du dina resor. Kombinera de olika händelserna, samordningen och åtgärderna för att skapa flerstegsscenarier för olika kanaler.

Här är de viktigaste stegen för att skicka meddelanden via resor:

1. Från **Bläddra** flik, klicka **[!UICONTROL Create Journey]** för att skapa en ny resa.

1. Redigera resans egenskaper i konfigurationsrutan som visas till höger. Läs mer om detta [section](journey-gs.md#change-properties).

   ![](assets/jo-properties.png)

1. Börja med att dra och släppa en händelse eller en **Läs målgrupp** från paletten till arbetsytan. Mer information om resedesign finns i [det här avsnittet](using-the-journey-designer.md).

   ![](assets/read-segment.png)

1. Dra och släpp nästa steg som personen kommer att följa. Du kan till exempel lägga till ett villkor följt av en kanalåtgärd. Mer information om aktiviteter finns i [det här avsnittet](using-the-journey-designer.md).

1. Testa din resa med testprofiler. Läs mer om detta [section](testing-the-journey.md)

1. Publicera resan för att aktivera den. Läs mer om detta [section](publishing-the-journey.md).

   ![](assets/jo-journeyuc2_32bis.png)

1. Övervaka din resa med de dedikerade rapportverktygen för att mäta hur effektiv din resa är. Läs mer om detta [section](../reports/live-report.md).

   ![](assets/jo-dynamic_report_journey_12.png)

## Definiera resans egenskaper {#change-properties}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties"
>title="Resans egenskaper"
>abstract="I det här avsnittet visas resans egenskaper. Som standard är skrivskyddade parametrar dolda. Vilka inställningar som är tillgängliga beror på resans status, på dina behörigheter och din produktkonfiguration."

Klicka på pennikonen i det övre högra hörnet för att komma åt resans egenskaper.

Du kan ändra namnet på resan, lägga till en beskrivning, tillåta återinträde, välja start- och slutdatum och, som administratör, definiera en **[!UICONTROL Timeout and error]** varaktighet. Du kan också tilldela enhetliga Adobe Experience Platform-taggar till din resa. På så sätt kan ni enkelt klassificera dem och förbättra sökningen från kampanjlistan. [Lär dig hur du arbetar med taggar](../start/search-filter-categorize.md#tags)

På den här skärmen visas publiceringsdatumet och namnet på den användare som publicerade resan.

The **Kopiera teknisk information** Med kan du kopiera teknisk information om den resa som supportteamet kan använda för att felsöka. Följande information kopieras: JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](assets/journey32.png)

### Ingång och återinträde {#entrance}

Som standard tillåter nya resor återinträde. Du kan avmarkera **Tillåt återinträde** om du vill erbjuda en engångspresentation när en person går in i en affär.

När **Tillåt återinträde** är aktiverat, **Vänteperiod för återinträde** -fältet visas. I det här fältet kan du definiera väntetiden innan du tillåter en profil att gå in på resan igen med en enda resa (med början från en händelse eller en målgruppskvalifikation). Detta förhindrar att resor utlöses felaktigt flera gånger för samma händelse. Som standard är fältet inställt på 5 minuter. Maximala längden är 29 dagar.

Läs mer om hantering av profilentré och återinträde på marknaden i [det här avsnittet](entry-management.md).

### Hantera åtkomst {#access}

Om du vill tilldela etiketter för anpassad eller grundläggande dataanvändning till resan klickar du på **[!UICONTROL Manage access]** -knappen. [Läs mer om OLA (Object Level Access Control)](../administration/object-based-access.md)

![](assets/journeys-manage-access.png)

### Tidszoner för resa och profil {#timezone}

Tidszonen definieras på resenivå. Du kan ange en fast tidszon eller använda Adobe Experience Platform-profiler för att definiera resetidszonen. Om en tidszon definieras i Adobe Experience Platform-profilen kan den hämtas under resan.

Mer information om hantering av tidszoner finns i [den här sidan](../building-journeys/timezone-management.md).

### Start- och slutdatum {#dates}

Du kan definiera en **Startdatum**. Om du inte har angett någon sådan kommer den att definieras automatiskt vid publiceringstidpunkten.

Du kan också lägga till en **Slutdatum**. Detta gör att profiler kan avslutas automatiskt när datumet nås. Om inget slutdatum anges kan profilerna behållas tills [tidsgräns för global resa](#global_timeout) (som i allmänhet är 30 dagar och reducerat till 7 dagar med tilläggserbjudanden för hälso- och sjukvårdsskölden och skölden för skydd av privatlivet). Det enda undantaget är återkommande läsningar på målgruppsresor med **Tvinga återinträde vid upprepning** som slutar vid startdatumet för nästa förekomst.

### Tidsgräns och fel i reseaktiviteter {#timeout_and_error}

När du redigerar en åtgärd eller villkorsaktivitet kan du definiera en alternativ sökväg om ett fel eller en timeout inträffar. Om bearbetningen av aktiviteten som förhör ett tredjepartssystem överskrider den tidsgräns som anges i färdens egenskaper (**[!UICONTROL Timeout and error]** -fält) väljs den andra sökvägen för att utföra en eventuell reservåtgärd.

Giltiga värden är mellan 1 och 30 sekunder.

Vi rekommenderar att du definierar en mycket kort **[!UICONTROL Timeout and error]** om resan är tidskänslig (exempel: reagera på en persons realtidsplats) eftersom du inte kan fördröja åtgärden i mer än några sekunder. Om resan är mindre tidskänslig kan du använda ett längre värde för att ge mer tid till det system som anropas för att skicka ett giltigt svar.

Journeys använder också en global tidsgräns. Se [nästa avsnitt](#global_timeout).

### Tidsgräns för global resa {#global_timeout}

Förutom [timeout](#timeout_and_error) som används i reseaktiviteter finns det också en timeout för den globala resan som inte visas i gränssnittet och som inte kan ändras.

Den här globala tidsgränsen stoppar de enskilda personernas framsteg under resan **30 dagar** efter att de gått in. Den här tidsgränsen reduceras till **7 dagar** med tillägg till skölden för hälso- och sjukvård samt skölden för skydd av privatlivet och säkerhet. Det innebär att en persons resa inte kan vara längre än 30 dagar (eller 7 dagar). Efter denna timeout-period tas personens data bort. Individer som fortfarande flyter i resan i slutet av timeoutperioden kommer att stoppas och de kommer inte att beaktas vid rapporteringen. Du kan därför se fler människor komma in på resan än att gå ut.

>[!NOTE]
>
>Resor reagerar inte direkt på förfrågningar om avanmälan, åtkomst eller radering av sekretess. Den globala tidsgränsen säkerställer dock att individer aldrig stannar mer än 30 dagar under någon resa.

På grund av den 30-dagars tidsgränsen för resan kan vi inte säkerställa att återinträdesspärren fungerar mer än 30 dagar när resan inte tillåts. Eftersom vi tar bort all information om personer som tagit sig in på resan 30 dagar efter ankomsten, kan vi inte veta vem som tagit sig in tidigare, mer än 30 dagar sedan.

En enskild person kan bara förlägga en vänteaktivitet om han eller hon har tillräckligt med tid kvar på resan för att slutföra väntetiden innan tidsgränsen på 30 dagar för resan har nåtts. Läs [den här sidan](../building-journeys/wait-activity.md).

## Duplicera en resa {#duplicate-a-journey}

Du kan duplicera en befintlig resa från **Bläddra** -fliken. Alla objekt och inställningar dupliceras till kopian av resan.

Gör så här:

1. Navigera till den resa du vill kopiera och klicka på **Fler åtgärder** -ikonen (de tre punkterna bredvid resans namn).
1. Välj **Duplicera**.

   ![Duplicera en resa](assets/duplicate-jo.png)

1. Ange namnet på resan och bekräfta. Du kan också ändra namnet på skärmen för reseegenskaper. Som standard anges namnet på följande sätt: `[JOURNEY-NAME]_copy`

   ![](assets/duplicate-jo2.png)

1. Den nya resan skapas och är tillgänglig i reselistan.
