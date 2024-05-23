---
solution: Journey Optimizer
product: journey optimizer
title: Om den avancerade uttrycksredigeraren
description: Lär dig skapa avancerade uttryck
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: uttrycksredigerare, data, resa
exl-id: 9ea6cc3a-6a1b-4e8f-82ff-f8b1812617d7
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 1%

---

# Om den avancerade uttrycksredigeraren {#about-the-advanced-expression-editor}

>[!CONTEXTUALHELP]
>id="ajo_journey_expression_advanced"
>title="Om den avancerade uttrycksredigeraren"
>abstract="Använd den avancerade uttrycksredigeraren för att skapa avancerade uttryck på olika skärmar i gränssnittet. Du kan till exempel skapa uttryck när du konfigurerar och använder resor och när du definierar ett datakällsvillkor."

Använd den avancerade uttrycksredigeraren Journey för att skapa avancerade uttryck på olika skärmar i gränssnittet. Du kan till exempel skapa uttryck när du konfigurerar och använder resor och när du definierar ett datakällsvillkor.

>[!NOTE]
>
>De funktioner och funktioner som finns i den avancerade uttrycksredigeraren Journey skiljer sig från dem som finns i [personaliseringsredigerare](../../personalization/functions/functions.md).

Det är också tillgängligt varje gång du behöver definiera åtgärdsparametrar som kräver specifika dataändringar. Du kan utnyttja data från händelser eller ytterligare information som hämtats från datakällan. Under en resa är den visade listan med händelsefält sammanhangsberoende och varierar beroende på vilka händelser som läggs till under resan.

Den avancerade uttrycksredigeraren har en uppsättning inbyggda funktioner och operatorer som du kan använda för att ändra värden och definiera ett uttryck som passar just dina behov. Med den avancerade uttrycksredigeraren kan du också definiera värden för den externa datakällparametern, ändra mappningsfält och samlingar, till exempel upplevelsehändelser.

![](../assets/journey65.png)

_Det avancerade gränssnittet för uttrycksredigeraren_

Den avancerade uttrycksredigeraren kan användas för att:

* skapa [avancerade villkor](../condition-activity.md#about_condition) om datakällor och händelseinformation
* definiera egen [vänteaktiviteter](../wait-activity.md#custom)
* definiera åtgärdsparametermappning

När det är möjligt kan du växla mellan de två lägena med **[!UICONTROL Advanced mode]** / **[!UICONTROL Simple mode]** -knappen. Det enkla läget beskrivs [här](../condition-activity.md#about_condition).

>[!NOTE]
>
>Villkoren kan definieras i den enkla eller avancerade uttrycksredigeraren. De returnerar alltid en boolesk typ.
>
>Åtgärdsparametrar kan definieras genom att välja fält eller via den avancerade uttrycksredigeraren. De returnerar en viss datatyp enligt deras uttryck.

## Åtkomst till den avancerade uttrycksredigeraren {#accessing-the-advanced-expression-editor}

Du kan komma åt den avancerade uttrycksredigeraren på olika sätt:

* När du skapar ett villkor för en datakälla kan du komma åt den avancerade redigeraren genom att klicka på **[!UICONTROL Advanced mode]**.

  ![](../assets/journeyuc2_33.png)

* När du skapar en anpassad timer visas den avancerade redigeraren direkt.
* När du mappar åtgärdsparametern klickar du på **[!UICONTROL Advanced mode]**.

## Identifiera gränssnittet{#discovering-the-interface}

På den här skärmen kan du skriva ditt uttryck manuellt.

![](../assets/journey70.png)

Till vänster på skärmen visas tillgängliga fält och funktioner:

* **[!UICONTROL Events]**: välj ett av fälten som tagits emot från den inkommande händelsen. Den visade listan med händelsefält är sammanhangsberoende och varierar beroende på vilka händelser som läggs till under resan. [Läs mer](../../event/about-events.md)
* **[!UICONTROL Audiences]**: om du har släppt en **[!UICONTROL Audience qualification]** väljer du den målgrupp du vill använda i ditt uttryck. [Läs mer](../condition-activity.md#using-a-segment)
* **[!UICONTROL Data Sources]**: välj i listan över fält som är tillgängliga från fältgrupperna i datakällorna. [Läs mer](../../datasource/about-data-sources.md)
* **[!UICONTROL Journey properties]**: I det här avsnittet grupperas de tekniska fält som rör resan för en viss profil om. [Läs mer](journey-properties.md)
* **[!UICONTROL Functions]**: välj i en lista över inbyggda funktioner som gör att du kan utföra komplex filtrering. Funktionerna är ordnade efter kategorier. [Läs mer](functions.md)

![](../assets/journey65.png)

En mekanism för automatisk komplettering visar sammanhangsberoende förslag.

![](../assets/journey68.png)

En syntaxvalideringsmekanism kontrollerar kodens integritet. Fel visas högst upp i redigeraren.

![](../assets/journey69.png)

**Behovet av parametrar när du skapar villkor med den avancerade uttrycksredigeraren**

Om du väljer ett fält från en extern datakälla som kräver att en parameter anropas (se [den här sidan](../../datasource/external-data-sources.md)) visas en ny flik till höger där du kan ange den här parametern. Parametervärdet kan komma från händelser som är placerade i resan eller Experience Platform-datakällan (och inte från andra externa datakällor). I en väderrelaterad datakälla kommer till exempel parametern&quot;city&quot; att användas ofta. Därför måste du välja var du vill få den här parametern city. Funktioner kan också användas för parametrar för att utföra formatändringar eller sammanfogningar.

![](../assets/journeyuc2_19.png)

Om du vill ta med parametrarna för datakällan i huvuduttrycket kan du definiera deras värden med nyckelordet &quot;params&quot; för mer komplicerade användningsområden. Se [den här sidan](../expression/field-references.md).
