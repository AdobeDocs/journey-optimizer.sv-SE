---
title: Rankningsformler
description: Lär dig hur du skapar formler för att rangordna erbjudanden
feature: Ranking, Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: 35d7488b-e7d8-402f-b337-28a0c869bff0
source-git-commit: 86b83f8b368a77ef96581c422f19f35d939e51f4
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 0%

---

# Använda AI-formelverktyget {#create-ranking-formulas}

**Rankningsformler** gör att du kan definiera regler som avgör vilket erbjudande som ska presenteras först, i stället för att ta hänsyn till prioritetspoängen.

Om du vill skapa de här reglerna ger formelverktyget för AI i **[!UICONTROL Adobe Journey Optimizer]** större flexibilitet och kontroll över hur erbjudanden rangordnas. I stället för att förlita dig på en statisk erbjudandeprioritet kan du nu definiera anpassade rankningsformler som kombinerar AI-modellpoäng, erbjudandeprioriteringar, profilattribut, erbjudandeattribut och sammanhangsbaserade signaler via ett guidat gränssnitt.

Med den här metoden kan ni dynamiskt justera offertrankningen baserat på valfri kombination av AI-driven benägenhet, affärsvärde och realtidskontext, vilket gör det enklare att anpassa beslut efter både marknadsföringsmål och kundbehov. AI-formelverktyget har stöd för enkla eller avancerade formler beroende på hur mycket kontroll du vill använda.

När en rankningsformel har skapats kan du tilldela den till en [urvalsstrategi](selection-strategies.md). Om flera erbjudanden kan presenteras när den här urvalsstrategin används, kommer beslutsmotorn att använda den valda formeln för att beräkna vilket erbjudande som ska levereras först.

## Skapa en rankningsformel {#create-ranking-formula}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_formulas"
>title="Skapa rankningsformler"
>abstract="Med formler kan du definiera regler som avgör vilken beslutspost som ska presenteras först, i stället för att ta hänsyn till posternas prioritetspoäng. När en rankningsformel har skapats kan du tilldela den till en urvalsstrategi."

Följ stegen nedan för att skapa en rankningsformel.

1. Gå till menyn **[!UICONTROL Strategy setup]** och välj sedan fliken **[!UICONTROL Ranking formulas]**. Listan med formler som skapats tidigare visas.

   ![](assets/ranking-formulas-list.png)

1. Klicka på **[!UICONTROL Create formula]**.

1. Ange formelnamnet och lägg till en beskrivning om du vill.

   ![](assets/create-formula.png){width="80%"}

1. Du kan också klicka på **[!UICONTROL Select AI model]** för att ange den modell som ska användas som referens för att skapa din rankningsformel.

   >[!NOTE]
   >
   >[Personaliserade optimeringsmodeller](../offers/ranking/personalized-optimization-model.md) som använder kontinuerliga mått stöds inte med formelverktyget för AI.

