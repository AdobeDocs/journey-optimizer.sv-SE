---
title: Skiljedomsrutiner för resor
description: Lär dig hur du skapar formler för att rangordna resor för medling, så att den bästa resan väljs per profil baserat på regler och sammanhang.
feature: Journeys, Decisioning
role: User
level: Intermediate
version: Journey Orchestration
badge: label="Begränsad tillgänglighet" type="Informative"
source-git-commit: fe6e8221201ee813251a46c6603d85f0803873c0
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 0%

---

# Använd formler för att rangordna resor {#journey-ranking-formulas}

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande begränsad. Kontakta din Adobe-representant för att få åtkomst.

[!DNL Adobe Journey Optimizer] hjälper dig att kontrollera vilka resor en profil kan registrera när de kvalificerar sig för mer än vad systemet tillåter. Om du vill göra det kan du använda [regeluppsättningar](rule-sets.md) för att definiera ändpunkter för resepost eller samtidighet. När en profil är berättigad till fler resor än vad som är tillåtet enligt begränsningen, avgör prioriteringen för varje resa vilka resor som väljs.

I stället för att använda prioritet kan du använda **rankningsformler** för att dynamiskt justera rankningen av resor baserat på reseattribut, profilattribut eller AI-modellpoäng.

Formler ger större flexibilitet än statisk prioritet. Du kan till exempel öka kundresan för guldkunder.

