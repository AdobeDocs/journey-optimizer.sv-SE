---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer skyddsräcken och begränsningar
description: Läs mer om Journey Optimizer skyddsräcken
feature: Journeys
topic: Content Management
role: User
level: Intermediate
mini-toc-levels: 1
exl-id: 5d59f21c-f76e-45a9-a839-55816e39758a
source-git-commit: 6c73a1ee024ca61b30d71e77268e51b93576ae62
workflow-type: tm+mt
source-wordcount: '2809'
ht-degree: 0%

---

# Skyddsritningar och begränsningar {#limitations}

Nedan hittar du ytterligare skyddsförslag och begränsningar när du använder [!DNL Adobe Journey Optimizer].

Tillstånd, produktbegränsningar och prestandaskydd visas på [Adobe Journey Optimizer produktbeskrivningssida](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}.


>[!CAUTION]
>
>* [Garantier för kundprofildata och segmentering i realtid](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails){target="_blank"} gäller även för Adobe Journey Optimizer.
>
>* Se även [Guardsutkast för datainmatning i kundprofilen i realtid](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/guardrails){target="_blank"}


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

<!--The following guardrails apply to the [email channel](../../rp_landing_pages/email-landing-page.md):-->

Du kan inte använda samma sändande domän för att skicka ut e-postmeddelanden från [!DNL Adobe Journey Optimizer] och från en annan produkt, till exempel [!DNL Adobe Campaign] eller [!DNL Adobe Marketo Engage].

### SMS-skyddsräcken {#sms-guardrails}

Följande skyddsförslag gäller för [SMS-kanalen](../sms/get-started-sms.md):

* Mediefiler för MMS kan inkluderas via en URL som stöds. Kontrollera att mediefilen överförs separat.
* Synkronisering av meddelandefeedback är för närvarande inte tillgängligt för MMS.
* Samtalshantering fungerar på SMS-kanalnivå för MMS.

### Inkommande kanalskyddsräcken {#inbound-guardrails}

* Journey Optimizer stöder en toppvolym på 5 000 inkommande begäranden per sekund. Skyddsplanen gäller för alla inkommande begäranden, som kan härröra från någon av de ingående kanaler som stöds av Journey Optimizer ([web](../web/get-started-web.md), [In-app](../in-app/get-started-in-app.md), [kodbaserade upplevelser](../code-based/get-started-code-based.md), [innehållskort](../../rp_landing_pages/content-card-landing-page.md)).

  Journey Optimizer inkommande kanaler har nya profiler som kanske inte har varit engagerade tidigare i andra kanaler som mål. Detta ökar det totala antalet profiler du kan göra gällande, vilket kan ha kostnadskonsekvenser om det avtalsenliga antalet profiler du har köpt överskrids.

  Licensvärden för varje paket visas på sidan [Journey Optimizer Product Description](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}.

* Journey Optimizer stöder maximalt 500 aktiva inkommande åtgärder när som helst. Dessa inkommande åtgärder ([web](../web/get-started-web.md), [In-app](../in-app/get-started-in-app.md), [kodbaserade upplevelser](../code-based/get-started-code-based.md), [innehållskort](../../rp_landing_pages/content-card-landing-page.md)) räknas om de är en del av en live-kampanj eller om de är en nod som används i en direktresa. När du har nått det här numret måste du inaktivera äldre kampanjer eller resor som använder inkommande åtgärder innan du kan starta nya.

* Om du vill använda [kodbaserad upplevelse](../code-based/get-started-code-based.md) i [!DNL Journey Optimizer] och leverera kodinnehållets nyttolast som kan användas av dina program följer du de krav som anges på [den här sidan](../code-based/code-based-prerequisites.md).

### Skyddsutkast för transaktionsmeddelanden {#transactional-message-guardrails}

Journey Optimizer har stöd för en toppvolym på 500 transaktionsmeddelanden per sekund i kampanjer.

## Garantier för landningssidor {#lp-guardrails}

Följande skyddsutkast gäller för [landningssidorna](../landing-pages/get-started-lp.md):

* Endast en **Form**-komponent kan användas på en enda primär sida.
* Komponenten **Form** kan inte användas i undersidor.
* Du kan inte lägga till en förrubrik på en landningssida.
* Du kan inte välja alternativet **Kod för egen** när du utformar en primär landningssida.

