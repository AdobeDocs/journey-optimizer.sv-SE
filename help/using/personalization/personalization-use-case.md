---
title: Personalisering använder case&colon; orderstatusmeddelande
description: Lär dig hur du personaliserar ett meddelande med profil, offertbeslut och kontextinformation.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 7d9c3d31-af57-4f41-aa23-6efa5b785260
source-git-commit: 8a68d1e6d498ef3055c703d4e73471ab6d7bff40
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 0%

---

# Personalisering: orderstatusmeddelande {#personalization-use-case}

I det här fallet får du se hur du använder flera typer av personalisering i ett enda push-meddelande. Tre typer av personalisering kommer att användas:

* **Profil**: meddelandepersonalisering baserad på ett profilfält
* **Beslut om erbjudandet**: personalisering baserad på offer decisioning
* **Kontext**: personalisering baserad på sammanhangsbaserade data från resan

Målet med det här exemplet är att skicka en händelse till [!DNL Journey Optimizer] varje gång en kundorder uppdateras. Därefter skickas ett push-meddelande till kunden med information om beställningen och ett personligt erbjudande.

I detta fall krävs följande krav:

* skapa och utforma ett push-meddelande, utan att publicera det. Se detta [section](../messages/get-started-content.md).
* konfigurera en orderhändelse som innehåller ordernummer, status och artikelnamn. Se detta [section](../event/about-events.md).
* skapa ett beslut, se [section](../offers/offer-activities/create-offer-activities.md).

## Steg 1 - Lägg till personalisering i profil {#add-perso}

1. Klicka på **[!UICONTROL Message]** och markera meddelandet.

   ![](assets/perso-uc.png)

1. Klicka på **Titel** fält.

   ![](assets/perso-uc2.png)

1. Skriv in ämnet och lägg till profilanpassning. Använd sökfältet för att hitta profilens förnamnsfält. Placera markören där du vill infoga anpassningsfältet i ämnestexten och klicka på **+** ikon. Klicka **Spara**.

   ![](assets/perso-uc3.png)

   >[!NOTE]
   >
   >Lämna meddelandet i utkast. Publicera den inte än.

## Steg 2 - Skapa resan {#create-journey}

1. Klicka på **[!UICONTROL Journeys]** och skapa en ny resa.

   ![](assets/perso-uc4.png)

1. Lägg till ditt tävlingsbidrag och en **Meddelande** aktivitet.

   ![](assets/perso-uc5.png)

1. I **Meddelande** väljer du det meddelande som skapades tidigare. Klicka **OK**.

   ![](assets/perso-uc6.png)

   Ett meddelande visas som informerar dig om att informationen om tävlingshändelsen och reseegenskaperna har skickats till meddelandet.

   ![](assets/perso-uc7.png)

   >[!NOTE]
   >
   >Meddelandet visas med en varningsikon. Det beror på att meddelandet inte har publicerats än.

## Steg 3 - Lägg till personalisering på kontextuella data {#add-perso-contextual-data}

1. Från **Meddelande** aktivitet, klicka på **Öppna meddelandet** ikon. Meddelandet öppnas på en ny flik.

   ![](assets/perso-uc8.png)

1. Klicka på **Titel** fält.

   ![](assets/perso-uc9.png)

1. Välj **Sammanhangsberoende attribut** -menyn. Sammanhangsberoende attribut är bara tillgängliga om en resa har skickat kontextuella data till meddelandet. Klicka **Journey Orchestration**. Följande sammanhangsberoende information visas:

   * **Händelser**: den här kategorin grupperar alla fält från händelser som placerats före **Meddelande** verksamhet under resan.
   * **Reseegenskaper**: de tekniska fält som rör resan för en viss profil, t.ex. rese-ID eller de specifika fel som påträffats. Läs mer i [Journey Orchestration dokumentation](../building-journeys/expression/journey-properties.md).

   ![](assets/perso-uc10.png)

1. Expandera **Händelser** och leta efter ordernummerfältet som hör till din händelse. Du kan också använda sökrutan. Klicka på **+** om du vill infoga anpassningsfältet i ämnestexten. Klicka **Spara**.

   ![](assets/perso-uc11.png)

1. Klicka nu på **Brödtext** fält.

   ![](assets/perso-uc12.png)

1. Skriv meddelandet och infoga från **[!UICONTROL Contextual attributes]** -menyn, namnet på orderobjektet och orderförloppet.

   ![](assets/perso-uc13.png)

1. Välj **Erbjudandebeslut** om du vill infoga en offer decisioning-variabel. Välj placering och klicka på **+** -ikonen bredvid beslutet om att lägga till den i brödtexten.

   ![](assets/perso-uc14.png)

1. Klicka på validera för att kontrollera att det inte finns några fel och klicka sedan på **Spara**.

   ![](assets/perso-uc15.png)

1. Publicera meddelandet nu.

   ![](assets/perso-uc16.png)

## Steg 4 - Testa och publicera resan {#test-publish}

1. Öppna resan igen. Om resan redan är öppen ser du till att du uppdaterar sidan. Nu när meddelandet har publicerats ser du att det inte finns något fel under resan. Klicka på **Testa** och sedan klicka **Utlös en händelse**.

   ![](assets/perso-uc17.png)

1. Ange de olika värden som ska godkännas i testet. Testläget fungerar bara med testprofiler. Profilidentifieraren måste motsvara en testprofil. Klicka **Skicka**.

   ![](assets/perso-uc18.png)

   Push-meddelandet skickas och visas på testprofilens mobiltelefon.

   ![](assets/perso-uc19.png)

1. Kontrollera att det inte finns något fel och publicera resan.
