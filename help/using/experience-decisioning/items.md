---
title: Beslutsobjekt
description: Lär dig hur du arbetar med beslutsobjekt
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 5c866814-d79a-4a49-bfcb-7a767d802e90
source-git-commit: 2b9261ff0f225a429b9be04db214452736163766
workflow-type: tm+mt
source-wordcount: '1724'
ht-degree: 0%

---

# Skapa ditt första beslutsobjekt {#items}

>[!CONTEXTUALHELP]
>id="ajo_exd_items"
>title="Hantera beslutsobjekt"
>abstract="Med Journey Optimizer kan ni skapa marknadsföringserbjudanden, så kallade beslutsobjekt, som ni kan skapa och ordna i en centraliserad katalog och samlingar. För närvarande konsolideras alla skapade beslutsobjekt i en enda katalog för erbjudanden. Från den här skärmen kan du även komma åt katalogschemat via **Redigera schema** och skapa anpassade attribut för dina beslutsobjekt."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/experience-decisioning/decision-items/catalogs.html" text="Konfigurera objektkatalogen"

>[!BEGINSHADEBOX &quot;Det du hittar i den här handboken&quot;]

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsposter: [Konfigurera objektkatalogen](catalogs.md) - **[Skapa beslutsobjekt](items.md)** - [Hantera artikelsamlingar](collections.md)
* Konfigurera objektmarkering: [Skapa beslutsregler](rules.md) - [Skapa rangordningsmetoder](ranking.md)
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

Med Journey Optimizer kan ni skapa marknadsföringserbjudanden, så kallade beslutsobjekt, som ni kan skapa och ordna i en centraliserad katalog och samlingar. De består av standardattribut och anpassade attribut som är anpassade efter just dina behov. Dessutom innehåller de profilbegränsningar som gör att du kan definiera till vilka ett beslutsobjekt kan visas.

Kontrollera att du har skapat en **beslutsregel** om du vill ange villkor för att bestämma vem beslutsobjektet kan visas för. [Lär dig hur du skapar beslutsregler](rules.md).

Om du vill skapa ett beslutsobjekt går du till **[!UICONTROL Experience Decisioning]** > **[!UICONTROL  Catalogs]** och sedan klicka **[!UICONTROL Create item]** följer du de steg som beskrivs i avsnitten nedan.

## Definiera beslutsobjektets attribut {#attributes}

>[!CONTEXTUALHELP]
>id="ajo_exd_item_priority"
>title="Definiera beslutsobjektets prioritet"
>abstract="Om en profil kvalificerar för flera artiklar kan prioriteten jämföra det här beslutsobjektet med andra. En högre prioritet ger objektet företräde framför andra."

>[!CONTEXTUALHELP]
>id="ajo_exd_item_custom_attributes"
>title="Definiera anpassade attribut"
>abstract="Anpassade attribut är specifika attribut som är anpassade efter dina behov och som du kan tilldela till ett beslutsobjekt. De skapas i beslutsobjektens katalogschema. Det här avsnittet visas bara om du har lagt till minst ett anpassat attribut i katalogschemat."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/experience-decisioning/decision-items/catalogs.html" text="Konfigurera objektkatalogen"

Börja med att definiera beslutsobjektets standardattribut och anpassade attribut:

![](assets/item-attributes.png)

