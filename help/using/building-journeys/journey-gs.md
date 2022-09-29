---
title: Kom igång med resor
description: Viktiga steg för att skapa din första resa med Adobe Journey Optimizer
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: d940191e-8f37-4956-8482-d2df0c4274aa
source-git-commit: cca94d15da5473aa9890c67af7971f2e745d261e
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 8%

---

# Kom igång med resor{#jo-quick-start}

## Förutsättningar{#start-prerequisites}

För att kunna skicka meddelanden med resor krävs följande konfigurationer:

1. **Konfigurera en händelse**: Om du vill utlösa dina resor tills vidare när en händelse tas emot, måste du konfigurera en händelse. Du definierar den förväntade informationen och hur den ska behandlas. Det här steget utförs av en **teknisk användare**. [Läs mer](../event/about-events.md).

   ![](assets/jo-event7bis.png)

1. **Skapa ett segment**: resan även kan avlyssna Adobe Experience Platform-segment för att skicka meddelanden i grupp till en viss uppsättning profiler. Därför måste ni skapa segment. [Läs mer](../segment/about-segments.md).

   ![](assets/segment2.png)

1. **Konfigurera datakällan**: Du kan definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel under dina förhållanden. En inbyggd datakälla i Adobe Experience Platform konfigureras även vid tidpunkten för etablering. Det här steget är inte nödvändigt om du bara utnyttjar data från händelserna under din resa. Det här steget utförs av en **teknisk användare**. [Läs mer](../datasource/about-data-sources.md)

   ![](assets/jo-datasource.png)

1. **Konfigurera en åtgärd**: Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. Läs mer om detta [section](../action/action.md). Det här steget utförs av en **teknisk användare**. Om du använder Journey Optimizer inbyggda meddelandefunktioner behöver du bara lägga till en kanalåtgärd på kundresan och utforma innehållet. Se [det här avsnittet](../messages/get-started-content.md).

   ![](assets/custom2.png)

## Bygg upp din resa{#jo-build}

>[!CONTEXTUALHELP]
>id="ajo_journey_create"
>title="Bygg upp din resa"
>abstract="På den här skärmen visas en lista över befintliga resor. Öppna en resa eller klicka på Skapa resa och kombinera olika aktiviteter för evenemang, samordning och åtgärder för att skapa flerstegsscenarier för flera kanaler."

Det här steget utförs av **företagsanvändare**. Här skapar du dina resor. Kombinera de olika händelserna, orkestreringen och åtgärderna för att skapa scenarier i flera steg över olika kanaler.

Här är de viktigaste stegen för att skicka meddelanden via resor:

1. Klicka på **[!UICONTROL Journeys]**. Listan över resor visas.

   ![](assets/interface-journeys.png)

1. Klicka **[!UICONTROL Create Journey]** för att skapa en ny resa.

1. Redigera resans egenskaper i konfigurationsrutan som visas till höger. Läs mer om detta [section](journey-gs.md#change-properties).

   ![](assets/jo-properties.png)

1. Börja med att dra och släppa en händelse eller en **Läs segment** från paletten till arbetsytan. Mer information om resedesign finns i [det här avsnittet](using-the-journey-designer.md).

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

Du kan ändra namnet på resan, lägga till en beskrivning, tillåta återinträde, välja start- och slutdatum och, som administratör, definiera en **[!UICONTROL Timeout and error]** varaktighet.

På den här skärmen visas publiceringsdatumet och namnet på den användare som publicerade resan.

The **Kopiera teknisk information** Med kan du kopiera teknisk information om den resa som supportteamet kan använda för att felsöka. Följande information kopieras: JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](assets/journey32.png)

### Ingång{#entrance}

Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet för engångsresor, till exempel om du vill erbjuda en engångsgåva när en person går in i en affär. I så fall vill ni inte att kunden ska kunna registrera sig på nytt och få erbjudandet igen.

När en resa&quot;slutar&quot; får den statusen **[!UICONTROL Closed]**. Resan kommer att sluta låta nya individer komma in på resan. Personer som redan är på resan kommer att slutföra resan normalt.

Efter den globala standardtidsgränsen på 30 dagar växlar resan till **Slutförd** status. Se det här [section](../building-journeys/journey-gs.md#global_timeout).

>[!NOTE]
>
>Enhetsresor (med början vid en händelse eller en segmentkvalificering) innehåller ett skyddsräcke som förhindrar att resorna aktiveras felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras tillfälligt som standard i 5 minuter. Om en händelse till exempel utlöser en resa kl. 12:01 för en viss profil och en annan tar emot kl. 12:03 (oavsett om det är samma händelse eller en annan som utlöser samma resa) kommer den resan inte att starta igen för den här profilen.

### Tidsgräns och fel i reseaktiviteter {#timeout_and_error}

När du redigerar en åtgärd eller villkorsaktivitet kan du definiera en alternativ sökväg om ett fel eller en timeout inträffar. Om bearbetningen av aktiviteten som förhör ett tredjepartssystem överskrider den tidsgräns som anges i färdens egenskaper (**[!UICONTROL Timeout and  error]** -fält) väljs den andra sökvägen för att utföra en eventuell reservåtgärd.

Giltiga värden är mellan 1 och 30 sekunder.

Vi rekommenderar att du definierar en mycket kort **[!UICONTROL Timeout and error]** om resan är tidskänslig (exempel: att reagera på en persons realtidsplats) eftersom du inte kan fördröja åtgärden i mer än några sekunder. Om resan är mindre tidskänslig kan du använda ett längre värde för att ge mer tid till det system som anropas för att skicka ett giltigt svar.

Journeys använder också en global tidsgräns. Se [nästa avsnitt](#global_timeout).

### Tidsgräns för global resa {#global_timeout}

Förutom [timeout](#timeout_and_error) som används i reseaktiviteter finns det också en timeout för den globala resan som inte visas i gränssnittet och som inte kan ändras. Den här tidsgränsen kommer att stoppa enskilda personers framsteg på resan 30 dagar efter att de har kommit in. Det innebär att en persons resa inte kan vara längre än 30 dagar. Efter timeoutperioden på 30 dagar tas personens data bort. Individer som fortfarande flyter på i slutet av tidsgränsen kommer att stoppas och de kommer att beaktas som fel vid rapporteringen.

>[!NOTE]
>
>Resor reagerar inte direkt på förfrågningar om avanmälan, åtkomst eller radering av sekretess. Den globala tidsgränsen säkerställer dock att individer aldrig stannar mer än 30 dagar under någon resa.

På grund av den 30-dagars tidsgränsen för resan kan vi inte säkerställa att återinträdesspärren fungerar mer än 30 dagar när resan inte tillåts. Eftersom vi tar bort all information om personer som tagit sig in på resan 30 dagar efter ankomsten, kan vi inte veta vem som tagit sig in tidigare, mer än 30 dagar sedan.

### Tidszon och profiltidszon {#timezone}

Tidszonen definieras på resenivå.

Du kan ange en fast tidszon eller använda Adobe Experience Platform-profiler för att definiera resetidszonen.

Om en tidszon definieras i Adobe Experience Platform-profilen kan den hämtas under resan.

Mer information om hantering av tidszoner finns i [den här sidan](../building-journeys/timezone-management.md).

### Hantera åtkomst {#access}

Klicka på **[!UICONTROL Manage access]** -knappen. [Läs mer om OLA (Object Level Access Control)](../administration/object-based-access.md)

![](assets/journeys-manage-access.png)
