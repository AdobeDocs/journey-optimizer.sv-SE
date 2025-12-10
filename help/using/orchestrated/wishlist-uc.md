---
solution: Journey Optimizer
product: journey optimizer
title: Skicka uppdateringar av önskelisteobjekt
description: Skicka uppdateringar av önskelisteobjekt
version: Campaign Orchestration
source-git-commit: 51c8c9282cb6eb9cdbd310d8f263d7973f28bbf0
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# Skicka uppdateringar av önskelisteobjekt {#wishist-uc}

>[!BEGINSHADEBOX]

I det här exemplet används ett **Önsklisteschema**, men samma metod gäller för alla entiteter med en-till-många-relation till **mottagare**, till exempel **Inköp**, **Prenumerationer** eller ett anpassat schema där varje mottagare kan ha flera associerade poster.

**Scheman som behövs för det här användningsfallet:**

* **Mottagare**: används som måldimension
* **Önsklisteobjekt**: med fält: `creationDate`, `product`, `Wishlistid`
* **Produkt**: med fält: `description`, `priceref`, `imageurl`
* **AbandonedCarts** (valfritt): med fält: `lastmodified`

➡️ [Lär dig konfigurera modellbaserade scheman](gs-schemas.md)

>[!ENDSHADEBOX]

![](assets/uc-reengagement-11.png){zoomable="yes"}

Denna samordnade kampanj fokuserar på att engagera besökarna på nytt genom att påminna dem om produkter som sparats i deras önskelista. Med Campaign Orchestration kan ni definiera målgruppen med villkor som baseras på önskelisteaktivitet, vilket får besökarna att konvertera igen.

1. Börja med att skapa en ny kampanj som särskilt syftar till ett nytt engagemang i önskelistan. Detta hjälper er att fokusera på budskap till kunder som har visat att de vill köpa genom att spara artiklar.

   ![](assets/uc-reengagement-1.png){zoomable="yes"}

1. Fyll i dina **kampanjinställningar**.

1. Lägg till en **[!UICONTROL Build audience]**-aktivitet för att identifiera den grupp kunder som ska målas baserat på önskelistans beteende.

   ![](assets/uc-reengagement-2.png){zoomable="yes"}

1. Ange en beskrivande **[!UICONTROL Label]** för den här målgruppen och välj **[!UICONTROL Recipients]** som **[!UICONTROL Targeting dimension]**. Klicka sedan på **[!UICONTROL Continue]** för att konfigurera målgruppen.

1. Klicka på **[!UICONTROL Add condition]** om du vill förfina målgruppen genom att skapa följande villkor:

   `WishlistItems Exist such as (creationDate greater than or equal to 36 months ago) AND (product is not empty`
ELLER
   `AbandonedCarts Exist such as lastmodified greater than or equal to 36 months ago`

   Den här målgruppen baseras på mottagare som har en önskelista, innehåller artiklar med produktbilder eller har en övergiven varukorg inom den angivna tidsramen.

   ![](assets/uc-reengagement-3.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Calculate]** för att se antalet profiler som påverkas av dessa villkor och **[!UICONTROL View results]** för att kontrollera detaljer för varje villkor och bekräfta att målgruppen matchar ditt målsegment.

   ![](assets/uc-reengagement-4.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Confirm]**.

1. Lägg till en **[!UICONTROL Enrichment]**-aktivitet för att anpassa kampanjen med **Önsklista** och **produktinformation**.

   ![](assets/uc-reengagement-5.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Add enrichment data]**.

1. Åtkomst till `Targeting dimension > Wishlistitems > Wishlistid`.

   ![](assets/uc-reengagement-6.png){zoomable="yes"}

1. Välj hur data samlas in, i det här fallet **[!UICONTROL Collect data]**, för att samla in önskelisteinformation för din målgrupp.

1. Välj antalet rader som ska hämtas. Som standard hämtas tre artiklar per önskelista, men detta kan justeras beroende på kampanjens behov för att markera fler eller färre produkter.

1. Klicka på **[!UICONTROL Add attribute]** om du vill skapa följande tre attribut:

   * `Product > description`
   * `Product > priceref`
   * `Product > imageurl`

   Detta berikar meddelandet med detaljerad produktinformation för att driva konverteringar.

   ![](assets/uc-reengagement-7.png){zoomable="yes"}

1. Lägg till en e-postaktivitet för att skapa ett personligt anpassat återengagemangsmeddelande för varje kund. Klicka på **[!UICONTROL Edit content]** för att börja designa ditt innehåll.

   ➡️ [Läs mer om e-postanpassning](../email/content-from-scratch.md)

   ![](assets/uc-reengagement-8.png){zoomable="yes"}

1. När du är klar med e-postmeddelandet sparar och kör du kampanjen i utkastläge genom att klicka på **[!UICONTROL Start]** från din samordnade kampanj.

1. När du har startat utkastläget kan du förhandsgranska målgruppen med önskningsinformation.

   Om du vill ha mer information klickar du på ett utdataresultat och väljer **[!UICONTROL Preview results]**.

   ![](assets/uc-reengagement-10.png){zoomable="yes"}

När kampanjen har slutförts kan vi utforska våra rapporter, som ger oss en robust uppsättning data och nyckeltal om hur vår kampanj fungerar.

➡️ [Läs mer om rapportering](../reports/campaign-global-report-cja.md)
