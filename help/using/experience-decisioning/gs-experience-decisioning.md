---
title: Kom igång med beslutsfattande
description: Läs mer om beslutsfattande
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: 4c57dbf9-b2a4-42da-8aa3-5a1b3a475a32
version: Journey Orchestration
source-git-commit: 9ac3eaba0b4c6536c1c447df825eb5f5c0afc900
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 4%

---

# Kom igång med beslutsfattande {#get-started-experience-decisioning}

>[!CONTEXTUALHELP]
>id="ajo_email_enable_experience_decisioning"
>title="Vad är det som bestämmer?"
>abstract="Beslutsfattandet är ett nytt verktyg förutom beslutshantering för att välja ut de bästa delarna från beslutsmotorn och leverera till varje enskild person. Det kräver ytterligare inställningar för att kunna använda det."

## Vad är beslut? {#about}

Beslutsfattandet förenklar personanpassningen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas Beslutsposter och en avancerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person.

Dessa beslutsobjekt är sömlöst integrerade i ett brett urval av inkommande ytor via den [kodbaserade upplevelsekanalen](../code-based/get-started-code-based.md), som är tillgänglig inom [!DNL Adobe Journey Optimizer]-kampanjer.

>[!IMPORTANT]
>
>Beslutsprinciper är tillgängliga för kodbaserad upplevelse och e-postkampanjer.

➡️ [Upptäck den här funktionen i en video](#video)

➡️ Ett heltäckande användningsexempel som visar hur du skapar beslut och använder dem i innehållsexperiment med den kodbaserade upplevelsekanalen visas i [det här avsnittet](experience-decisioning-uc.md).

## Viktiga steg för beslut {#steps}

De viktigaste stegen för att arbeta med beslut är följande:

1. **Tilldela rätt behörigheter**. Beslutsfattandet är endast tillgängligt för användare med tillgång till ett beslutsrelaterat **[!UICONTROL role]**, t.ex. beslutshanterare. Om du inte kan komma åt Beslutsfattandet måste du utöka din behörighet.

   +++Lär dig hur du tilldelar rollen Beslutsledare

   1. Om du vill tilldela en roll till en användare i [!DNL Permissions]-produkten går du till fliken **[!UICONTROL Roles]** och väljer Beslutshanterare.

      ![](assets/decision_permission_1.png)

   1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

      ![](assets/decision_permission_2.png)

   1. Ange användarens namn eller e-postadress eller välj användaren i listan och klicka på **[!UICONTROL Save]**.

      Om användaren inte har skapats tidigare, se [dokumentationen för Lägg till användare](https://experienceleague.adobe.com/sv/docs/experience-platform/access-control/ui/users).

      ![](assets/decision_permission_3.png)

   Användaren bör sedan få ett e-postmeddelande som omdirigeras till din instans.

   +++

1. **Konfigurera anpassade attribut**: Anpassa objektkatalogen efter dina specifika krav genom att konfigurera anpassade attribut i katalogschemat.

   ➡️ [Lär dig konfigurera objektkatalogen](catalogs.md)

1. **Skapa beslutsobjekt** som ska visas för målgruppen.

   ➡️ [Lär dig skapa beslutsobjekt](items.md) i användargränssnittet (och i [API-dokumentationen](api-reference/decisions-items/create.md))

1. **Ordna med samlingar**: Använd samlingar för att kategorisera beslutsobjekt baserat på attributbaserade regler. Införliva samlingar i era urvalsstrategier för att avgöra vilken samling av beslutsobjekt som ska övervägas.

   ➡️ [Lär dig hantera objektsamlingar](collections.md) i användargränssnittet (och i [API-dokumentationen](api-reference/items-collections/create.md))

1. **Skapa beslutsregler**: Beslutsregler används i beslutsobjekt och/eller urvalsstrategier för att avgöra till vilka ett beslutsobjekt kan visas.

   ➡️ [Lär dig skapa beslutsregler](rules.md)

1. **Implementera rangordningsmetoder**: Skapa rangordningsmetoder och tillämpa dem inom urvalsstrategier för att fastställa prioritetsordningen för val av beslutsobjekt.

   ➡️ [Lär dig hur du skapar rankningsmetoder](ranking/ranking.md)

1. **Skapa urvalsstrategier**: Bygg urvalsstrategier som utnyttjar samlingar, beslutsregler och rangordningsmetoder för att identifiera de beslutsobjekt som är lämpliga att visa för profiler.

   ➡️ [Lär dig skapa urvalsstrategier i användargränssnittet](selection-strategies.md) i användargränssnittet (och i [API-dokumentationen](api-reference/selection-strategies/create.md))

1. **Skapa en beslutspolicy och bädda in den i din kodbaserade eller e-postbaserade resa/kampanj**: Beslutspolicyer kombinerar flera urvalsstrategier för att bestämma vilka valbara beslutsposter som ska visas för den avsedda målgruppen.

   ➡️ [Lär dig hur du arbetar med beslutsprofiler](create-decision.md)
➡️ Följ implementeringsstegen i [det här avsnittet](../code-based/code-based-implementation-samples.md) för att leverera erbjudandet via den kodbaserade upplevelsekanalen.

## Ytterligare resurser

* **[Skapa beslutsobjekt](items.md)** - Lär dig hur du skapar och hanterar beslutsobjekt, inklusive erbjudanden, innehållsvariationer och upplevelser.
* **[Konfigurera beslutskataloger](catalogs.md)** - Lär dig hur du organiserar beslutsobjekt i kataloger för bättre hantering.
* **[Definiera urvalsstrategier](selection-strategies.md)** - Upptäck hur du skapar urvalsstrategier med berättiganderegler och rangordningsmetoder.
* **[Skapa beslutspolicyer](create-decision-policy.md)** - Lär dig hur du skapar beslutspolicyer som kombinerar strategier och begränsningar.
* **[Ranknings- och AI-modeller](ranking/ranking.md)** - Huvudrankningsformler och AI-modeller för personaliserade beslut.
* **[Migrera från beslutshantering](migrate-to-decisioning.md)** - Förstå fördelarna med att migrera till API:er för beslutsfattande och användning av migreringsverktyg.
* **[Beslutsfattarskyddsutkast](decisioning-guardrails.md)** - Granska viktiga begränsningar och bästa praxis för att fatta beslut om implementering.
* **[Självstudiekurser för beslutsfattande](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/decision-capabilities/decisioning/introduction-to-decisioning){target="_blank"}** - Utforska steg-för-steg-videokurser om beslutsfunktioner och metodtips.

## Instruktionsvideo {#video}

Läs mer om beslutsfunktionerna i Adobe Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/3475867?captions=swe&quality=12)
