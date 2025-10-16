---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer
description: Upptäck de viktigaste funktionerna och användningsområdena i Adobe Journey Optimizer
feature: Get Started
topic: Content Management
role: User
level: Beginner
exl-id: 956178c0-9985-4ff8-a29e-17dd367ce4d4
source-git-commit: 6c73a1ee024ca61b30d71e77268e51b93576ae62
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Kom igång med Journey Optimizer {#cjm-gs}

## Vad är [!DNL Adobe Journey Optimizer]?{#about-cjm}

[!DNL Adobe Journey Optimizer] hjälper företag att leverera sammankopplade, kontextuella och personaliserade upplevelser till sina kunder. Kundresan är hela processen för en kunds interaktioner med varumärket, från det första kontaktytan tills kunden går ur. Det börjar med informationsfasen, där kunderna lär sig om varumärket och börjar engagera. Kunden kommer sedan att interagera ytterligare med varumärket, besöka webbplatser online och fysiska webbplatser samt göra inköp, skicka meddelanden eller genomföra granskningar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och kombinerar en enhetlig kundprofil i realtid, ett API-första öppet ramverk, centraliserat beslut om erbjudanden samt artificiell intelligens (AI) och maskininlärning (ML) för personalisering och optimering. Med Journey Optimizer kan varumärken på ett intelligent sätt avgöra nästa bästa interaktion med skala, hastighet och flexibilitet under hela kundresan. Med [!DNL Adobe Journey Optimizer] kan företag skapa och leverera både schemalagda marknadsföringskampanjer (till exempel veckokampanjer för en butik) och skräddarsydd individuell kommunikation (till exempel ett push-meddelande för en artikel som en lojalitetsappkund kan ha tittat på som tidigare var ur lager) inom samma program.

➡️ [Upptäck Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/introduction-to-journey-optimizer/introduction.html?lang=sv-SE){target="_blank"} (video)


<!-- Use [!DNL Adobe Journey Optimizer] to build multi-step customer journeys that initiate a sequence of interactions, offers, and messages across channels in real time. This approach ensures customers are engaged at the optimal moments based on their actions and relevant business signals. Learn how to build journeys in [this section](../building-journeys/journey-gs.md).

You can also create audience-based campaigns to send messages.-->


## Användningsfall {#use-cases}

* Marknadsförarna kan använda [!DNL Adobe Journey Optimizer] för att skicka både individanpassad kommunikation och målgruppsbaserad gruppkommunikation. En klädbutik skickar till exempel vanligen enkäter till alla kunder som köpt produkter den senaste veckan. På grund av infallsvädret försenades några leveranser. När man ser vilka kunder som inte har fått leveranser kan klädbutiken utesluta dem från den schemalagda kundnöjdheten och istället skicka ett personligt mejl med en ursäkt för fördröjningen och erbjuda en rabattkod med produktrekommendationer som baseras på kundens tidigare inköp.

  Marknadsförarna kan också använda programmet för att skicka beteendebaserad kommunikation i realtid. Samma återförsäljare skulle till exempel kunna engagera en lojal kund som i realtid tar sig in på parkeringsplatsen genom att skicka ett push-meddelande till dem om en tröja som finns i lager i kundens storlek.

* Icke-marknadsförare som verksamhetsteam och kundsupport som är engagerade i kundupplevelsen kan använda [!DNL Adobe Journey Optimizer] för att hantera en mängd olika uppgifter, till exempel operativa meddelanden eller till och med för att övervaka introduktionsprocessen. Exempel: en nöjespark där parkbesökare laddar ned en mobilapp som en del av sin parkupplevelse. Underhållspersonalen kan använda [!DNL Adobe Journey Optimizer] för att meddela parkeringsbesökare om de platser som för närvarande är stängda på grund av underhåll.

## Viktiga funktioner {#key-capabilities}

[!DNL Adobe Journey Optimizer] är en flexibel och skalbar applikation för att skapa och leverera personaliserade, sammankopplade och vältajmade kundupplevelser för alla appar, enheter och kanaler.

![](assets/ajo-capabilities.png)

Viktiga funktioner:

* **Kundinsikter och engagemang i realtid** - En integrerad profil sammanfogar livedata från alla källor över kundkontaktytor, inklusive beteendedata, transaktionsdata, ekonomiska data och driftdata för att optimera personliga och sammanhangsbaserade upplevelser för kunderna i deras tid.

* **Modern flerkanalsmarknadsföring och -körning** - en enda arbetsyta där kundresan ska harmoniseras och optimeras för :1 kundinteraktion och marknadsföringsutåtriktad marknadsföring - för att hjälpa varumärken att leverera mer värde under hela kundlivscykeln. Kundresor som utformats i [!DNL Adobe Journey Optimizer] kan vara dynamiska och händelsebaserade för att hjälpa varumärken att reagera på realtidssignaler och koppla dessa interaktioner till schemalagda kampanjer så att rätt beslut kan fattas om vilken kommunikation som ska skickas till en kund, när och via vilka kanaler.

* **Intelligent Decision &amp; Personalization** - Varumärken kan tillämpa centraliserad beslutsfattande och införliva artificiell intelligens och maskininlärning för att konfigurera prediktiva insikter i hela kundupplevelsen, vilket gör det enklare att automatisera beslut och optimera upplevelsen i stor skala. Beslutsfattandet driver centraliserade erbjudanden över flera kanaler i stor skala genom [!DNL Adobe Journey Optimizer].


>[!NOTE]
>
>* Vilka komponenter och funktioner som är tillgängliga i din miljö beror på dina [behörigheter](../administration/permissions.md) och ditt [licenspaket](https://helpx.adobe.com/se/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}. Fråga din Adobe Customer Success Manager eller din Adobe-representant om du har några frågor.
>
>* Adobe Experience Cloud allmänna riktlinjer och procedurer för sekretess gäller för [!DNL Journey Optimizer]. [Läs mer om Adobe Experience Cloud sekretess](https://www.adobe.com/privacy/experience-cloud.html){target="_blank"}.


## Arkitektur {#architecture}

Förstå den grundläggande arkitekturen för [!DNL Adobe Journey Optimizer], integreringspunkten och relationen mellan [!DNL Journey Optimizer] och [!DNL Experience Platform] i diagrammet nedan.

Adobe Experience Platform är en kraftfull, flexibel, öppen och centraliserad databund som samlar in, standardiserar, styr, tillämpar AI-insikter på och sammanför data för att erbjuda genomtänkta och relevanta digitala kundupplevelser.

![](assets/ajo-aep-architecture-diagram.png){width="70%" zoomable="yes"}

Fyra program är inbyggda i Experience Platform: Adobe Real-Time Customer Data Platform, Journey Optimizer, Customer Journey Analytics och Adobe Mix Modeler.

Journey Optimizer basfunktioner och tjänster bygger på grundkomponenterna i Adobe Experience Platform, som innehåller kundprofilen i realtid. Journey Optimizer fungerar smidigt och samverkar med CDP och Customer Journey Analytics i realtid, men kan också fungera fristående som fristående program.

![](assets/ajo-architecture-diagram.png){width="70%" zoomable="yes"}


### Adobe Journey Optimizer Blueprints

Med digitala upplevelseutkast får du diagram över system- och dataflödesarkitektur som hjälper dig att bättre förstå hur Adobe Experience Platform och program integreras och implementeras. Planerna ger en visuell representation av data- och innehållsflöden mellan system och komponenter, sekvenser av operationer och beroenden som kan vara till hjälp vid utformningen av användningsfall och arkitekturen för Adobe Experience Platform och tillämpningar.

Se [Adobe Journey Optimizer-utkast](https://experienceleague.adobe.com/sv/docs/blueprints-learn/architecture/customer-journeys/journey-optimizer/journey-optimizer-overview){target="_blank"}.


>[!MORELIKETHIS]
>
>* [Viktiga steg att starta](quick-start.md)
>* [Designa resor och skicka meddelanden](../building-journeys/journey-gs.md)
>* [Live-rapporter](../reports/live-report.md)
>* [Journey Optimizer - säkerhetsöversikt](https://www.adobe.com/content/dam/cc/en/security/pdfs/AJO_SecurityOverview.pdf) (PDF)
>* [Journey Optimizer produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.htm){target="_blank"}
