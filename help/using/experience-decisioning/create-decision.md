---
title: Skapa beslutsprofiler
description: Lär dig hur du skapar beslutsprofiler
feature: Experience Decisioning
topic: Integrations
role: User
level: Experienced
badge: label="Begränsad tillgänglighet"
exl-id: 63aa1763-2220-4726-a45d-3a3a8b8a55ec
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 1%

---

# Skapa beslutsprofiler {#create-decision}

>[!CONTEXTUALHELP]
>id="ajo_code_based_decision"
>title="Vad är ett beslut?"
>abstract="Beslutspolicyer innehåller all urvalslogik för att beslutsmotorn ska kunna välja det bästa innehållet. Beslutspolicyn är kampanjspecifika. Deras mål är att välja de bästa erbjudandena för varje profil medan kampanjutvecklingen gör att du kan ange hur de valda beslutsobjekten ska presenteras, inklusive vilka objektattribut som ska inkluderas i meddelandet."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Om Experience Decision"

Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för upplevelser för att välja det bästa innehåll som ska levereras, beroende på målgruppen.

Beslutspolicyer innehåller all urvalslogik för att beslutsmotorn ska kunna välja det bästa innehållet. Beslutspolicyn är kampanjspecifika. Deras mål är att välja de bästa erbjudandena för varje profil medan kampanjutvecklingen gör att du kan ange hur de valda beslutsobjekten ska presenteras, inklusive vilka objektattribut som ska inkluderas i meddelandet.

>[!NOTE]
>
>Beslutsprinciper anges som beslut <!--but they are decision policies. TBC if this note is needed--> i användargränssnittet [!DNL Journey Optimizer].

## Lägga till en beslutsprincip i en kodbaserad kampanj {#add-decision}

>[!CONTEXTUALHELP]
>id="ajo_code_based_item_number"
>title="Definiera antalet artiklar som ska returneras"
>abstract="Välj det antal beslutsartiklar som du vill returnera. Om du till exempel väljer 2 visas de två bästa erbjudandena för den aktuella ytan."

>[!CONTEXTUALHELP]
>id="ajo_code_based_fallback"
>title="Välj en reservlinje"
>abstract="Ett reservobjekt visas för användaren när ingen av de urvalsstrategier som definierats för den beslutsprincipen är kvalificerad."

>[!CONTEXTUALHELP]
>id="ajo_code_based_strategy"
>title="Vad är en strategi?"
>abstract="Sekvensen med urvalsstrategi avgör vilken strategi som ska utvärderas först. Minst en strategi krävs. Beslutsposter i kombinerade strategier kommer att utvärderas tillsammans."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Skapa strategier"
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Utvärderingsorder"

Om du vill presentera det bästa dynamiska erbjudandet och upplevelsen för besökarna på din webbplats eller i din mobilapp lägger du till en beslutspolicy i en kodbaserad kampanj. Följ stegen nedan för att göra det.

1. Skapa en kampanj och välj åtgärden **[!UICONTROL Code-base experience]**. [Läs mer](../code-based/create-code-based.md)

