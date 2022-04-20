---
title: Kom igång med resor
description: Viktiga steg för att skapa din första resa med Adobe Journey Optimizer
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: d940191e-8f37-4956-8482-d2df0c4274aa
source-git-commit: a68cfae875b18266417e115d17c73cda7061475d
workflow-type: tm+mt
source-wordcount: '1793'
ht-degree: 6%

---

# Kom igång med resor{#jo-quick-start}

## Krav

För att kunna skicka meddelanden med resor krävs följande konfiguration:

1. **Konfigurera en händelse**: Om du vill utlösa dina resor tills vidare när en händelse tas emot, måste du konfigurera en händelse. Du definierar den förväntade informationen och hur den ska behandlas. Det här steget utförs av en **teknisk användare**. [Läs mer](../event/about-events.md).

   ![](assets/jo-event7bis.png)

1. **Skapa ett segment**: resan även kan avlyssna Adobe Experience Platform-segment för att skicka meddelanden i grupp till en viss uppsättning profiler. Därför måste ni skapa segment. [Läs mer](../segment/about-segments.md).

   ![](assets/segment2.png)

1. **Konfigurera datakällan**: Du kan definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel under dina förhållanden. En inbyggd datakälla i Adobe Experience Platform konfigureras även vid tidpunkten för etablering. Det här steget är inte nödvändigt om du bara utnyttjar data från händelserna under din resa. Det här steget utförs av en **teknisk användare**. [Läs mer](../datasource/about-data-sources.md)

   ![](assets/jo-datasource.png)

1. **Konfigurera en åtgärd**: Journey Optimizer meddelandefunktioner är inbyggda, du behöver bara utforma ditt innehåll och publicera ditt budskap. Se [det här avsnittet](../messages/get-started-content.md). Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. Läs mer om detta [section](../action/action.md). Det här steget utförs av en **teknisk användare**.

   ![](assets/create-content-push.png)

## Bygga din resa{#jo-build}

>[!CONTEXTUALHELP]
>id="ajo_journey_create"
>title="Bygg upp din resa"
>abstract="På den här skärmen visas en lista med tidigare skapade resor. Öppna en resa eller klicka på Skapa resa och kombinera olika aktiviteter för evenemang, samordning och åtgärder för att skapa flerstegsscenarier för flera kanaler."

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

## Ändra egenskaper {#change-properties}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties"
>title="Resans egenskaper"
>abstract="Du kan ändra namnet på resan, lägga till en beskrivning, tillåta återinträde, välja start- och slutdatum och definiera en timeout och felvaraktighet om du är administratör."

Klicka på pennikonen i det övre högra hörnet för att komma åt resans egenskaper.

Du kan ändra namnet på resan, lägga till en beskrivning, tillåta återinträde, välja start- och slutdatum och definiera en **[!UICONTROL Timeout and error]** längd om du är administratör.

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

Mer information om hantering av tidszoner finns i [den här sidan](../building-journeys/timezone-management.md).

### Burst-läge {#burst}

Burst-läget är ett betalt tillägg som gör att det går att skicka mycket snabba push-meddelanden i stora volymer. Det används för enkla resor som innehåller ett lässegment och ett enkelt push-meddelande. Burst används när fördröjning i meddelandeleverans är affärskritisk när du vill skicka en snabb push-varning på mobiltelefoner, till exempel ett meddelande om nyheter till användare som har installerat din nyhetskanalapp.

Begränsningar:

* Resan måste börja med ett lässegment. Händelser tillåts inte.
* Nästa steg måste vara ett push-meddelande. Ingen annan aktivitet eller steg tillåts (förutom den valfria slutaktiviteten):
   * Skjut bara kanal
   * Ingen personalisering tillåts i meddelandet
   * Meddelandet måste vara litet (&lt;2kB)

Viktigt:

Om något av kraven inte är uppfyllt, är inte sprängningsläget tillgängligt under resan.

Aktivera Burst-läget genom att öppna resan och klicka på pennikonen i det övre högra hörnet för att komma åt resans egenskaper. Aktivera sedan **Aktivera sprängningsläge** växla.

![](assets/burst.png)

Burst-läget inaktiveras om du ändrar en burst-resa och lägger till en aktivitet som inte är kompatibel med burst (meddelande, annan åtgärd, en händelse osv.). Ett meddelande visas.

![](assets/burst2.png)