## Underdomänsskydd {#subdomain-guardrails}

Skyddsförslag och begränsningar som gäller för delegering av underdomäner i Journey Optimizer finns på [den här sidan](../configuration/delegate-subdomain.md#guardrails).

## Fragmentskyddsräcken {#fragments-guardrails}

Följande skyddsutkast gäller för [fragment](../content-management/fragments.md):

* Om du vill skapa, redigera, arkivera och publicera fragment behöver du behörigheterna **[!DNL Manage library items]** och **[Publicera fragment]** i produktprofilen för **[!DNL Content Library Manager]**. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)
* Visuella fragment är bara tillgängliga för e-postkanalen.
* Uttrycksfragment är inte tillgängliga för kanalen i appen.
* Visuella fragment får inte överskrida 100 kB. Uttrycksfragment får inte överskrida 200 kB.
* Om du vill använda ett fragment i en resa eller kampanj måste det ha statusen **Live**.
* [Sammanhangsbaserade attribut](../personalization/personalization-build-expressions.md) stöds inte i fragment.
* Visuella fragment är inte korskompatibla mellan Använd teman och Manuell formatering. Om du vill kunna använda ett fragment i ett innehåll där du vill använda ett tema, måste det här fragmentet skapas i läget Använd teman. [Läs mer om teman](../email/apply-email-themes.md)
* När spårning är aktiverat i en resa eller kampanj spåras länkarna, om du lägger till länkar till ett fragment och om det här fragmentet används i ett meddelande, till exempel alla andra länkar som finns i meddelandet. [Läs mer om länkar och spårning](../email/message-tracking.md)

## Målgrupper och skyddsräcken {#audience}

Du kan publicera upp till 10 publikkompositioner i en given sandlåda. Om du har nått det här tröskelvärdet måste du ta bort en disposition för att frigöra utrymme och publicera en ny.

Läs mer om målgruppskompositioner på [den här sidan](../audience/get-started-audience-orchestration.md).

## Beslutsfattare och beslutsföringsgarantier {#decisioning-guardrails}

Garantier och begränsningar som ska beaktas när man arbetar med beslut eller beslutshantering beskrivs i dessa avsnitt av beslut och beslutshantering:

* [Avgörande av skyddsräcken och begränsningar](../experience-decisioning/decisioning-guardrails.md)
* [Garantier och begränsningar för beslutshantering](../offers/decision-management-guardrails.md)

## Resehanddukar {#journeys-guardrails}

### Allmänna skyddsräcken för resan {#journeys-guardrails-journeys}