1. I [kodredigeraren](../code-based/create-code-based.md#edit-code) väljer du ikonen **[!UICONTROL Decision policy]** och klickar på **[!UICONTROL Add decision policy]**.

   ![](assets/decision-code-based-create.png)

1. Fyll i informationen för din beslutsprincip: lägg till ett namn och välj en katalog.

   >[!NOTE]
   >
   >För närvarande är bara standardkatalogen **[!UICONTROL Offers]** tillgänglig.

   ![](assets/decision-code-based-details.png)

1. Välj det antal objekt som du vill returnera. Om du till exempel väljer 2 visas de två bästa erbjudandena för den aktuella ytan. Klicka på **[!UICONTROL Next]**

1. Använd knappen **[!UICONTROL Add strategy]** för att definiera urvalsstrategier för din beslutspolicy. Varje strategi består av en erbjudandesamling som är kopplad till en begränsning för behörighet och en rangordningsmetod för att avgöra vilka erbjudanden som ska visas. [Läs mer](selection-strategies.md)

   ![](assets/decision-code-based-strategies.png)

   >[!NOTE]
   >
   >Minst en strategi krävs. Du kan inte lägga till fler än 10 strategier.

1. Från skärmen **[!UICONTROL Add strategy]** kan du även skapa en strategi. Knappen **[!UICONTROL Create selection strategy]** dirigerar om dig till menyn **[!UICONTROL Experience decisioning]** > **[!UICONTROL Strategy setup]**. [Läs mer](selection-strategies.md)

   ![](assets/decision-code-based-add-strategy.png)

1. När du lägger till flera strategier utvärderas de i en viss ordning. Den första strategin som lades till i sekvensen utvärderas först och så vidare. [Läs mer](#evaluation-order)

   Om du vill ändra standardsekvensen kan du dra och släppa strategierna och/eller grupperna för att ordna om dem som du vill.

   ![](assets/decision-code-based-strategy-groups.png)

1. Lägg till ett reserv. Ett reservobjekt visas för användaren om ingen av ovanstående urvalsstrategier är kvalificerad.

   ![](assets/decision-code-based-strategy-fallback.png)

   Du kan välja valfritt objekt i listan, som visar alla beslutsobjekt som har skapats i den aktuella sandlådan. Om ingen urvalsstrategi är kvalificerad visas reservdelen för användaren oavsett vilka datum och villkor för behörighet som gäller för det valda objektet <!--nor frequency capping when available - TO CLARIFY-->.

   >[!NOTE]
   >
   >En reservlösning är valfri. Om ingen reservlösning har valts och ingen strategi är kvalificerad visas ingenting av [!DNL Journey Optimizer].

1. Spara markeringen och klicka på **[!UICONTROL Create]**. Nu när beslutspolicyn har skapats kan du använda beslutsattributen i ditt kodbaserade upplevelseinnehåll. [Läs mer](#use-decision-policy)

   ![](assets/decision-code-based-decision-added.png)

## Utvärderingsorder {#evaluation-order}

Som beskrivs ovan består en strategi av en samling, en rangordningsmetod och begränsningar för behörighet.

Du kan:

* Ange den sekventiella ordning du vill att strategierna ska utvärderas,
* Kombinera olika strategier så att de utvärderas tillsammans och inte separat.

Flera strategier och grupperingar av dem avgör prioriteringen av strategierna och rangordningen av godtagbara erbjudanden. Den första strategin har högsta prioritet och de strategier som kombineras inom samma grupp har samma prioritet.

Du har till exempel två samlingar, en i strategi A och en i strategi B. Begäran är att två beslutsobjekt ska skickas tillbaka. Låt oss säga att det finns två giltiga erbjudanden från strategi A och tre giltiga erbjudanden från strategi B.

* Om de två strategierna **inte kombineras** eller i sekventiell ordning (1 och 2) returneras de två främsta giltiga erbjudandena från den första strategin på den första raden. Om det inte finns två godtagbara erbjudanden för den första strategin kommer beslutsmotorn att gå vidare till nästa strategi i sekvens för att hitta så många erbjudanden som fortfarande behövs, och kommer i slutändan att returnera en reservlösning om det behövs.

  ![](assets/decision-code-based-consecutive-strategies.png)

* Om de två samlingarna **utvärderas samtidigt**, eftersom det finns två giltiga erbjudanden från strategi A och tre giltiga erbjudanden från strategi B, kommer alla fem erbjudanden att grupperas tillsammans baserat på det värde som fastställs av respektive rangordningsmetod. Två erbjudanden begärs, och därför returneras de två främsta erbjudandena från dessa fem.

  ![](assets/decision-code-based-combined-strategies.png)

+++ **Exempel med flera strategier**

Låt oss nu titta på ett exempel där du har flera strategier indelade i olika grupper.

Du definierade tre strategier. Strategi 1 och strategi 2 kombineras i grupp 1 och strategi 3 är oberoende (grupp 2).

De berättigade erbjudandena för varje strategi och deras prioritet (används vid rankningsfunktionens utvärdering) är följande:

* Grupp 1:
   * Strategi 1 - (erbjudande 1, erbjudande 2, erbjudande 3) - prioritet 1
   * Strategi 2 - (erbjudande 3, erbjudande 4, erbjudande 5) - prioritet 1

* Grupp 2:
   * Strategi 3 - (erbjudande 5, erbjudande 6) - Prioritet 0

Strategierbjudanden med högst prioritet utvärderas först och läggs till i listan med rankade erbjudanden.

**Iteration 1:**

Strategi 1 och strategi 2-erbjudanden utvärderas tillsammans (erbjudande 1, erbjudande 2, erbjudande 3, erbjudande 4, erbjudande 5). Låt oss säga att resultatet är:

Erbjudande 1-10
Erbjudande 2-20
Erbjudande 3-30 från strategi 1, 45 från strategi 2. Det högsta av båda kommer att övervägas, så 45 kommer att beaktas.
Erbjudande 4-40
Erbjudande 5-50

Rankade erbjudanden: Erbjudande 5, Erbjudande 3, Erbjudande 4, Erbjudande 2, Erbjudande 1.

**Iteration 2:**

Strategi 3-erbjudanden utvärderas (erbjudande 5, erbjudande 6). Låt oss säga att resultatet är:

* Erbjudande 5 - Kommer inte att utvärderas eftersom det redan finns i resultatet ovan.
* Erbjudande 6-60

Rankade erbjudanden: Erbjudande 5, Erbjudande 3, Erbjudande 4, Erbjudande 2, Erbjudande 1, Erbjudande 6.

+++

## Använd beslutsprincipen i kodredigeraren {#use-decision-policy}

När beslutsprincipen har skapats kan den användas i [personaliseringsredigeraren](../code-based/create-code-based.md#edit-code). Följ stegen nedan för att göra det.

>[!NOTE]
>
>Kodbaserad upplevelse utnyttjar personaliseringsredigeraren [!DNL Journey Optimizer] med alla dess funktioner för personalisering och redigering. [Läs mer](../personalization/personalization-build-expressions.md)

1. Klicka på knappen **[!UICONTROL Insert policy]**. Koden som motsvarar beslutspolicyn läggs till.

   ![](assets/decision-code-based-add-decision.png)

   >[!NOTE]
   >
   >Den här sekvensen upprepas det antal gånger som du vill att beslutsprincipen ska returneras. Om du t.ex. väljer att returnera två objekt när [du skapar beslutet](#add-decision) kommer samma sekvens att upprepas två gånger.

1. Nu kan du lägga till alla beslutsattribut du vill i den koden. De tillgängliga attributen lagras i **[!UICONTROL Offers]**-katalogens schema. Anpassade attribut lagras i mappen **`_<imsOrg`>** och standardattribut i mappen **`_experience`**. [Läs mer i offertkatalogens schema](catalogs.md)

   ![](assets/decision-code-based-decision-attributes.png)

   >[!NOTE]
   >
   >För artikelspårning för beslutsprincip måste attributet `trackingToken` läggas till enligt följande för beslutsprincipinnehåll:
   >`trackingToken: {{item._experience.decisioning.decisionitem.trackingToken}}`

1. Klicka på varje mapp för att expandera den. Placera musmarkören på önskad plats och klicka på ikonen + bredvid det attribut du vill lägga till. Du kan lägga till så många attribut du vill i koden.

   ![](assets/decision-code-based-add-decision-attributes.png)

1. Du kan också lägga till andra attribut som är tillgängliga i personaliseringsredigeraren, till exempel profilattribut.

   ![](assets/decision-code-based-decision-profile-attribute.png)

## Rapportering i Customer Journey Analytics {#cja}

Om du arbetar med Customer Journey Analytics kan du skapa anpassade rapportinstrumentpaneler för kodbaserade kampanjer med hjälp av Experience Decision.

De huvudsakliga stegen visas nedan. Detaljerad information om hur du arbetar med Customer Journey Analytics finns i [Customer Journey Analytics-dokumentationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing){target="_blank"}.

1. Skapa och konfigurera en **anslutning** i Customer Journey Analytics. På så sätt kan du ansluta till den datauppsättning som du vill ha rapporter för. [Lär dig skapa en anslutning](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}

1. Skapa en **datavy** och koppla den till anslutningen som skapades tidigare. På fliken **[!UICONTROL Components]** väljer du de relevanta schemafält som du vill visa i rapporter. Se till att du tar med fälten **propositionInteract** och **propositionDisplay** i Experience Decision. [Lär dig hur du skapar och konfigurerar datavyer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}

1. Kombinera datakomponenter, tabeller och visualiseringar i **arbetsyteprojekt** för att skapa och dela rapporter för den kodbaserade kampanjen.[Lär dig skapa arbetsyteprojekt](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects){target="_blank"}