Testa och publicera sedan din resa som vanligt. Testlägesmeddelanden skickas inte via burst-läget.

## Avsluta en resa

En resa kan ta slut för en individ på grund av två orsaker:

* Personen kommer till den sista aktiviteten i en bana. Den senaste aktiviteten kan vara en slutaktivitet eller en annan aktivitet. Det finns ingen skyldighet att avsluta ett tågläge med en slutaktivitet. Läs [den här sidan](../building-journeys/end-activity.md).
* Personen kommer till en villkorsaktivitet (eller en vänteaktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återinträda i resan om återinträde tillåts. Läs [den här sidan](../building-journeys/journey-gs.md#change-properties)

En resa kan avslutas på grund av följande orsaker:

* Resan stängs manuellt via **[!UICONTROL Close to new entrances]** -knappen.
* En segmentbaserad resa som utförts i ett enda steg.
* Efter den sista förekomsten av en återkommande segmentbaserad resa.

När en resa stängs (av någon av anledningarna ovan) får den statusen **[!UICONTROL Closed]**. Resan kommer att sluta låta nya individer komma in på resan. Personer som redan är på resan kommer att slutföra resan normalt. Efter den globala standardtidsgränsen på 30 dagar växlar resan till **Slutförd** status. Se det här [section](../building-journeys/journey-gs.md#global_timeout).

Om ni behöver stoppa alla personers framsteg på resan kan ni stoppa den. Om du stoppar resan kommer alla personer på resan att tidsgränsen för timeout.

Så här stänger eller stoppar du en resa manuellt:

The **[!UICONTROL Stop]** och **[!UICONTROL Close to new entrances]** kan du avsluta **live** resor. Att avsluta en resa innebär **att nya kunders ankomst till resan blockeras** och att de kunder som redan är med på resan kan uppleva det hela tiden. Det här är det mest rekommenderade sättet att få ett slut på en resa eftersom den erbjuder den bästa upplevelsen för kunderna. Att stoppa en resa innebär att alla som redan har tagit sig in på en resa stoppas i processen. Resan är i stort sett avstängd.

>[!NOTE]
>
>Observera att du inte kan återuppta en stängd eller stoppad resa.

### Stänga en resa

Du kan stänga en resa manuellt för att säkerställa att kunder som redan har gått in på resan kan slutföra sin resa, men nya användare inte kan ta sig in på resan.

När en resa stängs får den statusen **[!UICONTROL Closed]**. Efter den globala standardtidsgränsen på 30 dagar växlar resan till **Slutförd** status. Se det här [section](../building-journeys/journey-gs.md#global_timeout).

En stängd reseversion kan inte startas om eller tas bort. Du kan skapa en ny version av den eller duplicera den. Endast slutförda resor kan tas bort.

Om du vill stänga en resa från listan över resor klickar du på **[!UICONTROL Ellipsis]** knapp som finns till höger om resenamnet och väljer **[!UICONTROL Close to new entrances]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. I **[!UICONTROL Journeys]** klickar du på den resa du vill stänga.
1. Klicka på nedpilen längst upp till höger.

   ![](assets/finish_drop_down_list.png)

1. Klicka på **[!UICONTROL Close to new entrances]**. En dialogruta visas.
1. Klicka **[!UICONTROL Close to new entrances]** för att bekräfta.

### Stoppa en resa

Du kan stoppa en resa när en kris inträffar och all behandling måste avslutas omedelbart under en resa.

Det går inte att starta om en stoppad reseversion.

När den stoppas får en resa statusen **[!UICONTROL Stopped]**.

Du kan till exempel stoppa en resa om en marknadsförare upptäcker att resan riktar sig mot fel målgrupp eller en anpassad åtgärd som ska leverera meddelanden inte fungerar korrekt. Om du vill stoppa en resa från listan över resor klickar du på **[!UICONTROL Ellipsis]** knapp som finns till höger om resenamnet och väljer **[!UICONTROL Stop]**.

![](assets/journey-finish-quick-action.png)

Du kan även:

1. I **[!UICONTROL Journeys]** klickar du på den resa du vill stoppa.
1. Klicka på nedpilen i det övre högra hörnet.

![](assets/finish_drop_down_list.png)

1. Klicka på **[!UICONTROL Stop]**. En dialogruta visas.
1. Klicka **[!UICONTROL Stop]** för att bekräfta.
