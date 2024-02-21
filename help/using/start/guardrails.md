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
source-git-commit: f275820c3f79bb4c9aca8593c2c761ccd4283795
workflow-type: tm+mt
source-wordcount: '1908'
ht-degree: 0%

---

# Skyddsritningar och begränsningar {#limitations}

Tillstånd, produktbegränsningar och prestandaskydd finns i [Adobe Journey Optimizer produktbeskrivningssida](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}.

Du måste också vara medveten om [Garantier för kundprofildata i realtid innan du startar](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html){target="_blank"}.

Nedan finns ytterligare skyddsutkast och begränsningar när du använder [!DNL Adobe Journey Optimizer].

## Webbläsare som stöds {#browsers}

Adobe [!DNL Journey Optimizer] -gränssnittet är utformat för att fungera optimalt i den senaste versionen av Google Chrome. Du kan ha problem med att använda vissa funktioner i äldre versioner eller i andra webbläsare.

## Meddelandeskyddsutkast {#message-guardrails}

* Du kan inte lägga till bilagor i ett e-postmeddelande med [!DNL Journey Optimizer].
* Du kan inte använda samma sändande domän för att skicka ut meddelanden från [!DNL Adobe Journey Optimizer] och från en annan produkt, som [!DNL Adobe Campaign] eller [!DNL Adobe Marketo Engage] till exempel.


## Garantier för landningssidor {#lp-guardrails}

* Bara en **Formulär** -komponenten kan användas på en enda primär sida.
* The **Formulär** -komponenten kan inte användas i undersidor.
* Du kan inte lägga till en förrubrik på en landningssida.
* Du kan inte välja **Koda din egen** när du utformar en primär landningssida.

<!--
## SMS guardrails {#sms-guardrails}

* MMS Capability is only available for Sinch.
* Media files for MMS can be included through a supported URL. Please ensure that the media file is uploaded separately.
* Message feedback syncing is not currently available for MMS.
* Consent management operates at the SMS channel level for MMS.
-->

## Fragmentskyddsräcken {#fragments-guardrails}

* Visuella fragment är bara tillgängliga för e-postkanalen.
* Uttrycksfragment är inte tillgängliga för webben och appkanaler.

## Resehanddukar {#journeys-guardrails}

### Allmänna skyddsräcken för resan {#journeys-guardrails-journeys}

* Antalet aktiviteter under en resa är begränsat till 50. Antalet aktiviteter visas i den övre vänstra delen av arbetsytan. Detta underlättar läsbarhet, kvalitetskontroll och felsökning.
* När du publicerar resor skalas och justeras vi automatiskt för att säkerställa maximal genomströmning och stabilitet. I närheten av milstolpen för 100 direktresor på en gång visas ett meddelande i användargränssnittet om detta. Om du ser det här meddelandet och behöver förlänga dina resor mer än 100 resor i taget kan du skapa en biljett för kundvård så hjälper vi dig att nå dina mål.
* När du använder en målgruppskvalifikation på en resa kan det ta upp till 10 minuter innan målgruppsaktiviteten är aktiv och lyssnar på profiler som kommer in eller lämnar målgruppen.
* En reseinstans för en profil har en maxstorlek på 1 MB. Alla data som samlas in som en del av körningen lagras i den aktuella reseinstansen. Det innebär att data från en inkommande händelse, profilinformation som hämtats från Adobe Experience Platform, anpassade åtgärdssvar osv. lagras i den reseinstansen och påverkar resans storlek. När en resa börjar med en händelse bör du begränsa den maximala nyttolasten för händelsen (t.ex. under 800 kB) för att undvika att nå den gränsen efter några få aktiviteter vid körningen av resan. När gränsen nås har profilen en felstatus och kommer inte att ingå i resan.


### Allmänna åtgärder {#general-actions-g}

* Tre försök utförs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet. Alla HTTP-fel utom HTTP 401, 403 och 404 anges på nytt.
* Den inbyggda **Reaktion** -händelsen gör att du kan reagera på åtgärder som är klara. Läs mer i [den här sidan](../building-journeys/reaction-events.md). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse.
* Du kan inte placera två åtgärder parallellt. Du måste lägga till dem en i taget.
* En profil kan inte finnas flera gånger på samma resa samtidigt. Om återinträde är aktiverat kan en profil återansluta en resa, men kan inte göra det förrän den tidigare instansen av resan har avslutats helt. [Läs mer](../building-journeys/end-journey.md)

### Reseversioner {#journey-versions-g}

