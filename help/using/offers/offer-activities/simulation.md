---
title: Skapa simuleringar
description: Lär dig hur du skapar simuleringar
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: da9e898b-8e5d-43da-9226-5c9ccb78e174
source-git-commit: 39b52f39ec19c185d2cd95634a60e37f62a66f83
workflow-type: tm+mt
source-wordcount: '480'
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
   >Som standard är alla dedupliceringsflaggor aktiverade för simulering, vilket innebär att beslutsmotorn tillåter dubbletter och därmed kan göra samma förslag för flera beslut/placeringar. Läs mer på [!DNL Decisions] Egenskaper för API-begäran i [det här avsnittet](../api-reference/decisions-api/deliver-offers.md).<!--Deduplication note TO REMOVE WHEN SIMULATIONS V2 is on PROD-->

<!--SIMULATIONS V2

## Define simulation settings {#define-simulation-settings}

To edit the default settings for your simulations, follow the steps below.

1. Click **[!UICONTROL Settings]**.

    ![](../../assets/offers_simulation-settings.png)

1. In the **[!UICONTROL Deduplication]** section, you can choose to allow duplicate offers accross decisions and/or placements. It means that multiple decisions/placements may get assigned the same offer.

    ![](../../assets/offers_simulation-settings-deduplication.png)

    >[!NOTE]
    >
    >By default, all Deduplication flags are enabled for simulation, which means that the decision engine allows duplicates and thus can make the same proposition accross multiple decisions/placements. Learn more on the [!DNL Decisions] API request properties in [this section](../api-reference/decisions-api/deliver-offers.md).

