---
title: Resebegränsningar
description: Läs mer om begränsningar för resor
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 5d59f21c-f76e-45a9-a839-55816e39758a
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# Begränsningar {#journey-limitations}

Här är begränsningar för användningen av resor.

## Allmänna åtgärdsbegränsningar

* Det finns ingen sändande begränsning. 
* Tre försök utförs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet. 
* Den inbyggda **Reaktion** gör att du kan reagera på åtgärder som är klara (se det här [page](../building-journeys/reaction-events.md)). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse. 
* Du kan inte placera två åtgärder parallellt. Du måste lägga till dem en i taget.

## Begränsningar för meddelandeåtgärd

* När du lägger till ett flerkanalsmeddelande skickas två meddelanden.

## Begränsningar för reseversioner {#journey-versions-limitations}

* En resa som börjar med en händelseaktivitet i v1 kan inte börja med något annat än en händelse i andra versioner. Du kan inte påbörja en resa med en **Segmentkvalificering** -händelse.
* En resa som börjar med en **Segmentkvalificering** aktivitet i v1 måste alltid börja med **Segmentkvalificering** i andra versioner.
* Det segment och namnutrymme som valts i **Segmentkvalificering** (första noden) kan inte ändras i nya versioner.
* Regeln för återinträde måste vara densamma i alla reseversioner.
* En resa som börjar med en **Läs segment** kan inte börja med en annan händelse i nästa version.
 

## Begränsningar för anpassade åtgärder

* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar. 
* Endast anropsmetoderna POST och PUT stöds. 
* Namnet på frågeparametern eller huvudet får inte börja med &quot;.&quot; eller &quot;$&quot;. 
* IP-adresser tillåts inte. 
* Interna Adobe-adresser (.adobe.) tillåts inte.
 

## Begränsningar för händelser

* För systemgenererade händelser måste strömmande data som används för att initiera en kundresa konfigureras inom Journey Optimizer först för att få ett unikt orkestrerings-ID. Detta Orchestration-ID måste bifogas till strömningsnyttolasten som kommer till Adobe Experience Platform. Denna begränsning gäller inte regelbaserade händelser.
 

## Begränsningar för datakällor

* Externa datakällor kan utnyttjas inom en kundresa för att söka externa data i realtid. Dessa källor måste kunna användas via REST API, ha stöd för JSON och kunna hantera antalet begäranden.

## Resor som börjar samtidigt som en profil skapas {#journeys-limitation-profile-creation}

Det finns en fördröjning i skapandet/uppdateringen av API-baserade profiler i Adobe Experience Platform. Servicenivåmålet (SLT) i form av fördröjning är &lt; 1 min från intag till en enhetlig profil för 95:e percentilen begäranden, vid en volym på 20 000 förfrågningar per sekund (RPS).

Om en resa utlöses samtidigt för att skapa en profil och omedelbart kontrollerar/hämtar information från profiltjänsten kanske den inte fungerar som den ska.

Du kan välja mellan följande två lösningar:

* Lägg till en vänteaktivitet efter den första händelsen för att ge Adobe Experience Platform den tid det behöver för att utföra inmatningen till profiltjänsten.

* Konfigurera en resa som inte omedelbart utnyttjar profilen. Om resan till exempel är utformad för att bekräfta att ett konto har skapats, kan upplevelsehändelsen innehålla information som behövs för att skicka det första bekräftelsemeddelandet (förnamn, efternamn, e-postadress osv.).

## Läs segmentbegränsningar

* Strömmade segment är alltid uppdaterade, men gruppsegment beräknas inte vid hämtningen. De utvärderas endast varje dag vid den dagliga grupputvärderingen.