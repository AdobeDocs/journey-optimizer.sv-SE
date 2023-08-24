---
solution: Journey Optimizer
product: journey optimizer
title: Utsändningslistor
description: Lär dig hur du använder startlistor i Journey Optimizer
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
keywords: utsädeslista, seedlist, seed, configuration
source-git-commit: 1276aa334a057de1a14b7772d07dd9e2ac4f614f
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 3%

---

# Använd dirigerade listor {#seed-lists}

Seed-listor i [!DNL Journey Optimizer] gör att du automatiskt kan inkludera specifika dirigerade adresser i dina leveranser.

>[!CAUTION]
>
>Den här funktionen gäller för närvarande bara för e-postkanalen.

Fröadresser används för mottagare i målgruppen som inte matchar dess definierade villkor. På så sätt kan mottagare som ligger utanför leveransomfånget ta emot leveransen, precis som andra målmottagare gör.

Seed-adresser är inte riktiga profiler eller testprofiler eftersom de inte innehåller någon profilinformation. De är bara mottagare som tillhör interna intressenter som lagras i systemet. När de väljs ut i en viss kampanj eller resa inkluderas de vid leveranstillfället, vilket innebär att de får en kopia av leveransen i försäkringssyfte.

* Genom att ta emot leveranser samtidigt och under samma förhållanden som era kunder kan ni med hjälp av utsädeslistor övervaka de e-postkopior som skickas ut för att säkerställa att alla visningsformat, bilder och länkar är korrekta samt hålla reda på de faktiska meddelanden som skickas till mottagarna.

  Exempel:

+++ Om du är marknadschef:

  Ni vill att alla teammedlemmar ska få kopior av skickade meddelanden samtidigt som era kunder. På så sätt kan teamet se till att meddelanden skickas ut med den förväntade layouten, aktiva URL:er, korrekt text och bilder - allt som planerat före körningen.

+++

+++ Om du är produktägare:

  Ni måste hålla reda på faktiska meddelanden som skickas till kunderna. Ert team och ert ledarskap kan vara intresserade av vissa kampanjer och behöver läggas till på ad hoc-basis för att kunna ta emot kopior av meddelanden vid leveranstillfället.

+++

* En annan orsak till att du använder listor med startsidor är att du skyddar din sändlista. Genom att infoga dirigerade adresser i din e-postlista kan du lägga märke till om de används av en tredje part, eftersom de dirigerade adresserna som finns där kommer att få leveranserna som skickas till din e-postlista.

## Åtkomst till startlistor {#access-seed-lists}

Om du vill få tillgång till de startlistor som redan skapats går du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** och markera **[!UICONTROL Seed list]**.

>[!CAUTION]
>
>Behörigheterna att visa, exportera och hantera dirigerade listor är begränsade till [Reseadministratörer](../administration/ootb-product-profiles.md#journey-administrator). Läs mer om hantering [!DNL Journey Optimizer] användarrättigheter i [det här avsnittet](../administration/permissions-overview.md).

![](assets/seed-list-access.png)

Du kan söka efter dirigerade listor efter namn och/eller filtrera den användare som skapade listan eller på det datum listan skapades. När du har valt det här alternativet kan du rensa filtret som visas högst upp i listan.

![](assets/seed-list-filtering.png)

Använd **[!UICONTROL Delete]** om du vill ta bort en post permanent.

>[!CAUTION]
>
>Det går inte att ta bort en startvärdeslista som används i en aktiv [kampanj](../campaigns/review-activate-campaign.md) eller [resa](../building-journeys/publishing-the-journey.md). Du måste inaktivera kampanjen/resan eller redigera den för att använda en annan yta som inte har startvärdeslistan markerad. [Läs mer om hur du använder en startvärdeslista](#use-seed-list)

Du kan klicka på ett namn på en startlista om du vill redigera den. <!--Use the **[!UICONTROL Edit]** button to edit a seed list.-->

## Skapa en startvärdeslista {#create-seed-list}

>[!CONTEXTUALHELP]
>id="ajo_seed_list_details"
>title="Definiera din startvärdeslista"
>abstract="Fyll i informationen i listan över utsädeslistor för att automatiskt ta med särskilda adresser i leveranserna. Dessa adresser kommer att inkluderas vid leveranstillfället och kommer att få en exakt kopia av leveransen i försäkringssyfte."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html" text="Vad är startlistor?"

>[!CONTEXTUALHELP]
>id="ajo_seed_addresses"
>title="Ange de dirigerade adresser som ska användas"
>abstract="Lägg till de dirigerade adresser som automatiskt kommer att inkluderas i leveranserna. Du kan antingen importera en CSV-fil eller ange e-postadresser manuellt."

Följ stegen nedan för att skapa en startvärdeslista.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL Seed list]** -menyn.

1. Markera knappen **[!UICONTROL Create seed list]**.

   ![](assets/seed-list-create-button.png)

1. Fyll i detaljerna. Börja med att lägga till ett namn.

   ![](assets/seed-list-details.png)

   >[!NOTE]
   >
   >Namn måste börja med en bokstav (A-Z) och endast innehålla alfanumeriska tecken eller specialtecken ( _, ., -).

1. Markera kanalen. För närvarande är endast e-postkanalen tillgänglig.

1. Välj en testprofil. Eftersom dirigerade adresser inte innehåller någon profilinformation, kommer den här testprofilen endast att användas för att visa personaliseringsdata i det meddelande som skickas till dirigerade adresser.

   >[!NOTE]
   >
   >Det går bara att välja en testprofil åt gången.

1. Lägg till de dirigerade adresser som du vill skicka leveranser till. Du kan antingen importera en CSV-fil eller ange e-postadresser manuellt.

   ![](assets/seed-list-email-addresses.png)

   >[!NOTE]
   >
   >Du kan kombinera båda alternativen, men det totala antalet adresser i en startvärdeslista får inte överstiga 50.

1. Klicka på **[!UICONTROL Create]** för att bekräfta. Listan med nyskapade startvärden visas i [Skärm för lista med startsidor](#access-seed-lists).

## Använd en startlista i en kampanj eller resa {#use-seed-list}

Nu när din startlista har skapats kan du använda den i alla kampanjer och under alla resor för att inkludera motsvarande startadresser i leveranserna. För att göra detta, följ nedanstående steg.

>[!CAUTION]
>
>Meddelanden som skickas till dirigerade adresser inkluderas inte i rapporter.

1. Skapa en yta och välj **[!UICONTROL Email]** kanal. [Läs mer](../email/email-settings.md)

1. Välj önskad lista i listan [motsvarande avsnitt](../email/email-settings.md#seed-list).

   >[!NOTE]
   >
   >Det går bara att välja en startvärdeslista åt gången.

   ![](assets/seed-list-surface.png)

1. Skicka in ytan.

1. Skapa en [kampanj](../campaigns/create-campaign.md) eller en [resa](../building-journeys/journey-gs.md).

1. Välj **[!UICONTROL Email]** och väljer [yta](channel-surfaces.md) inklusive den utsädeslista som är relevant för dig.

   ![](assets/seed-list-campaign-email.png)

1. Aktivera [kampanj](../campaigns/review-activate-campaign.md) eller publicera [resa](../building-journeys/publishing-the-journey.md).

Varje gång ett e-postmeddelande skickas till kunderna via kampanjen eller resan får e-postadresserna på den valda startlistan också det på samma villkor, vid samma tidpunkt och med samma innehåll som målmottagarna.

>[!NOTE]
>
>För resor skickas e-postleveransen till dirigeringsadresserna endast under den första körningen.

