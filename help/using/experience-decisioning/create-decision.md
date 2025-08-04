---
title: Skapa beslutsprofiler
description: Lär dig hur du skapar beslutsprofiler
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: 63aa1763-2220-4726-a45d-3a3a8b8a55ec
source-git-commit: 229fb3d120727b51e011d8056f8d914c7968f2d0
workflow-type: tm+mt
source-wordcount: '2435'
ht-degree: 0%

---

# Skapa beslutsprofiler {#create-decision}

>[!CONTEXTUALHELP]
>id="ajo_code_based_decision"
>title="Vad är ett beslut?"
>abstract="Beslutspolicyer innehåller all urvalslogik för att beslutsmotorn ska kunna välja det bästa innehållet. Beslutspolicyn är kampanjspecifika. Deras mål är att välja de bästa erbjudandena för varje profil medan kampanjutvecklingen gör att du kan ange hur de valda beslutsobjekten ska presenteras, inklusive vilka objektattribut som ska inkluderas i meddelandet."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Om beslut"

>[!CONTEXTUALHELP]
>id="ajo_journey_decision_policy"
>title="Definiera en beslutspolicy"
>abstract="Med en beslutspolicy kan ni välja ut de bästa elementen från beslutsmotorn och leverera dem till rätt målgrupp."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Om beslut"

>[!CONTEXTUALHELP]
>id="ajo_exd_decision_policy"
>title="Beslutspolitik"
>abstract="Med en beslutspolicy kan ni välja ut de bästa elementen från beslutsmotorn och leverera till varje målgrupp."

>[!CONTEXTUALHELP]
>id="ajo_exd_placements"
>title="Placement"
>abstract="En placering bestämmer var returnerade objekt från beslutsmotorn visas i ett meddelande. Ni kan spåra deras prestanda på olika ställen i rapporteringen."

>[!CONTEXTUALHELP]
>id="ajo_exd_decision_attribute"
>title="Välj beslutsattribut från katalog"
>abstract="Beslutsattribut lagras i katalogschemat. Välj ett attribut som du vill använda här från den valda katalogen."

Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för att dynamiskt returnera det bästa innehållet för varje målgruppsmedlem. Deras mål är att välja de bästa erbjudandena för varje profil, medan kampanjen/resan gör att du kan ange hur de valda beslutsobjekten ska presenteras, inklusive vilka objektattribut som ska inkluderas i meddelandet.

## Viktiga steg {#key}

De viktigaste stegen för att utnyttja beslutsstrategier i era budskap är följande:

