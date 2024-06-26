---
solution: Journey Optimizer
product: journey optimizer
title: Anpassa innehåll i Journey Optimizer
description: Kom igång med personalisering.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Beginner
keywords: uttryck, redigerare, start, personalisering
exl-id: f448780b-91bc-455e-bf10-9a9aee0a0b24
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Kom igång med personalisering{#add-personalization}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card5"
>title="Personalisera upplevelser"
>abstract="Använd **Adobe Journey Optimizer** för att anpassa era meddelanden till varje specifik mottagare genom att utnyttja de data och den information ni har om dem. Det kan vara deras förnamn, intressen, var de bor, vad de har köpt och mycket annat."

Upptäck [!DNL Adobe Journey Optimizer] personaliseringsfunktioner för att anpassa era meddelanden till varje specifik mottagare genom att utnyttja de data och den information ni har om dem. Det kan vara deras förnamn, intressen, var de bor, vad de har köpt och mycket annat.

➡️ [Lär dig hur du anpassar ett meddelande i dessa videofilmer](#video-perso)
➡️ [Upptäck användningsfall som utnyttjar personalisering](personalization-use-case.md)

## Skapa personaliseringsuttryck med en dedikerad syntax {#syntax}

[!DNL Journey Optimizer] använder **inline** enkel personaliseringssyntax baserad på Handlebars, som gör att du kan skapa uttryck med innehåll inneslutet av dubbla klammerparenteser **{{}}**. Du kan lägga till flera uttryck i samma innehåll eller fält utan begränsningar. [Läs mer om personaliseringssyntaxen](personalization-syntax.md).

**Exempel:**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`
* `Hello {{profile.person.name.fullName}}`

När du bearbetar meddelandet (e-post och push) ersätter Journey Optimizer uttrycket med data i Experience Platform-databasen:  `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` blir &quot;Hello John Doe&quot;.

## Utnyttja profildata för att personalisera era meddelanden {#data}

Personaliseringen baseras på profildata som hanteras av **Individuell XDM-profil** schema definierat i Adobe Experience Platform. Läs mer i [Dokumentation för Adobe Experience Platform Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

>[!CAUTION]
>The **Individuell XDM-profil** schema är det enda schema som du kan använda för att anpassa innehåll i [!DNL Journey Optimizer].

Dessutom kan du också utnyttja **beräknade attribut** för att personalisera ert innehåll. Beräknade attribut baseras på profilaktiverade Experience Event-datauppsättningar som importerats till Adobe Experience Platform och fungerar som aggregerade datapunkter lagrade i kundprofiler som sammanfattar individuella beteendehändelser [Lär dig hur du arbetar med beräknade attribut](../audience/computed-attributes.md)

## Arbeta med personaliseringsredigeraren {#editor}

[!DNL Journey Optimizer] har en personaliseringsredigerare där du kan välja, ordna, anpassa och validera alla data för att skapa en anpassad personalisering för ditt innehåll. Det finns flera verktyg som du kan använda för att bygga ditt personaliseringsinnehåll, till exempel felper-funktioner, fördefinierat uttrycksbibliotek, attribut och mycket mer.

* [Lär dig arbeta med personaliseringsredigeraren](personalization-build-expressions.md)
* [Lär dig var du kan utföra personalisering](personalization-contexts.md).

## Instruktionsfilmer{#video-perso}

Lär dig hur du använder sammanhangsbaserad händelseinformation från en resa för att personalisera ett meddelande.

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

Lär dig hur du lägger till profilbaserad personalisering i ett meddelande och hur du använder målgruppsmedlemskap som en förutsättning för ett personaliseringsblock.

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)

