---
title: Kom igång med beslutsfattande
description: Läs mer om beslutsfattande
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: 4c57dbf9-b2a4-42da-8aa3-5a1b3a475a32
source-git-commit: 5b377982f43902a4549f24c022fa8f4947d896a8
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 0%

---

# Kom igång med beslutsfattande {#get-started-experience-decisioning}

>[!CONTEXTUALHELP]
>id="ajo_email_enable_experience_decisioning"
>title="Vad är det som bestämmer?"
>abstract="Beslutsfattandet är ett nytt verktyg förutom beslutshantering för att välja ut de bästa delarna från beslutsmotorn och leverera till varje enskild person. Det kräver ytterligare inställningar för att kunna använda det."

## Vad är beslut? {#about}

Beslutsfattandet förenklar personaliseringen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas beslutsposter och en avancerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person.

Dessa beslutsobjekt integreras smidigt i ett brett urval av inkommande ytor via den [nya kodbaserade upplevelsekanalen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/code-based-experience/get-started-code-based), som nu är tillgänglig inom Journey Optimizer-kampanjer.

>[!IMPORTANT]
>
>Beslutspolicyer är endast tillgängliga för kodbaserade upplevelsekampanjer.

➡️ Ett heltäckande användningsexempel som visar hur du skapar beslut och använder dem i innehållsexperiment med den kodbaserade upplevelsekanalen visas i [det här avsnittet](experience-decisioning-uc.md).

## Skyddsritningar och begränsningar {#guardrails}

För att säkerställa optimal användning av beslut bör du tänka på följande skyddsförslag och begränsningar:

### Allmänna skyddsräcken {#general}

* **Erbjudandeobjekt**: Varje objektsamling kan innehålla upp till 500 erbjudandeobjekt.
* **Anpassade attribut**: Ett beslutsobjekt kan innehålla maximalt 100 anpassade attribut.
* **Urvalsstrategier och beslutsposter per princip**: En beslutspolicy stöder upp till 10 urvalsstrategier och beslutsposter tillsammans.

### Villkor för deltagande {#eligibility}

* **Kapslingsnivåer**: Kapslingsdjupet är begränsat till 30 nivåer. Detta mäts genom att räkna de `)` avslutande parenteserna i PQL-strängen.
* **Regelsträngsstorlek**: En regelsträng kan vara upp till 15 kB för UTF-8-kodade tecken. Detta motsvarar 15 000 ASCII-tecken (1 byte vardera), eller 3 750-7 500 icke-ASCII-tecken (2-4 byte vardera).

### Rankningsformler {#ranking}

* **Kapslingsnivåer**: Kapslingsdjupet är begränsat till 30 nivåer. Detta mäts genom att räkna de `)` avslutande parenteserna i PQL-strängen.
* **Formelsträngsstorlek**: En regelsträng kan vara upp till 8 kB för UTF-8-kodade tecken. Detta motsvarar 8 000 ASCII-tecken (1 byte vardera), eller 2 000-4 000 icke-ASCII-tecken (2-4 byte vardera).

## Viktiga steg för beslut {#steps}

De viktigaste stegen för att arbeta med beslut är följande:

1. **Tilldela rätt behörigheter**. Beslutsfattandet är endast tillgängligt för användare med tillgång till ett beslutsrelaterat **[!UICONTROL role]**, t.ex. beslutshanterare. Om du inte kan komma åt Beslutsfattandet måste du utöka din behörighet.

   +++Lär dig hur du tilldelar rollen Beslutsledare

   1. Om du vill tilldela en roll till en användare i [!DNL Permissions]-produkten går du till fliken **[!UICONTROL Roles]** och väljer Beslutshanterare.

      ![](assets/decision_permission_1.png)

   1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

      ![](assets/decision_permission_2.png)

   1. Ange användarens namn eller e-postadress eller markera användaren i listan och klicka på **[!UICONTROL Save]**.

      Om användaren inte har skapats tidigare, se [dokumentationen för Lägg till användare](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users).

      ![](assets/decision_permission_3.png)

   Användaren bör sedan få ett e-postmeddelande som omdirigeras till din instans.

+++

1. **Konfigurera anpassade attribut**: Anpassa objektkatalogen efter dina specifika krav genom att konfigurera anpassade attribut i katalogschemat.

   ➡️ [Lär dig konfigurera objektkatalogen](catalogs.md)

1. **Skapa beslutsobjekt** som ska visas för målgruppen.

   ➡️ [Lär dig skapa avgörande objekt](items.md) ([API-dokumentation](api-reference/decisions-items/create.md))

1. **Ordna med samlingar**: Använd samlingar för att kategorisera beslutsobjekt baserat på attributbaserade regler. Införliva samlingar i era urvalsstrategier för att avgöra vilken samling av beslutsobjekt som ska övervägas.

   ➡️ [Lär dig hantera objektsamlingar](collections.md) ([API-dokumentation](api-reference/items-collections/create.md))

1. **Skapa beslutsregler**: Beslutsregler används i beslutsobjekt och/eller urvalsstrategier för att avgöra till vilka ett beslutsobjekt kan visas.

   ➡️ [Lär dig skapa beslutsregler](rules.md)

1. **Implementera rangordningsmetoder**: Skapa rangordningsmetoder och tillämpa dem inom beslutsstrategier för att fastställa prioritetsordningen för val av beslutsobjekt.

   ➡️ [Lär dig hur du skapar rankningsmetoder](ranking.md)

1. **Skapa urvalsstrategier**: Bygg urvalsstrategier som utnyttjar samlingar, beslutsregler och rangordningsmetoder för att identifiera de beslutsobjekt som är lämpliga att visa för profiler.

   ➡️ [Lär dig skapa urvalsstrategier](selection-strategies.md) ([API-dokumentation](api-reference/selection-strategies/create.md))

1. **Skapa en beslutspolicy och bädda in den i din kodbaserade kampanj**: Beslutspolicyer kombinerar flera urvalsstrategier för att bestämma vilka valbara beslutsposter som ska visas för den avsedda målgruppen.

   ➡️ [Lär dig hur du arbetar med beslutsprofiler](create-decision.md)
