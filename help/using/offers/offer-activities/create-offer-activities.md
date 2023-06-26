---
title: Skapa beslut
description: Lär dig hur du skapar beslut
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 7a217c97-57e1-4f04-a92c-37632f8dfe91
source-git-commit: 146dda9b180a4767b7041b50382f9a0eac0a0058
workflow-type: tm+mt
source-wordcount: '2100'
ht-degree: 1%

---

# Skapa beslut {#create-offer-activities}

Besluten är behållare för dina erbjudanden som utnyttjar beslutsmotorn för erbjudanden för att välja det bästa erbjudandet som ska levereras, beroende på leveransmålet.

➡️ [Lär dig hur du skapar erbjudandeaktiviteter i den här videon](#video)

Listan över beslut finns i **[!UICONTROL Offers]** meny > **[!UICONTROL Decisions]** -fliken. Det finns filter som hjälper dig att hämta beslut utifrån status eller start- och slutdatum.

![](../assets/activities-list.png)

Innan du bestämmer dig måste du kontrollera att komponenterna nedan har skapats i Erbjudandebiblioteket:

* [Placeringar](../offer-library/creating-placements.md)
* [Samlingar](../offer-library/creating-collections.md)
* [Personaliserade erbjudanden](../offer-library/creating-personalized-offers.md)
* [Reserverbjudanden](../offer-library/creating-fallback-offers.md)

## Skapa beslutet {#create-activity}

1. Gå till beslutslistan och klicka sedan på **[!UICONTROL Create decision]**.

1. Ange beslutets namn.

1. Definiera start- och slutdatum och sluttid om det behövs, och klicka sedan på **[!UICONTROL Next]**.

   ![](../assets/activities-name.png)

1. Om du vill tilldela egna eller centrala dataanvändningsetiketter till ett beslut väljer du **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../../administration/object-based-access.md)

## Definiera beslutsomfattningar {#add-decision-scopes}

1. Välj en placering i listrutan. Den kommer att läggas till i det första beslutsomfånget i ditt beslut.

   ![](../assets/activities-placement.png)

1. Klicka **[!UICONTROL Add]** för att välja utvärderingskriterier för den här placeringen.

   ![](../assets/activities-evaluation-criteria.png)

   Varje villkor består av en erbjudandesamling som är kopplad till en begränsning för behörighet och en rangordningsmetod för att fastställa vilka erbjudanden som ska visas i placeringen.

   >[!NOTE]
   >
   >Minst ett utvärderingskriterier krävs.

1. Välj den erbjudandesamling som innehåller de erbjudanden som ska övervägas och klicka sedan på **[!UICONTROL Add]**.

   ![](../assets/activities-collection.png)

   >[!NOTE]
   >
   >Du kan klicka på **[!UICONTROL Open offer collections]** om du vill visa en lista med samlingar på en ny flik, som gör att du kan bläddra bland samlingarna och erbjudandena som de innehåller.

   Den valda samlingen läggs till i villkoren.

   ![](../assets/activities-collection-added.png)

