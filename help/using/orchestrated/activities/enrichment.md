---
solution: Journey Optimizer
product: journey optimizer
title: Använd anrikningsaktiviteten
description: Lär dig använda anrikningsaktiviteten
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 8a0aeae8-f4f2-4f1d-9b89-28ce573fadfd
source-git-commit: 4fa50df6827e07e6f6f3c5730d1ae2a1af0d426d
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# Berikning {#enrichment}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_enrichment"
>title="Anrikningsaktivitet"
>abstract="Med aktiviteten **Enrichment** kan du förbättra måldata med ytterligare information från databasen. Det används ofta i ett arbetsflöde efter segmenteringsaktiviteter."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena{1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Aktiviteten **[!UICONTROL Enrichment]** är en **[!UICONTROL Targeting]**-aktivitet som gör att du kan förbättra dina målgruppsdata med ytterligare attribut.

Ni kan använda den här informationen för att segmentera er målgrupp mer exakt, baserat på beteenden, preferenser eller behov, och för att skapa personaliserade meddelanden som bättre kan kopplas till varje profil.

## Lägg till en anrikningsaktivitet {#enrichment-configuration}

>[!CONTEXTUALHELP]
>id="ajo_targetdata_personalization_enrichmentdata"
>title="Anrikningsdata"
>abstract="Välj de data som ska användas för att berika er samordnade kampanj. Du kan välja två typer av anrikningsdata: ett enskilt anrikningsattribut från måldimensionen, eller en samlingslänk, som är en länk med en 1-N-kardinalitet mellan tabellerna."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_enrichment_data"
>title="Anrikningsaktivitet"
>abstract="När data om berikning har lagts till i den orkestrerade kampanjen kan de användas i aktiviteter som lagts till efter Enrichment-aktiviteten för att segmentera kunder i distinkta grupper baserat på deras beteenden, önskemål och behov, eller för att skapa personaliserade marknadsföringsmeddelanden och kampanjer som troligtvis får genklang hos målgruppen."

Så här konfigurerar du aktiviteten **Enrichment**:

1. Lägg till en **anrikningsaktivitet**.

1. Klicka på **Lägg till anrikningsdata** och markera attributet som ska användas för att utöka data.

   Du kan välja två typer av anrikningsdata: ett enskilt anrikningsattribut från måldimensionen eller en samlingslänk. Var och en av dessa typer beskrivs i exemplen nedan:

   * [Single enrichment-attribut](#single-attribute)
   * [Samlingslänk](#collection-link)

   ![](../assets/enrichment-1.png)

## Exempel {#example}

### Single enrichment-attribut {#single-attribute}

I det här exemplet berikar ni publiken med ett enda attribut, till exempel födelsedatum, från den aktuella målgruppsdimensionen.

Så här gör du:

1. Klicka på **[!UICONTROL Add enrichment data]**.

1. Välj ett enkelt fält, till exempel **[!UICONTROL Date of birth]**, från den aktuella dimensionen.

   ![](../assets/enrichment-2.png)

1. Klicka på **[!UICONTROL Confirm]**.

### Samlingslänk {#collection-link}

Det här användningsfallet berikar er målgrupp med data från en länkad tabell. Du vill till exempel hämta de tre senaste inköpen under 100 USD.

För att uppnå detta ska du konfigurera anrikningen enligt följande:

* **Anrikningsattribut**: **[!UICONTROL Price]**

* **Antal poster att hämta**: 3

* **Filter**: Inkludera endast inköp där **[!UICONTROL Price]** är mindre än 100 dollar

#### Lägg till attributet {#add-attribute}

Markera först samlingslänken som innehåller de data som du vill utöka med.

1. Klicka på **[!UICONTROL Add enrichment data]**.

1. Markera fältet **[!UICONTROL Price]** i tabellen **[!UICONTROL Purchases]**.

   ![](../assets/enrichment-2.png)

#### Definiera samlingsinställningarna{#collection-settings}

Konfigurera sedan hur data ska samlas in och hur många poster som ska inkluderas.

1. Välj **[!UICONTROL Collect data]** i listrutan **[!UICONTROL Select how the data is collected]**.

   ![](../assets/enrichment-4.png)

1. Ange `3` i fältet **[!UICONTROL Lines to retrieve (Columns to create)]**.

1. Om du vill utföra en aggregering (t.ex. genomsnittligt inköpsbelopp) väljer du **[!UICONTROL Aggregated data]** och sedan **[!UICONTROL Average]** i listrutan **[!UICONTROL Aggregate function]**.

   ![](../assets/enrichment-5.png)

1. Använd fälten **[!UICONTROL Label]** och **[!UICONTROL Alias]** för att göra det enklare att identifiera de berikade attributen i efterföljande aktiviteter.

#### Definiera filtren{#collection-filters}

Lägg slutligen på filter för att säkerställa att endast relevanta poster inkluderas:

1. Klicka på **[!UICONTROL Create filters]**.

1. Lägg till följande två villkor:

   * **[!UICONTROL Price]** finns (för att exkludera NULL:er)

   * **[!UICONTROL Price]** är mindre än 100

   ![](../assets/enrichment-6.png)

1. Klicka på **[!UICONTROL Confirm]**.


<!--
#### Define the sorting{#collection-sorting}

We now need to apply sorting in order to retrieve the three **latest** purchases.

1. Activate the **Enable sorting** option.
1. Click inside the **Attribute** field.
1. Select the **Order date** field.
1. Click **Confirm**. 
1. Select **Descending** from the **Sort** drop-down.

![](../assets/workflow-enrichment7bis.png)


## Data reconciliation {#reconciliation}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_enrichment_reconciliation"
>title="Reconciliation"
>abstract="The **Enrichment** activity can be used to reconcile data from the Journey Optimizer schema with data from another schema, or with data coming from a temporary schema such as data uploaded using a Load file activity. This type of link defines a reconciliation towards a unique record. Journey Optimizer creates a link to a target table by adding a foreign key in it for storing a reference to the unique record."

The **Enrichment** activity can be used to reconcile data from the the Campaign database schema with data from another schema, or with data coming from a temporary schema such as data uploaded using a Load file activity. This type of link defines a reconciliation towards a unique record. Journey Optimizer creates a link to a target table by adding a foreign key in it for storing a reference to the unique record.

For example, you can use this option to reconcile a profile's country, specified in an uploaded file, with one of the countries available in the dedicated table of the Campaign database. 

Follow the steps to configure an **Enrichment** activity with a reconciliation link: 

1. Click the **Add link** button in the **Reconciliation** section.
1. Identify the data you want to create a reconciliation link with.

    * To create a reconciliation link with data from the Campaign database, select **Database schema** and choose the schema where the target is stored. 
    * To create a reconciliation link with data coming from the input transition, select **Temporary schema** and choose the orchestrated campaign transition where the target data is stored. 

1. The **Label** and **Name** fields are automatically populated based on the selected target schema. You can change their values if necessary.

1. In the **Reconciliation criteria** section, specify how you want to reconcile data from the source and destination tables:

    * **Simple join**: Reconcile a specific field from the source table with another field in the destination table. To do this, click the **Add join** button and specify the **Source** and **Destination** fields to use for the reconciliation.

        >[!NOTE]
        >
        >You can use one or more **Simple join** criteria, in which case they must all be verified so that the data can be linked together.

    * **Advanced join**: Use the query modeler to configure the reconciliation criteria. To do this, click the **Create condition** button then define your reconciliation criteria by building your own rule using AND and OR operations.

The example below shows an orchestrated campaign configured to create a link between Journey Optimizer profiles table and a temporary table generated a **Load file** activity. In this example, the **Enrichment** activity reconciliates both tables using the email address as reconciliation criteria.

![](../assets/enrichment-reconciliation.png)

### Enrichment with linked data {#link-example}

The example below shows an orchestrated campaign configured to create a link between two transitions. The first transitions targets profile data using a **Query** activity, while the second transition includes purchase data stored into a file loaded through a Load file activity.

![](../assets/enrichment-uc-link.png)

* The first **Enrichment** activity links the primary set (data from the **Query** activity) with the schema from the **Load file** activity. This allows us to match each profile targeted by the query with the corresponding purchase data.

    ![](../assets/enrichment-uc-link-purchases.png)

* A second **Enrichment** activity is added in order to enrich data from the orchestrated campaign table with the purchase data coming from the **Load file** activity. This allows us to use those data in further activities, for example, to personalize messages sent to the customers with information on their purchase.

    ![](../assets/enrichment-uc-link-data.png)


## Create links between tables {#create-links}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_enrichment_simplejoin"
>title="Link definition"
>abstract="Create a link between the working table data and Adobe Journey Optimizer. For example, if you load data from a file which contains the account number, country and email of recipients, you have to create a link towards the country table in order to update this information in their profiles."

The **[!UICONTROL Link definition]** section allows you to create a link between the working table data and Adobe Journey Optimizer. For example, if you load data from a file which contains the account number, country and email of recipients, you have to create a link towards the country table in order to update this information in their profiles.

There are several types of links available:

* **[!UICONTROL 1 cardinality simple link]**: Each record from the primary set can be associated with one and only one record from the linked data.
* **[!UICONTROL 0 or 1 cardinality simple link]**: Each record from the primary set can be associated with 0 or 1 record from the linked data, but not more than one.
* **[!UICONTROL N cardinality collection link]**: Each record from the primary set can be associated with 0, 1 or more (N) records from the linked data.

To create a link, follow these steps:

1. In the **[!UICONTROL Link definition]** section, click the **[!UICONTROL Add link]** button.

    ![](../assets/workflow-enrichment-link.png)

1. In the **Relation type** drop-down list, choose the type of link you want to create.

1. Identify the target you want to link the primary set to:

    * To link an existing table in the database, choose **[!UICONTROL Database schema]** and select the desired table from the **[!UICONTROL Target schema]** field.
    * To link with data from the input transition, choose **Temporary schema** and select the transition whose data you want to use.

1. Define the reconciliation criteria to match data from the primary set with the linked schema. There are two types of joins available:

    * **Simple join**: Select a specific attribute to match data from the two schemas. Click **Add join** and select the **Source** and **Destination** attributes to use as reconciliation criteria. 
    * **Advanced join**: Create a join using advanced conditions. Click **Add join** and click the **Create condition** button to open the query modeler.

A workflow example using links is available in the [Examples](#link-example) section.

## Add offers {#add-offers}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_enrichment_offer_proposition"
>title="Offer proposition"
>abstract="The Enrichment activity allows you to add offers for each profile."

The **[!UICONTROL Enrichment]** activity allows you to add offers for each profile.

To do so, follow the steps to configure an **[!UICONTROL Enrichment]** activity with an offer: 

1. In the **[!UICONTROL Enrichment]** activity, at the **[!UICONTROL Offer proposition]** section, click on the **[!UICONTROL Add offer]** button

    ![](../assets/enrichment-addoffer.png)

1. You have two choices for the offer selection :

    * **[!UICONTROL Search for the best offer in category]** : check this option and specify the offer engine call parameters (offer space, category or theme(s), contact date, number of offers to keep). The engine will calculate the best offer(s) to add according to these parameters. We recommend completing either the Category or the Theme field, rather than both at the same time.

        ![](../assets/enrichment-bestoffer.png)

    * **[!UICONTROL A predefined offer]** : check this option and specify an offer space, a specific offer, and a contact date to directly configure the offer that you would like to add, without calling the offer engine.

        ![](../assets/enrichment-predefinedoffer.png)

1. After selecting your offer, click on **[!UICONTROL Confirm]** button.

You can now use the offer in the delivery activity.



### Using the offers from Enrichment activity

Within an orchestrated campaign, if you want to use the offers you get from an enrichment activity in your delivery, follow the steps below:

1. Open the delivery activity and go in the content edition. Click on **[!UICONTROL Offers settings]** button and select in the drop-down list the **[!UICONTROL Offers space]** corresponding to your offer. 
If you want to to view only offers from the enrichment activity, set the number of **[!UICONTROL Propositions]** to 0, and save the modifications.

    ![](../assets/offers-settings.png) 

1. In the Email Designer, when adding a personalization with offers, click on the **[!UICONTROL Propositions]** icon, it will display the offer(s) you get from the **[!UICONTROL Enrichment]** activity. Open the offer you want to choose by clicking on it.

    ![](../assets/offers-propositions.png) 

    Go in **[!UICONTROL Rendering functions]** and choose **[!UICONTROL HTML rendering]** or **[!UICONTROL Text rendering]** according to your needs.

    ![](../assets/offers-rendering.png) 

>[!NOTE]
>
>If you choose to have more than one offer in the **[!UICONTROL Enrichment]** activity at the **[!UICONTROL Number of offers to keep]** option, all the offers are displayed when clicking on the **[!UICONTROL Propositions]** icon.

-->