Varje gång du refererar till en modellpoäng när du definierar formeln nedan används den AI-modell som du valde.

    >[!CAUTION]
    >
    >När du använder en AI-modell som ingår i en rankningsformel, återspeglas inte data i rapporten [Konverteringsgrad för Holdout och Modellstyrd trafik](../reports/campaign-global-report-cja-code.md#conversion-rate).

1. Definiera villkoren som avgör rangordningsgraden för de matchande beslutsobjekten. Du kan antingen

   * fylla i avsnittet **[!UICONTROL Criteria]** från [användargränssnittet](#ranking-select-criteria),
   * eller växla till [kodredigeraren](#ranking-code-editor).

<!--## Select an ELS dataset {#els-dataset}

To leverage data from an AEP dataset, you can select it in the **[!UICONTROL ELS settings]** section.

1. Select an ELS dataset from the list.

1. Select a decision attribute. This action is mandatory.

![](assets/formula-els-settings.png){width="80%"}

-->

## Definiera villkor med formelverktyget {#ranking-select-criteria}

Med ett intuitivt gränssnitt kan du finjustera besluten genom att justera AI-poängen (benägenhet), erbjudandevärdet (prioritet), sammanhangsbaserade hävstångseffekter och egenskaper för externa profiler - individuellt eller i kombination - för att optimera varje interaktion. <!--Whether you're maximizing revenue, promoting strategic offers, or balancing business goals with real-time context, the formula builder gives you total control in defining ranking strategies.-->

Följ stegen nedan för att definiera villkor direkt från gränssnittet.

<!--![](assets/ranking-formula-criteria.png){width="80%"}-->

1. I avsnittet **[!UICONTROL Criterion 1]** anger du vilka beslutsobjekt du vill tillämpa ett rangordningsresultat på genom att göra följande:
   * välj ett [beslutsobjektattribut](items.md#attributes),
   * välja en logisk operator,
   * lägg till ett matchande villkor - du kan antingen ange ett värde eller välja ett profilattribut eller [kontextdata](context-data.md).

   ![](assets/ranking-formula-criterion-1.png){width="70%"}

1. Om du vill kan du ange ytterligare element för att förfina matchningsvillkoren så att villkoren blir sanna.

   ![](assets/ranking-formula-addtional-conditions.png){width="80%"}

   Du har t.ex. definierat kriterium 1, t.ex. det anpassade attributet *Väder* *Lika med* villkoret *varm*. Dessutom kan du lägga till ytterligare ett villkor, till exempel om det första villkoret är uppfyllt och om temperaturen överskrider 75 grader vid tidpunkten för begäran, är villkor 1 sant.<!--Add a screenshot with the example-->

1. Skapa ett uttryck som tilldelar ett rangordningsbetyg till beslutsobjekten som uppfyller villkoret ovan. Du kan referera till något av följande:

   * poängen som kom från AI-modellen som du valfritt valde i **[!UICONTROL Details]** section [above](#create-ranking-formula);
   * beslutsobjektets prioritet, som är ett värde som tilldelas manuellt när [ett beslutsobjekt skapas](items.md#attributes); <!--If a profile qualifies for multiple decision items, a higher priority grants the item precedence over others.-->
   * Alla attribut som kan finnas i profilen, t.ex. eventuella externt härledda benägenhetspoäng.
   * ett statiskt värde som du kan tilldela i ett kostnadsfritt format,
   * en kombination av samtliga ovanstående.

   ![](assets/ranking-formula-expression.png){width="70%"}

   >[!NOTE]
   >
   >Klicka på ikonen bredvid fältet för att lägga till fördefinierade variabler.

1. Klicka på **[!UICONTROL Add criterion]** om du vill lägga till ett eller flera villkor så många gånger som behövs. Logiken är följande:
   * Om det första kriteriet är sant för en viss beslutspost har den företräde framför de nästa.
   * Om det inte är sant, går beslutsmotorn vidare till det andra kriteriet och så vidare.

1. I det sista fältet kan du skapa ett uttryck som tilldelas alla beslutsobjekt som inte uppfyller ovanstående villkor.

   ![](assets/ranking-formula-criteria-not-met.png){width="70%"}

1. Klicka på **[!UICONTROL Create]** för att slutföra din rankningsformel. Du kan nu markera den i listan för att visa information om den och redigera eller ta bort den. Den är klar att användas i en [urvalsstrategi](selection-strategies.md) för att rangordna kvalificerade beslutsartiklar.

### Exempel på rangordningsformel

Se exemplet nedan:

![](assets/ranking-formula-example.png){width="80%"}

Om beslutsobjektets region (anpassat attribut) är lika med profilens geografiska etikett (profilattribut), kommer rankningspoängen som uttrycks här (som är en kombination av beslutsobjektsprioriteten, AI-modellpoängen och ett statiskt värde) att tillämpas på alla beslutsposter som uppfyller det villkoret.

## Använda kodredigeraren {#ranking-code-editor}

Om du vill uttrycka rankningsformler i **PQL-syntax** växlar du till kodredigeraren med den dedikerade knappen längst upp till höger på skärmen. Mer information om hur du använder PQL-syntaxen finns i [dedikerad dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=sv-SE).

>[!CAUTION]
>
>Den här åtgärden förhindrar att du återgår till standardvyn för verktyget för den här formeln.

Du kan sedan utnyttja profilattribut, [kontextdata](context-data.md) och [beslutsobjektattribut](items.md#attributes).

Du vill till exempel prioritera alla erbjudanden med attributet&quot;hot&quot; om vädret är varmt. För att göra detta skickades **contextData.wall=hot** i beslutsanropet. <!--[Learn how to work with context data](context-data.md)-->

![](assets/ranking-formula-code-editor.png){width="80%"}

>[!IMPORTANT]
>
>När du skapar en rankningsformel stöds inte att titta tillbaka till en tidigare tidsperiod, som att lägga till en upplevelsehändelse som inträffade under den sista månaden som en del av formeln. Alla försök att inkludera en uppslagsperiod när formeln skapas kommer att utlösa ett fel när den sparas.

### Exempel på rankningsformel för PQL {#ranking-formula-examples}

Du kan skapa många olika rankningsformler efter behov. Nedan finns några exempel.

+++Boost erbjuder med visst attribut baserat på profilattribut

Om profilen finns i den stad som motsvarar erbjudandet fördubblas prioriteten för alla erbjudanden i den staden.

**Rankningsformel:**

```
if( offer.characteristics.get("city") = homeAddress.city, offer.rank.priority * 2, offer.rank.priority)
```

+++

+++Boost erbjuder där slutdatumet är mindre än 24 timmar nu

**Rankningsformel:**

```
if( offer.selectionConstraint.endDate occurs <= 24 hours after now, offer.rank.priority * 3, offer.rank.priority)
```

+++

+++Boost-erbjudanden baserat på kundernas benägenhet att köpa den produkt som erbjuds

Ni kan höja poängen för ett erbjudande baserat på kundens benägenhetspoäng.

I det här exemplet är instanstenanten *_salesvelocity* och profilschemat innehåller ett intervall med poäng lagrade i en array:

![](../offers/assets/ranking-example-schema.png)

Med detta i åtanke för en profil som:

```
{"_salesvelocity": {"individualScoring": [
                    {"core": {
                            "category":"insurance",
                            "propensityScore": 96.9
                        }},
                    {"core": {
                            "category":"personalLoan",
                            "propensityScore": 45.3
                        }},
                    {"core": {
                            "category":"creditCard",
                            "propensityScore": 78.1
                        }}
                    ]}
}
```

+++

+++Boost erbjuder baserat på kontextdata {#context-data}

Med [!DNL Journey Optimizer] kan du öka vissa erbjudanden baserat på de kontextdata som skickas i anropet. Om till exempel `contextData.weather=hot` skickas måste prioriteten för alla erbjudanden med `attribute=hot` öka. Detaljerad information om hur du skickar kontextdata med API:erna **Edge Decisioning** och **Decisioning** finns i [det här avsnittet](context-data.md)

Observera att när du använder API:t **Decisioning** läggs kontextdata till i profilelementet i begärandetexten, som i exemplet nedan.

```
"xdm:profiles": [
{
    "xdm:identityMap": {
        "crmid": [
            {
            "xdm:id": "CRMID1"
            }
        ]
    },
    "xdm:contextData": [
        {
            "@type":"_xdm.context.additionalParameters;version=1",
            "xdm:data":{
                "xdm:weather":"hot"
            }
        }
    ]
    
}],
```

+++

