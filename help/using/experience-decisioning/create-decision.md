---
title: Skapa beslutsprofiler
description: Lär dig hur du skapar beslutsprofiler
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: 63aa1763-2220-4726-a45d-3a3a8b8a55ec
source-git-commit: 7ce241ca8ae6d2be6152a1c393a8301ce2f397a3
workflow-type: tm+mt
source-wordcount: '1682'
ht-degree: 0%

---

# Skapa beslutsprofiler {#create-decision}

>[!CONTEXTUALHELP]
>id="ajo_code_based_decision"
>title="Vad är ett beslut?"
>abstract="Beslutspolicyer innehåller all urvalslogik för att beslutsmotorn ska kunna välja det bästa innehållet. Beslutspolicyn är kampanjspecifika. Deras mål är att välja de bästa erbjudandena för varje profil medan kampanjutvecklingen gör att du kan ange hur de valda beslutsobjekten ska presenteras, inklusive vilka objektattribut som ska inkluderas i meddelandet."

<!--additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="About Decisioning"-->

Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för att välja det bästa innehållet att leverera, beroende på målgruppen.

<!--Decision policies contain all of the selection logic for the decisioning engine to pick the best content. Decision policies are campaign specific. -->Deras mål är att välja de bästa erbjudandena för varje profil, medan kampanjen/resan gör att du kan ange hur de valda beslutsobjekten ska presenteras, inklusive vilka objektattribut som ska inkluderas i meddelandet.

>[!NOTE]
>
>Beslutsprinciper anges som beslut <!--but they are decision policies. TBC if this note is needed--> i användargränssnittet [!DNL Journey Optimizer].

De viktigaste stegen för att utnyttja beslutsregler i era kodbaserade kampanjer är följande:

