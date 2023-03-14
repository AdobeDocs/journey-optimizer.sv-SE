---
solution: Journey Optimizer
product: journey optimizer
title: Statistiska beräkningar som används av Adobe Journey Optimizer Experimentation
description: Läs mer om statistiska beräkningar som används vid försök
feature: A/B Testing
topic: Content Management
role: User
level: Experienced
keywords: innehåll, experiment, statistik, beräkning
hide: true
hidefromtoc: true
exl-id: 60a1a488-a119-475b-8f80-3c6f43c80ec9
badge: label="Beta" type="Informative"
source-git-commit: 160e4ce03d3be975157c30fbe511875a85b00551
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 0%

---

# Förstå statistiska beräkningar {#experiment-calculations}

>[!BEGINSHADEBOX]

Vad du hittar i den här dokumentationen:

* [Kom igång med innehållsexperiment](get-started-experiment.md)
* [Skapa ett innehållsexperiment](content-experiment.md)
* **[Förstå statistiska beräkningar](experiment-calculations.md)**
* [Konfigurera experimentrapporter](reporting-configuration.md)
* [Statistiska beräkningar i experimentrapporten](experiment-report-calculations.md)

>[!ENDSHADEBOX]

I den här artikeln beskrivs de statistiska beräkningar som används när du kör Experiment i Adobe Journey Optimizer.

Experimentationen använder avancerade statistiska metoder för att beräkna **Konfidenssekvenser** och **Förtroende**, som gör att du kan köra dina experiment så länge som det behövs och kontinuerligt övervaka dina resultat.

I den här artikeln beskrivs hur Experimentation fungerar och en intuitiv introduktion till Adobe **Valfri tidsgiltig konfidenssekvens**.

För expertanvändare beskrivs de tekniska detaljerna och referenserna i [den här sidan](../campaigns/assets/confidence_sequence_technical_details.pdf).

## Statistisk testning och kontroll av fel {#statistical-testing}

![](assets/technote_1.png)

Som framgår av tabellen ovan är många statistiska undersökningsmetoder utformade för att kontrollera två typer av fel:

* **Falska positiva värden (Type-I-fel)**: är ett felaktigt avvisande av nollhypotesen, när det faktiskt är sant. När det gäller onlineundersökningar innebär detta att vi felaktigt drar slutsatsen att resultatmåttet är olika för varje behandling, även om det var samma.
   </br>Innan vi genomför experimentet väljer vi vanligtvis ett tröskelvärde `\alpha`. När experimentet är klart `p-value` beräknas och vi avvisar `null if p < \alpha`. En vanlig tröskel är `\alpha = 0.05`, vilket innebär att vi i längden förväntar oss att 5 av 100 experiment ska vara falska positiva.

* **Falska negativ (typ II-fel)**: innebär att vi inte kan avvisa den nollhypotesen trots att den är falsk. För experiment innebär detta att vi inte avvisar nollhypotesen, när den faktiskt är annorlunda. För att kontrollera den här typen av fel måste vi i allmänhet ha tillräckligt många användare i vårt experiment för att garantera en viss styrka, definierad som `1 - \beta`(dvs. ett minus sannolikheten för ett typ II-fel).

De flesta statistiska startmetoder kräver att du korrigerar provstorleken i förväg, baserat på den effektstorlek som du vill bestämma samt feltolerans (`\alpha` och `\beta`) i förväg. Adobe Journey Optimizer metod är dock utformad för att du kontinuerligt ska kunna se dina resultat, oavsett provstorlek.

## Adobe Statistisk metod: Valfri tidsgiltig konfidenssekvens

A **Konfidenssekvens** är en sekventiell analog till en **Konfidensintervall**, t.ex. om du upprepar dina experiment hundra gånger och beräknar en uppskattning av medelvärdet och dess associerade 95 %-konfidenssekvens för varje ny användare som deltar i experimentet. En 95-procentig konfidenssekvens inkluderar det verkliga värdet för mätvärdet i 95 av de 100 experiment du utförde. Ett 95-procentigt konfidensintervall kunde endast beräknas en gång per experiment för att ge samma 95-procentiga garanti. inte för varje enskild ny användare. Med Confidence Sequences kan du därför kontinuerligt övervaka experiment utan att öka andelen falskt positiva fel.

Skillnaden mellan konfidenssekvenser och konfidensintervall för ett enskilt experiment visas i animeringen nedan:

![](assets/technote_2.gif)

**Konfidenssekvenser** ändra fokus på experiment till uppskattningar i stället för hypotesstester, dvs. med fokus på en korrekt uppskattning av skillnaden i medel mellan behandlingar, i stället för om en nollhypotes ska avvisas baserat på ett tröskelvärde för statistisk signifikans eller inte.

På liknande sätt som för relationen mellan `p-values`, eller **Förtroende** och **Konfidensintervall**, finns det också en relation mellan **Konfidenssekvenser** och när som helst `p-values`eller när som helst med giltig tillförlitlighet. Med tanke på hur välkända kvantiteter som Konfidensen är, tillhandahåller Adobe båda **Konfidenssekvenser** och varje gång det finns giltig tillförlitlighet i rapporterna.

Den teoretiska grunden för **Konfidenssekvenser** kommer från studien av sekvenser av slumpmässiga variabler som kallas martingales. Nedan finns några viktiga resultat för expertläsare, men det är tydligt att yrkesutövare har gjort detta:

>[!NOTE]
>
>Konfidenssekvenser kan tolkas som säkra sekventiella analoger med konfidensintervall. Du kan titta på och tolka data i dina Experimenter när du vill och stoppa eller fortsätta med experimenten. motsvarande valfri tid som är giltig, eller `p-value`, är också säkert att tolka.

Det är viktigt att notera att eftersom konfidenssekvenser är&quot;när som helst giltiga&quot;, är de mer försiktiga än en metod med fast horisont som används med samma provstorlek. Konfidenssekvensens gränser är i allmänhet bredare än en beräkning av konfidensintervall, medan alla tidsperioder som är giltiga konfidensintervall är mindre än en beräkning av en fast horisont. Fördelen med denna konservatism är att du säkert kan tolka dina resultat hela tiden.

## Förklaring av en expert till slutsats

![](assets/experimentation_report_2.png)

Varje gång du tittar på experimentrapporten analyserar Adobe de data som har ackumulerats i experimentet fram till den här tidpunkten och deklarerar ett experiment som &quot;semikoloniserande&quot; när det giltiga konfidensintervallet för varje tidpunkt överskrider ett tröskelvärde på 95 % för minst en av behandlingarna.

I det här skedet kommer den behandling som ger bäst resultat (baserat på konverteringsgraden eller det profilnormaliserade måttvärdet) att markeras överst på rapportskärmen och markeras med en stjärna i tabellrapporten. Endast behandlingar med ett konfidensintervall på mer än 95% tillsammans med utgångsvärdet beaktas vid denna bestämning.

När det finns mer än två behandlingar används länken för korrigering av Bonferroni för att korrigera flera jämförelseproblem, och styr den familjvisa felfrekvensen. I detta scenario är det också möjligt att det finns flera behandlingar vars konfidensgrad är större än 95 procent och vars konfidensintervall överlappar varandra. I det här fallet deklarerar Adobe Journey Optimizer den som har den högsta konverteringsgraden (eller profilnormaliserade mätvärden) som den bästa prestandan.
