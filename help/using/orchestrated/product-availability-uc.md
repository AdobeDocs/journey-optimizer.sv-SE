---
solution: Journey Optimizer
product: journey optimizer
title: Meddela användare om produkttillgänglighet
description: Meddela användare om produkttillgänglighet
feature: Use Cases
version: Campaign Orchestration
source-git-commit: 619db0a371b96fbe9480300a874839b7b919268d
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---

# Meddela användare om produkttillgänglighet {#product-availability-uc}

>[!BEGINSHADEBOX]

I det här användningsexemplet visas flernivåutskick: skapa ett distinkt e-postmeddelande för varje önskelisteobjekt genom att använda den e-postadress som lagras med det enskilda objektet i stället för mottagarposten. Detta gör att kunderna kan få separata meddelanden för varje produkt på deras önskelista även om de använder olika e-postadresser för olika artiklar.

>[!ENDSHADEBOX]

![](assets/notify-6.png){zoomable="yes"}

Designa ett butiksmeddelande som informerar kunderna när artiklar från deras önskelista blir tillgängliga igen. Det här meddelandet hjälper dem att engagera intresserade kunder på nytt och uppmuntrar dem att slutföra sitt köp medan lagret fylls på.

1. Börja med att skapa en ny kampanj som särskilt syftar till ett nytt engagemang i önskelistan. Detta garanterar att ert budskap fokuserar på kunder som redan har visat sig vilja köpa genom att spara produkter i deras önskelista.

   ![](assets/uc-reengagement-1.png){zoomable="yes"}

1. Fyll i **[!UICONTROL Campaign Settings]**, t.ex. kampanjnamn, beskrivning, start- och slutdatum och relevanta taggar.

1. Lägg till en **[!UICONTROL Build audience]**-aktivitet med önskelista som **[!UICONTROL Targeting dimension]**.

   ![](assets/notify-1.png){zoomable="yes"}

1. Lägg till villkoret om du bara vill inkludera önskelistor som har skapats under de senaste 36 månaderna.

   ![](assets/notify-2.png){zoomable="yes"}

1. Lägg till en **[!UICONTROL Change dimension]**-aktivitet för att växla tillbaka från önskelistor till respektive kunduppsättning för målinriktning.

   ![](assets/notify-3.png){zoomable="yes"}

1. När du har startat utkastläget kan du förhandsgranska målgruppen med önskningsinformation. Om du vill ha mer information klickar du på ett utdataresultat och väljer **[!UICONTROL Preview results]**.

   Här visas både mottagare och deras Önsklisteobjekt. Vissa kunder har flera Önsklisteobjekt och, genom att skicka flera nivåer, får ett separat e-postmeddelande för varje objekt. I vissa fall använder kunderna olika e-postadresser för att göra separata förfrågningar.

   ![](assets/notify-4.png){zoomable="yes"}

1. Om du vill kunna skicka ett separat e-postmeddelande för varje objekt kontrollerar du att [din e-postkonfiguration](../orchestrated/target-dimension.md) är inställd med `Recipients - email` som **[!UICONTROL Profile Target Dimension]** och `Wishlistitems` som **[!UICONTROL Secondary dimension]**.

   Välj sedan **[!UICONTROL Execution Address]** som `wishlist.email` på menyn **[!UICONTROL Secondary dimension]**. Varje önskelistepost utlöser ett separat e-postmeddelande med den e-postadress som lagras i önskelisteinformationen som den sekundära dimensionen.

   ![](assets/notify-5.png){zoomable="yes"}

1. Lägg till en **[!UICONTROL Email]**-aktivitet för att skapa ett meddelande om produkttillgänglighet. Klicka på **[!UICONTROL Edit content]** för att börja designa ditt innehåll.

   ➡️ [Läs mer om e-postanpassning](../email/content-from-scratch.md)

   ![](assets/notify-7.png){zoomable="yes"}

1. När kampanjen är testad och klar klickar du på **[!UICONTROL Publish]** för att göra den offentlig.

I den här samordnade kampanjen får kunden ett separat e-postmeddelande för var och en av sina önskelisteobjekt. Varje meddelande skickas till den specifika e-postadressen som är kopplad till önskelistan, där personligt innehåll hämtas från detaljerna för önskelisteobjektet.

