---
solution: Journey Optimizer
product: journey optimizer
title: Lägg till en inbyggd kanalåtgärd till en resa
description: Lär dig hur du lägger till en inbyggd kanalåtgärd till en resa
feature: Journeys, Activities, Channels Activity
topic: Content Management
role: User
level: Intermediate
keywords: resa, meddelande, push, sms, e-post, in-app, webb, innehållskort, kodbaserad upplevelse
exl-id: 4db07a9e-c3dd-4873-8bd9-ac34c860694c
source-git-commit: 994eac32591f4ca352d310bc06057bd20ea03886
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# Använd inbyggda kanalåtgärder {#add-a-message-in-a-journey}

>[!CONTEXTUALHELP]
>id="ajo_message_activity"
>title="Inbyggd kanalåtgärd"
>abstract="Journey Optimizer har inbyggda funktioner för kanalåtgärder. Du kan enkelt lägga till en utgående (e-post, SMS/MMS), push) eller inkommande (In-app, webb, kodbaserad upplevelse, innehållskort) aktivitet under resan och definiera inställningar och innehåll. Sedan utförs den och skickas i samband med resan."

[!DNL Journey Optimizer] har inbyggda funktioner för kanalåtgärder. Du kan enkelt lägga till en utgående (e-post, SMS/MMS), push) eller inkommande (In-app, webb, kodbaserad upplevelse, innehållskort) aktivitet under resan och definiera inställningar och innehåll. Sedan utförs den och skickas i samband med resan.

>[!NOTE]
>
>Du kan också ange specifika åtgärder för att skicka meddelanden till dig. [Läs mer](#recommendation)

Följ stegen nedan om du vill lägga till en inbyggd kanalåtgärd för en resa.

1. Starta din resa med en [Event](general-events.md)- eller [Read Audience](read-audience.md)-aktivitet.

1. Dra och släpp en utgående (**e-post**, **push**, **SMS**) eller en inkommande (**In-app**, **web**, **kodbaserad upplevelse**, **innehållskort**) från avsnittet **Åtgärder** till arbetsytan.

   ![](assets/journey-web-activity.png)

1. Konfigurera aktiviteten.

   * Lär dig de detaljerade stegen för att skapa meddelandeinnehåll enligt följande:

     <table style="table-layout:fixed">
      <tr style="border: 0;">
      <td>
      <a href="../email/create-email.md">
      <img alt="Lead" src="../assets/do-not-localize/email.jpg">
      </a>
      <div><a href="../email/create-email.md"><strong>Skapa e-post</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../push/create-push.md">
      <img alt="Sällan" src="../assets/do-not-localize/push.jpg">
      </a>
      <div>
      <a href="../push/create-push.md"><strong>Skapa push-meddelanden<strong></a>
      </div>
      <p>
      </td>
      <td>
      <a href="../sms/create-sms.md">
      <img alt="Validering" src="../assets/do-not-localize/sms.jpg">
      </a>
      <div>
      <a href="../sms/create-sms.md"><strong>Skapa textmeddelanden (SMS/MMS)</strong></a>
      </div>
      <p>
      </td>
      </tr>
      </table>

   * Lär dig de detaljerade stegen för att skapa en inkommande åtgärd på följande sätt:

     <table style="table-layout:fixed">
      <tr style="border: 0;">
      <td>
      <a href="../in-app/create-in-app.md">
      <img alt="Lead" src="../assets/do-not-localize/in-app.jpg">
      </a>
      <div><a href="../in-app/create-in-app.md"><strong>Skapa meddelanden i programmet</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../web/create-web.md">
      <img alt="Lead" src="../assets/do-not-localize/web-create.jpg">
      </a>
      <div><a href="../web/create-web.md"><strong>Skapa webbupplevelser</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../content-card/create-content-card.md">
      <img alt="Lead" src="../assets/do-not-localize/sms-config.jpg">
      </a>
      <div><a href="../content-card/create-content-card.md"><strong>Skapa innehållskort</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../code-based/create-code-based.md">
      <img alt="Sällan" src="../assets/do-not-localize/web-design.jpg">
      </a>
      <div>
      <a href="../code-based/create-code-based.md"><strong>Skapa kodbaserade upplevelser<strong></a>
      </div>
      <p>
      </td>
      </tr>
      </table>

     >[!NOTE]
     >
     >Varje inkommande meddelandeaktivitet levereras med en 3-dagars **Wait**-aktivitet. [Läs mer](../building-journeys/wait-activity.md#auto-wait-node)

## Rekommendation {#recommendation}

[!DNL Journey Optimizer] har inbyggd meddelandefunktion. Med anpassade åtgärder kan du emellertid konfigurera anslutningen för ett tredjepartssystem för att skicka meddelanden eller API-anrop.

* Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. [Läs mer](../action/action.md)

* Om du arbetar med Campaign och Journey Optimizer, se följande avsnitt:

   * [[!DNL Journey Optimizer] och Campaign v7/v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] och Campaign Standard](../action/acs-action.md)

## Uppdatera liveinnehåll{#update-live-content}

Ni kan uppdatera innehållet i en inbyggd kanalåtgärd i en direktresa.

Det gör du genom att öppna din direktresa, välja kanalaktiviteten och klicka på **Redigera innehåll**.

![](assets/add-a-message2.png)

Du kan dock inte ändra de attribut som används i personaliseringen, vare sig det är profilattribut eller kontextuella data (från händelse- eller reseegenskaper).

Om du ändrade sammanhangsberoende data visas följande felmeddelande: ERR_AUTHORING_JOURNEYVERSION_201

Om du har ändrat profilattribut visas följande felmeddelande: ERR_AUTHORING_JOURNEYVERSION_202

Observera att för aktiviteten i appen kan ändringar göras i innehållet medan resan pågår, men utlösare i appen kan inte ändras.
