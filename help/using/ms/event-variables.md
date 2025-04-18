---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med händelsevariabler i samordnade kampanjer
description: Lär dig hur du utnyttjar händelsevariabler i dina samordnade kampanjer
hide: true
hidefromtoc: true
exl-id: f86dd262-0209-42f6-a180-736f1de98d78
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Arbeta med händelsevariabler {#event-variables}

I vissa samordnade kampanjaktiviteter kan du redigera skript i uttrycksredigeraren för att utföra specifika åtgärder som att hämta data från tidigare aktiviteter, skapa villkor eller beräkna filnamn baserat på händelsevariabler.

## Vad är händelsevariabler? {#scripting}

Skript som körs i kontexten för en orkestrerad kampanj får åtkomst till en serie med ytterligare globala **objekt**, till exempel den orkestrerade kampanj som körs (`ìnstance`), dess olika aktiviteter (`task`) eller händelserna som aktiverade en viss aktivitet (`event`).

Till varje typ av **object** kopplas en kategori med **variabler** som kan utnyttjas i uttrycksredigeraren när skript redigeras i aktiviteter som **[!UICONTROL JavaScript code]** eller **[!UICONTROL Test]**.

* **Instansvariabler** (`instance.vars.xxx`) är jämförbara med globala variabler. De delas av alla aktiviteter.
* **Aktivitetsvariabler** (`task.vars.xxx`) är jämförbara med lokala variabler. De används bara av den aktuella uppgiften. Variablerna används av beständiga aktiviteter för att lagra data och används ibland för att utbyta data mellan olika skript för samma aktivitet.
* **Händelsevariabler** (`vars.xxx`) möjliggör datautbyte mellan de grundläggande aktiviteterna i en iscensatt kampanjprocess. Dessa variabler skickas av aktiviteten som aktiverade den pågående uppgiften. De överförs sedan till följande aktiviteter. **Händelsevariabler** är de variabler som används oftast, och de bör användas i stället för förekomstvariabler.

## Utnyttja händelsevariabler i uttrycksredigeraren {#expression-editor}

Fördefinierade händelsevariabler är tillgängliga för användning i den vänstra delen av uttrycksredigeraren. Du kan också skapa nya variabler genom att initiera en ny variabel i koden.

![](assets/event-variables.png)

Förutom dessa händelsemariabler kan du även använda menyn **[!UICONTROL Conditions]** i den vänstra rutan för att skapa villkor och menyn **[!UICONTROL Add current date]** för att använda funktioner som är relaterade till datumformatering.
