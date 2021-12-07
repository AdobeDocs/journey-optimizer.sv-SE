---
title: Skapa simuleringar
description: Lär dig hur du skapar simuleringar
feature: Offers
topic: Integrations
role: User
level: Intermediate
source-git-commit: 899b8b47d6c6121c19e485376de368358049c05f
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# Skapa simuleringar

## Om simulering

Om du vill validera din beslutslogik kan du simulera vilka erbjudanden som ska levereras till en testprofil för en viss placering.

<!--Simulation allows you to view the results of offer decisions as a selected profile.-->

På så sätt kan ni testa och förfina olika versioner av era erbjudanden utan att det påverkar målmottagarna.

>[!NOTE]
>
>Den här funktionen simulerar en enda begäran till [!DNL Decisions] API. Läs mer på [Leverera erbjudanden med API:t för beslut](../api-reference/decisions-api/deliver-offers.md).

Om du vill komma åt den här funktionen väljer du **[!UICONTROL Simulation]** från **[!UICONTROL Decision management]** > **[!UICONTROL Offers]** -menyn.

![](../../assets/offers_simulation-tab.png)

<!--
➡️ [Discover this feature in video](#video)
-->

## Välj testprofiler

Först måste du välja de testprofiler som du ska använda för simulering.

1. Klicka på **[!UICONTROL Manage profile]**.

   ![](../../assets/offers_simulation-manage-profile.png)

1. Markera det identitetsnamnutrymme som du vill använda för att identifiera testprofiler. I det här exemplet använder vi **E-post** namnutrymme.

   >[!NOTE]
   >
   >Ett identitetsnamnutrymme definierar kontexten för en identifierare, till exempel en e-postadress eller ett CRM-ID. Läs mer om Adobe Experience Platform identitetsnamnutrymmen [i det här avsnittet](../../get-started-identity.md){target=&quot;_blank&quot;}.

1. Ange identitetsvärdet och klicka på **[!UICONTROL View]** för att lista tillgängliga profiler.

   ![](../../assets/offers_simulation-add-profile.png)

1. Lägg till andra profiler om du vill testa olika profildata och spara urvalet.

   ![](../../assets/offers_simulation-save-profiles.png)

1. När du har lagt till visas alla profiler i listrutan under **[!UICONTROL Test profile]**. Du kan växla mellan de sparade testprofilerna för att visa resultatet för varje vald profil.

   ![](../../assets/offers_simulation-saved-profiles.png)

1. Du kan klicka på **[!UICONTROL Profile details]** för att visa valda profildata.

<!--Learn more on [selecting test profiles](preview.md#select-test-profiles)-->

## Lägg till beslutsomfattningar

Välj sedan de erbjudandebeslut som du vill simulera i dina testprofiler.

1. Välj **[!UICONTROL Add decision scope]**.

   ![](../../assets/offers_simulation-add-decision.png)

1. Välj en placering i listan.

   ![](../../assets/offers_simulation-add-decision-scope.png)

1. De tillgängliga besluten visas.

   * Du kan använda sökfältet för att förfina markeringen.
   * Du kan klicka på **[!UICONTROL Open offer decisions]** om du vill öppna en lista med alla beslut som du har skapat. Läs mer på [beslut](create-offer-activities.md).

   Välj önskat beslut och klicka på **[!UICONTROL Add]**.

   ![](../../assets/offers_simulation-add-decision-scope-add.png)

1. Beslutsomfånget du just definierade visas på huvudarbetsytan.

   Du kan justera antalet erbjudanden som du vill begära. Om du till exempel väljer 2 visas de två bästa erbjudandena för detta beslutsområde.

   ![](../../assets/offers_simulation-request-offer.png)

   >[!NOTE]
   >
   >Du kan begära upp till 30 erbjudanden.

1. Upprepa stegen ovan om du vill lägga till så många beslut du behöver.

   ![](../../assets/offers_simulation-add-more-decisions.png)

   >[!NOTE]
   >
   >Även om du definierar flera beslutsomfattningar simuleras bara en API-begäran.
   >
   >Alla dedupliceringsflaggor är aktiverade som standard för simulering, vilket innebär att beslutsmotorn tillåter dubbletter och därmed kan göra samma förslag i flera beslut. Läs mer på [!DNL Decisions] Egenskaper för API-begäran i [det här avsnittet](../api-reference/decisions-api/deliver-offers.md).

## Visa simuleringsresultat

När du har lagt till ett beslutsområde och valt en testprofil kan du visa resultatet.

1. Klicka på **[!UICONTROL View results]**.

   ![](../../assets/offers_simulation-view-results.png)

1. De bästa erbjudandena visas enligt den valda profilen för varje beslut.

   Välj ett erbjudande om du vill visa information om det.

   ![](../../assets/offers_simulation-offer-details.png)

1. Välj en annan profil i listan om du vill visa resultatet av erbjudandebesluten för en annan testprofil.

1. Du kan lägga till, ta bort eller uppdatera beslutsomfattningarna så många gånger som behövs.

>[!NOTE]
>
>Varje gång du ändrar profiler eller uppdaterar beslutsomfattningar måste du uppdatera resultaten med **[!UICONTROL View results]** -knappen.

<!--Questions

* Is it recommended to first select profiles or first add decision scopes?
* What does Request offer changes?
* Nothing displays when I click View results? Can't see any score...
* What's the typical example? i.e. how many decisions do you select, and how do you compare scores?
* What do you learn from simulation? i.e. if I selected 2 decisions and I compare the scores, which one is better or should I use for my customers?
* Is there a way to create relevant test profiles?
* Error on Profile details link.
* Is there a tutorial planned to be released?
* Why still a big red frame when no profile is found?

## Tutorial video {#video}

>[!NOTE]
>
>This video applies to the Offer Decisioning application service built on Adobe Experience Platform. However, it provides generic guidance to use Offer in the context of Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/329606?quality=12)
-->