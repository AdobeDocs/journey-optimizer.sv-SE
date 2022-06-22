---
title: Kom igång med resor
description: Viktiga steg för att skapa din första resa med Adobe Journey Optimizer
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: d940191e-8f37-4956-8482-d2df0c4274aa
source-git-commit: 8a68d1e6d498ef3055c703d4e73471ab6d7bff40
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 7%

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

1. **Konfigurera en åtgärd**: Journey Optimizer meddelandefunktioner är inbyggda, du behöver bara utforma ditt innehåll och publicera ditt budskap. Se [det här avsnittet](../messages/get-started-content.md). Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. Läs mer om detta [section](../action/action.md). Det här steget utförs av en **teknisk användare**.

   ![](assets/create-content-push.png)

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

1. Dra och släpp nästa steg som personen kommer att följa. Du kan till exempel lägga till ett villkor följt av ett meddelande. Mer information om aktiviteter finns i [det här avsnittet](using-the-journey-designer.md).

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

Du kan ändra namnet på resan, lägga till en beskrivning, tillåta återinträde, välja start- och slutdatum och, som administratör, definiera en **[!UICONTROL Timeout and error]** varaktighet. Om det är aktiverat för din organisation kan du även aktivera [burst messaging](#burst).

På den här skärmen visas publiceringsdatumet och namnet på den användare som publicerade resan.

The **Kopiera teknisk information** Med kan du kopiera teknisk information om den resa som supportteamet kan använda för att felsöka. Följande information kopieras: JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](assets/journey32.png)

### Ingång{#entrance}

Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet för engångsresor, till exempel om du vill erbjuda en engångsgåva när en person går in i en affär. I så fall vill ni inte att kunden ska kunna registrera sig på nytt och få erbjudandet igen.

När en resa&quot;slutar&quot; får den statusen **[!UICONTROL Closed]**. Resan kommer att sluta låta nya individer komma in på resan. Personer som redan är på resan kommer att slutföra resan normalt.

Efter den globala standardtidsgränsen på 30 dagar växlar resan till **Slutförd** status. Se det här [section](../building-journeys/journey-gs.md#global_timeout).

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

### Burst-läge {#burst}

Burst-läget är ett Journey Optimizer-tillägg som gör att det går att skicka mycket snabba push-meddelanden i stora volymer. Det används för enkla resor som innehåller en **Lässegment** och ett enkelt push-meddelande. Burst används när fördröjning i meddelandeleverans är affärskritisk när du vill skicka en snabb push-varning på mobiltelefoner, till exempel ett meddelande om nyheter till användare som har installerat din nyhetskanalapp.

Burst-meddelanden innehåller följande krav:

* Resan måste börja med en **Lässegment** aktivitet. Händelser tillåts inte.
* Nästa steg måste vara ett push-meddelande. Ingen annan kanal, aktivitet eller steg tillåts.
* Ingen personalisering tillåts i push-meddelandet.
* Meddelandet måste vara litet (&lt;2kB).

>[!CAUTION]
>
>Om något av kraven inte är uppfyllt, är inte sprängningsläget tillgängligt under resan.

Aktivera **Burst-läge**&#x200B;öppnar du resan och klickar på pennikonen längst upp till höger för att komma åt resans egenskaper. Aktivera sedan **Aktivera sprängningsläge** växla.

![](assets/burst.png)

Burst-läget inaktiveras automatiskt om du ändrar en burst-resa och lägger till en aktivitet som inte är kompatibel med burst-meddelanden, till exempel ett e-postmeddelande, andra åtgärder, en händelse osv.

![](assets/burst2.png)

Testa och publicera sedan din resa som vanligt. Observera att meddelanden inte skickas i sprängningsläge i testläge.

I den här videon får du veta vilka användningsexempel som gäller för burst-meddelanden och hur du konfigurerar en resa för burst-meddelanden:

>[!VIDEO](https://video.tv.adobe.com/v/334523?quality=12)
