---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer skyddsräcken och begränsningar
description: Läs mer om Journey Optimizer skyddsräcken
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 5d59f21c-f76e-45a9-a839-55816e39758a
source-git-commit: 41448cfa8efc4a7b74b0a490f02e53efdbc0a2e7
workflow-type: tm+mt
source-wordcount: '2457'
ht-degree: 0%

---

# Skyddsritningar och begränsningar {#limitations}

Nedan finns ytterligare skyddsutkast och begränsningar när du använder [!DNL Adobe Journey Optimizer].

Tillstånd, produktbegränsningar och prestandaskydd visas på [Adobe Journey Optimizer produktbeskrivningssida](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}.

Du måste också känna till [Guardsändningar för kundprofildata i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html){target="_blank"} innan du börjar.

## Webbläsare som stöds {#browsers}

Adobe [!DNL Journey Optimizer]-gränssnittet är utformat för att fungera optimalt i den senaste versionen av Google Chrome. Du kan ha problem med att använda vissa funktioner i äldre versioner eller i andra webbläsare.

## Skyddsutkast för datauppsättningar {#datasets-guardrails}

Från och med februari 2025 introduceras ett TTL-skyddsräcke (time-to-live) för Journey Optimizer systemgenererade datauppsättningar i **nya sandlådor och nya organisationer** enligt följande:

* 90 dagar för data i profilarkivet,
* 13 månader för data i sjön.

Den här ändringen kommer att introduceras i **befintliga kundsandlådor** i en efterföljande fas. [Läs mer om datauppsättningar - TTL-skyddsutkast (Time-To-Live)](../data/datasets-ttl.md)

## Kanaler, skyddsräcken {#channel-guardrails}

