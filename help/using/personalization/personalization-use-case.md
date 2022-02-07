---
title: Personalisering använder case&colon; orderstatusmeddelande
description: Learn how to personalize a message with profile, offer decision, and context information.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 7d9c3d31-af57-4f41-aa23-6efa5b785260
source-git-commit: b43e3432ede1d4985e0a6b57b57c5efc3cf60c50
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Personalisering: orderstatusmeddelande {#personalization-use-case}

In this use case, you will see how to use multiple types of personalization in a single push notification message. Tre typer av personalisering kommer att användas:

* **Profil**: meddelandepersonalisering baserad på ett profilfält
* **Offer decision**: personalization based on offer decisioning variables
* **Kontext**: personalisering baserad på sammanhangsbaserade data från resan

Målet med det här exemplet är att skicka en händelse till [!DNL Journey Optimizer] varje gång en kundorder uppdateras. Därefter skickas ett push-meddelande till kunden med information om beställningen och ett personligt erbjudande.

I detta fall krävs följande krav:

* create and design a push notification message, without publishing it. Se detta [section](../messages/create-message.md).
* konfigurera en orderhändelse som innehåller ordernummer, status och artikelnamn. Se detta [section](../event/about-events.md).
* skapa ett beslut (tidigare kallat&quot;erbjudandeaktivitet&quot;), se denna [section](../offers/offer-activities/create-offer-activities.md).

## Steg 1 - Lägg till personalisering i profil {#add-perso}

1. Klicka på **[!UICONTROL Message]** och markera meddelandet.

   ![](assets/perso-uc.png)

1. Klicka på **Titel** fält.

   ![](assets/perso-uc2.png)

1. Type in the subject and add profile personalization. Använd sökfältet för att hitta profilens förnamnsfält. Placera markören där du vill infoga anpassningsfältet i ämnestexten och klicka på **+** ikon. Click **Save**.

   ![](assets/perso-uc3.png)

   >[!NOTE]
   >
   >Leave the message in draft. Publicera den inte än.

## Step 2 - Create the journey {#create-journey}

1. Klicka på **[!UICONTROL Journeys]** och skapa en ny resa.

   ![](assets/perso-uc4.png)

1. Add your entry event, a **Message** and an **End** activity.

   ![](assets/perso-uc5.png)

1. I **Meddelande** väljer du det meddelande som skapades tidigare. Click **Ok**.

   ![](assets/perso-uc6.png)

   A message is displayed to inform you that the entry event data and journey properties have been passed to the message.

   ![](assets/perso-uc7.png)

   >[!NOTE]
   >
   >Meddelandet visas med en varningsikon. Det beror på att meddelandet inte har publicerats än.

## Step 3 - Add personalization on contextual data {#add-perso-contextual-data}

1. From the **Message** activity, click the **Open the message** icon. The message opens in a new tab.

   ![](assets/perso-uc8.png)

1. Click the **Title** field.

   ![](assets/perso-uc9.png)

1. Select the **Context** category. Det här objektet är bara tillgängligt om en resa har passerat kontextdata till meddelandet. Click **Journey Orchestration**. Följande sammanhangsberoende information visas:

   * **Händelser**: den här kategorin grupperar alla fält från händelser som placerats före **Meddelande** verksamhet under resan.
   * **Reseegenskaper**: de tekniska fält som rör resan för en viss profil, t.ex. rese-ID eller de specifika fel som påträffats. Läs mer i [Journey Orchestration dokumentation](../building-journeys/expression/journey-properties.md).

   ![](assets/perso-uc10.png)

1. Expandera **Händelser** och leta efter ordernummerfältet som hör till din händelse. Du kan också använda sökrutan. Klicka på **+** om du vill infoga anpassningsfältet i ämnestexten. Click **Save**.

   ![](assets/perso-uc11.png)

1. Klicka nu på **Brödtext** fält.

   ![](assets/perso-uc12.png)

1. Skriv meddelandet och infoga från **Kontext** kategori, orderartikelns namn och orderförloppet.

   ![](assets/perso-uc13.png)

1. From the drop-down, select **Offer decision** to insert an offer decisioning variable. Välj placering och klicka på **+** -ikonen bredvid beslutet (tidigare kallat&quot;erbjudandeaktivitet&quot;) för att lägga till den i brödtexten.

   ![](assets/perso-uc14.png)

1. Klicka på validera för att kontrollera att det inte finns några fel och klicka sedan på **Spara**.

   ![](assets/perso-uc15.png)

1. Publicera meddelandet nu.

   ![](assets/perso-uc16.png)

## Steg 4 - Testa och publicera resan {#test-publish}

1. Öppna resan igen. Om resan redan är öppen ser du till att du uppdaterar sidan. Nu när meddelandet har publicerats ser du att det inte finns något fel under resan. Klicka på **Testa** och sedan klicka **Utlös en händelse**.

   ![](assets/perso-uc17.png)

1. Ange de olika värden som ska godkännas i testet. Test mode only works with test profiles. Profilidentifieraren måste motsvara en testprofil. Klicka **Skicka**.

   ![](assets/perso-uc18.png)

   Push-meddelandet skickas och visas på testprofilens mobiltelefon.

   ![](assets/perso-uc19.png)

1. Kontrollera att det inte finns något fel och publicera resan.
