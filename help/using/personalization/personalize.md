---
solution: Journey Optimizer
product: journey optimizer
title: Anpassa innehåll i Journey Optimizer
description: Kom igång med personalisering.
feature: Personalization
topic: Personalization
role: Developer
level: Beginner
keywords: uttryck, redigerare, start, personalisering
exl-id: f448780b-91bc-455e-bf10-9a9aee0a0b24
source-git-commit: efb943e5a6f27becc6e8b6128b776e46d6141823
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---

# Kom igång med personalisering{#add-personalization}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card5"
>title="Personalisera upplevelser"
>abstract="Använd **Adobe Journey Optimizer** för att anpassa dina meddelanden till varje specifik mottagare genom att utnyttja de data och den information du har om dem. Det kan vara deras förnamn, intressen, var de bor, vad de har köpt och mycket annat."

Med personaliseringsfunktionerna i [!DNL Adobe Journey Optimizer] kan du anpassa dina meddelanden till varje specifik mottagare genom att utnyttja de data och den information du har om dem. Det kan vara deras förnamn, intressen, var de bor, vad de har köpt och mycket annat.

## Så fungerar personalisering

Med **personaliseringsredigeraren** kan du välja, ordna, anpassa och validera alla data för att skapa en anpassad personalisering för ditt innehåll, och använda olika verktyg som hjälpfunktioner eller fördefinierade uttryck för att anpassa meddelanden effektivt.

Journey Optimizer använder en infogad personaliseringssyntax baserad på Handlebars, som gör att du kan skapa uttryck med innehåll inneslutet av dubbla klammerparenteser **`{{}}`**.

När du bearbetar meddelandet ersätter Journey Optimizer uttrycket med data som finns i Experience Platform datamängd. Till exempel blir `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` dynamiskt `Hello John Doe`.

Med den här syntaxen kan du anpassa meddelanden i flera fält, inklusive ämnesrader, meddelandetexter, push-meddelanden och URL:er.

## Data som används för personalisering

Personalization baseras på profildata som hanteras av schemat **XDM Individual Profile** som definierats i Adobe Experience Platform. Schemat **XDM Individual Profile** är det enda schema som du kan använda för att anpassa innehåll i [!DNL Journey Optimizer]. Läs mer i [dokumentationen för Adobe Experience Platform datamodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

Du kan också utnyttja **beräknade attribut** för att anpassa ditt innehåll. Beräknade attribut gör att du kan sammanfatta enskilda beteendehändelser i beräknade profilattribut som är tillgängliga på Adobe Experience Platform. [Lär dig arbeta med beräknade attribut](../audience/computed-attributes.md)

Dessutom kan du i [!DNL Journey Optimizer] utnyttja data från Adobe Experience Platform i personaliseringsredigeraren för att anpassa ditt innehåll. För att göra detta måste datauppsättningar som behövs för sökpersonalisering först aktiveras via ett API-anrop. När du är klar kan du använda deras data för att anpassa ditt innehåll till Journey Optimizer. Den här funktionen är för närvarande tillgänglig som betaversion. [Läs mer](../personalization/aep-data-perso.md)

## Lär dig mer och experimentera med personalisering {#playground}

**[!DNL Adobe Journey Optimizer]** innehåller ett interaktivt verktyg som hjälper dig att lära dig och experimentera med personaliseringsfunktioner.

Den här spelmiljön innehåller en simulerad miljö för att skriva och testa personaliseringskod med exempeldata utan att det krävs livedatauppsättningar. Du kan utnyttja fördefinierade kodexempel, redigera nyttolaster för dummy-profiler och förhandsgranska resultatet av din personaliseringskod i realtid.

![personalisering, spelplattform](assets/playground.png)

➡️ [Åtkomst till personaliseringsspelgrunden](https://experienceleague.adobe.com/sv/apps/journey-optimizer/ajo-personalization){target="_blank"}

## Låt oss dyka djupare

Nu när du har en förståelse för personalisering i **[!DNL Journey Optimizer]** är det dags att gå djupare in i dessa dokumentationsavsnitt för att börja arbeta med funktionen.

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="personalization-build-expressions.md">
<img alt="lägg till personalisering" src="assets/do-not-localize/add.png">
</a>
<div>
<a href="personalization-build-expressions.md"><strong>Lägg till personalisering</strong></a>
</div>
<p>
</td>
<td>
<a href="../personalization/personalization-syntax.md">
<img alt="Lead" src="assets/do-not-localize/syntax.png">
</a>
<div><a href="../personalization/personalization-syntax.md"><strong>Personalization-syntax</strong>
</div>
<p>
</td>
<td>
<a href="../personalization/functions/functions.md">
<img alt="Sällan" src="assets/do-not-localize/functions.png">
</a>
<div>
<a href="../personalization/functions/functions.md"><strong>Hjälpfunktionslista</strong></a>
</div>
<p></td>
<td>
<a href="../personalization/personalization-use-case.md">
<img alt="Sällan" src="assets/do-not-localize/uc.png">
</a>
<div>
<a href="../personalization/personalization-use-case.md"><strong>Användningsexempel för Personalization</strong></a>
</div>
<p></td>
</tr></table>

## Instruktionsfilmer{#video-perso}

Lär dig hur du använder sammanhangsbaserad händelseinformation från en resa för att personalisera ett meddelande.

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

Lär dig hur du lägger till profilbaserad personalisering i ett meddelande och hur du använder målgruppsmedlemskap som en förutsättning för ett personaliseringsblock.

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)

Lär dig hur du använder personaliseringsredigerarens spelmiljö för att skriva och testa personaliseringskod med exempeldata.

>[!VIDEO](https://video.tv.adobe.com/v/3457868?quality=12)

Utforska fler videokurser om personaliseringsfunktioner och metodtips i [Personalization självstudiekurser](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/personalize-content/personalization-editor-overview){target="_blank"}
