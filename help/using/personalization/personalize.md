---
title: Anpassa innehåll i Journey Optimizer
description: Kom igång med personalisering.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Beginner
exl-id: f448780b-91bc-455e-bf10-9a9aee0a0b24
source-git-commit: baa98afcc8e5e9be3062c8c16adc7f4ae17b15b7
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 4%

---

# Kom igång med personalisering{#add-personalization}

Upptäck [!DNL Adobe Journey Optimizer] personaliseringsfunktioner för att anpassa era meddelanden till varje specifik mottagare genom att utnyttja de data och den information ni har om dem. Det kan vara deras förnamn, intressen, var de bor, vad de har köpt och mycket annat.

➡️ [Lär dig hur du anpassar ett meddelande i dessa videofilmer](#video-perso)

[!DNL Journey Optimizer] använder **inline** enkel personaliseringssyntax baserad på Handlebars, som gör att du kan skapa uttryck med innehåll inneslutet av dubbla klammerparenteser **{{}}**. Du kan lägga till flera uttryck i samma innehåll eller fält utan begränsningar. Läs mer i [Anpassningssyntax](personalization-syntax.md).

Personaliseringen baseras på profildata som hanteras av **Individuell XDM-profil** schema definierat i Adobe Experience Platform. Läs mer i [Dokumentation för Adobe Experience Platform Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target=&quot;_blank&quot;}.

>[!CAUTION]
>The **Individuell XDM-profil** schema är det enda schema som du kan använda för att anpassa innehåll i [!DNL Journey Optimizer].

**Exempel:**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`

* `Hello {{profile.person.name.fullName}}`

När du bearbetar meddelandet (e-post och push) ersätter Journey Optimizer uttrycket med data som finns i databasen för Experience Cloud Platform:  `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` blir &quot;Hello John Doe&quot;.

## Instruktionsvideor{#video-perso}

Lär dig hur du använder sammanhangsbaserad händelseinformation från en resa för att personalisera ett meddelande.

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

Lär dig hur du använder sammanhangsbaserad händelseinformation från en resa för att personalisera ett meddelande.

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)
