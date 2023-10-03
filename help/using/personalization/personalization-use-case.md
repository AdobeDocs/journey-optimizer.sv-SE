---
solution: Journey Optimizer
product: journey optimizer
title: Personalisering använder skiftläge&kolon; orderstatusmeddelande
description: Lär dig hur du personaliserar ett meddelande med profil, offertbeslut och kontextinformation.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, användningsfall, personalisering
exl-id: 7d9c3d31-af57-4f41-aa23-6efa5b785260
source-git-commit: c0afa3e2bc6dbcb0f2f2357eebc04285de8c5773
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Personalisering - användningsfall: orderstatusmeddelande {#personalization-use-case}

I det här fallet får du se hur du kan använda flera typer av personalisering i ett enda push-meddelande. Tre typer av personalisering kommer att användas:

* **Profil**: meddelandepersonalisering baserad på ett profilfält
* **Beslut om erbjudandet**: personalisering baserad på variabler för beslutshantering
* **Kontext**: personalisering baserad på kontextuella data från resan

Målet med det här exemplet är att skicka en händelse till [!DNL Journey Optimizer] varje gång en kundorder uppdateras. Därefter skickas ett push-meddelande till kunden med information om beställningen och ett personligt erbjudande.

I det här fallet krävs följande krav:

* konfigurera en orderhändelse som innehåller ordernummer, status och artikelnamn. Se detta [section](../event/about-events.md).
* skapa ett beslut, se [section](../offers/offer-activities/create-offer-activities.md).

## Steg 1 - Skapa resan {#create-journey}

1. Klicka på **[!UICONTROL Journeys]** och skapa en ny resa.

   ![](assets/perso-uc4.png)

1. Lägg till ditt tävlingsbidrag och en **Push** Åtgärdsaktivitet.

   ![](assets/perso-uc5.png)

1. Konfigurera och utforma push-meddelanden. Se detta [section](../push/create-push.md).

## Steg 2 - Lägg till personalisering i profil {#add-perso}

1. I **Push** aktivitet, klicka **Redigera innehåll**.

1. Klicka på **Titel** fält.

   ![](assets/perso-uc2.png)

1. Skriv in ämnet och lägg till profilanpassning. Använd sökfältet för att hitta profilens förnamnsfält. Placera markören där du vill infoga anpassningsfältet i ämnestexten och klicka på **+** -ikon. Klicka **Spara**.

   ![](assets/perso-uc3.png)

## Steg 3 - Lägg till personalisering på kontextuella data {#add-perso-contextual-data}

1. I **Push** aktivitet, klicka **Redigera innehåll** och klicka på **Titel** fält.

   ![](assets/perso-uc9.png)

1. Välj **Sammanhangsberoende attribut** -menyn. Sammanhangsberoende attribut är bara tillgängliga om en resa har skickat kontextuella data till meddelandet. Klicka **Journey Orchestration**. Följande sammanhangsberoende information visas:

   * **Händelser**: den här kategorin grupperar alla fält från händelser som placerats före kanalåtgärdsaktiviteten på resan.
   * **Reseegenskaper**: de tekniska fält som rör resan för en viss profil, t.ex. rese-ID eller de specifika fel som påträffats. Läs mer i [Journey Orchestration dokumentation](../building-journeys/expression/journey-properties.md).

   ![](assets/perso-uc10.png)

1. Expandera **Händelser** och leta efter ordernummerfältet som hör till din händelse. Du kan också använda sökrutan. Klicka på **+** om du vill infoga anpassningsfältet i ämnestexten. Klicka **Spara**.

   ![](assets/perso-uc11.png)

1. Klicka nu på **Brödtext** fält.

   ![](assets/perso-uc12.png)

1. Skriv meddelandet och infoga från **[!UICONTROL Contextual attributes]** -menyn, namnet på orderobjektet och orderförloppet.

   ![](assets/perso-uc13.png)

1. Välj **Erbjudandebeslut** om du vill infoga en decimalvariabel. Markera placeringen och klicka på **+** -ikonen bredvid beslutet om att lägga till den i brödtexten.

   ![](assets/perso-uc14.png)

1. Klicka på validera för att kontrollera att det inte finns några fel och klicka sedan på **Spara**.

   ![](assets/perso-uc15.png)

## Steg 4 - Testa och publicera resan {#test-publish}

1. Klicka på **Testa** knapp och sedan klicka **Utlös en händelse**.

   ![](assets/perso-uc17.png)

1. Ange de olika värden som ska godkännas i testet. Testläget fungerar bara med testprofiler. Profilidentifieraren måste motsvara en testprofil. Klicka **Skicka**.

   ![](assets/perso-uc18.png)

   Push-meddelandet skickas och visas på testprofilens mobiltelefon.

   ![](assets/perso-uc19.png)

1. Kontrollera att det inte finns något fel och publicera resan.
