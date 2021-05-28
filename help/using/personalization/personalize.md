---
title: Anpassa innehåll i Journey Optimizer
description: Kom igång med personalisering
source-git-commit: 8c58dd667ea59a17833bbe3482b1a233ac2e28fe
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 3%

---

# Kom igång med personalisering{#add-personalization}

![](../assets/do-not-localize/badge.png)

Upptäck möjligheterna till personalisering av Journey Optimier så att ni kan anpassa era meddelanden till varje viss mottagare genom att utnyttja de data och den information ni har om honom/henne. Det kan vara hans förnamn, intressen, var han bor, vad han köpte och mycket annat.

Journey Optimizer använder en **infogad** enkel personaliseringssyntax baserad på Handlebars, som gör att du kan skapa uttryck med innehåll omgivet av dubbla klammerparenteser **{{}}**. Du kan lägga till flera uttryck i samma innehåll eller fält utan begränsningar. Läs mer i [Personaliseringssyntax](personalization-syntax.md).

Anpassningen baseras på profildata som hanteras av schemat **XDM Individual Profile** som definieras i Adobe Experience Platform. Mer information finns i [dokumentationen för Adobe Experience Platform datamodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv).

>[!CAUTION]
>Schemat **XDM Individual Profile** är det enda schema som du kan använda för att anpassa innehåll i Journey Optimizer.

**Exempel:**

```
Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}

Hello {{profile.person.gender}} {{profile.person.name.fullName}}
```

När du bearbetar meddelandet (e-post och push) ersätter Journey Optimizer uttrycket med data som finns i databasen för Experience Cloud Platform.

```
Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}} becomes “Hello John Doe”.
```