1. Använd **[!UICONTROL Eligibility]** om du vill begränsa urvalet av erbjudanden för den här placeringen.

   Den här begränsningen kan tillämpas med en **beslutsregel** eller en eller flera **Adobe Experience Platform segment**. Båda beskrivs i [det här avsnittet](../offer-library/add-constraints.md#segments-vs-decision-rules).

   * Om du vill begränsa urvalet av erbjudanden till medlemmarna i ett Experience Platform-segment väljer du **[!UICONTROL Segments]** och sedan klicka **[!UICONTROL Add segments]**.

     ![](../assets/activity_constraint_segment.png)

     Lägg till ett eller flera segment från den vänstra rutan och kombinera dem med **[!UICONTROL And]** / **[!UICONTROL Or]** logiska operatorer.

     ![](../assets/activity_constraint_segment2.png)

     Lär dig hur du arbetar med segment i [det här avsnittet](../../segment/about-segments.md).

   * Om du vill lägga till en markeringsbegränsning med en beslutsregel använder du kommandot **[!UICONTROL Decision rule]** och välj önskad regel.

     ![](../assets/activity_constraint_rule.png)

     Lär dig hur du skapar en beslutsregel i [det här avsnittet](../offer-library/creating-decision-rules.md).

1. När du väljer segment eller beslutsregler kan du se information om de uppskattade kvalificerade profilerna. Klicka **[!UICONTROL Refresh]** för att uppdatera data.

   >[!NOTE]
   >
   >Profiluppskattningar är inte tillgängliga när regelparametrar innehåller data som inte finns i profilen, till exempel kontextdata. Exempel: en regel som kräver att det aktuella vädret är ≥80 grader.

   ![](../assets/activity_constraint-estimate.png)

1. Definiera den rangordningsmetod som du vill använda för att välja det bästa erbjudandet för varje profil. [Läs mer](../offer-activities/configure-offer-selection.md).

   ![](../assets/activity_ranking-method.png)

   * Om flera erbjudanden är berättigade till den här placeringen är **[!UICONTROL Offer priority]** -metoden använder det värde som definieras i erbjudandena: erbjudandet med högsta prioritet kommer att levereras till användaren.

   * Om du vill använda en viss beräknad poäng för att välja vilket erbjudande du vill leverera väljer du **[!UICONTROL Formula]** eller **[!UICONTROL AI model]**. [Läs mer](../offer-activities/configure-offer-selection.md).

1. Klicka **[!UICONTROL Add]** för att definiera fler villkor för samma placering.

   ![](../assets/activity_add-collection.png)

1. När du lägger till flera villkor utvärderas de i en viss ordning. Den första samlingen som lades till i sekvensen utvärderas först och så vidare. [Läs mer](#evaluation-criteria-order)

   Om du vill ändra standardsekvensen kan du dra och släppa samlingarna för att ordna om dem som du vill.

   ![](../assets/activity_reorder-collections.png)

1. Du kan också utvärdera flera villkor samtidigt. Det gör du genom att dra och släppa samlingen ovanpå en annan.

   ![](../assets/activity_move-collection.png)

   De har nu samma rankning och kommer därför att utvärderas samtidigt. [Läs mer](#evaluation-criteria-order)

   ![](../assets/activity_same-rank-collections.png)

1. Använd **[!UICONTROL New scope]** -knappen. Upprepa stegen ovan för varje beslutsomfattning.

   ![](../assets/activity_new-scope.png)

   >[!NOTE]
   >
   >När flera beslutsomfattningar läggs till påverkas ordningen för utvärderingskriterier. [Läs mer](#multiple-scopes)

### Ordning för utvärderingskriterier {#evaluation-criteria-order}

Som beskrivs ovan består utvärderingskriterierna av en samling, behörighetskrav och en rangordningsmetod. Du kan ange den ordningsföljd i vilken du vill att utvärderingskriterierna ska utvärderas, men du kan också kombinera flera utvärderingskriterier så att de utvärderas tillsammans och inte separat.

#### Med ett omfång {#one-scope}


I ett och samma beslutsomfång avgör flera kriterier och gruppering av dem prioriteringen av kriterierna och rangordningen av godtagbara erbjudanden. De första kriterierna har den högsta prioriteten och de kriterier som kombineras inom samma&quot;grupp&quot; har samma prioritet.

Du har till exempel två samlingar, en i utvärderingskriterier A och en i utvärderingskriterier B. Begäran är att två erbjudanden ska skickas tillbaka. Låt oss säga att det finns två godtagbara erbjudanden från utvärderingskriterier A och tre giltiga erbjudanden från utvärderingskriterier B.

* Om de två utvärderingskriterierna är **inte kombinerad** och/eller i sekventiell ordning (1 och 2), kommer de två främsta godtagbara anbuden från utvärderingskriterierna att returneras på första raden. Om det inte finns två godtagbara erbjudanden för de första utvärderingskriterierna kommer beslutsmotorn att gå vidare till nästa utvärderingskriterier i följd för att hitta så många erbjudanden som fortfarande behövs, och kommer vid behov att returnera en reservlösning.

  ![](../assets/activity_consecutive-rank-collections.png)

* Om de två samlingarna **utvärderas samtidigt** Eftersom det finns två godtagbara erbjudanden från utvärderingskriterierna A och tre godtagbara erbjudanden från utvärderingskriterierna B, kommer samtliga fem erbjudanden att vara samlade på grundval av det värde som fastställs av respektive rangordningsmetod. Två erbjudanden begärs, och därför returneras de två främsta erbjudandena från dessa fem.

  ![](../assets/activity_same-rank-collections.png)

+++ **Exempel med flera kriterier**

Låt oss nu titta på ett exempel där du har flera kriterier för ett enskilt omfång indelade i olika grupper.

Du definierade tre kriterier. Kriterierna 1 och 2 sammanslås i grupp 1 och Kriterierna 3 är oberoende (grupp 2).

De berättigade anbuden för varje kriterium och deras prioritet (används vid rankningsfunktionens utvärdering) är följande:

* Grupp 1:
   * Kriterium 1 - (erbjudande 1, erbjudande 2, erbjudande 3) - prioritet 1
   * Kriterium 2 - (erbjudande 3, erbjudande 4, erbjudande 5) - prioritet 1

* Grupp 2:
   * Kriterium 3 - (erbjudande 5, erbjudande 6) - Prioritet 0

De högst prioriterade erbjudandena utvärderas först och läggs till i listan med rankade erbjudanden.

**Upprepning 1:**

Kriterium 1 och Villkor 2 utvärderas tillsammans (erbjudande 1, erbjudande 2, erbjudande 3, erbjudande 4, erbjudande 5). Låt oss säga att resultatet är:

Erbjudande 1 - 10 Erbjudande 2 - 20 Erbjudande 3 - 30 från villkor 1, 45 från villkor 2. Det högsta av båda kommer att övervägas, så 45 kommer att beaktas.
Erbjudande 4 - 40 Erbjudande 5 - 50

Det rankade erbjudandet är nu följande: Erbjudande 5, erbjudande 3, erbjudande 4, erbjudande 2, erbjudande 1.

**Upprepning 2:**

Villkor 3 utvärderas (erbjudande 5, erbjudande 6). Låt oss säga att resultatet är:

* Erbjudande 5 - Kommer inte att utvärderas eftersom det redan finns i resultatet ovan.
* Erbjudande 6-60

Erbjudandena är nu följande: Erbjudande 5, erbjudande 3, erbjudande 4, erbjudande 2, erbjudande 1, erbjudande 6.

+++

#### Med flera omfång {#multiple-scopes}

**Om duplicering är av**

När du lägger till flera beslutsomfattningar i ett beslut, och om duplicering inte tillåts på flera platser, väljs de giltiga erbjudandena i tur och ordning i den ordning som beslutsomfattningarna i begäran gäller.

>[!NOTE]
>
>The **[!UICONTROL Allow Duplicates across placements]** -parametern ställs in på placeringsnivån. Om duplicering är inställt på false för en placering i en beslutsbegäran, ärver alla placeringar i begäran inställningen false. [Läs mer om dupliceringsparametern](../offer-library/creating-placements.md)

Låt oss ta ett exempel där du har lagt till två beslutsomfattningar som:

* Omfång 1: Det finns fyra giltiga erbjudanden (Erbjudande 1, Erbjudande 2, Erbjudande 3, Erbjudande 4) och begäran avser två erbjudanden som ska skickas tillbaka.
* Tillämpningsområde 2: Det finns fyra giltiga erbjudanden (Erbjudande 1, Erbjudande 2, Erbjudande 3, Erbjudande 4) och begäran avser två erbjudanden som ska skickas tillbaka.

+++ **Exempel 1**

Markeringen ser ut så här:

1. De två bästa erbjudandena från Scope 1 returneras (Erbjudande 1, Erbjudande 2).
1. De två återstående giltiga erbjudandena från Scope 2 returneras (Erbjudande 3, Erbjudande 4).

+++

+++ **Exempel 2**

I det här exemplet har erbjudande 1 nått sin frekvensgräns. [Läs mer om frekvensbegränsning](../offer-library/add-constraints.md#capping)

Markeringen ser ut så här:

1. De två återstående giltiga erbjudandena från Scope 1 returneras (Erbjudande 2, Erbjudande 3).
1. Det återstående berättigade erbjudandet från Scope 2 kommer att returneras (erbjudande 4).

+++

+++ **Exempel 3**

I det här exemplet nådde Erbjudande 1 och Erbjudande 3 sin frekvensgräns. [Läs mer om frekvensbegränsning](../offer-library/add-constraints.md#capping)

Markeringen ser ut så här:

1. De två återstående giltiga erbjudandena från Scope 1 returneras (Erbjudande 2, Erbjudande 4).
1. Det finns inga fler berättigade erbjudanden för Scope 2, så [grunderbjudande](#add-fallback) returneras.

+++

**Om duplicering är aktiverat**

När duplicering tillåts på alla ersättningar kan samma erbjudande föreslås flera gånger på olika platser. Om det är aktiverat kommer systemet att överväga samma erbjudande för flera praktik. [Läs mer om dupliceringsparametern](../offer-library/creating-placements.md)

Låt oss ta samma exempel som ovan där du lade till två beslutsomfattningar som:

* Omfång 1: Det finns fyra giltiga erbjudanden (Erbjudande 1, Erbjudande 2, Erbjudande 3, Erbjudande 4) och begäran avser två erbjudanden som ska skickas tillbaka.
* Tillämpningsområde 2: Det finns fyra giltiga erbjudanden (Erbjudande 1, Erbjudande 2, Erbjudande 3, Erbjudande 4) och begäran avser två erbjudanden som ska skickas tillbaka.

+++ **Exempel 1**

Markeringen ser ut så här:

1. De två bästa erbjudandena från Scope 1 returneras (Erbjudande 1, Erbjudande 2).
1. Samma två bästa erbjudanden från Scope 2 returneras (erbjudande 1, erbjudande 2).

+++

+++ **Exempel 2**

I det här exemplet har erbjudande 1 nått sin frekvensgräns. [Läs mer om frekvensbegränsning](../offer-library/add-constraints.md#capping)

Markeringen ser ut så här:

1. De två återstående giltiga erbjudandena från Scope 1 returneras (Erbjudande 2, Erbjudande 3).

1. Samma återstående två giltiga erbjudanden från Scope 2 returneras (Erbjudande 2, Erbjudande 3).

+++

+++ **Exempel 3**

I det här exemplet nådde Erbjudande 1 och Erbjudande 3 sin frekvensgräns. [Läs mer om frekvensbegränsning](../offer-library/add-constraints.md#capping)

Markeringen ser ut så här:

1. De två återstående giltiga erbjudandena från Scope 1 returneras (Erbjudande 2, Erbjudande 4).

1. Samma återstående två giltiga erbjudanden från Scope 2 returneras (Erbjudande 2, Erbjudande 4).

+++

## Lägg till ett reserverbjudande {#add-fallback}

När du har definierat beslutsomfattningarna definierar du det reserverbjudande som presenteras som en sista utväg till de kunder som inte matchar reglerna och begränsningarna för erbjudanden.

Det gör du genom att välja det i listan över tillgängliga reserverbjudanden för de ersättningar som definierats i beslutet och sedan klicka på **[!UICONTROL Next]**.

![](../assets/add-fallback-offer.png)

>[!NOTE]
>
>Du kan klicka på **[!UICONTROL Open offer library]** länk för att visa listan med erbjudanden på en ny flik.

## Granska och spara beslutet {#review}

Om allt är korrekt konfigurerat visas en sammanfattning av beslutsegenskaperna.

1. Se till att beslutet är klart att användas för att presentera erbjudanden för kunderna. Alla beslutsomfattningar och det reserverbjudande som det innehåller visas.

   ![](../assets/review-decision.png)

1. Du kan expandera eller komprimera varje placering. Du kan förhandsgranska tillgängliga erbjudanden, berättigandeinformation och rankningsinformation för varje placering. Du kan även visa information om de uppskattade kvalificerade profilerna. Klicka **[!UICONTROL Refresh]** för att uppdatera data.

   ![](../assets/review-decision-details.png)

1. Klicka på **[!UICONTROL Finish]**.
1. Välj **[!UICONTROL Save and activate]**.

   ![](../assets/save-activities.png)

   Du kan också spara beslutet som utkast för att redigera det och aktivera det senare.

Beslutet visas i listan med **[!UICONTROL Live]** eller **[!UICONTROL Draft]** status, beroende på om du har aktiverat den eller inte i föregående steg.

Den är nu klar att användas för att leverera erbjudanden till kunder.

## Beslutslista {#decision-list}

I beslutslistan kan du välja vilket beslut som ska visas. Därifrån kan du också redigera den och ändra dess status (**Utkast**, **Live**, **Slutförd**, **Arkiverad**), duplicera beslutet eller ta bort det.

![](../assets/decision_created.png)

Välj **[!UICONTROL Edit]** knapp för att gå tillbaka till beslutsversionsläget, där du kan ändra beslutets [information](#create-activity), [beslutsomfattningar](#add-decision-scopes) och [grunderbjudande](#add-fallback).

>[!IMPORTANT]
>
>Om ett beslut om erbjudande som används i ett kundmeddelande ändras måste du avpublicera resan och publicera den på nytt.  På så sätt säkerställs att ändringarna införlivas i kundens budskap och att meddelandet överensstämmer med de senaste uppdateringarna.

Välj ett live-beslut och klicka **[!UICONTROL Deactivate]** för att återställa beslutsstatus till **[!UICONTROL Draft]**.

Om du vill ange status igen till **[!UICONTROL Live]** väljer du **[!UICONTROL Activate]** som nu visas.

![](../assets/decision_activate.png)

The **[!UICONTROL More actions]** aktiverar de åtgärder som beskrivs nedan.

![](../assets/decision_more-actions.png)

* **[!UICONTROL Complete]**: anger beslutets status till **[!UICONTROL Complete]**, vilket innebär att beslutet inte kan anropas längre. Den här åtgärden är bara tillgänglig för aktiverade beslut. Beslutet är fortfarande tillgängligt i listan, men du kan inte återställa dess status till **[!UICONTROL Draft]** eller **[!UICONTROL Approved]**. Du kan bara duplicera, ta bort eller arkivera den.

* **[!UICONTROL Duplicate]**: skapar ett beslut med samma egenskaper, beslutsomfattningar och reserverbjudande. Som standard har det nya beslutet **[!UICONTROL Draft]** status.

* **[!UICONTROL Delete]**: tar bort beslutet från listan.

  >[!CAUTION]
  >
  >Beslutet och dess innehåll kommer inte längre att vara tillgängliga. Det går inte att ångra den här åtgärden.
  >
  >Om beslutet används i ett annat objekt kan det inte tas bort.

* **[!UICONTROL Archive]**: anger beslutsstatus till **[!UICONTROL Archived]**. Beslutet är fortfarande tillgängligt i listan, men du kan inte återställa dess status till **[!UICONTROL Draft]** eller **[!UICONTROL Approved]**. Du kan bara duplicera eller ta bort den.

Du kan också ta bort eller ändra status för flera beslut samtidigt genom att markera motsvarande kryssrutor.

![](../assets/decision_multiple-selection.png)

Om du vill ändra status för flera beslut med olika status, ändras bara statusen.

![](../assets/decision_change-status.png)

När ett beslut har skapats kan du klicka på dess namn i listan.

![](../assets/decision_click-name.png)

På så sätt kan du få tillgång till detaljerad information för det beslutet. Välj **[!UICONTROL Change log]** tabba till [övervaka alla ändringar](../get-started/user-interface.md#changes-log) som har tagits till beslutet.

![](../assets/decision_information.png)

## Instruktionsvideo{#video}

Lär dig hur du skapar erbjudandeaktiviteter i beslutsprocessen.

>[!VIDEO](https://video.tv.adobe.com/v/329606?quality=12)


