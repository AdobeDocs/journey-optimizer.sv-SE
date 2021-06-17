---
title: Körning av övervakarmeddelande
description: Läs riktlinjerna för övervakning
feature: Övervakning
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Meddelandeövervakning {#monitor-message-execution}

[!DNL Journey Optimizer] ger möjlighet att övervaka meddelanden som är publicerade och utlösta för att vara säkra på att meddelandena körs, skickas och levereras. Du kan se hur dina meddelanden fungerar över resor <!--and APIs--> i realtid från listan **[!UICONTROL Executions]**.

Om du vill komma åt den här listan går du till startsidan för **[!DNL Journey Optimizer]**, väljer **[!UICONTROL Messages]** och klickar på fliken **[!UICONTROL Executions]**.

På den här fliken finns två vyer: **[!UICONTROL Live view]** och **[!UICONTROL Global view]**.

* På fliken **[!UICONTROL Live view]** finns en **realtidsöversikt över alla utförda meddelanden** som utlöses av en eller flera [resor](building-journeys/journey.md) **under de senaste 24 timmarna enbart**.

   ![](assets/message-execution-tab-live.png)

   Den här listan uppdateras automatiskt var sextio sekund. Om ingen körning utfördes de senaste 24 timmarna för ett specifikt meddelande visas null-värden (0) för det meddelandet i alla kolumner.

* På fliken **[!UICONTROL Global view]** finns en **översikt över alla meddelanden som körs** och som utlöses av en eller flera [resor](building-journeys/journey.md) **sedan meddelandets startdatum**.

   ![](assets/message-execution-tab-global.png)

   Den här listan uppdateras automatiskt var nittio minut. Data sammanställs över tid sedan varje meddelandes startdatum.

Om ett meddelande publiceras men ännu inte aktiveras av en resa, visas det inte på någon av flikarna. Endast följande element visas:
* Meddelanden som har utlösts men ännu inte startats (väntar).
* Meddelanden som har utlösts och som körs (pågående).

<!--For multichannel messages, one row per channel is displayed for each message. STILL VALID? looks like NOT-->

>[!NOTE]
>
>Om ett meddelande har använts på flera resor visas en rad per resa för varje körning.

<!--![](assets/message-execution-multichannel.png)-->

<!--If a message has been used in several journeys, the **[!UICONTROL Source]** column displays **[!UICONTROL Multiple]**.-->

Som standard visas meddelandena med början från det senaste körningsdatumet. Klicka på ikonen **[!UICONTROL Filters]** för att söka efter meddelandena efter kanal, startdatum och/eller slutdatum.

![](assets/message-execution-tab-filters.png)

Med den andra kolumnen i <!--**[!UICONTROL Quick action]**-->kan du öppna motsvarande [meddelande](create-message.md) och komma åt [Live-rapporten](reports/live-report.md) om du är i **[!UICONTROL Live view]** eller [Global Report](reports/global-report.md) om du är i **[!UICONTROL Global view]**.

![](assets/message-execution-open-live-report.png)

För varje meddelandekörning visas ett antal indikatorer:

* **[!UICONTROL Message label]**: Meddelanderubrik som du definierade när du  [skapade meddelandet](create-message.md). Körnings-ID, som genereras automatiskt, visas inom parentes.

   <!--**[!UICONTROL Execution ID]**: Automatically generated identifier.
  **[!UICONTROL Source]**: Name of the journey leveraging that message.-->

* **[!UICONTROL Journey - Version - Action]**: Namn på den resa som utnyttjar meddelandet, version av resan och etikett på den åtgärd som drar nytta av meddelandet under resan.

* **[!UICONTROL Status]**: Status för meddelandekörning.  <!--List all the possible statuses? For now only Live status? The user cannot stop or cancel the execution. TBC by Fred-->

* **[!UICONTROL Start date]**: Datum och tid när meddelandet har körts från resan.

   <!--Targeted: Number of targeted profiles for each message execution. To come?-->

* **[!UICONTROL Excluded]**: Antal profiler som har uteslutits från det ursprungliga målet på grund av undantagsregler.

* **[!UICONTROL Sent]**: Antal meddelanden som har skickats.

* **[!UICONTROL Delivered]**: Antal meddelanden som levererats i mottagarens postlåda (e-post) eller enhet (push) utan att generera ett studs eller något annat leveransfel.

* **[!UICONTROL Bounces]**: Antal meddelanden som inte kan levereras på grund av ett leveransfel. [Läs mer om studsar](suppression-list.md).

* **[!UICONTROL Opens]**: Antal meddelanden som har öppnats.

* **[!UICONTROL Clicks]**: Antal klick på länkar i ett e-postmeddelande.

   >[!NOTE]
   >
   >Klickningar finns inte för push-meddelanden: När en användare klickar på ett push-meddelande öppnas programmet, som bara kan betraktas som en öppen fil.

* **[!UICONTROL Errors]**: Antal meddelanden som inte kan skickas på grund av ett tekniskt fel.

* **[!UICONTROL Spam complaints]**: Antal meddelanden som har markerats som skräppost av mottagare. [Läs mer om klagomål](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html#metrics-for-deliverability).

Om du klickar på varje hyperlänk öppnas motsvarande meddelandesammanfattningsvy. [Läs mer om meddelanden](create-message.md).