>[!NOTE]
>
>I sällsynta fall kan tillfälliga avbrott i en viss region leda till att giltiga profiler utesluts från resor eller att felaktigt markerade e-postmeddelanden markeras som studsar. När tjänsterna har återställts kontrollerar du reseloggarna på nytt, kontrollerar tillståndsprofilfälten och publicerar sedan resan på nytt om det behövs. Om ett ISP-fel inträffar bör du lära dig hur du tar bort profiler från listan över inaktiveringar i [det här avsnittet](../configuration/manage-suppression-list.md#remove-from-suppression-list).
>

### E-postskyddsutkast {#message-guardrails}

Följande skyddsutkast gäller för [e-postkanalen](../email/get-started-email.md):

* Du kan inte lägga till bilagor i ett e-postmeddelande med [!DNL Journey Optimizer].
* Du kan inte använda samma sändande domän för att skicka ut meddelanden från [!DNL Adobe Journey Optimizer] och från en annan produkt, till exempel [!DNL Adobe Campaign] eller [!DNL Adobe Marketo Engage].

### SMS-skyddsräcken {#sms-guardrails}

Följande skyddsförslag gäller för [SMS-kanalen](../sms/get-started-sms.md):

* Mediefiler för MMS kan inkluderas via en URL som stöds. Kontrollera att mediefilen överförs separat.
* Synkronisering av meddelandefeedback är för närvarande inte tillgängligt för MMS.
* Samtalshantering fungerar på SMS-kanalnivå för MMS.

### Skyddsutkast för webbkanal {#web-guardrails}

[!DNL Journey Optimizer] [webbkampanjer](../web/get-started-web.md) har nya profiler som inte har varit engagerade tidigare i andra kanaler som mål. Detta ökar det totala antalet profiler du kan göra gällande, vilket kan ha kostnadskonsekvenser om det avtalsenliga antalet profiler du har köpt överskrids.

Licensvärden för varje paket visas på sidan [Journey Optimizer Product Description](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}.

### Kodbaserade kanalgarantier {#code-based-guardrails}

Om du vill använda kodbaserade upplevelseåtgärder i [!DNL Journey Optimizer] och leverera kodinnehållets nyttolast som kan användas av dina program följer du de krav som anges på [den här sidan](../code-based/code-based-prerequisites.md).

## Garantier för landningssidor {#lp-guardrails}

Följande skyddsutkast gäller för [landningssidorna](../landing-pages/get-started-lp.md):

* Endast en **Form**-komponent kan användas på en enda primär sida.
* Komponenten **Form** kan inte användas i undersidor.
* Du kan inte lägga till en förrubrik på en landningssida.
* Du kan inte välja alternativet **Kod för egen** när du utformar en primär landningssida.

## Underdomänsskydd {#subdomain-guardrails}

Som standard kan du i [!DNL Journey Optimizer] delegera upp till 10 underdomäner totalt (som omfattar både e-post- och webbkanaler).

Beroende på ditt licensavtal kan du dock delegera upp till 100 underdomäner. Kontakta Adobe och läs mer om hur många underdomäner du har rätt till.

Läs mer om domändelegering på [den här sidan](../configuration/delegate-subdomain.md).

## Fragmentskyddsräcken {#fragments-guardrails}

Följande skyddsutkast gäller för [fragment](../content-management/fragments.md):

* Visuella fragment är bara tillgängliga för e-postkanalen.
* Uttrycksfragment är inte tillgängliga för kanalen i appen.

## Målgrupper och skyddsräcken {#audience}

Du kan publicera upp till 10 publikkompositioner i en given sandlåda. Om du har nått det här tröskelvärdet måste du ta bort en disposition för att frigöra utrymme och publicera en ny.

Läs mer om målgruppskompositioner i [den här sidan](../audience/get-started-audience-orchestration.md).

## Beslutsfattare och beslutsföringsgarantier {#decisioning-guardrails}

Garantier och begränsningar som ska beaktas när man arbetar med beslut eller beslutshantering beskrivs i dessa avsnitt av beslut och beslutshantering:

* [Avgörande av skyddsräcken och begränsningar](../experience-decisioning/decisioning-guardrails.md)
* [Garantier och begränsningar för beslutshantering](../offers/decision-management-guardrails.md)


## Resehanddukar {#journeys-guardrails}

### Allmänna skyddsräcken för resan {#journeys-guardrails-journeys}

* Antalet aktiviteter under en resa är begränsat till 50. Antalet aktiviteter visas i den övre vänstra delen av arbetsytan. Detta underlättar läsbarhet, kvalitetskontroll och felsökning.
* När du publicerar resor skalas och justeras vi automatiskt för att säkerställa maximal genomströmning och stabilitet. I närheten av milstolpen för 100 direktresor på en gång visas ett meddelande i användargränssnittet om detta. Om du ser det här meddelandet och behöver förlänga dina resor mer än 100 resor i taget kan du skapa en biljett för kundvård så hjälper vi dig att nå dina mål.
  <!-- DOCAC-10977 * As you publish journeys, we automatically scale and adjust to ensure maximum throughput and stability. As you near the milestone of 500 live journeys at one time, you will see a notification appear in the UI on this achievement. If you see this notification and have a need to extend your journeys beyond 500 live journeys at a time, please create a ticket for customer care and we will help you reach your goals.-->
* När du använder en målgruppskvalifikation på en resa kan det ta upp till 10 minuter innan målgruppsaktiviteten är aktiv och lyssnar på profiler som kommer in eller lämnar målgruppen.
* En reseinstans för en profil har en maxstorlek på 1 MB. Alla data som samlas in som en del av körningen lagras i den aktuella reseinstansen. Det innebär att data från en inkommande händelse, profilinformation som hämtats från Adobe Experience Platform, anpassade åtgärdssvar osv. lagras i den reseinstansen och påverkar resans storlek. När en resa börjar med en händelse bör du begränsa den maximala nyttolasten för händelsen (t.ex. under 800 kB) för att undvika att nå den gränsen efter några få aktiviteter vid körningen av resan. När gränsen nås har profilen en felstatus och kommer inte att ingå i resan.
* Förutom den tidsgräns som används i reseaktiviteter finns det också en global tidsgräns för resan som inte visas i gränssnittet och som inte kan ändras. Den här globala tidsgränsen stoppar de enskilda personernas framsteg under resan 91 dagar efter att de har gått in. [Läs mer](../building-journeys/journey-properties.md#global_timeout)

### Allmänna åtgärder {#general-actions-g}

Följande skyddsutkast gäller för [åtgärderna](../building-journeys/about-journey-activities.md) på dina resor:

* Tre försök utförs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet. Alla HTTP-fel utom HTTP 401, 403 och 404 anges på nytt.
* Den inbyggda **Reaction**-händelsen gör att du kan reagera på åtgärder som inte är i kartong. Läs mer på [den här sidan](../building-journeys/reaction-events.md). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse.
* Du kan inte placera två åtgärder parallellt. Du måste lägga till dem en i taget.
* En profil kan inte finnas flera gånger på samma resa samtidigt. Om återinträde är aktiverat kan en profil återansluta en resa, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt. [Läs mer](../building-journeys/end-journey.md)

### Reseversioner {#journey-versions-g}

Följande skyddsutkast gäller för [reseversionerna](../start/user-interface.md):

* En resa som börjar med en händelseaktivitet i v1 kan inte börja med något annat än en händelse i andra versioner. Du kan inte starta en resa med en **målgruppskvalificeringshändelse**.
* En resa som börjar med en **målgruppskvalifikation**-aktivitet i v1 måste alltid börja med en **målgruppskompetens** i andra versioner.
* Den målgrupp och det namnområde som valts i **Målgruppskvalifikation** (första noden) kan inte ändras i nya versioner.
* Regeln för återinträde måste vara densamma i alla reseversioner.
* En resa som börjar med en **Läs målgrupp** kan inte börja med en annan händelse i nästa versioner.
* Du kan inte skapa en ny version av en läsande målgruppsresa med inkrementell läsning. Du måste duplicera resan.

### Anpassade åtgärder {#custom-actions-g}

Följande skyddsutkast gäller för [anpassade åtgärder](../action/action.md) på dina resor:

* En begränsning på 300 000 anrop över en minut har definierats för alla anpassade åtgärder, per värd och per sandlåda. Se [den här sidan](../action/about-custom-action-configuration.md). Den här gränsen har fastställts baserat på kundanvändning för att skydda externa slutpunkter som har anpassats efter anpassade åtgärder. Du måste tänka på detta vid målgruppsbaserade resor genom att definiera en lämplig läsfrekvens (5 000 profiler/er när anpassade åtgärder används). Om det behövs kan du åsidosätta den här inställningen genom att definiera en större begränsning för begränsning eller begränsning via våra API:er för begränsning/begränsning. Läs [den här sidan](../configuration/external-systems.md).
* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar.
* Anropsmetoderna POST, PUT och GET stöds
* Namnet på frågeparametern eller -rubriken får inte börja med &quot;.&quot; eller &quot;$&quot;
* IP-adresser tillåts inte
* Interna Adobe-adresser (`.adobe.*`) tillåts inte i URL:er och API:er.
* Inbyggda anpassade åtgärder kan inte tas bort.
* Anpassade åtgärder stöder bara JSON-format när du använder begäran- eller svarsnyttolaster. Läs [den här sidan](../action/about-custom-action-configuration.md#custom-actions-limitations).
* När du väljer en slutpunkt som ska användas som mål med en anpassad åtgärd ska du se till att:

   * Den här slutpunkten kan ha stöd för resans genomströmning genom att använda konfigurationer från [API:t för begränsning](../configuration/throttling.md) eller [API:t för begränsning](../configuration/capping.md). Var försiktig med att en begränsningskonfiguration inte får vara lägre än 200 TPS. Alla målslutpunkter måste ha stöd för minst 200 TPS.
   * Den här slutpunkten måste ha en svarstid som är så låg som möjligt. Beroende på förväntat dataflöde kan en hög svarstid påverka det faktiska dataflödet.

### Händelser {#events-g}

Följande skyddsutkast gäller för [händelserna](../event/about-events.md) på dina resor:

* Journey Optimizer har stöd för en toppvolym på 5 000 inkommande resehändelser per sekund.
* Händelseutlösta resor kan ta upp till fem minuter för att behandla den första åtgärden i resan.
* För systemgenererade händelser måste strömmande data som används för att initiera en kundresa konfigureras inom Journey Optimizer först för att få ett unikt orkestrerings-ID. Detta Orchestration-ID måste bifogas till strömningsnyttolasten som kommer till Adobe Experience Platform. Denna begränsning gäller inte regelbaserade händelser.
* Affärsevenemang kan inte användas tillsammans med enhetsevenemang eller målgruppsaktiviteter.
* Enhetsresor (som inleds med en händelse eller en publikation) innehåller ett skyddsräcke som förhindrar att resorna aktiveras felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras tillfälligt som standard i 5 minuter. Om en händelse till exempel utlöser en resa kl. 12:01 för en viss profil och en annan tar emot kl. 12:03 (oavsett om det är samma händelse eller en annan som utlöser samma resa) kommer den resan inte att starta igen för den här profilen.
* Journey Optimizer kräver att händelser direktuppspelas till datainsamlingens bastjänst (DCCS) för att kunna utlösa en resa. Händelser som är inkapslade i batch eller händelser från interna Journey Optimizer-datauppsättningar (meddelandefeedback, e-postspårning osv.) kan inte användas för att utlösa en resa. I de fall där du inte kan få direktuppspelade händelser måste du skapa en målgrupp baserat på dessa händelser och använda aktiviteten **Läs målgrupp** i stället. Målgruppskompetens kan användas tekniskt, men rekommenderas inte eftersom den kan orsaka efterföljande utmaningar baserat på de åtgärder som används.

### Datakällor {#data-sources-g}

Följande skyddsutkast gäller för [datakällorna](../datasource/about-data-sources.md) på dina resor:

* Externa datakällor kan utnyttjas inom en kundresa för att söka efter externa data i realtid. Dessa källor måste kunna användas via REST API, ha stöd för JSON och kunna hantera antalet begäranden.
* Interna Adobe-adresser (`.adobe.*`) tillåts inte i URL:er och API:er.

>[!NOTE]
>
>Eftersom svaren nu stöds bör du använda anpassade åtgärder i stället för datakällor för externa datakällor som användningsfall.

### Resor och skapande av profiler {#journeys-limitation-profile-creation}

Det finns en fördröjning i skapandet/uppdateringen av API-baserade profiler i Adobe Experience Platform. Servicenivåmålet (SLT) i form av fördröjning är &lt; 1 min från intag till en enhetlig profil för 95:e percentilen begäranden, vid en volym på 20 000 förfrågningar per sekund (RPS).

Om en resa utlöses samtidigt för att skapa en profil och omedelbart kontrollerar/hämtar information från profiltjänsten kanske den inte fungerar som den ska.

Du kan välja mellan följande två lösningar:

* Lägg till en vänteaktivitet efter den första händelsen för att ge Adobe Experience Platform den tid det behöver för att utföra inmatningen till profiltjänsten.

* Konfigurera en resa som inte omedelbart utnyttjar profilen. Om resan till exempel är utformad för att bekräfta att ett konto har skapats, kan upplevelsehändelsen innehålla information som behövs för att skicka det första bekräftelsemeddelandet (förnamn, efternamn, e-postadress osv.).

### Uppdatera profil {#update-profile-g}

Specifika skyddsutkast gäller för aktiviteten **[!UICONTROL Update profile]**. De listas på [den här sidan](../building-journeys/update-profiles.md).

### Läs målgrupp {#read-segment-g}

Följande skyddsutkast gäller för [Läs målgruppsaktiviteten](../building-journeys/read-audience.md):

* Direktuppspelade målgrupper är alltid uppdaterade, men batchmålgrupper beräknas inte vid hämtningen. De utvärderas endast varje dag vid den dagliga grupputvärderingen.
* För resor som använder en **Läs målgrupp**-aktivitet finns det ett maximalt antal resor som kan påbörjas exakt samtidigt. Återförsök kommer att utföras av systemet men undvik att ha fler än fem resor (med **Läs målgrupp**, schemalagd eller starta&quot;så snart som möjligt&quot;) med början vid exakt samma tid genom att sprida dem över tiden, t.ex. mellan 5 och 10 minuter.
* Det går inte att använda aktiviteten **Läs målgrupp** med Adobe Campaign-aktiviteter.
* Aktiviteten **Läs målgrupp** kan bara användas som en första aktivitet i en resa, efter en affärshändelseaktivitet.
* En resa kan bara ha en **Läs målgrupp**-aktivitet.
* Se även rekommendationer om hur du använder aktiviteten **Läs målgrupp** i [den här sidan](../building-journeys/read-audience.md).
* Återförsök används som standard på målgruppsinlösta resor (med början från en **Läs målgrupp** eller en **affärshändelse**) när exportjobbet hämtas. Om ett fel inträffar när exportjobbet skapas görs nya försök var 10:e minut (max 1 timme). Efter det kommer vi att betrakta det som ett misslyckande. Dessa typer av resor kan därför utföras upp till en timme efter den schemalagda tiden.

### Målgruppskvalifikation {#audience-qualif-g}

Följande skyddsutkast gäller för [Målgruppskvalificering](../building-journeys/audience-qualification-events.md)-reseaktiviteten:

* Det går inte att använda aktiviteten Audience-kvalificering med Adobe Campaign-aktiviteter.

### Uttrycksredigerare {#expression-editor}

Följande skyddsutkast gäller för [reseuttrycksredigeraren](../building-journeys/expression/expressionadvanced.md):

* Det går inte att använda fältgrupper för upplevelsehändelser på resor som börjar med en läsare, en målgrupp eller en affärshändelseaktivitet. Du måste skapa en ny målgrupp och använda ett villkor för målgrupp under resan.

### Aktivitet i appen {#in-app-activity-limitations}

Följande skyddsutkast gäller för åtgärden **[!UICONTROL In-app message]**. Läs mer om meddelanden i appen på [den här sidan](../in-app/create-in-app.md).

* Den här funktionen är för närvarande inte tillgänglig för vårdkunder.

* Personalization kan bara innehålla profilattribut.

* Aktiviteten i appen kan inte användas med Adobe Campaign-aktiviteter.

* Visning i appen är knuten till resans livscykel, vilket innebär att när resan avslutas för en profil kommer alla meddelanden i appen under resan inte att visas för den profilen.  Det är därför inte möjligt att stoppa ett meddelande i appen direkt från en reseaktivitet. I stället måste du avsluta hela kundresan för att förhindra att meddelanden i appen visas i profilen.

* I testläge beror visningen i appen på resans livslängd. Om du vill förhindra att resan avslutas för tidigt under testningen justerar du värdet **[!UICONTROL Wait time]** för dina **[!UICONTROL Wait]**-aktiviteter.

* **[!UICONTROL Reaction]** aktiviteter kan inte användas för att reagera på en öppning eller ett klick i appen.

* En aktiveringsfördröjning kan uppstå från det att en användarprofil når en aktivitet i appen på arbetsytan till dess att meddelandet visas i appen.

* Innehållets storlek för meddelanden i appen är begränsad till 2 MB. Om du inkluderar stora bilder kan det försvåra publiceringsprocessen.

### Hoppaktivitet {#jump-g}

Specifika skyddsutkast gäller för aktiviteten **[!UICONTROL Jump]**. De listas på [den här sidan](../building-journeys/jump.md#jump-limitations).

### Kampanjaktiviteter {#ac-g}

Följande skyddsförslag gäller för **[!UICONTROL Campaign v7/v8]**- och **[!UICONTROL Campaign Standard]**-aktiviteterna:

* Adobe Campaign-aktiviteter kan inte användas med en läs- eller målgruppsaktivitet.
* Kampanjaktiviteter kan inte användas med andra kanalaktiviteter: kort, kodbaserad upplevelse, e-post, push, SMS, meddelanden i appen, webb.