1. Ange ett namn och en beskrivning.
1. Ange start- och slutdatum. Posten kommer endast att beaktas av beslutsmotorn inom dessa datum.
1. Ange **[!UICONTROL Priority]** för beslutsobjektet jämfört med andra, om en profil kvalificerar för flera poster. En högre prioritet ger objektet företräde framför andra.
1. The **Taggar** I kan du tilldela enhetliga Adobe Experience Platform-taggar till dina beslutsobjekt. På så sätt kan du enkelt klassificera dem och förbättra sökningen. [Lär dig hur du arbetar med taggar](../start/search-filter-categorize.md#tags)

   >[!NOTE]
   >
   >Prioriteten är en heltalsdatatyp. Alla attribut som är heltalsdatatyper ska innehålla heltalsvärden (inga decimaler).

1. Ange anpassade attribut (valfritt). Anpassade attribut är specifika attribut som är anpassade efter dina behov och som du kan tilldela till ett beslutsobjekt. De definieras i beslutsobjektens katalogschema. [Lär dig hur du arbetar med kataloger](catalogs.md)

1. När beslutsobjektets attribut har definierats klickar du på **[!UICONTROL Next]**.

## Konfigurera berättigandet för beslutsobjektet {#eligibility}

>[!CONTEXTUALHELP]
>id="ajo_exd_item_constraints"
>title="Lägga till målgrupper eller beslutsregler"
>abstract="Som standard är alla profiler berättigade att ta emot beslutsobjektet, men du kan använda målgrupper eller regler för att begränsa objektet till enbart vissa profiler."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences.html" text="Använda målgrupper"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/experience-decisioning/selection/rules.html" text="Använd beslutsregler"

Som standard är alla profiler berättigade att ta emot beslutsobjektet, men du kan använda målgrupper eller regler för att begränsa objektet till enbart specifika profiler, båda lösningarna som motsvarar olika användningar. Expandera avsnittet nedan om du vill ha mer information:

+++Använda målgrupper kontra decimalregler

En målgrupps utdata är i princip en lista med profiler, medan en beslutsregel är en funktion som körs på begäran mot en enskild profil under beslutsprocessen.

* **Målgrupper**: Å ena sidan är målgrupperna en grupp Adobe Experience Platform-profiler som matchar en viss logik baserat på profilattribut och upplevelsehändelser. Erbjudandehanteringen innebär dock inte att publiken beräknas om, vilket kanske inte är aktuellt när erbjudandet presenteras.

* **Beslutsregler**: Å andra sidan baseras en beslutsregel på data som är tillgängliga i Adobe Experience Platform och avgör till vem ett erbjudande kan visas. När regeln har valts i ett erbjudande eller i ett beslut för en viss placering verkställs den varje gång ett beslut fattas, vilket säkerställer att varje profil får det senaste och bästa erbjudandet.

+++

* Om du vill begränsa presentationen av beslutsobjektet till medlemmarna i en eller flera av Adobe Experience Platform målgrupper väljer du **[!UICONTROL Visitors who fall into one or multiple audiences]** lägg sedan till en eller flera målgrupper från den vänstra rutan och kombinera dem med **[!UICONTROL And]** / **[!UICONTROL Or]** logiska operatorer. [Läs mer om målgrupper](../audience/about-audiences.md).

* Om du vill koppla en specifik beslutsregel till beslutsobjektet väljer du **[!UICONTROL By rule]** drar du sedan den önskade regeln från den vänstra rutan till det centrala området. [Läs mer om beslutsregler](rules.md).

![](assets/item-constraints.png)

När du väljer målgrupper eller beslutsregler kan du se information om de uppskattade kvalificerade profilerna. Klicka **[!UICONTROL Refresh]** för att uppdatera data.

>[!NOTE]
>
>Profiluppskattningar är inte tillgängliga när regelparametrar innehåller data som inte finns i profilen, till exempel kontextdata. Exempel: en regel som kräver att det aktuella vädret är ≥80 grader.

## Ange regler för begränsning {#capping}

Begränsning används som en begränsning för att definiera det maximala antal gånger ett erbjudande kan presenteras. Genom att begränsa antalet gånger användarna får specifika erbjudanden kan ni undvika att överdriva era kunder och därmed optimera varje kontaktyta med det bästa erbjudandet. Du kan skapa upp till 10 takbeläggningar för ett visst beslutsobjekt.

![](assets/item-capping.png)

>[!NOTE]
>
>
>Det kan ta upp till 3 sekunder att uppdatera värdet för den räknare som används. Anta att du visar en webbanderoll som visar ett erbjudande på din webbplats. Om en viss användare bläddrar till nästa sida på webbplatsen på mindre än 3 sekunder ökas inte räknarvärdet för den användaren.

Klicka på knappen **[!UICONTROL Create capping]** följer du dessa steg:

1. Definiera vilken **[!UICONTROL Capping event]** beaktas för att öka räknaren.

   * **[!UICONTROL Decision event]** (standardvärde): Maximalt antal gånger ett erbjudande kan presenteras.
   * **[!UICONTROL Impression]** (endast inkommande kanaler): Maximalt antal gånger som erbjudandet kan visas för en användare.
   * **[!UICONTROL Clicks]**: Maximalt antal gånger en användare kan klicka på beslutsobjektet.
   * **[!UICONTROL Custom event]**: Du kan definiera en anpassad händelse som ska användas för att ange hur många gånger objektet ska skickas. Du kan t.ex. sätta ett tak för antalet inlösen tills de är lika med 10000 eller tills en viss profil har lösts in 1 gång. Om du vill göra det använder du [Adobe Experience Platform XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"} scheman för att skapa en anpassad händelseregel.

   >[!NOTE]
   >
   >För alla takthändelser utom beslutshändelser kanske feedback för beslutshanteringen inte samlas in automatiskt, vilket kan leda till att appningsräknaren inte ökas korrekt. För att vara säker på att varje takthändelse spåras och tas med i appningsräknaren måste du se till att schemat som används för att samla in upplevelsehändelser innehåller rätt fältgrupp för den händelsen. Detaljerad information om datainsamling finns i Journey Optimizer beslutsdokumentation:
   >* [Insamling av data för beslutshantering](../offers/data-collection/data-collection.md)
   >* [Konfigurera datainsamling](../offers/data-collection/schema-requirement.md)

1. Välj typ av begränsning:

   * Välj **[!UICONTROL In total]** för att definiera hur många gånger objektet kan föreslås för den kombinerade målgruppen, vilket betyder för alla användare. Om du till exempel är en återförsäljare av elektronikprodukter och har en &quot;TV-affär&quot; vill du att erbjudandet bara ska returneras 200 gånger för alla profiler.

* Välj **[!UICONTROL Per profile]** för att definiera hur många gånger erbjudandet kan erbjudas en och samma användare. Om du till exempel är en bank med ett Platinum-kreditkortserbjudande vill du inte att det här erbjudandet ska visas mer än fem gånger per profil. Ni tror faktiskt att om användaren har sett erbjudandet fem gånger och inte har följt det, har de större chans att agera på nästa bästa erbjudande.

1. I **[!UICONTROL Capping count limit]** anger du hur många gånger erbjudandet kan visas för alla användare eller per profil, beroende på vilken typ av appning som valts. Talet måste vara ett heltal större än 0.

   Du har till exempel definierat en anpassad capping-händelse som antalet utcheckningar som ska beaktas. Om du anger 10 i dialogrutan **[!UICONTROL Capping count limit]** inga fler erbjudanden skickas efter 10 utcheckningar.

1. I **[!UICONTROL Reset capping frequency]** i den nedrullningsbara listan anger hur ofta räknaren återställs. Det gör du genom att definiera tidsperioden för inventeringen (varje dag, varje vecka eller varje månad) och ange hur många dagar/veckor/månader du vill ha. Om du till exempel vill att antalet fästingar ska återställas varannan vecka väljer du **[!UICONTROL Weekly]** från motsvarande nedrullningsbar lista och typ **2** i det andra fältet.

   >[!NOTE]
   >
   >Räknaren för frekvensbegränsning återställs på **12 am UTC**, den dag du definierade eller den första dagen i veckan/månaden, om tillämpligt. Veckostartdagen är **söndag**. Den längd du väljer får inte överskrida **2 år** (dvs. motsvarande antal månader, veckor eller dagar).
   >
   >När du har publicerat din beslutspost kan du inte ändra tidsperioden (månadsvis, veckovis eller dagligen) som du har valt för frekvensen. Du kan fortfarande redigera frekvensbegränsningen om objektet har **[!UICONTROL Draft]** status och har aldrig publicerats tidigare med frekvensbegränsning aktiverad.

1. Klicka **[!UICONTROL Create]** för att bekräfta att en regel har skapats. Du kan skapa upp till 10 regler för ett enskilt beslutsobjekt. Klicka på **[!UICONTROL Create capping]** och upprepa stegen ovan.

   ![](assets/item-capping-rules.png)

1. När du har definierat regler för behörighet och begränsning för beslutsobjektet klickar du på **[!UICONTROL Next]** för att granska och spara objektet.

1. Beslutsobjektet visas nu i listan med **[!UICONTROL Draft]** status. Klicka på ellipsknappen och markera när den är klar att visas för profiler **[!UICONTROL Approve]**.

   ![](assets/item-approve.png)

<!--* Identifying how many times a given customer has been shown a decision item. 
If a marketer wants to determine how many times a specific customer has been shown an offer, they can do that. Go to Profiles menu, Attributes tab. You’ll see all counter values. The alphanumeric string is associated to the offer. To make the map, go to an item, in the URL check the last alphanumeric strings. D stands for day, w stands for week, m for month. “Ce” custom event-->

## Hantera beslutsobjekt {#manage}

I listan över beslutsobjekt kan du redigera ett beslutsobjekt och ändra dess status (**Utkast**, **Godkänd**, **Arkiverad**), duplicera eller ta bort den.

Om du vill ändra ett beslutsobjekt öppnar du det, gör ändringarna och sparar det.

Om du väljer ett beslutsobjekt eller klickar på ellipsknappen aktiveras de åtgärder som beskrivs nedan.

* **[!UICONTROL Approve]**: Anger beslutsobjektets status till Godkänd.
* **[!UICONTROL Undo approve]**: Anger beslutsobjektets status tillbaka till **[!UICONTROL Draft]**.
* **[!UICONTROL Duplicate]**: Skapar ett beslutsobjekt med identiska attribut och begränsningar. Som standard har det nya objektet **[!UICONTROL Draft]** status.
* **[!UICONTROL Delete]**: Tar bort beslutsobjektet från listan.

  >[!IMPORTANT]
  >
  >När den tagits bort är beslutsobjektet och dess innehåll inte längre tillgängliga. Det går inte att ångra den här åtgärden. Om beslutsobjektet används i en samling eller ett beslut kan det inte tas bort. Du måste ta bort beslutsobjektet från alla objekt först.

* **[!UICONTROL Archive]**: Anger beslutsobjektets status till **[!UICONTROL Archived]**. Beslutsobjektet är fortfarande tillgängligt från listan, men du kan inte återställa dess status till **[!UICONTROL Draft]** eller **[!UICONTROL Approved]**. Du kan bara duplicera eller ta bort den.
