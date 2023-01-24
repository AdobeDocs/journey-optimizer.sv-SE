---
solution: Journey Optimizer
product: journey optimizer
title: Om den avancerade uttrycksredigeraren
description: Läs mer om hur du skapar avancerade uttryck
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: uttrycksredigerare, data, resa
exl-id: 9ea6cc3a-6a1b-4e8f-82ff-f8b1812617d7
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 79%

---

# Om den avancerade uttrycksredigeraren {#about-the-advanced-expression-editor}

>[!CONTEXTUALHELP]
>id="ajo_journey_expression_advanced"
>title="Om den avancerade uttrycksredigeraren"
>abstract="Använd den avancerade uttrycksredigeraren för att skapa avancerade uttryck på olika skärmar i gränssnittet. Du kan till exempel skapa uttryck när du konfigurerar och använder resor och när du definierar ett datakällsvillkor."

Använd den avancerade uttrycksredigeraren för att skapa avancerade uttryck på olika skärmar i gränssnittet. Du kan till exempel skapa uttryck när du konfigurerar och använder resor och när du definierar ett datakällsvillkor.
Den är också tillgänglig varje gång du behöver definiera åtgärdsparametrar som kräver specifika dataändringar. Du kan utnyttja data från händelser eller ytterligare information som hämtats från datakällan. I en resa är den lista med händelsefält som visas sammanhangsberoende och varierar beroende på vilka händelser som läggs till i resan.

Den avancerade uttrycksredigeraren har en uppsättning inbyggda funktioner och operatorer som du använder för att manipulera värden och definiera ett uttryck som passar dina behov. Med den avancerade uttrycksredigeraren kan du även definiera värden för den externa datakällans parameter samt ändra kartläggningsfält och samlingar, till exempel upplevelsehändelser.

![](../assets/journey65.png)

_Gränssnittet för den avancerade uttrycksredigeraren_

Den avancerade uttrycksredigeraren kan användas till att:

* skapa [avancerade villkor](../condition-activity.md#about_condition) för datakällor och händelseinformation
* definiera anpassade [vänteaktiviteter](../wait-activity.md#custom)
* definiera kartläggning av åtgärdsparametrar

När det är möjligt kan du växla mellan de två lägena med hjälp av knappen **[!UICONTROL Advanced mode]**/**[!UICONTROL Simple mode]** . Det enkla läget beskrivs [här](../condition-activity.md#about_condition).

>[!NOTE]
>
>Villkor kan definieras i den enkla eller avancerade uttrycksredigeraren. De returnerar alltid en boolesk typ.
>
>Åtgärdsparametrar kan definieras genom fältval eller via den avancerade uttrycksredigeraren. De returnerar en viss datatyp enligt sina uttryck.

## Komma åt den avancerade uttrycksredigeraren {#accessing-the-advanced-expression-editor}

Du kan komma åt den avancerade uttrycksredigeraren på olika sätt.

* När du skapar ett villkor för datakällan kan du klicka på **[!UICONTROL Advanced mode]** för att komma åt den avancerade redigeraren.

   ![](../assets/journeyuc2_33.png)

* När du skapar en anpassad timer visas den avancerade redigeraren direkt.
* Klicka på **[!UICONTROL Advanced mode]** när du kartlägger en åtgärdsparameter.

## Lära känna gränssnittet{#discovering-the-interface}

Med den här skärmen kan du ange ett uttryck manuellt.

![](../assets/journey70.png)

Till vänster på skärmen visas tillgängliga fält och funktioner:

* **[!UICONTROL Events]**: välj ett av fälten som har tagits emot från den inkommande händelsen. Listan med händelsefält som visas är sammanhangsberoende och varierar beroende på vilka händelser som läggs till i resan. [Läs mer](../../event/about-events.md)
* **[!UICONTROL Segments]**: om du har släppt en **[!UICONTROL Segment qualification]** väljer du det segment som du vill använda i uttrycket. [Läs mer](../condition-activity.md#using-a-segment)
* **[!UICONTROL Data Sources]**: välj i listan bland tillgängliga fält från datakällornas fältgrupper. [Läs mer](../../datasource/about-data-sources.md)
* **[!UICONTROL Journey properties]**: I det här avsnittet grupperas de tekniska fält som rör resan för en viss profil. [Läs mer](journey-properties.md)
* **[!UICONTROL Functions]**: välj i listan bland inbyggda funktioner som du använder för att utföra komplex filtrering. Funktionerna är organiserade per kategori. [Läs mer](functions.md)

![](../assets/journey65.png)

En mekanism för automatisk komplettering visar sammanhangsberoende förslag.

![](../assets/journey68.png)

En mekanism för syntaxvalidering kontrollerar kodens integritet. Fel visas överst på redigeraren.

![](../assets/journey69.png)

**Behovet av parametrar när du skapar villkor med den avancerade uttrycksredigeraren**

Om du väljer ett fält från en extern datakälla som kräver att en parameter anropas (se [den här sidan](../../datasource/external-data-sources.md). I en väderrelaterad datakälla används till exempel parametern &quot;city&quot; ofta. Därför måste du välja var du vill hämta den här parametern &quot;city&quot;. Funktioner kan även tillämpas på parametrar om man vill utföra formateringsändringar eller sammansättningar.

![](../assets/journeyuc2_19.png)

För mer komplicerade användningsfall kan du definiera parametrarnas värden med nyckelordet &quot;params&quot; för att inkludera dem från datakällan i huvuduttrycket. Läs [den här sidan](../expression/field-references.md).
