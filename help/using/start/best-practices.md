---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer bästa praxis
description: Läs mer om Journey Optimizer bästa praxis
feature: Get Started
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 271fb85d-5621-4a12-b3d1-65cf6021b174
source-git-commit: 6c73a1ee024ca61b30d71e77268e51b93576ae62
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 0%

---

# Bästa praxis {#best-practices}

## Riktlinjer för användning i realtid och flerkanalspersonalisering {#real-time-guidance}

Efter uppdateringen av Identity Service 2.0 har identitetskaritning i realtid utvecklats.

Adobe Journey Optimizer använder identitetstjänsten för att sammanfoga profiler och personalisera upplevelser för användaren. Det innebär att det finns vissa viktiga aspekter av tjänsten som du bör känna till när du bygger upp dina användningsfall. Som varumärke vill ni leverera en upplevelse till en person. Med identitetsdiagrammet kan marknadsförare förstå vilka enheter en person är kopplad till över olika kanaler. Diagrammet kan innehålla identiteter som representerar en person (CRMID) eller en webbläsare (ECID). Identitetstjänsten sammanfogar denna information, vilket gör det möjligt att skapa en&quot;360-gradersvy&quot; av en person eller en sammanfogad profil. Det innebär att när någon bläddrar på webbplatsen och sedan loggar in kan alla tidigare data från den sessionen kopplas till inloggningsanvändaren. Den här åtgärden utförs i några olika steg:

1. Inledande sammanslagning av identiteter - När en person loggar in kopplas inloggningsidentifieraren (CRMID) till webbläsaridentifieraren (webb- eller mobilappssession):

   * Detta kan ta 30 min - 4 timmar att slutföra.
   * Vanligtvis genererar den här inloggningshändelsen ett identitetsdiagram som länkar CRMID till ECID.

1. Efter den första sammanfogningen kopplas alla data som skickas in med någon av de två identiteterna till den sammanfogade profilen och är tillgängliga för personalisering i Journey Optimizer i realtid. Det kan ta upp till en minut att uppdatera profilen med de senaste beteendedata. Se den här [sidan](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=sv).

Tänk på följande när du bygger användningsexempel:

1. Varumärket vill återengagera en besökare på webbplatsen 30 minuter efter att han eller hon har lämnat företaget (t.ex. övergivna kundvagnsmeddelanden):

   Använd identiteten med data - ECID. Om du vill fånga 100 % av de besökare som har gett sin e-postadress/app-installation inom de senaste 30 minuterna, bör du använda den cookie-baserade identiteten för att starta den här resan (ECID). Detta förutsätter att din e-postadress, push-token eller annan adress för upplevelsen är kopplad till ECID.

1. Engagemang i alla kanaler på webben, i e-post, via push, osv.:

   * Du måste ha adresserna för kommunikation tillgängliga i profilen vid tidpunkten för interaktionen. För att detta ska ske på ett konsekvent och snabbt sätt måste du se till att dina data är kopplade till den identitet du vill använda.
   * Om du behöver använda information från en nyligen installerad app- eller webbläsarsession i kombination med känd eller inloggad information, måste den här kommunikationen skickas ut efter att identiteterna har sammanfogats. Detta kan variera per kund och vi uppmuntrar dig att vänta i minst 30 minuter för att få högsta antal profiler.

## Skala med resedaggar {#scale}

I det här avsnittet får du hjälp med att skala med följande två begränsningar:

* Journey Optimizer har 50 aktiviteter i ryggen på en arbetsyta. Det här skyddsutkastet är utformat för att hjälpa till med läsbarhet, QA och felsökning. Antalet aktiviteter i en resa visas i den övre vänstra delen av arbetsytan när du kommer inom tio aktiviteter från den här gränsen.

* När du publicerar resor skalas och justeras Journey Optimizer automatiskt för att säkerställa maximal genomströmning och stabilitet. I närheten av milstolpen för 100 live-resor på en gång i en sandlåda visas en orange övertäckning och ett varningstecken i gränssnittet för den här uppgiften. Om du ser det här meddelandet och behöver förlänga dina resor mer än 100 resor i taget kan du skapa en biljett för kundvård så hjälper vi dig att nå dina mål.

<!--DOCAC-10977

* As you publish journeys, Journey Optimizer automatically scales and adjusts to ensure maximum throughput and stability. As you near the milestone of 500 live journeys at one time in a sandbox, you will see an orange overlay and warning sign appear in the interface on this achievement. If you see this notification and have a need to extend your journeys beyond 500 live journeys at a time, please create a ticket for customer care and we will help you reach your goals.-->


Det finns ett antal bästa metoder som du kan implementera och som hjälper dig att hålla dig inom räckhåll och använda systemet effektivt.

* Om du närmar dig gränsen för antal resor i realtid kan du först gå till fliken **Översikt** under **Resor** för att se hur många resor som har varit aktiva under de senaste 24 timmarna som hade aktiva profiler. Du kan kontrollera antalet profiler som kommer in och avslutar resan i det här avsnittet för att avgöra det.

  ![](assets/journey-guardrails2.png)

* I avsnittet Resurslager kan du sedan filtrera alla resor efter Status = &quot;Live&quot; och Typ = &quot;Läs målgrupp&quot;. Sortera sedan efter publiceringsdatum (äldsta till nyaste). Klicka på resan och gå till schemat. Stoppa alla liveresor som hade ett schema för att köra **En gång** eller **Så snart som möjligt** och som är äldre än en dag och bara har en åtgärd.

  ![](assets/journey-guardrails1.png)

* Om din **läs målgruppsresa** bara har en åtgärd, inga väntningar/beslut eller optimering av sändningstiden bör du överväga att flytta dem till Journey Optimizer Campaigns. Kampanjer passar bättre för engagemanget i ett enda steg. En av de största skillnaderna mellan Campaign och Journeys är om ni anser att det är viktigt att aktivt lyssna på användarengagemanget för att avgöra nästa steg och engagera er i en annan åtgärd.
* Om du vill minska antalet aktiviteter inom en resa kontrollerar du villkorsstegen. Det finns många tillfällen då du kan flytta villkoren till segmentdefinition eller målgruppskomposition.
* Om samma villkor upprepas på flera resor (samtyckeskontroller, inaktiveringar) bör du överväga att flytta dem som en del av segmentdefinitionen. Om du t.ex. har ett villkor för att kontrollera att e-postadressen inte är tom på flera resor, ska villkoret ingå i segmentdefinitionen.
* Om kundresan har flera villkor som delar upp målgruppen för att se siffrorna i varje steg bör du överväga att använda Customer Journey Analytics eller någon annan rapporteringslösning som är bättre lämpad för analys.
* Om du närmar dig gränsen för antal noder på arbetsytan bör du överväga att konsolidera åtgärder med dynamiska parametrar eller innehåll för att leverera rätt innehåll i stället för explicita noder.

* Om du har en **Läs målgrupp**-resa med ett gruppsegment (A) och du använder ett inAudience-direktuppspelningssegment (B) inom resan för att exkludera (d.v.s. utföra A-B), bör du överväga att flytta den logiken till segmenteringslogiken och använda exkluderingen som en del av själva segmenteringslogiken.