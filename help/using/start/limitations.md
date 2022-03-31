---
title: Journey Optimizer begränsningar
description: Läs mer om Journey Optimizer begränsningar
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 5d59f21c-f76e-45a9-a839-55816e39758a
source-git-commit: d2ae8f7a2a44ac92d26520e5c85a19a2660ed8e2
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 0%

---

# Begränsningar {#limitations}

Tillstånd, produktbegränsningar och prestandaskydd finns i[ Adobe Journey Optimizer produktbeskrivningssida](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target=&quot;_blank&quot;}.

Nedan finns ytterligare begränsningar när du använder [!DNL Adobe Journey Optimizer].

## Begränsningar i meddelanden {#limitations-messages}

* Du kan inte lägga till bilagor i ett e-postmeddelande med [!DNL Journey Optimizer].
* BCC för e-post stöds inte i [!DNL Journey Optimizer].
* Du kan inte använda samma sändande domän för att skicka ut meddelanden från [!DNL Adobe Journey Optimizer] och från en annan produkt, som [!DNL Adobe Campaign] eller [!DNL Adobe Marketo Engage] till exempel.

## Begränsningar av landningssidor {#limitations-lp}

* Bara en **Formulär** kan användas på en enda primär sida.
* The **Formulär** -komponenten kan inte användas i undersidor.
* Du kan inte lägga till en förrubrik på en landningssida.
* Du kan inte välja **Koda din egen** när du utformar en primär landningssida.

## Begränsningar av resor {#limitations-journeys}

### Allmänna åtgärder {#general-actions}

* Det finns ingen sändande begränsning.
* Tre försök utförs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet.
* Den inbyggda **Reaktion** -händelsen gör att du kan reagera på åtgärder som är klara. Läs mer i [den här sidan](../building-journeys/reaction-events.md). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse.
* Du kan inte placera två åtgärder parallellt. Du måste lägga till dem en i taget.

### Meddelandeåtgärd {#message-action}

* När du lägger till ett flerkanalsmeddelande skickas två meddelanden.

### Reseversioner {#journey-versions-limitations}

* En resa som börjar med en händelseaktivitet i v1 kan inte börja med något annat än en händelse i andra versioner. Du kan inte påbörja en resa med en **Segmentkvalificering** -händelse.
* En resa som börjar med en **Segmentkvalificering** aktivitet i v1 måste alltid börja med **Segmentkvalificering** i andra versioner.
* Det segment och namnutrymme som valts i **Segmentkvalificering** (första noden) kan inte ändras i nya versioner.
* Regeln för återinträde måste vara densamma i alla reseversioner.
* En resa som börjar med en **Läs segment** kan inte börja med en annan händelse i nästa version.

### Anpassade åtgärder {#custom-actions}

* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar.
* Endast anropsmetoderna POST och PUT stöds
* Namnet på frågeparametern eller huvudet får inte börja med &quot;.&quot; eller &quot;$&quot;
* IP-adresser tillåts inte
* Interna Adobe-adresser (.adobe.) tillåts inte.

### Händelser {#events}

* För systemgenererade händelser måste strömmande data som används för att initiera en kundresa konfigureras inom Journey Optimizer först för att få ett unikt orkestrerings-ID. Detta Orchestration-ID måste bifogas till strömningsnyttolasten som kommer till Adobe Experience Platform. Denna begränsning gäller inte regelbaserade händelser.

### Datakällor {#data-sources}

* Externa datakällor kan utnyttjas inom en kundresa för att söka efter externa data i realtid. Dessa källor måste kunna användas via REST API, ha stöd för JSON och kunna hantera antalet begäranden.

### Resor som börjar samtidigt som en profil skapas {#journeys-limitation-profile-creation}

Det finns en fördröjning i skapandet/uppdateringen av API-baserade profiler i Adobe Experience Platform. Servicenivåmålet (SLT) i form av fördröjning är &lt; 1 min från intag till en enhetlig profil för 95:e percentilen begäranden, vid en volym på 20 000 förfrågningar per sekund (RPS).

Om en resa utlöses samtidigt för att skapa en profil och omedelbart kontrollerar/hämtar information från profiltjänsten kanske den inte fungerar som den ska.

Du kan välja mellan följande två lösningar:

* Lägg till en vänteaktivitet efter den första händelsen för att ge Adobe Experience Platform den tid det behöver för att utföra inmatningen till profiltjänsten.

* Konfigurera en resa som inte omedelbart utnyttjar profilen. Om resan till exempel är utformad för att bekräfta att ett konto har skapats, kan upplevelsehändelsen innehålla information som behövs för att skicka det första bekräftelsemeddelandet (förnamn, efternamn, e-postadress osv.).

### Lässegment {#read-segment}

* Strömmade segment är alltid uppdaterade, men gruppsegment beräknas inte vid hämtningen. De utvärderas endast varje dag vid den dagliga grupputvärderingen.