1. [Lägga till en beslutsprincip i en kodbaserad upplevelse](#add-decision)
1. [Använd beslutsprincipen](#use-decision-policy)
1. [Skapa anpassade Customer Journey Analytics rapportpaneler](cja-reporting.md)

## Lägga till en beslutsprincip i en kodbaserad upplevelse {#add-decision}

>[!CONTEXTUALHELP]
>id="ajo_code_based_item_number"
>title="Definiera antalet artiklar som ska returneras"
>abstract="Välj det antal beslutsartiklar som du vill returnera. Om du till exempel väljer 2 visas de två bästa erbjudandena för den aktuella konfigurationen."

>[!CONTEXTUALHELP]
>id="ajo_code_based_fallback"
>title="Välj en reservlinje"
>abstract="Ett reservobjekt visas för användaren när ingen av de urvalsstrategier som definierats för den beslutsprincipen är kvalificerad."

>[!CONTEXTUALHELP]
>id="ajo_code_based_strategy"
>title="Vad är en strategi?"
>abstract="Sekvensen med urvalsstrategi avgör vilken strategi som ska utvärderas först. Minst en strategi krävs. Beslutsposter i kombinerade strategier kommer att utvärderas tillsammans."

<!--additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Create strategies"
additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Evaluation order"-->

Om du vill presentera det bästa dynamiska erbjudandet och upplevelsen för besökarna på din webbplats eller i din mobilapp, lägger du till en beslutspolicy till en kodbaserad kampanj eller resa. Följ stegen nedan för att göra det.

### Skapa beslutsprincipen {#add}

1. Skapa en kampanj och välj åtgärden **[!UICONTROL Code-base experience]**. [Läs mer](../code-based/create-code-based.md)

1. Välj **[!UICONTROL Decision policy]** i [kodredigeraren](../code-based/create-code-based.md#edit-code) och klicka på **[!UICONTROL Add decision policy]**.

   ![](assets/decision-code-based-create.png)

1. Som standard skapar du en ny profil.

   >[!NOTE]
   >
   >Du kan också välja att välja en befintlig profil.

1. Fyll i informationen för din beslutsprincip: lägg till ett namn och välj en katalog.

   >[!NOTE]
   >
   >För närvarande är bara standardkatalogen **[!UICONTROL Offers]** tillgänglig.

1. Välj det antal objekt som du vill returnera. Om du till exempel väljer 2 visas de två bästa erbjudandena för den aktuella konfigurationen. Klicka på **[!UICONTROL Next]**.

   ![](assets/decision-code-based-details.png)

### Välj objekt och urvalsstrategier {#select}

I avsnittet **[!UICONTROL Strategy sequence]** kan du välja vilka beslutsobjekt och urvalsstrategier som ska presenteras med beslutspolicyn.

1. Klicka på knappen **[!UICONTROL Add]**.

1. Välj vilken typ av objekt som ska ingå i profilen:

   * **[!UICONTROL Selection strategy]**: Lägg till en eller flera markeringsstrategier. Beslutsstrategier utnyttjar samlingar som är kopplade till behörighetskrav och rangordningsmetoder för att fastställa vilka poster som ska visas. Du kan välja en befintlig urvalsstrategi eller skapa en ny med knappen **[!UICONTROL Create selection strategy]**. [Lär dig hur du skapar urvalsstrategier](selection-strategies.md)

   * **[!UICONTROL Decision item]**: Lägg till enskilda beslutsobjekt som ska visas utan att behöva köra en urvalsstrategi. Du kan bara välja ett beslutsobjekt i taget. Alla villkor som anges för artikeln gäller.

   ![](assets/decision-code-based-strategy-sequence.png)

   >[!NOTE]
   >
   >En beslutspolicy stöder upp till 10 urvalsstrategier och beslutsposter tillsammans. [Läs mer om hur du bestämmer dig för skyddsprofiler och begränsningar](gs-experience-decisioning.md#guardrails)

1. När du lägger till flera beslutsposter och/eller strategier utvärderas de i en viss ordning. Det första objektet som lades till i sekvensen utvärderas först och så vidare.

   Om du vill ändra standardsekvensen kan du dra och släppa objekten och/eller grupperna för att ordna om dem som du vill. [Läs mer](#evaluation-order)

### Hantera utvärderingsordning i en beslutspolicy {#evaluation-order}

När du har lagt till beslutsposter och urvalsstrategier i din policy kan du ordna dem för att fastställa deras utvärderingsordning och kombinera urvalsstrategier för att utvärdera dem tillsammans.

Den **sekventiella ordningen** i vilken objekt och strategier utvärderas anges med siffror till vänster om varje objekt eller grupp av objekt. Om du vill flytta positionen för en urvalsstrategi (eller en grupp strategier) i sekvensen drar och släpper du den till en annan position.

>[!NOTE]
>
>Endast markeringsstrategier kan dras och släppas i en sekvens. Om du vill ändra positionen för ett beslutsobjekt måste du ta bort det och lägga tillbaka det med knappen **[!UICONTROL Add]** när du har lagt till de andra objekten som du vill utvärdera tidigare.

![](assets/decision-code-based-strategy-groups.png)

Du kan också **kombinera** flera markeringsstrategier i grupper så att de utvärderas tillsammans och inte separat. Om du vill göra det klickar du på knappen **`+`** under en urvalsstrategi för att kombinera den med en annan. Du kan också dra och släppa en markeringsstrategi på en annan om du vill gruppera de två strategierna i en grupp.

>[!NOTE]
>
>Beslutsobjekt kan inte grupperas tillsammans med andra objekt eller urvalsstrategier.

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

### Lägg till reserverbjudanden {#fallback}

När du har valt beslutsobjekt och/eller urvalsstrategier kan du lägga till reserverbjudanden som visas för användarna om inga av ovanstående objekt eller urvalsstrategier är kvalificerade.

![](assets/decision-code-based-strategy-fallback.png)

Du kan välja valfritt objekt i listan, som visar alla beslutsobjekt som har skapats i den aktuella sandlådan. Om ingen urvalsstrategi är kvalificerad visas reservdelen för användaren oavsett vilka datum och villkor för behörighet som gäller för det valda objektet <!--nor frequency capping when available - TO CLARIFY-->.

>[!NOTE]
>
>En reservlösning är valfri. Om ingen reservlösning har valts och ingen strategi är kvalificerad visas ingenting av [!DNL Journey Optimizer]. Du kan lägga till upp till det antal objekt som beslutsprincipen begär. Detta garanterar att ett visst antal artiklar returneras om så önskas för användningsfallet.

När din beslutsprincip är klar sparar du den och klickar på **[!UICONTROL Create]**. Nu när beslutspolicyn har skapats kan du använda beslutsattributen i ditt kodbaserade upplevelseinnehåll. [Läs mer](#use-decision-policy)

![](assets/decision-code-based-decision-added.png)

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

1. Nu kan du lägga till alla beslutsattribut du vill i den koden. De tillgängliga attributen lagras i **[!UICONTROL Offers]**-katalogens schema. Anpassade attribut lagras i mappen **`_<imsOrg`>** och standardattribut i mappen **`_experience`**. [Läs mer om offertkatalogens schema](catalogs.md)

   ![](assets/decision-code-based-decision-attributes.png)

   >[!NOTE]
   >
   >För artikelspårning för beslutsprincip måste attributet `trackingToken` läggas till enligt följande för beslutsprincipinnehåll:
   >`trackingToken: {{item._experience.decisioning.decisionitem.trackingToken}}`

1. Klicka på varje mapp för att expandera den. Placera musmarkören på önskad plats och klicka på ikonen + bredvid det attribut du vill lägga till. Du kan lägga till så många attribut du vill i koden.

   ![](assets/decision-code-based-add-decision-attributes.png)

1. Du kan också lägga till andra attribut som är tillgängliga i personaliseringsredigeraren, till exempel profilattribut.

   ![](assets/decision-code-based-decision-profile-attribute.png)

1. Klicka på **[!UICONTROL Save and close]** för att bekräfta ändringarna.

1. Granska och publicera er kodbaserade kampanj eller resa. [Lär dig hur](../code-based/publish-code-based.md)

   När utvecklaren gör ett API- eller SDK-anrop för att hämta innehåll för den yta som definieras i kanalkonfigurationen, tillämpas ändringarna på webbsidan eller appen.

   >[!NOTE]
   >
   >För närvarande kan du inte simulera innehåll från användargränssnittet i en [kodbaserad upplevelse](../code-based/create-code-based.md) -kampanj eller resa med hjälp av beslut. Det finns en tillfällig lösning i [det här avsnittet](../code-based/code-based-decisioning-implementations.md).

1. Om du vill se hur dina beslut fungerar kan du skapa anpassade [Customer Journey Analytics-rapportinstrumentpaneler](cja-reporting.md).


