---
title: Skapa urvalsstrategier
description: Lär dig hur du skapar urvalsstrategier
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
source-git-commit: 69a2ef17b6f5ccd40c08858f7b434029964d544d
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 1%

---

# Skapa urvalsstrategier {#selection-strategies}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsobjekt
   * [Konfigurera objektkatalogen](catalogs.md)
   * [Skapa beslutsobjekt](items.md)
   * [Hantera artikelsamlingar](collections.md)
* Konfigurera val av objekt
   * [Skapa beslutsregler](rules.md)
   * [Skapa rangordningsmetoder](ranking.md)
* **[Skapa urvalsstrategier](selection-strategies.md)**
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

En urvalsstrategi är en återanvändbar artikel, som består av en samling som är kopplad till en kvalificeringsbegränsning och en rangordningsmetod för att avgöra vilka erbjudanden som ska visas när de väljs ut i en [beslutspolitik](create-decision.md).

## Få tillgång till och hantera urvalsstrategier

1. Gå till **[!UICONTROL Experience Decisioning]** > **[!UICONTROL Configuration]** > **[!UICONTROL Selection strategies]**.

1. Alla markeringsstrategier som har skapats hittills visas. Det finns filter som hjälper dig att hämta strategier enligt rangordningsmetoden.

   ![](assets/strategy-list-filters.png)

1. Klicka på ett markeringsstrateginamn om du vill redigera det.

1. Samlingen, rangordningsmetoden och behörighetskraven som valts för varje strategi visas också. Du kan klicka på ikonen bredvid varje samlingsnamn om du vill redigera en samling direkt.

   ![](assets/strategy-list-edit-collection.png)

## Skapa en urvalsstrategi

Följ stegen nedan för att skapa en urvalsstrategi.

1. Från **[!UICONTROL Selection strategies]** lager, klicka **[!UICONTROL Create selection strategy]**.

   ![](assets/strategy-create-button.png)

1. Lägg till ett namn för strategin.

   >[!NOTE]
   >
   >För närvarande är det bara standardinställningen **[!UICONTROL Offers]** katalogen är tillgänglig.

1. Fyll i informationen för din urvalsstrategi med början av namnet.

   ![](assets/strategy-create-screen.png)

1. Välj erbjudandet [samling](collections.md) som innehåller de erbjudanden som ska övervägas.

1. Använd **[!UICONTROL Eligibility]** fält för att begränsa urvalet av erbjudanden för den här urvalsstrategin.

   ![](assets/strategy-create-eligibility.png)

   * Om du vill begränsa urvalet av erbjudanden till medlemmarna i en Experience Platform-målgrupp väljer du **[!UICONTROL Audiences]** och välj en målgrupp i listan. [Lär dig hur du arbetar med målgrupper](../audience/about-audiences.md)

   * Om du vill lägga till en markeringsbegränsning med en beslutsregel använder du **[!UICONTROL Decision rule]** och välj önskad regel. [Lär dig skapa en regel](rules.md)

1. Definiera den rangordningsmetod som du vill använda för att välja det bästa erbjudandet för varje profil. [Läs mer](#select-ranking-method)

   ![](assets/strategy-create-ranking.png)

   * Om flera erbjudanden är berättigade för den här strategin är [Prioritet](#offer-priority) -metoden använder det värde som definieras i erbjudandena.

   * Om du vill använda en viss beräknad poäng för att välja vilket erbjudande du vill leverera väljer du [Formel](#ranking-formula) eller [AI-modell](#ai-ranking).

1. Klicka på **[!UICONTROL Create]**. Den är nu klar att användas i en [beslut](create-decision.md)

## Välj en rangordningsmetod {#select-ranking-method}

Om flera erbjudanden är berättigade till en viss urvalsstrategi kan du välja den metod som ska användas för att välja det bästa erbjudandet för varje profil när du skapar en urvalsstrategi. Du kan rangordna erbjudanden genom att:

* [Prioritet](#offer-priority)
* [Formel](#ranking-formula)
* [AI-rankning](#ai-ranking)

### Prioritet {#offer-priority}

När flera erbjudanden kan komma i fråga för en viss placering i ett beslut är de som har högst **prioritet** kommer att levereras till kunderna först.

![](assets/item-priority.png)

Prioritetspoäng för erbjudanden tilldelas när en [beslutsobjekt](items.md).

### Rankningsformel {#ranking-formula}

Förutom att ge prioritet kan du med Journey Optimizer skapa **rankningsformler**. Detta är formler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att beakta offertens prioritetspoäng.

Du kan till exempel öka prioriteten för alla erbjudanden där slutdatumet är mindre än 24 timmar från och med nu, eller öka erbjudandena från kategorin&quot;löpande&quot; om profilens intressepunkt är&quot;igång&quot;. Lär dig skapa en rankningsformel i [det här avsnittet](ranking.md).

När du har skapat den kan du använda den här formeln i en urvalsstrategi. Om flera erbjudanden kan presenteras när den här urvalsstrategin används kommer den valda formeln att användas för att beräkna vilket erbjudande som ska levereras först.

### AI-rankning {#ai-ranking}

Du kan också använda ett utbildat modellsystem som automatiskt rangordnar erbjudanden för en viss profil genom att välja en AI-modell. Lär dig skapa en AI-modell i [det här avsnittet](ranking.md).

När en AI-modell har skapats kan du använda den i en urvalsstrategi. Om flera erbjudanden är berättigade avgör det tränade modellsystemet vilket erbjudande som ska presenteras först för denna urvalsstrategi.