1. [Skapa en beslutspolicy i ett e-postmeddelande eller en kodbaserad upplevelse](#add-decision)

   Ställ in en beslutspolicy i e-postmeddelandet eller den kodbaserade upplevelsen genom att välja hur många objekt som ska returneras, konfigurera urvalsstrategier, reservalternativ och utvärderingsordning.

1. [Använd beslutsprincipen i ditt innehåll](#use-decision-policy)

   Anpassa innehållet med beslutsunderlag och attribut från de beslutsobjekt du vill visa i meddelandet.

1. [Skapa rapportinstrumentpaneler](cja-reporting.md)

   Bygg anpassade Customer Journey Analytics-kontrollpaneler för att mäta prestanda och få insikt i hur era beslutsstrategier och -erbjudanden levereras och engageras.

## Skyddsritningar och begränsningar

* **Begränsad tillgänglighet - Beslutsprincip i e-postmeddelanden** - För närvarande är det begränsad tillgänglighet att skapa beslutsprinciper i e-postmeddelanden. Kontakta din Adobe-representant för att få åtkomst.
* **Spegelsidor** - För tillfället återges inte beslutsobjekt i e-postspegelsidor.
* **Spårnings- och länktyp** - Om du vill spåra länkar som skapats genom beslut definierar du dem i schemat som&quot;Decisioning Assets&quot;. Attributbaserade länkar går inte att spåra.
* **Beslutsprincipkapsling i e-postmeddelanden** - Det går inte att kapsla flera beslutsprinciper i en överordnad e-postkomponent som redan har en associerad beslutsprincip.
* **Duplicerade resor/kampanjer med beslut** - Om du duplicerar en resa eller kampanj som innehåller en beslutsprincip refererar den duplicerade versionen till det ursprungliga e-postmeddelandet eller den kodbaserade upplevelsen, vilket ger upphov till fel. Konfigurera alltid om beslutsprincipen efter duplicering.
* **Samtyckesprinciper** - Det tar upp till 48 timmar att genomföra uppdateringar av medgivandeprinciper. Om en beslutspolicy refererar till ett attribut som är knutet till en nyligen uppdaterad medgivandepolicy, kommer ändringarna inte att tillämpas omedelbart.

  Om nya profilattribut som omfattas av en samtyckespolicy läggs till i en beslutspolicy kommer de att vara användbara, men den medgivandepolicy som är kopplad till dem kommer inte att tillämpas förrän förseningen har passerat.

  Samtyckesregler är endast tillgängliga för organisationer som har Adobe Healthcare Shield eller tillägg till Privacy and Security Shield.

* **AI-rankning** - För tillfället stöds inte AI-rankning för e-postkanalen i resor med beslut.

## Skapa en beslutspolicy i ett e-postmeddelande eller en kodbaserad upplevelse {#add-decision}

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
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Skapa strategier"

Om du vill presentera det bästa dynamiska erbjudandet och upplevelsen för mottagarna och besökarna i dina e-postmeddelanden på din webbplats eller i din mobilapp lägger du till en beslutspolicy i ett e-postmeddelande eller en kodbaserad kampanj eller resa. Följ stegen nedan för att göra det.

### Skapa en beslutspolicy {#add}

1. Lägg till en **[!UICONTROL Email]**- eller **[!UICONTROL Code-base experience]**-åtgärd under en resa eller kampanj.

1. För e-postmeddelanden växlar du **[!UICONTROL Enable decisioning]** på konfigurationsskärmen.

   ![](assets/decision-policy-enable.png)

   >[!IMPORTANT]
   >
   >Om du aktiverar beslutsfattande rensas befintligt e-postinnehåll. Om du redan har utformat e-postmeddelandet måste du spara innehållet som en mall i förväg.
   >
   >Observera att alla beslutsprinciper som har konfigurerats i e-postmeddelandet inte sparas i mallen. Om du tillämpar mallen på ett annat e-postmeddelande måste du konfigurera om profilen.

1. Profiler kan skapas i e-post- och kodbaserade upplevelser med personaliseringsredigeraren. De kan också skapas i e-postmeddelanden från en dedikerad meny i e-postprogrammet Designer. Expandera avsnitten nedan om du vill ha mer information.

   +++Personalization editor

   1. Öppna anpassningsredigeraren och välj **[!UICONTROL Decision policy]**.
   1. Klicka på knappen **[!UICONTROL Add decision policy]** om du vill skapa en ny profil.

      ![](assets/decision-code-based-create.png)

   +++

   +++E-posta Designer **[!UICONTROL Decisioning]**-menyn

   1. Markera en komponent, klicka på ikonen **[!UICONTROL Decisioning]** i verktygsfältet eller egenskapsrutan och välj sedan **[!UICONTROL Add new policy]**.

   1. Välj **[!UICONTROL Reuse decision output]** om du vill återanvända en beslutsprincip som redan har skapats i det här e-postmeddelandet.

      ![](assets/decision-policy-email-designer.png)

   +++

1. Ange ett namn och välj en katalog (för närvarande begränsad till standardkatalogen **[!UICONTROL Offers]**).

1. Välj antalet objekt som ska returneras. Om du till exempel väljer 2 visas de två bästa erbjudandena för den aktuella konfigurationen.

   ![](assets/decision-code-based-details.png)

   För e-postmeddelanden kan flera objekt bara returneras i en **[!UICONTROL Repeat grid]**-innehållskomponent. Expandera avsnittet nedan om du vill ha mer information:

+++ Returnera flera beslutsobjekt i e-postmeddelanden

   1. Dra en **[!UICONTROL Repeat Grid]**-komponent till arbetsytan och konfigurera den som du vill med hjälp av rutan **[!UICONTROL Settings]**.

      ![](assets/decision-policy-repeat.png)

   1. Klicka på ikonen **[!UICONTROL Decisioning]** i verktygsfältet på arbetsytan eller öppna rutan **[!UICONTROL Decisioning]** och välj **[!UICONTROL Add decision policy]**.

   1. Ange antalet objekt som ska returneras i fältet **[!UICONTROL Number of items]** och konfigurera sedan beslutsprincipen enligt nedan. Det maximala antalet objekt som du kan markera begränsas av antalet rutor som definieras i komponenten **[!UICONTROL Repeat grid]**.

   ![](assets/decision-policy-repeat-number.png)

+++

1. Klicka på **[!UICONTROL Next]**.

### Välj objekt och urvalsstrategier {#select}

I avsnittet **[!UICONTROL Strategy sequence]** kan du välja vilka beslutsobjekt och urvalsstrategier som ska presenteras med beslutspolicyn.

1. Klicka på **[!UICONTROL Add]** och välj vilken typ av objekt som ska inkluderas i profilen:

   * **[!UICONTROL Selection strategy]**: Lägg till en eller flera markeringsstrategier. Beslutsstrategier utnyttjar samlingar som är kopplade till behörighetskrav och rangordningsmetoder för att fastställa vilka poster som ska visas. Du kan välja en befintlig urvalsstrategi eller skapa en ny med knappen **[!UICONTROL Create selection strategy]**. [Lär dig hur du skapar urvalsstrategier](selection-strategies.md)

   * **[!UICONTROL Decision item]**: Lägg till enskilda beslutsobjekt som ska visas utan att behöva köra en urvalsstrategi. Du kan bara välja ett beslutsobjekt i taget. Alla villkor som anges för artikeln gäller.

   ![](assets/decision-code-based-strategy-sequence.png)

   >[!NOTE]
   >
   >En beslutspolicy stöder upp till 10 urvalsstrategier och beslutsposter tillsammans. [Läs mer om hur du bestämmer dig för skyddsprofiler och begränsningar](gs-experience-decisioning.md#guardrails)

1. När du lägger till flera beslutsposter och/eller strategier utvärderas de i en viss ordning. Det första objektet som lades till i sekvensen utvärderas först och så vidare. Om du vill ändra standardsekvensen drar och släpper du objekten och/eller grupperna för att ordna om dem som du vill. Expandera avsnittet nedan om du vill ha mer information.

   +++Hantera utvärderingsordning i en beslutspolicy

   När du har lagt till beslutsposter och urvalsstrategier i din policy kan du ordna dem för att fastställa deras utvärderingsordning och kombinera urvalsstrategier för att utvärdera dem tillsammans.

   Den **sekventiella ordningen** i vilken objekt och strategier utvärderas anges med siffror till vänster om varje objekt eller grupp av objekt. Om du vill flytta positionen för en urvalsstrategi (eller en grupp strategier) i sekvensen drar och släpper du den till en annan position.

   ![](assets/decision-code-based-strategy-groups.png)

   >[!NOTE]
   >
   >Endast markeringsstrategier kan dras och släppas i en sekvens. Om du vill ändra positionen för ett beslutsobjekt måste du ta bort det och lägga tillbaka det med knappen **[!UICONTROL Add]** när du har lagt till de andra objekten som du vill utvärdera tidigare.

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

   **Exempel med flera strategier**

   Låt oss nu titta på ett exempel där du har flera strategier indelade i olika grupper. Du definierade tre strategier. Strategi 1 och strategi 2 kombineras i grupp 1 och strategi 3 är oberoende (grupp 2). De berättigade erbjudandena för varje strategi och deras prioritet (används vid rankningsfunktionens utvärdering) är följande:

   * Grupp 1:
      * Strategi 1 - (erbjudande 1, erbjudande 2, erbjudande 3) - prioritet 1
      * Strategi 2 - (erbjudande 3, erbjudande 4, erbjudande 5) - prioritet 1

   * Grupp 2:
      * Strategi 3 - (erbjudande 5, erbjudande 6) - Prioritet 0

   Strategierbjudanden med högst prioritet utvärderas först och läggs till i listan med rankade erbjudanden.

   * **Iteration 1:**

     Strategi 1 och strategi 2-erbjudanden utvärderas tillsammans (erbjudande 1, erbjudande 2, erbjudande 3, erbjudande 4, erbjudande 5). Låt oss säga att resultatet är:

     Erbjudande 1-10
Erbjudande 2-20
Erbjudande 3-30 från strategi 1, 45 från strategi 2. Det högsta av båda kommer att övervägas, så 45 kommer att beaktas.
Erbjudande 4-40
Erbjudande 5-50

     Rankade erbjudanden: Erbjudande 5, Erbjudande 3, Erbjudande 4, Erbjudande 2, Erbjudande 1.

   * **Iteration 2:**

     Strategi 3-erbjudanden utvärderas (erbjudande 5, erbjudande 6). Låt oss säga att resultatet är:

      * Erbjudande 5 - Kommer inte att utvärderas eftersom det redan finns i resultatet ovan.
      * Erbjudande 6-60

     Rankade erbjudanden: Erbjudande 5, Erbjudande 3, Erbjudande 4, Erbjudande 2, Erbjudande 1, Erbjudande 6.

   +++

1. Klicka på **[!UICONTROL Next]**

### Lägg till reserverbjudanden {#fallback}

När du har valt beslutsobjekt och/eller urvalsstrategier kan du lägga till reserverbjudanden som visas om ingen av ovanstående poster eller urvalsstrategier är kvalificerad.

Du kan välja valfritt objekt i listan, som visar alla beslutsobjekt som har skapats i den aktuella sandlådan. Om ingen urvalsstrategi är kvalificerad visas reservdelen för användaren oavsett vilka datum och villkor för behörighet som gäller för det valda objektet <!--nor frequency capping when available - TO CLARIFY-->.

![](assets/decision-code-based-strategy-fallback.png)

>[!NOTE]
> Reservationer är valfria. Upp till antalet begärda objekt kan väljas. Om ingen är berättigad och ingen reservlösning är inställd visas ingenting.

### Spara och hantera beslutsstrategier {#save}

När din beslutsprincip är klar sparar du den och klickar på **[!UICONTROL Create]**.

För e-postmeddelanden måste du definiera en placering för den komponent som är kopplad till beslutspolicyn. Om du vill göra det klickar du på knappen **[!UICONTROL Decisioning]** i rutan för komponentegenskaper och väljer **[!UICONTROL Assign placement]**. [Lär dig hur du arbetar med placeringar](../experience-decisioning/placements.md)

![](assets/decision-policy-rail.png)

Du kan redigera eller ta bort en beslutsprincip när som helst med hjälp av ellipsknappen i personaliseringsredigeraren, eller på menyn **[!UICONTROL Decisioning]** i komponentens egenskapspanel.

>[!BEGINTABS]

>[!TAB Redigera eller ta bort en princip från personaliseringsredigeraren]

![](assets/decision-policy-edit.png)

>[!TAB Redigera eller ta bort en princip från komponentens egenskaper]

![](assets/decision-policy-edit-properties.png)

>[!ENDTABS]

## Använd en beslutspolicy i ditt innehåll {#use-decision-policy}

När du väl har skapat en beslutspolicy och de attribut som är kopplade till de returnerade beslutsposterna kan du använda i ditt innehåll för att anpassa ditt innehåll. Gör så här:

### Infoga beslutsprincipkoden {#insert-code}

1. Öppna anpassningsredigeraren och gå till menyn **[!UICONTROL Decision policy]**.

1. För e-postmeddelanden klickar du på **[!UICONTROL Insert syntax]** för att lägga till koden som motsvarar beslutsprincipen. Klicka på **[!UICONTROL Insert policy]** för kodbaserade upplevelser.

   +++Infoga kod för beslutspolicy i e-postmeddelanden

   ![](assets/decision-policy-add.png)

   Om ingen placering har associerats med komponenten i förväg för e-postmeddelanden väljer du en i listan och klickar på **[!UICONTROL Assign]**.

   ![](assets/decision-policy-placement.png)

   +++

   +++Infoga beslutsprincipkod i kodbaserad upplevelse

   ![](assets/decision-code-based-add-decision.png)

   +++

   >[!NOTE]
   >
   >Om knappen för kodinfogning inte visas kan det bero på att en beslutsprincip redan har konfigurerats för den överordnade komponenten.

1. Koden för beslutspolicyn läggs till. Den här sekvensen upprepas det antal gånger som du vill att beslutsprincipen ska returneras. Om du t.ex. väljer att returnera två objekt när [du skapar beslutet](#add-decision) kommer samma sekvens att upprepas två gånger.

### Utnyttja attribut för beslutsartiklar {#attributes}

Nu kan du lägga till alla beslutsattribut du vill i den koden. De tillgängliga attributen lagras i **[!UICONTROL Offers]**-katalogens schema. Anpassade attribut lagras i mappen **`_<imsOrg`>** och standardattribut i mappen **`_experience`**. [Läs mer om offertkatalogens schema](catalogs.md)

![](assets/decision-code-based-decision-attributes.png)

>[!NOTE]
>
>För artikelspårning för beslutsprincip måste attributet `trackingToken` läggas till enligt följande för beslutsprincipinnehåll:
>&#x200B;>`trackingToken: {{item._experience.decisioning.decisionitem.trackingToken}}`

1. Klicka på varje mapp för att expandera den. Placera musmarkören på önskad plats och klicka på ikonen + bredvid det attribut du vill lägga till. Du kan lägga till så många attribut du vill i koden.

   ![](assets/decision-code-based-add-decision-attributes.png)

1. Se till att du kapslar in `#each`-slingan i ett par hakparenteser `[ ]` och lägger till ett komma precis före den avslutande `/each`.

   ![](assets/decision-code-based-wrap-code.png)

1. Du kan också lägga till andra attribut som är tillgängliga i personaliseringsredigeraren, till exempel profilattribut.

   ![](assets/decision-code-based-decision-profile-attribute.png)

## Slutliga steg {#final-steps}

När innehållet är klart kan du granska och publicera kampanjen eller resan:

* [Publicera en resa](../building-journeys/publishing-the-journey.md)
* [Granska aktivering av en kampanj](../campaigns/review-activate-campaign.md)
* [Publicera och aktivera en kodbaserad upplevelse](../code-based/publish-code-based.md)

När utvecklaren gör ett API- eller SDK-anrop för att hämta innehåll för den yta som definieras i kanalkonfigurationen, kommer ändringarna att tillämpas på webbsidan eller appen för kodbaserade upplevelser.

>[!NOTE]
>
>För närvarande kan du inte simulera innehåll från användargränssnittet i en [kodbaserad upplevelse](../code-based/create-code-based.md) -kampanj eller resa med hjälp av beslut. Det finns en tillfällig lösning i [det här avsnittet](../code-based/code-based-decisioning-implementations.md).

Om du vill se hur dina beslut fungerar kan du skapa anpassade [Customer Journey Analytics-rapportinstrumentpaneler](cja-reporting.md).