* En resa som börjar med en händelseaktivitet i v1 kan inte börja med något annat än en händelse i andra versioner. Du kan inte påbörja en resa med en **Målgruppskvalifikation** -händelse.
* En resa som börjar med en **Målgruppskvalifikation** aktivitet i v1 måste alltid börja med en **Målgruppskvalifikation** i andra versioner.
* Den målgrupp och det namnutrymme som valts i **Målgruppskvalifikation** (första noden) kan inte ändras i nya versioner.
* Regeln för återinträde måste vara densamma i alla reseversioner.
* En resa som börjar med en **Läs målgrupp** kan inte börja med en annan händelse i nästa version.
* Du kan inte skapa en ny version av en läsande målgruppsresa med inkrementell läsning. Du måste duplicera resan.

### Anpassade åtgärder {#custom-actions-g}

* En begränsning på 300 000 anrop över en minut har definierats för alla anpassade åtgärder, per värd och per sandlåda. Se [den här sidan](../action/about-custom-action-configuration.md). Den här gränsen har fastställts baserat på kundanvändning för att skydda externa slutpunkter som har anpassats efter anpassade åtgärder. Du måste ta hänsyn till detta vid målgruppsbaserade resor genom att definiera en lämplig läsfrekvens (5 000 profiler/er när anpassade åtgärder används). Om det behövs kan du åsidosätta den här inställningen genom att definiera en större begränsning för begränsning eller begränsning via våra API:er för begränsning/begränsning. Läs [den här sidan](../configuration/external-systems.md).
* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar.
* Anropsmetoderna POST, PUT och GET stöds
* Namnet på frågeparametern eller -rubriken får inte börja med &quot;.&quot; eller &quot;$&quot;
* IP-adresser tillåts inte
* Adobe adresser (`.adobe.*`) tillåts inte i URL:er och API:er.
* Inbyggda anpassade åtgärder kan inte tas bort.
* När du väljer en slutpunkt som ska användas som mål med en anpassad åtgärd ska du se till att:

   * Den här slutpunkten kan stödja resans genomströmning med hjälp av konfigurationer från [Begränsnings-API](../configuration/throttling.md) eller [API för begränsning](../configuration/capping.md) för att begränsa den. Var försiktig med att en begränsningskonfiguration inte får vara lägre än 200 TPS. Alla målpunkter måste ha stöd för minst 200 TPS.
   * Den här slutpunkten måste ha en svarstid som är så låg som möjligt. Beroende på förväntat dataflöde kan en hög svarstid påverka det faktiska dataflödet.

### Händelser {#events-g}

* För systemgenererade händelser måste strömmande data som används för att initiera en kundresa konfigureras inom Journey Optimizer först för att få ett unikt orkestrerings-ID. Detta Orchestration-ID måste bifogas till strömningsnyttolasten som kommer till Adobe Experience Platform. Denna begränsning gäller inte regelbaserade händelser.
* Affärsevenemang kan inte användas tillsammans med enhetsevenemang eller målgruppsaktiviteter.
* Enhetsresor (som inleds med en händelse eller en publikation) innehåller ett skyddsräcke som förhindrar att resorna aktiveras felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras tillfälligt som standard i 5 minuter. Om en händelse till exempel utlöser en resa kl. 12:01 för en viss profil och en annan tar emot kl. 12:03 (oavsett om det är samma händelse eller en annan som utlöser samma resa) kommer den resan inte att starta igen för den här profilen.
* Journey Optimizer kräver att händelser direktuppspelas till datainsamlingens bastjänst (DCCS) för att kunna utlösa en resa. Insamlade händelser i en grupp eller händelser från interna Journey Optimizer-datauppsättningar (meddelandefeedback, e-postspårning osv.) kan inte användas för att utlösa en resa. Om du inte kan få direktuppspelade händelser kan du bygga en målgrupp baserat på dessa händelser och använda **Läs målgrupp** i stället. Målgruppskvalificering kan tekniskt sett användas, men kan orsaka problem längre fram i kedjan baserat på de åtgärder som används.

### Datakällor {#data-sources-g}

* Externa datakällor kan utnyttjas inom en kundresa för att söka efter externa data i realtid. Dessa källor måste kunna användas via REST API, ha stöd för JSON och kunna hantera antalet begäranden.
* Adobe adresser (`.adobe.*`) tillåts inte i URL:er och API:er.

>[!NOTE]
>
>Eftersom svaren nu stöds bör du använda anpassade åtgärder i stället för datakällor för externa datakällor som användningsfall.

### Resor och skapande av profiler {#journeys-limitation-profile-creation}

Det finns en fördröjning i skapandet/uppdateringen av API-baserade profiler i Adobe Experience Platform. Servicenivåmålet (SLT) i form av fördröjning är &lt; 1 min från intag till en enhetlig profil för 95:e percentilen begäranden, vid en volym på 20 000 förfrågningar per sekund (RPS).

Om en resa utlöses samtidigt för att skapa en profil och omedelbart kontrollerar/hämtar information från profiltjänsten kanske den inte fungerar som den ska.

Du kan välja mellan följande två lösningar:

