---
solution: Journey Optimizer
product: journey optimizer
title: Använda Journey Optimizer API:er
description: Journey Optimizer tillhandahåller RESTful-API:er som gör att du programmässigt kan utföra nyckelåtgärder i dina program. Lär dig hur du får åtkomst till och använder dem.
feature: Integrations, Data Ingestion
role: Developer
level: Intermediate
exl-id: 4c897c52-6eb2-4d6e-aaa9-9bd83608b2b6
source-git-commit: e46ab0637a0fa4a2b4b8b6ff3b8ab3eb5d38e0f7
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---

# Arbeta med [!DNL Journey Optimizer] API:er {#apis-gs}

## Snabb åtkomst {#quick-access}

>[!IMPORTANT]
>
>**Kom igång med Journey Optimizer API:er:**
>
>* **[Bläddra i den fullständiga API-referensen](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}** - få tillgång till alla Journey Optimizer API:er och testa dem direkt
>* **[Konfigurera autentisering](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}** - Samla in nödvändiga autentiseringsuppgifter för att börja använda API:erna
>* **[API:er för beslutshantering](../offers/api-reference/getting-started.md)** - Hantera erbjudanden och beslut programmatiskt
>* **[API:er för Experience Decision](../experience-decisioning/api-reference/getting-started.md)** - Hantera beslutsobjekt, urvalsstrategier och berättiganderegler programmatiskt

## Översikt {#overview}

Med Adobe Journey Optimizer API kan ni leverera personaliserade, sammankopplade och aktuella kundupplevelser i alla appar, enheter och kanaler och i sin tur effektivt hantera hela kundresan. Kundresan är hela processen för en kunds interaktioner med ett varumärke, från det första kontaktytan tills kunden går ur. Det börjar med informationsfasen, där kunderna lär sig om varumärket och börjar engagera. Kunden kommer sedan att interagera ytterligare med varumärket, besöka webbplatser online och fysiska, göra inköp, skicka meddelanden eller genomföra granskningar.

Adobe Journey Optimizer bygger på Adobe Experience Platform och kombinerar en enhetlig kundprofil i realtid, ett API-första öppet ramverk, centraliserad definition av erbjudanden samt artificiell intelligens (AI) och maskininlärning (ML) för personalisering och optimering. Genom att integrera med Journey Optimizer API kan varumärken på ett intelligent sätt avgöra vilken interaktion som är bäst när det gäller skala, hastighet och flexibilitet under hela kundresan.

## Autentisering {#authentication}

Innan du använder Journey Optimizer API:er måste du konfigurera autentisering för att komma åt API-slutpunkterna.

Följ [autentiseringsguiden](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} för att samla in de autentiseringsuppgifter som krävs för alla Journey Optimizer API:er.

## API-dokumentation {#api-documentation}

Den fullständiga Adobe Journey Optimizer API-dokumentationen innehåller detaljerad information om alla tillgängliga slutpunkter, förfrågnings-/svarsformat och interaktiva testfunktioner.

Gå till [Adobe Journey Optimizer API-dokumentationen](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"} och bläddra till **API-referenserna** för att utforska alla tillgängliga API:er.

## API:er för beslutshantering {#decision-management-apis}

Journey Optimizer tillhandahåller dedikerade API:er för beslutshantering, så att ni kan programmässigt hantera erbjudanden, beslut och ersättningar.

Se [Utvecklarhandboken för API:t för beslutshantering](../offers/api-reference/getting-started.md) för att komma igång med API:er för erbjudandebeslut.

## API:er för Experience Decision {#experience-decisioning-apis}

Journey Optimizer erbjuder även API:er för Experience Decision för att leverera personaliserade beslutsobjekt via kodbaserade upplevelser. Experience Decision ger en förenklad strategi för personalisering med beslutsunderlag, regler för behörighet och urvalsstrategier.

**Tillgängliga API-åtgärder:**

* **Beslutsobjekt** - Skapa, läsa, uppdatera och ta bort beslutsobjekt
* **Urvalsstrategier** - Definiera hur du väljer och rangordnar beslutsobjekt
* **Kvalifikationsregler** - Ange villkor för berättigande för artikel
* **Objektsamlingar** - Ordna beslutsobjekt i samlingar
* **Rankningsformler** - Konfigurera anpassad rankningslogik
* **Placements** - Definiera var beslutsobjekt kan visas

Läs mer i [API-referens för Experience Decision](../experience-decisioning/api-reference/getting-started.md)