* Antalet aktiviteter under en resa är begränsat till 50. Antalet aktiviteter visas i den övre vänstra delen av arbetsytan. Detta underlättar läsbarhet, kvalitetskontroll och felsökning.
* Som standard är antalet körningar (live/paused/dry run) på en gång begränsat till 100.  Det aktuella antalet resor visas ovanför arbetsytan.
* När du publicerar resor skalas och justeras vi automatiskt för att säkerställa maximal genomströmning och stabilitet. I närheten av milstolpen för 100 direktresor på en gång visas ett meddelande i användargränssnittet om detta. Om du ser det här meddelandet och behöver förlänga dina resor mer än 100 resor i taget kan du skapa en biljett för kundvård så hjälper vi dig att nå dina mål.
* När du använder en målgruppskvalifikation på en resa kan det ta upp till 10 minuter innan målgruppsaktiviteten är aktiv och lyssnar på profiler som kommer in eller lämnar målgruppen.
* En reseinstans för en profil har en maxstorlek på 1 MB. Alla data som samlas in som en del av körningen lagras i den aktuella reseinstansen. Det innebär att data från en inkommande händelse, profilinformation som hämtats från Adobe Experience Platform, anpassade åtgärdssvar osv. lagras i den reseinstansen och påverkar resans storlek. När en resa börjar med en händelse bör du begränsa den maximala nyttolasten för händelsen (t.ex. under 800 kB) för att undvika att nå den gränsen efter några få aktiviteter vid körningen av resan. När gränsen nås har profilen en felstatus och kommer inte att ingå i resan.
* Förutom den tidsgräns som används i reseaktiviteter finns det också en global tidsgräns för resan som inte visas i gränssnittet och som inte kan ändras. Den här globala tidsgränsen stoppar de enskilda personernas framsteg under resan 91 dagar efter att de har gått in. [Läs mer](../building-journeys/journey-properties.md#global_timeout)

### Allmänna åtgärder {#general-actions-g}

Följande skyddsutkast gäller för [åtgärderna](../building-journeys/about-journey-activities.md) på dina resor:

* Tre försök utförs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet. Alla HTTP-fel utom HTTP 401, 403 och 404 anges på nytt.
* Den inbyggda **Reaction**-händelsen gör att du kan reagera på åtgärder som inte är i kartong. Läs mer på [den här sidan](../building-journeys/reaction-events.md). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse.
* Du kan inte placera två åtgärder parallellt. Du måste lägga till dem en i taget.
* En profil kan inte finnas flera gånger under samma resa, samtidigt, för alla aktiva [versioner av resan](../building-journeys/publishing-the-journey.md#create-a-new-version-of-a-journey-journey-create-new-version). Om återinträde är aktiverat kan en profil återansluta en resa, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt. [Läs mer](../building-journeys/end-journey.md)

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

* En begränsning på 300 000 anrop över en minut har definierats för alla anpassade åtgärder, per värd och per sandlåda. Se [den här sidan](../action/about-custom-action-configuration.md). Den här gränsen har fastställts baserat på kundanvändning för att skydda externa slutpunkter som har anpassats efter anpassade åtgärder. Om det behövs kan du åsidosätta den här inställningen genom att definiera en större begränsning för begränsning eller begränsning via våra API:er för begränsning/begränsning. Läs [den här sidan](../configuration/external-systems.md).
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

* Journey Optimizer har stöd för en toppvolym på 5 000 inkommande resehändelser per sekund, över alla sandlådor. Läs mer om den här begränsningen [på den här sidan](../event/about-events.md#event-thoughput).
* Händelseutlösta resor kan ta upp till fem minuter för att behandla den första åtgärden i resan.
* För systemgenererade händelser måste strömmande data som används för att initiera en kundresa konfigureras inom Journey Optimizer först för att få ett unikt orkestrerings-ID. Detta Orchestration-ID måste bifogas till strömningsnyttolasten som kommer till Adobe Experience Platform. Denna begränsning gäller inte regelbaserade händelser.
* Affärsevenemang kan inte användas tillsammans med enhetsevenemang eller målgruppsaktiviteter.
* Enhetsresor (som inleds med en händelse eller en publikation) innehåller ett skyddsräcke som förhindrar att resorna aktiveras felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras tillfälligt som standard i 5 minuter. Om en händelse till exempel utlöser en resa vid 12:01 för en viss profil och en annan tar emot vid 12:03 (oavsett om det är samma händelse eller en annan som utlöser samma resa) startar den resan inte igen för den här profilen.
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


### Ytterligare identifierare {#supplemental}

Särskilda skyddsräcken gäller för användningen av kompletterande identifierare under resor. De listas på [den här sidan](../building-journeys/supplemental-identifier.md#guardrails).

### Uttrycksredigerare {#expression-editor}

Följande skyddsutkast gäller för [reseuttrycksredigeraren](../building-journeys/expression/expressionadvanced.md):

* Det går inte att använda fältgrupper för upplevelsehändelser på resor som börjar med en läsare, en målgrupp eller en affärshändelseaktivitet. Du måste skapa en ny målgrupp och använda ett `inaudience`-villkor under resan.
* `timeSeriesEvents`-attribut kan inte användas i uttrycksredigeraren. Skapa en ny fältgrupp baserad på ett `XDM ExperienceEvent`-schema för att få åtkomst till Experience Events på profilnivå.

### Reseverksamhet {#activities}

#### Målgruppskvalificeringsaktivitet {#audience-qualif-g}

Följande skyddsutkast gäller för [Målgruppskvalificering](../building-journeys/audience-qualification-events.md)-reseaktiviteten:

* Det går inte att använda aktiviteten Audience-kvalificering med Adobe Campaign-aktiviteter.
* Kompletterande identifierare stöds inte för kundkvalificeringsresor.

#### Kampanjaktiviteter {#ac-g}

Följande skyddsförslag gäller för **[!UICONTROL Campaign v7/v8]**- och **[!UICONTROL Campaign Standard]**-aktiviteterna:

* Adobe Campaign-aktiviteter kan inte användas med en läs- eller målgruppsaktivitet.
* Kampanjaktiviteter kan inte användas med andra kanalaktiviteter: kort, kodbaserad upplevelse, e-post, push, SMS, meddelanden i appen, webb.

#### Aktivitet i appen {#in-app-activity-limitations}

Följande skyddsutkast gäller för åtgärden **[!UICONTROL In-app message]**. Läs mer om meddelanden i appen på [den här sidan](../in-app/create-in-app.md).

* Den här funktionen är för närvarande inte tillgänglig för vårdkunder.

* Personalization kan bara innehålla profilattribut.

* Aktiviteten i appen kan inte användas med Adobe Campaign-aktiviteter.

* Visning i appen är knuten till resans livscykel, vilket innebär att när resan avslutas för en profil kommer alla meddelanden i appen under resan inte att visas för den profilen.  Det är därför inte möjligt att stoppa ett meddelande i appen direkt från en reseaktivitet. I stället måste du avsluta hela kundresan för att förhindra att meddelanden i appen visas i profilen.

* I testläge beror visningen i appen på resans livslängd. Om du vill förhindra att resan avslutas för tidigt under testningen justerar du värdet **[!UICONTROL Wait time]** för dina **[!UICONTROL Wait]**-aktiviteter.

* **[!UICONTROL Reaction]** aktiviteter kan inte användas för att reagera på en öppning eller ett klick i appen.

* En aktiveringsfördröjning kan uppstå från det att en användarprofil når en aktivitet i appen på arbetsytan till dess att meddelandet visas i appen.

* Innehållets storlek för meddelanden i appen är begränsad till 2 MB. Om du inkluderar stora bilder kan det försvåra publiceringsprocessen.

#### Hoppaktivitet {#jump-g}

Specifika skyddsutkast gäller för aktiviteten **[!UICONTROL Jump]**. De visas på [den här sidan](../building-journeys/jump.md#jump-limitations).

#### Läs målgruppsaktivitet {#read-segment-g}

Följande skyddsutkast gäller för [Läs målgruppsaktiviteten](../building-journeys/read-audience.md):

* Direktuppspelade målgrupper är alltid uppdaterade, men batchmålgrupper beräknas inte vid hämtningen. De utvärderas endast varje dag vid den dagliga grupputvärderingen.
* För resor som använder en **Läs målgrupp**-aktivitet finns det ett maximalt antal resor som kan påbörjas exakt samtidigt. Återförsök kommer att utföras av systemet men undvik att ha fler än fem resor (med **Läs målgrupp**, schemalagd eller starta&quot;så snart som möjligt&quot;) med början vid exakt samma tid genom att sprida dem över tiden, t.ex. mellan 5 och 10 minuter.
* Det går inte att använda aktiviteten **Läs målgrupp** med Adobe Campaign-aktiviteter.
* Aktiviteten **Läs målgrupp** kan bara användas som en första aktivitet i en resa, efter en affärshändelseaktivitet.
* En resa kan bara ha en **Läs målgrupp**-aktivitet.
* Se även rekommendationer om hur du använder aktiviteten **Läs målgrupp** på [den här sidan](../building-journeys/read-audience.md).
* Återförsök används som standard på målgruppsinlösta resor (med början från en **Läs målgrupp** eller en **affärshändelse**) när exportjobbet hämtas. Om ett fel inträffar när exportjobbet skapas görs nya försök var 10:e minut (max 1 timme). Efter det kommer vi att betrakta det som ett misslyckande. Dessa typer av resor kan därför utföras upp till en timme efter den schemalagda tiden.
* För resor som använder extra ID:n är läsfrekvensen för läsmålgruppsaktiviteten för varje reseinstans begränsad till högst 500 profiler per sekund.

Se även [den här sidan](../building-journeys/read-audience.md#must-read).

#### Uppdatera profilaktivitet {#update-profile-g}

Specifika skyddsutkast gäller för aktiviteten **[!UICONTROL Update profile]**. De visas på [den här sidan](../building-journeys/update-profiles.md).

## Garantier för kampanjsamordning {#orchestration-guardrails}

Garantier och begränsningar som du bör tänka på när du arbetar med kampanjsamordning beskrivs i det här avsnittet: [Guardsänkar och begränsningar](../orchestrated/guardrails.md).
