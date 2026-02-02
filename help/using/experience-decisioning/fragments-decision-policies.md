---
title: Utnyttja fragment i beslutspolicyer
description: Lär dig utnyttja fragment i beslutsregler
feature: Decisioning
topic: Integrations
role: User
level: Experienced
source-git-commit: 083545ff7b2dc5ce45ef3766321fdf12e1b96c5c
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 1%

---


# Utnyttja fragment i beslutspolicyer {#fragments}

Om din beslutspolicy innehåller beslutsposter, inklusive fragment, kan du utnyttja dessa fragment i beslutspolicykoden. [Läs mer om fragment](../content-management/fragments.md)

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande endast tillgänglig för **kodbaserad upplevelse** och för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill veta mer.

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

1. Navigera till **[!UICONTROL Helper functions]** och lägg till funktionen **** `{% let variable = expression %} {{variable}}` i kodfönstret, där du kan deklarera variabeln för fragmentet.

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

* För JSON-fragment är JSON-objektets giltighet inte säkerställd. Kontrollera att uttrycksfragmentets innehåll är en giltig JSON så att det kan användas i beslutsobjekt.

Vid körning valideras kampanjinnehållet (inklusive fragmentinnehåll från beslutsobjekt). Om valideringen misslyckas återges inte kampanjen.
