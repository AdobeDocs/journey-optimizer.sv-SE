---
title: Personalisering - användningsfall
description: Personalisering - användningsfall
source-git-commit: cd1b07bbb4b247d1d8c0cc87be9e4bdad22377ed
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 0%

---


# Användningsexempel för personalisering {#personalization-use-case}

![](../assets/do-not-localize/badge.png)

I det här fallet får du se hur du använder flera typer av personalisering i ett enda push-meddelande. Tre typer av personalisering kommer att användas:

* **Profil**: meddelandepersonalisering baserad på ett profilfält
* **Erbjudandebeslut**: personalisering baserad på beslutsvariabler för erbjudanden
* **Kontext**: personalisering baserad på sammanhangsbaserade data från resan

Målet med det här exemplet är att skicka en händelse till Journey Optimizer varje gång en kundorder uppdateras. Därefter skickas ett push-meddelande till kunden med information om beställningen och ett personligt erbjudande.

I detta fall krävs följande krav:

* skapa och utforma ett push-meddelande, utan att publicera det. Se det här [avsnittet](../create-message.md).
* konfigurera en orderhändelse som innehåller ordernummer, status och artikelnamn. Se det här [avsnittet](../event/about-events.md).
* skapa ett beslut (tidigare kallat&quot;erbjudandeaktivitet&quot;), se [avsnittet](../offers/offer-activities/create-offer-activities.md).

## Steg 1 - Lägg till personalisering i profil

1. Klicka på menyn **[!UICONTROL Message]** och markera meddelandet.

   ![](assets/perso-uc.png)

1. Klicka på fältet **Titel**.

   ![](assets/perso-uc2.png)

1. Skriv in ämnet och lägg till profilanpassning. Använd sökfältet för att hitta profilens förnamnsfält. Placera markören där du vill infoga anpassningsfältet i ämnestexten och klicka på ikonen **+**. Klicka på **Spara**.

   ![](assets/perso-uc3.png)

   >[!NOTE]
   >
   >Lämna meddelandet i utkast. Publicera den inte än.

## Steg 2 - Skapa resan

1. Klicka på menyn **[!UICONTROL Journeys]** och skapa en ny resa.

   ![](assets/perso-uc4.png)

1. Lägg till en anmälningshändelse, ett **Meddelande** och en **Slut**-aktivitet.

   ![](assets/perso-uc5.png)

1. Markera det meddelande som skapats tidigare i aktiviteten **Meddelande**. Klicka på **OK**.

   ![](assets/perso-uc6.png)

   Ett meddelande visas som informerar dig om att informationen om tävlingshändelsen och reseegenskaperna har skickats till meddelandet.

   ![](assets/perso-uc7.png)

   >[!NOTE]
   >
   >Meddelandet visas med en varningsikon. Det beror på att meddelandet inte har publicerats än.

## Steg 3 - Lägg till personalisering på kontextuella data

1. Klicka på ikonen **Öppna meddelandet** i aktiviteten **Meddelande**. Meddelandet öppnas på en ny flik.

   ![](assets/perso-uc8.png)

1. Klicka på fältet **Titel**.

   ![](assets/perso-uc9.png)

1. Välj kategorin **Kontext**. Det här objektet är bara tillgängligt om en resa har passerat kontextdata till meddelandet. Klicka på **Journey Orchestration**. Följande sammanhangsberoende information visas:

   * **Händelser**: I den här kategorin grupperas alla fält från händelser som placerats före  **** meddelandeaktiviteten på resan.
   * **Reseegenskaper**: de tekniska fält som rör resan för en viss profil, t.ex. rese-ID eller de specifika fel som påträffats. Se [Journey Orchestration-dokumentationen](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/syntax/journey-properties.html#building-advanced-conditions-journeys).

   ![](assets/perso-uc10.png)

1. Expandera objektet **Händelser** och sök efter det ordernummerfält som är relaterat till händelsen. Du kan också använda sökrutan. Klicka på ikonen **+** för att infoga anpassningsfältet i ämnestexten. Klicka på **Spara**.

   ![](assets/perso-uc11.png)

1. Klicka nu på fältet **Body**.

   ![](assets/perso-uc12.png)

1. Skriv meddelandet och infoga orderobjektets namn och orderförloppet från kategorin **Kontext**.

   ![](assets/perso-uc13.png)

1. I listrutan väljer du **Erbjudandebeslut** om du vill infoga en variabel för offer decisioning. Markera placeringen och klicka på ikonen **+** bredvid beslutet (tidigare kallat &#39;offer activity&#39;) för att lägga till den i brödtexten.

   ![](assets/perso-uc14.png)

1. Klicka på validera för att kontrollera att det inte finns några fel och klicka sedan på **Spara**.

   ![](assets/perso-uc15.png)

1. Publicera meddelandet nu.

   ![](assets/perso-uc16.png)

## Steg 4 - Testa och publicera resan

1. Öppna resan igen. Om resan redan är öppen ser du till att du uppdaterar sidan. Nu när meddelandet har publicerats ser du att det inte finns något fel under resan. Klicka på knappen **Testa** och klicka sedan på **Utlös en händelse**.

   ![](assets/perso-uc17.png)

1. Ange de olika värden som ska godkännas i testet. Testläget fungerar bara med testprofiler. Profilidentifieraren måste motsvara en testprofil. Klicka på **Skicka**.

   ![](assets/perso-uc18.png)

   Push-meddelandet skickas och visas på testprofilens mobiltelefon.

   ![](assets/perso-uc19.png)

1. Kontrollera att det inte finns något fel och publicera resan.