1. In the **[!UICONTROL Response format]** section, you can choose to include metadata in the code view. Check the corresponding option, and select the metadata of your choice. They will be displayed in the request and response payloads when selecting **[!UICONTROL View code]**. Learn more in the [View simulation results](#simulation-results) section.

    ![](../../assets/offers_simulation-settings-response-format.png)

    >[!NOTE]
    >
    >When turning on the option, all items are selected by default.

1. Click **[!UICONTROL Save]**.-->

<!--NOT FOR SIMULATIONS V2

In the **[!UICONTROL API for simulation]** section, select the API you want to use: **[!UICONTROL Hub]** or **[!UICONTROL Edge]**.
Hub and Edge are two different end points for simulation data.

In the **[!UICONTROL Context data]** section, you can add as many elements as needed.

    >[!NOTE]
    >
    >This section is hidden if you select Edge API in the section above. Hub allows the use of Context Data, Edge does not.

Context data allows the user to add contextual data that could affect the simulation score.
For instance, let's say the customer has an offer for a discount on ice cream. In the rules for that offer, it can have logic that would rank it higher when the temperature is above 80 degrees. In simulation, the user could add context data: temperature=65 and that offer would rank lower, of they could add temperature=95 and that would rank higher.
-->

## Visa simuleringsresultat {#simulation-results}

När du har lagt till ett beslutsområde och valt en testprofil kan du visa resultatet.

1. Klicka på **[!UICONTROL View results]**.

   ![](../../assets/offers_simulation-view-results.png)

1. De bästa erbjudandena visas enligt den valda profilen för varje beslut.

   Välj ett erbjudande om du vill visa information om det.

   ![](../../assets/offers_simulation-offer-details.png)

   <!--
    SIMULATIONS V2
    1. Click **[!UICONTROL View code]** to display the request and response payloads. [Learn more](#view-code)-->

1. Välj en annan profil i listan om du vill visa resultatet av erbjudandebesluten för en annan testprofil.

1. Du kan lägga till, ta bort eller uppdatera beslutsomfattningarna så många gånger som behövs.

>[!NOTE]
>
>Varje gång du ändrar profiler eller uppdaterar beslutsomfattningar måste du uppdatera resultaten med **[!UICONTROL View results]** -knappen.

<!--
SIMULATIONS V2

## View code {#view-code}

To use the request payload outside of [!DNL Journey Optimizer] - for troubleshooting purpose for example, you can copy it by clicking the corresponding button on top of the code view.
    
>[!NOTE]
>
>You cannot copy the response payload.

Below is an example of code view:

    ```
    curl -X POST \
    'https://platform.adobe.io/data/core/ode/{CONTAINER_ID}/decisions' \
    -H 'Accept: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"' \
    -H 'Content-Type: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"' \
    -H 'Authorization: Bearer eyJhbGciOiJSUzI1NiIsIng1dSI6Imltc19uYTEtc3RnMS1rZXktMS5jZXIifQ.eyJpZCI6IjE2NDMxMzg3NDMxODlfOTIzY2ZjZjgtOWVkYy00MjE1LWJjODgtYmEyYTY2ZGIyYmMyX3VlMSIsInR5cGUiOiJhY2Nlc3NfdG9rZW4iLCJjbGllbnRfaWQiOiJhY3BfdWlfcGxhdGZvcm0iLCJ1c2VyX2lkIjoiNDhENTc0N0E2MDc3NkRERTBBNDk0MDFEQEFkb2JlSUQiLCJzdGF0ZSI6IntcInNlc3Npb25cIjpcImh0dHBzOi8vaW1zLW5hMS1zdGcxLmFkb2JlbG9naW4uY29tL2ltcy9zZXNzaW9uL3YxL1l6azNNakE0TXpNdFpXVTVaUzAwTVdOaExUZ3pNamd0TmpFM1pqZ3lOak5qTmpSakxTMDBPRVExTnpRM1FUWXdOemMyUkVSRk1FRTBPVFF3TVVSQVFXUnZZbVZKUkFcIn0iLCJhcyI6Imltcy1uYTEtc3RnMSIsImFhX2lkIjoiNDhENTc0N0E2MDc3NkRERTBBNDk0MDFEQEFkb2JlSUQiLCJjdHAiOjAsImZnIjoiV0VQQTNUSUY0UjRaQTZEWlBDUk1BMklBQ1U9PT09PT0iLCJzaWQiOiIxNjQzMDYwMDg0NzI2XzYzNGJkNDEzLWMwYTktNDA0NS1iNTM3LWRmMzgzYzU5ZGIxY191ZTEiLCJydGlkIjoiMTY0MzEzODc0MzE4OV9lYWMxOWY5Yi00ZjhhLTQ1NWMtOWVmMi1mNjYwNmQ0ODY4N2ZfdWUxIiwibW9pIjoiYmVjOTQzYzIiLCJwYmEiOiIiLCJvYyI6InJlbmdhKm5hMXItc3RnMSoxN2U5MmIzNzYzNCo2MEJEVjBGUlhOMFlRMkdHSkRON0E5Tk1HOCIsInJ0ZWEiOiIxNjQ0MzQ4MzQzMTg5IiwiZXhwaXJlc19pbiI6Ijg2NDAwMDAwIiwic2NvcGUiOiJvcGVuaWQsc2Vzc2lvbixyZWFkX29yZ2FuaXphdGlvbnMsYWRkaXRpb25hbF9pbmZvLnByb2plY3RlZFByb2R1Y3RDb250ZXh0LGFkZGl0aW9uYWxfaW5mby5yb2xlcyxhdWRpZW5jZW1hbmFnZXJfYXBpLEFkb2JlSUQiLCJjcmVhdGVkX2F0IjoiMTY0MzEzODc0MzE4OSJ9.TgZ998KHA4Zeoyq7b_NbPv8aPHb2cs9GgP3uJKrTbzosylKKRYqLpj_8HkloI-bFVQFCBCOWbCwtJtkcRIvFlQFruTr5bpMatPV8izEUVutO6smkYBFoGFYyEGuN5Xe97uOJZEHzFSWguGZtgttSrNhXr-j0hFloofjXDJXPB_911dzXALp5s15sd3HLH9XWTwwlqF_a5SMNDXaSj1800RxsB9bJ8_YL0x4pqQwjYJxRGMhiy7Y9IOpwogSBEiqCQitlKYgaO7yaJzFwhfyisnqM7_MWX2ETn-kGFEOoBHxXDTx9P2OPojzb8ChWQgmGf7Expyvtc1ke3nJkppzrxg' \
    -H 'x-api-key: {API_KEY}' \
    -H 'x-gw-ims-org-id: 5D1328435BF324E90A49402A@AdobeOrg' \
    -H 'x-sandbox-name: prod' \
    -D '{
      "xdm:propositionRequests": [
            {
                  "xdm:placementId": "xcore:offer-placement:1416f4109d9d292c",
                  "xdm:activityId": "xcore:offer-activity:1416f4aad9fd99d7",
                  "xdm:itemCount": 2
            }
      ],
      "xdm:profiles": [
            {
                  "xdm:identityMap": {
                        "email": [
                              {
                                    "xdm:id": "poyfair@adobe.com"
                              }
                        ]
                  }
            }
      ],
      "xdm:allowDuplicatePropositions": {
            "xdm:acrossActivities": true,
            "xdm:acrossPlacements": true
      },
      "xdm:responseFormat": {
            "xdm:includeMetadata": {
                  "xdm:activity": [],
                  "xdm:option": [],
                  "xdm:placement": []
            }
      }
    }'
    ```

>[!NOTE]
>
>When copying the request payload into your own code, make sure you replace CONTAINER_ID and API_KEY with your own values.-->

