---
product: experience platform
solution: Experience Platform
title: Anpassad optimeringsmodell
description: Läs mer om personaliserade optimeringsmodeller
feature: Ranking, Offers
role: User
level: Intermediate
exl-id: c73b3092-e96d-4957-88e6-500e99542782
source-git-commit: 0ea2ed03a476e0b64a8ebfadde403ff9f9e57bba
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# Anpassad optimeringsmodell {#personalized-optimization-model}

## Översikt {#overview}

Genom att utnyttja den senaste tekniken inom maskininlärning och djupinlärning under övervakning kan en företagsanvändare (marknadsförare) med automatisk anpassning definiera affärsmål och använda sina kunddata för att utbilda affärsorienterade modeller för att leverera personaliserade erbjudanden och maximera nyckeltal.

![](../../rn/assets/do-not-localize/ai-ranking.gif)

## Antaganden och begränsningar för nyckelmodeller {#key}

För att maximera fördelen med automatisk personalisering finns det vissa viktiga antaganden och begränsningar att vara medveten om.

* **Erbjudandena är tillräckligt olika så att användarna får olika preferenser bland erbjudandena i fråga**. Om erbjudandena är för lika kommer en resulterande modell att få mindre effekt eftersom svaren verkar vara slumpmässiga.
Om en bank t.ex. har två kreditkort med den enda skillnaden att vara färg, spelar det ingen roll vilket kort som rekommenderas, men om varje kort har olika villkor, ger detta en logisk grund för varför vissa kunder skulle välja ett och ger tillräckligt stor skillnad mellan erbjudandena för att skapa en mer slagkraftig modell.
* **Användarens trafikkomposition är stabil**. Om användartrafikens sammansättning ändras dramatiskt under modellutbildning och -prediktion kan modellens prestanda försämras. Anta till exempel att det i modellutbildningsfasen bara finns data för användare i målgrupp A, men den tränade modellen används för att generera prognoser för användare i målgrupp B, och att modellens prestanda kan påverkas.
* **Prestandan ändras inte dramatiskt under en kort tidsperiod** när den här modellen uppdateras varje vecka och prestandaändringar visas när modellen uppdateras. En produkt var till exempel mycket populär tidigare, men i en offentlig rapport identifieras produkten som skadlig för vår hälsa och den här produkten blir ovanligt snabb. I det här scenariot kan modellen fortsätta att förutsäga den här produkten tills modellen uppdateras med ändringar i användarbeteendet.

## Så här fungerar det {#how}

Modellen lär sig komplexa funktionsinteraktioner mellan erbjudanden, användarinformation och sammanhangsbaserad information för att rekommendera personaliserade erbjudanden till slutanvändare. Funktioner är indata i modellen.

Det finns tre typer av funktioner:

| Funktionstyper | Så här lägger du till funktioner i modeller |
|--------------|----------------------------|
| Beslutsobjekt (placementID, activityID, DecisionScopeID) | Ingår i beslutsledningens feedback Experience Events skickas till AEP |
| Målgrupper | 0-50 målgrupper kan läggas till som funktioner när du skapar AI-modellen för rankning |
| Kontextdata | En del av beslutsfeedback Experience Events skickas till AEP. Tillgängliga kontextdata att lägga till i schema: Commerce Details, Channel Details, Application Details, Web Details, Environment Details, Device Details, placeContext |

Modellen har två faser:

* I **utbildning i offlinemodell** en modell utbildas av att man lär sig och memorerar funktionsinteraktioner i historiska data.
* I **online-insikt** fas rangordnas anbudsförfrågningar baserat på realtidspoäng som genereras av modellen. Till skillnad från traditionell filtreringsteknik för samarbete, som är svår att inkludera funktioner för användare och erbjudanden, är automatisk personalisering en djupgående inlärningsbaserad rekommendationsmetod och kan inkludera och lära sig komplexa och icke-linjära interaktionsmönster.

Här är ett förenklat exempel som illustrerar grundtanken bakom automatisk personalisering. Anta att vi har en datauppsättning som lagrar historiska interaktioner mellan användare och erbjudanden, vilket visas i bild 1. Det finns:
* Två erbjudanden, offer_1 och offer_2,
* Två funktioner, feature_1 och feature_2,
* En svarskolumn.

Värdet för feature_1, feature_2 och response är antingen 0 eller 1. När vi tittar på de blå och orange rutorna i bild 1 ser vi att för offer_1 är det troligare att svaren är 1 när feature_1 och feature_2 har samma värden, medan för offer_2 är etiketterna troligare 1 när feature_1 är 0 och feature_2 är 1. Vi kan också se att offer_1 används i den röda rutan när feature_1 är 0 och feature_2 är 1, och svaret är 0. Baserat på mönstret vi ser i orange rutor är offer_2 förmodligen bättre när feature_1 är 0 och feature_2 är 1.

Det handlar i princip om att lära sig och memorera historiska funktionsinteraktioner och använda dem för att generera personaliserade prognoser.

![](../assets/perso-ranking-schema.png)

## Problem med kallstart {#cold-start}

Problem med kallstart uppstår när det inte finns tillräckligt med data för att kunna rekommendera. För automatisk personalisering finns det två typer av kallstartsproblem.

* **Efter att en ny AI-modell har skapats utan historiska data**, erbjudandena kommer att slumpmässigt erbjudas under en period för att samla in data och uppgifterna kommer att användas för att utbilda den första modellen.
* **När den första modellen har släppts** 10 % av den totala trafiken kommer att fördelas slumpvis, medan 90 % av trafiken kommer att användas för modellrekommendationer. Om nya erbjudanden läggs till i AI-modellen skulle de därför levereras som en del av 10 % av trafiken. De data som samlas in för dessa erbjudanden avgör hur många gånger de väljs ut bland 90 % av trafiken när modellen fortsätter att uppdateras.

## Omskolning {#re-training}

Modellerna kommer att omutbildas för att lära sig de senaste funktionsinteraktionerna och minska prestandaförsämringen varje vecka.