<!--
>[!NOTE]
>
>Journey ranking formulas follow the same guardrails as decisioning ranking formulas (nesting depth, rule string size). [Learn more about Decisioning guardrails & limitations](../experience-decisioning/decisioning-guardrails.md#ranking-formulas).-->

## Skapa en rankningsformel {#create-journey-ranking-formula}

Följ stegen nedan för att skapa en rankningsformel för dina resor.

1. Gå till avsnittet **[!UICONTROL Orchestration ranking]** och välj sedan fliken **[!UICONTROL Ranking formulas]**. Listan med formler som skapats tidigare visas.

1. Klicka på **[!UICONTROL Create formula]**.

1. Ange formelnamnet och lägg till en beskrivning om du vill.

   ![Rutan med information om formel med namn och beskrivning](assets/journey-formula-details.png){width="80%"}


   >[!NOTE]
   >
   >Rankningsobjektet är den enhet som rankningsformeln gäller för. Som standard är rankningsobjektet inställt på **[!UICONTROL Journey]**.

   <!--
    Selecting a formula entity specifies which type of item—such as journeys or other entities—the ranking formula will apply to. This determines the context in which the formula operates, allowing you to define rules that influence how those items are ranked.-->

1. Du kan också klicka på **[!UICONTROL Select AI model]** för att ange den modell som ska användas som referens för att skapa din rankningsformel.

<!--
    >[!NOTE]
    >
    >[Personalized optimization models](../experience-decisioning/ranking/personalized-optimization-model.md) using continuous metrics are not supported with the AI formula builder.

    Every time you refer to a model score when defining your formula below, the AI model that you selected will be used. [Learn more on AI models](../experience-decisioning/ranking/ai-models.md)-->

1. I avsnittet **[!UICONTROL Criterion 1]** anger du vilka resor du vill tillämpa ett rangordningsresultat på genom att göra följande:

   * Välj ett [reseattribut](../building-journeys/journey-properties.md) (t.ex. resenamn, taggar, prioritet eller andra reseegenskaper);
   * välja en logisk operator,
   * lägg till ett matchande villkor - du kan antingen skriva/välja ett värde eller välja ett profilattribut.

   ![Kriterium 1-avsnitt med reseattribut, operator och matchande villkor](assets/journey-formula-criterion-1.png){width="70%"}

1. Om du vill kan du ange ytterligare element för att förfina matchningsvillkoren så att villkoren blir sanna.

   ![Ytterligare villkor för att förfina matchningsvillkor](assets/journey-formula-additional-condition.png){width="70%"}

   Du har till exempel definierat *Villkor 1*, som *Resenstaggar* innehåller *Lojalitet*. Dessutom kan du lägga till ett annat villkor, till exempel om *lojalitetsstatusen* är lika med *Gold*, då är *Villkor 1* sant.

1. Skapa ett uttryck som tilldelar en rankningspoäng till de resor som uppfyller det villkor som definieras ovan. Du kan referera till något av följande:
   * en variabel:
      * reseprioritet, som är ett manuellt värde som tilldelas resan när [en resa skapas](../building-journeys/journey-gs.md);
      * bakgrundsmusik som kommer från den AI-modell som du valde ovan,
   * ett attribut:
      * Alla attribut som kan finnas i profilen, t.ex. eventuella externt härledda benägenhetspoäng.
      * ett reseattribut,
   * ett statiskt värde som du kan tilldela i ett kostnadsfritt format,
   * en kombination av allt ovanstående.

   ![Expression Builder för att tilldela rankningspoäng med hjälp av variabler, attribut eller statiska värden](assets/journey-formula-expression.png){width="70%"}

1. Klicka på **[!UICONTROL Add criterion]** om du vill lägga till ett eller flera villkor så många gånger som behövs. Logiken är följande:
   * Om det första kriteriet är sant för en viss beslutspost har den företräde framför de nästa.
   * Om det inte är sant, går beslutsmotorn vidare till det andra kriteriet och så vidare.

1. När du har definierat alla villkor kan du i det sista fältet skapa ett uttryck som tilldelas alla resor som inte uppfyller kriterierna ovan.

   ![Uttrycksfält för resor som inte uppfyller några villkor](assets/journey-formula-criteria-not-met.png){width="70%"}

1. Klicka på **[!UICONTROL Create]** för att slutföra din rankningsformel.

Du kan nu välja den här formeln från listan för att visa information om den och redigera eller ta bort den. Den är sedan tillgänglig när du konfigurerar en regeluppsättning. [Lär dig hur](#assign-formula-to-ruleset)

### Exempel på rankningsformler {#journey-ranking-formula-example}

Titta på exemplen nedan.

+++Exempel 1: Använd reseprioritet eller AI-poäng baserat på resemärken

![Rankningsformel: Marknadstaggen använder reseprioritet](assets/journey-formula-ex-1.png){width="60%"}

Om resan har en&quot;Marketing&quot;-tagg är prioriteringen av resan.

![Rankningsformel: Promo-taggen använder AI-modellpoäng](assets/journey-formula-ex-2.png){width="60%"}

Om resan har en Promo-tagg är rankningspoängen AI-modellpoängen.

+++

+++Exempel 2: Öka lojalitetsresorna efter profilstatus


![Rankningsformel: Lojalitetstaggen med guldstatus använder reseprioritet plus 5](assets/journey-formula-ex-3.png){width="60%"}

Om resan har en&quot;Loyalty&quot;-tagg och profilens lojalitetsstatus är Gold, är den rangordning som används reseprioriteten plus 5.

![Rankningsformel: Lojalitetstaggen med Silver-status använder reseprioritet plus 2](assets/journey-formula-ex-4.png){width="60%"}

Om resan har en Loyalty-tagg och profilens lojalitetsstatus är Silver är rangordningspoängen reseprioriteten plus 2.

Om inget av de ovanstående villkoren uppfylls, är den rangordning som används reseprioriteten.

+++

### Använda kodredigeraren {#journey-ranking-formula-code-editor}

Om du vill uttrycka rankningsformler i **PQL-syntax** växlar du till kodredigeraren med den dedikerade knappen längst upp till höger på skärmen. Mer information om hur du använder PQL-syntaxen finns i [dedikerad dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=sv-SE).

>[!CAUTION]
>
>Den här åtgärden förhindrar att du återgår till standardvyn för verktyget för den här formeln.

Du kan sedan använda attribut för resan, profilattribut och statiska värden för att skapa din rankningsformel.

<!--The code editor is similar to the one used in Decisioning ranking formulas. [Learn more](../experience-decisioning/ranking/ranking-formulas.md#ranking-code-editor)-->

## Tilldela formeln till en regeluppsättning {#assign-formula-to-ruleset}

Om du vill använda en formel för att rangordna dina resor måste du tilldela den till en regeluppsättning.

>[!NOTE]
>
>Formler tilldelas på regeluppsättningsnivå, inte på enskilda resor.

1. På menyn **[!UICONTROL Business rules]** skapar du en regeluppsättning som du vill använda för skiljeväggar för resan. [Lär dig hur](rule-sets.md#Create)

1. Se till att du väljer domänen **[!UICONTROL Journey]**.

   ![Regeluppsättningsegenskaper med resedomän vald](assets/journey-formula-rule-set-journey.png){width="60%"}

1. I regeluppsättningsegenskaperna anger du **[!UICONTROL Ranking method]** till **[!UICONTROL Formula]** (i stället för standardvärdet **[!UICONTROL Priority]**).

1. Välj den rankningsformel som du skapade i listrutan.

   ![Regeluppsättning med rangordningsformel vald från nedrullningsbar lista](assets/journey-rule-set-formula.png){width="60%"}

1. Skapa de regler för capping för resan som du vill lägga till i regeluppsättningen. [Lär dig hur](journey-capping.md#create-rule)

1. Spara regeluppsättningen.

Nu tilldelas formeln till regeluppsättningen. Du kan sedan tillämpa den regeln på dina resor.

## Använd regeluppsättningen på en resa {#assign-rule-set-to-journey}

Följ stegen nedan för att tilldela regeluppsättningen till en resa.

1. Skapa eller öppna den resa som du vill tilldela regeluppsättningen till. [Lär dig skapa en resa](../building-journeys/journey-gs.md)

1. Välj regeluppsättningen i listrutan i reseegenskaperna.  [Lär dig hur](journey-capping.md#apply-capping).

   >[!NOTE]
   >
   >Endast en regeluppsättning i taget kan användas på en resa.

1. Spara resan.

Alla resor som använder den här regeluppsättningen kommer att rangordnas med den valda formeln när taket tillämpas.

Om du vill övervaka hur regler och rankningsformler fungerar läser du avsnittet [Resebegränsning och konflikter](../reports/channel-report-cja.md#rule-sets) i översiktsrapporten.

<!--
## Reporting {#reporting}

Reporting for journey arbitration helps you understand how rule sets and ranking formulas perform:

* **Exclusions** – Whether journeys were excluded from users and which rule set (and reason) prevented entry.
* **Rule set performance** – For each rule set, metrics such as journey enters, journey exclusions, journey engagement, and other optimization metrics.
* **Cross-journey view** – Time-based view of profiles across journeys (e.g. journey enters, failures, exclusions) to see the impact of capping and ranking.

Use these reports to validate that your formulas and caps are behaving as intended and to tune ranking logic over time.-->

