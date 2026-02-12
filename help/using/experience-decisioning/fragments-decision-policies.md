---
title: Utnyttja fragment i beslutspolicyer
description: Lär dig utnyttja fragment i beslutsregler
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: 70f64348-092b-4350-91dc-72c3c07300f9
source-git-commit: b414d330a25a98c11b7417beda4536c54c41fd83
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Utnyttja fragment i beslutspolicyer {#fragments}

Om din beslutspolicy innehåller beslutsposter, inklusive fragment, kan du utnyttja dessa fragment i beslutspolicykoden. [Läs mer om fragment](../content-management/fragments.md)

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande bara tillgänglig för **kodbaserad upplevelse** -kanalen.

Anta till exempel att du vill visa olika innehåll för flera mobila enhetsmodeller. Se till att du har lagt till fragment som motsvarar de enheterna i beslutsposten som du använder i beslutspolicyn. [Lär dig hur](items.md#attributes).

![](assets/item-fragments.png){width=70%}

När du är klar kan du använda någon av följande metoder:

>[!BEGINTABS]

>[!TAB Infoga koden direkt]

Kopiera och klistra in kodblocket nedan i beslutspolicykoden. Ersätt `variable` med fragment-ID och `placement` med fragmentreferensnyckeln:

```
{% let variable =  get(item._experience.decisioning.offeritem.contentReferencesMap, "placement").id %}
{{fragment id = variable}}
```

>[!TAB Följ de detaljerade stegen]

1. Navigera till **[!UICONTROL Helper functions]** och lägg till funktionen **&#x200B;**&#x200B;`{% let variable = expression %} {{variable}}` i kodfönstret, där du kan deklarera variabeln för fragmentet.

   ![](assets/decision-let-function.png)

1. Använd funktionen **Karta** > **Hämta** `{%= get(map, string) %}` för att skapa ditt uttryck. Kartan är det fragment som beslutsobjektet refererar till och strängen kan vara den enhetsmodell som du angav i beslutsobjektet som **[!UICONTROL Fragment reference key]**.

   ![](assets/decision-map-function.png)

1. Du kan också använda ett kontextuellt attribut som skulle innehålla detta enhetsmodell-ID.

   ![](assets/decision-contextual-attribute.png)

1. Lägg till variabeln som du valde för fragmentet som fragment-ID.

   ![](assets/decision-fragment-id.png)

>[!ENDTABS]

Fragment-ID och referensnyckel väljs från beslutsobjektets **[!UICONTROL Fragments]**-avsnitt.

>[!WARNING]
>
>Om fragmentnyckeln är felaktig eller om fragmentinnehållet inte är giltigt, kommer återgivningen att misslyckas och orsaka fel i Edge-anropet.

## Stödlinjer när fragment används {#fragments-guardrails}

**Beslutsobjekt och kontextattribut**

Attribut för beslutsobjekt och kontextalattribut stöds inte som standard i [!DNL Journey Optimizer]-fragment. Du kan emellertid använda globala variabler i stället, som beskrivs nedan.

Säg att du vill använda variabeln *sport* i ditt fragment.

1. Referera den här variabeln i fragmentet, till exempel:

   ```
   Elevate your practice with new {{sport}} gear!
   ```

1. Definiera variabeln med funktionen **Let** i beslutsprincipblocket. I exemplet nedan definieras *sport* med attributet för beslutsobjekt:

   ```
   {#each decisionPolicy.13e1d23d-b8a7-4f71-a32e-d833c51361e0.items as |item|}}
   {% let sport = item._cjmstage.value %}
   {{fragment id = get(item._experience.decisioning.offeritem.contentReferencesMap, "placement1").id }}
   {{/each}}
   ```

**Innehållsvalidering av beslutsfragment**

* På grund av dessa fragment, när de används i en kampanj, hoppas meddelandevalideringen under skapandet av kampanjinnehåll över för fragment som refereras i beslutsobjekt.

* Valideringen av fragmentinnehållet sker bara när fragmenten skapas och publiceras.

* För uttrycksfragment av JSON-typ valideras innehållet syntaktiskt när fragmentet sparas. Valideringsfel visas som varningar.

Vid körning valideras kampanjinnehållet (inklusive fragmentinnehåll från beslutsobjekt). Om valideringen misslyckas återges inte kampanjen.