* Lägg till en vänteaktivitet efter den första händelsen för att ge Adobe Experience Platform den tid det behöver för att utföra inmatningen till profiltjänsten.

* Konfigurera en resa som inte omedelbart utnyttjar profilen. Om resan till exempel är utformad för att bekräfta att ett konto har skapats, kan upplevelsehändelsen innehålla information som behövs för att skicka det första bekräftelsemeddelandet (förnamn, efternamn, e-postadress osv.).

### Läs målgrupp {#read-segment-g}

* Direktuppspelade målgrupper är alltid uppdaterade, men batchmålgrupper beräknas inte vid hämtningen. De utvärderas endast varje dag vid den dagliga grupputvärderingen.
* För resor som använder aktiviteten Läs målgrupp finns det ett maximalt antal resor som kan påbörjas exakt samtidigt. Nya försök kommer att utföras av systemet men undvik att ha fler än fem resor (med Läs publik, schemalagd eller starta&quot;så snart som möjligt&quot;) med början vid exakt samma tidpunkt genom att sprida dem över tiden, till exempel med 5 till 10 minuters mellanrum.

### Uttrycksredigerare {#expression-editor}

* Det går inte att använda fältgrupper för upplevelsehändelser på resor som börjar med en läsare, en målgrupp eller en affärshändelseaktivitet. Ni måste skapa en ny målgrupp och använda ett villkor för målgrupp under resan.


### Aktivitetsbegränsningar i appen {#in-app-activity-limitations}

* Den här funktionen är för närvarande inte tillgänglig för vårdkunder.

* Personalisering kan bara innehålla profilattribut.

* Visning i appen är knuten till resans livscykel, vilket innebär att när resan avslutas för en profil kommer alla meddelanden i appen under resan inte att visas för den profilen.  Det är därför inte möjligt att stoppa ett meddelande i appen direkt från en reseaktivitet. I stället måste du avsluta hela kundresan för att stoppa visningen av meddelanden i appen från att visas i profilen.

* I testläge beror visningen i appen på resans livslängd. Justera **[!UICONTROL Wait time]** värde för **[!UICONTROL Wait]** verksamhet.

* **[!UICONTROL Reaction]** -aktiviteter kan inte användas för att reagera på en öppning eller klickning i appen.

* En aktiveringsfördröjning kan uppstå från det att en användarprofil når en aktivitet i appen på arbetsytan till dess att meddelandet visas i appen.

* Innehållets storlek för meddelanden i appen är begränsad till 2 MB. Om du inkluderar stora bilder kan det försvåra publiceringsprocessen.

## Målgrupper och skyddsräcken {#audience}

* Du kan publicera upp till 10 publikkompositioner i en given sandlåda. Om du har nått det här tröskelvärdet måste du ta bort en disposition för att frigöra utrymme och publicera en ny.

## Handläggningsgaranti {#decision-management}

### Prestandaskydd {#performance-guardrails}

Leveransflödet motsvarar antalet beslutssvar som kan levereras av beslutsstyrningsapptjänsten under en angiven tidsperiod. Antalet beslut per sekund anges i tabellen nedan.

| API | Beslut per sekund |
|---------|----------|
| API-begäranden för beslut | 500 per sekund |
| API-begäranden för Edge Decision | 5 000 per sekund |

### Begränsningar {#offers-limitations}

Begränsningarna för beslutshantering anges nedan.

* **Godkända personaliserade erbjudanden + reseräkningar** - Upp till 10 000 kombinerade godkända personliga erbjudanden och godkända reserverbjudanden.
* **Beslut** - Upp till 10 000 beslut.
* **Live-beslut** - Offer decisioning App Service stöder upp till 1 000 Live-beslut.
* **Erbjudanden som returneras per svar** - Offera decisioningen stöder upp till 100 returnerade erbjudanden per begäran för alla beslutsomfattningar som efterfrågas.
* **Samlingar** - Upp till 10 000 samlingar.
* **Samlingar per beslut** - Upp till 30 samlingar per beslut.
* **Beslutsregler + rangordningsfunktioner** Upp till 10 000 kombinerade beslutsregler och rankningsfunktioner.
* **Placeringar** - Upp till 1 000 praktik.
* **Placeringar per beslut** - Upp till 30 praktik per beslut.
* **Rankningsmetod per beslut** - Offer decisioning App Service stöder upp till 30 rankningsfunktioner per beslut.
* **AI-rankningsmodell** - Offer decisioning App Service stöder upp till 5 AI-rankningsmodeller.
* **Samlingskvalificerare per erbjudande eller samling** - Offer decisioning App Service har stöd för upp till 20 samlingskvalificerare i ett personligt erbjudande eller en enda samling.
* **Totalt antal samlingskvalificerare** - Offer decisioning App Service stöder upp till 1 000 Collection Qualifiers.