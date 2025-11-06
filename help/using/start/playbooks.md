---
solution: Journey Optimizer
product: journey optimizer
title: Use Case Playbooks
description: Lär dig hur du använder Adobe Experience Platform Use Case Playbooks med Adobe Journeys Optimizer.
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 2214ec90-580e-469e-9b14-d8cb2d4bb050
source-git-commit: efb943e5a6f27becc6e8b6128b776e46d6141823
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 1%

---

# Use Case Playbooks {#playbooks}

## Vad används spelböcker för gemener/VERSALER {#gs}

Använd fallspelsböcker är fördefinierade arbetsflöden som åtgärdar vanliga användningsfall som du kan utföra med Adobe Experience Platform och Journey Optimizer.

![animerad bild med Use Case Playbooks](../rn/assets/do-not-localize/playbooks.gif){width="85%"}

Varje spelbok innehåller en omfattande översikt som innehåller avsikter, mål, målinriktade personligheter och resurser som behövs för att implementera den. Dessutom finns det en mindmap i varje spelbok som visuellt representerar verkliga kundkontaktytor som är kopplade till spelboken.

![Övergiven spelningsbok för kundvagn visas i vyn Upptäck spelningsböcker](assets/playbooks-detail.png){width="85%"}

## Förhandskrav {#prerequisites}

Följande konfigurationssteg krävs innan du arbetar med Använd fallspelningsböcker. Detaljerad information om varje steg finns på sidan [Kom igång](https://experienceleague.adobe.com/docs/experience-platform/use-case-playbooks/playbooks/get-started.html){target="_blank"} i dokumentationen för Use Case Playbooks.

* Skapa en sandlåda
* Konfigurera användarbehörigheter
* Konfigurera Journey Optimizer-kanalkonfigurationer för e-post-, push- och SMS-meddelanden

## Få åtkomst till och aktivera en spelbok {#access}

Om du vill få åtkomst till spelböcker går du till menyn **[!UICONTROL Playbooks]** som finns i den vänstra navigeringslisten. Biblioteket innehåller flera spelböcker som har implementerats med Adobe Journey Optimizer. Om du enkelt vill komma åt dem använder du de filter som finns bredvid sökfältet. En omfattande lista över Journey Optimizer spelböcker finns i [Use Case Playbooks-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/use-case-playbooks/playbooks/playbooks-list.html){target="_blank"}.

![Spelningsbokslista med filterruta öppnad](assets/playbooks-filter.png){width="85%"}

När du har valt den spelbok som bäst passar dina behov kan du aktivera den. Detta skapar en instans av spelboken och genererar automatiskt de resurser som behövs för att stödja ditt specifika användningsfall. Resurserna innehåller Journey Optimizer-resurser som resor, meddelanden och Adobe Experience Platform-resurser som scheman eller segment.

>[!NOTE]
>
>Syftet med de här objekten är att hjälpa dig att förstå alla resurser som behövs för att implementera ditt specifika användningsfall. De innehåller inga data och skapas i utvecklingssandlådor.

Om du vill implementera ditt användningssätt kan du navigera till varje objekt för att anpassa det efter dina behov. Du kan också dela URL:en för spelningsbokens instanssida mellan ditt team för att samarbeta vid implementeringen av användningsexemplet.

Dessutom kan du importera spelboksresurser till andra sandlådor. På så sätt kan du justera de genererade resurserna mot dina befintliga resurser och se till att de är kompatibla med dina data, om du redan har konfigurerat dina egna scheman, fält och fältgrupper. De här stegen beskrivs i Använd fallspelningsböcker: [Publicera spelboksgenererade resurser till andra sandlådor](https://experienceleague.adobe.com/docs/experience-platform/use-case-playbooks/playbooks/data-awareness.html){target="_blank"}.

## Skapa egna spelböcker (privat beta) {#create}

>[!AVAILABILITY]
>
>Skapa fallspelsböcker är för närvarande bara tillgängligt för en uppsättning organisationer som en privat beta. Kontakta din Adobe-representant för att få åtkomst.

Förutom att använda fördefinierade spelböcker kan du skapa och dela egna spelböcker i Adobe Experience Platform.

Du kan definiera metadata med hjälp av AI-assistans eller manuell inmatning, associera tekniska resurser som scheman, segment och dela dina spelböcker i olika IMS-organisationer.

Mer information om hur du skapar och delar spelböcker finns i Use Case Playbooks-dokumentationen: [Författare och dela dina egna spelböcker med hjälp av AI Assistant](https://experienceleague.adobe.com/docs/experience-platform/use-case-playbooks/playbooks/author.html#sharing-playbooks-sandboxes){target="_blank"}.
