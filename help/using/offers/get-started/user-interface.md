---
title: Användargränssnitt för Erbjud bibliotek
description: Läs mer om användargränssnittet i Offer Library
feature: Decision Management
topic: Integrations
role: User
level: Beginner, Intermediate
exl-id: 722f9c3b-b505-48c0-b126-31a7a841c245
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 2%

---

# Erbjud användargränssnitt för bibliotek {#user-interface}

The **[!UICONTROL Decision management]** -avsnittet i den vänstra listen har två menyer som ger dig tillgång till funktioner för att hantera beslut:

Använd **[!UICONTROL Offers]** -meny för att hantera och leverera erbjudanden:


![](../assets/offers_menu.png)

* **[!UICONTROL Overview]**: Ny på [!DNL decision management]? Följ stegen på skärmen för att komma igång med att konfigurera ersättningar, erbjudanden och samlingar. När du redan känner till [!DNL decision management], får du en översikt över dina senaste erbjudanden, samlingar och beslut. [Läs mer](#overview)
* **[!UICONTROL Offers]**: Skapa och få tillgång till personliga erbjudanden och reserverbjudanden. Lär dig hur du skapar [erbjudanden](../offer-library/creating-personalized-offers.md) och [reserverbjudanden](../offer-library/creating-fallback-offers.md)
* **[!UICONTROL Collections]**: Ordna era erbjudanden i statiska och dynamiska samlingar. [Läs mer](../offer-library/creating-collections.md)
* **[!UICONTROL Decisions]**: Skapa och hantera beslut för att leverera erbjudanden. [Läs mer](../offer-activities/create-offer-activities.md)
* **[!UICONTROL Batch decisioning]**: Leverera offertbeslut till alla profiler inom en viss Adobe Experience Platform-målgrupp. [Läs mer](../batch-delivery.md)
* **[!UICONTROL Simulation]**: Validera din beslutslogik genom att simulera vilka erbjudanden som ska levereras till en testprofil för en viss placering. [Läs mer](../offer-activities/simulation.md)

Använd **[!UICONTROL Components]** meny för att skapa och hantera komponenter som krävs för att skapa erbjudanden och beslut:

![](../assets/offer_activities.png)

* **[!UICONTROL Placements]**: Skapa och hantera praktik där era erbjudanden visas. [Läs mer](../offer-library/creating-placements.md)
* **[!UICONTROL Collection qualifiers]**: Skapa och hantera samlingskvalificerare (kallas tidigare taggar) för att ordna och filtrera dina erbjudanden. [Läs mer](../offer-library/creating-tags.md)
* **[!UICONTROL Rules]**: Hantera villkoren för hur dina erbjudanden presenteras. [Läs mer](../offer-library/creating-decision-rules.md)
* **[!UICONTROL Ranking]**: Skapa och hantera rankningsformler för att avgöra vilket erbjudande som ska presenteras först för en viss placering. [Läs mer](../ranking/create-ranking-formulas.md)

>[!NOTE]
>
>Om du har problem med att komma åt beslutshanteringen eller vissa funktioner i den, bör du höra med en Admin-användare att du har fått de behörigheter som krävs. Se [Bevilja åtkomst till beslutsledning](starting-offer-decisioning.md#granting-acess-to-decision-management).

## Översikt {#overview}

När du är nybörjare på [!DNL decision management], **[!UICONTROL Overview]** hjälper dig steg för steg att börja bygga ditt första offertbeslut. Följ stegen på skärmen för att börja skapa praktik, erbjudanden och samlingar. När du är klar med de här första stegen uppmanas du att skapa offertbeslut.

>[!NOTE]
>
>De viktigaste stegen för att skapa erbjudanden och använda dem i ett beslut presenteras i [det här avsnittet](../offer-library/key-steps.md).

När du är mer bekant med [!DNL decision management] och du redan har skapat minst ett erbjudande-beslut, **[!UICONTROL Overview]** -fliken visar dina senaste erbjudanden, samlingar och beslut.

Klicka på ett erbjudande eller på ett beslut om du vill få direkt tillgång till den valda artikelns information.

Klicka på **[!UICONTROL View all]** för att komma åt erbjudandet, samlingen eller beslutslistorna.

![](../assets/overview_view-all.png)

## Söka efter och filtrera information {#search-and-filter-information}

Använd **sökfält** för att hitta ett specifikt objekt.

**Filter** Du kan också komma åt filen genom att klicka på filterikonen längst upp till vänster i listan. De gör att du kan filtrera de visade elementen enligt olika villkor. Du kan till exempel filtrera de placeringar som har skapats för e-postkommunikationskanalen och bildtypsinnehållet.

![](../assets/filters.png)

## Anpassa visad information {#customize-displayed-information}

Listor från beslutshanteringsmenyer kan anpassas med hjälp av konfigurationsknappen högst upp till höger i listorna.

På så sätt kan du välja vilken information som ska visas efter dina behov.

Observera att kolumnanpassning sparas för varje användare.

![](../assets/columns.png)

## Informationsrutan {#information-pane}

I de olika listorna väljer du ett element för att visa en informationsruta där du kan hämta information och utföra grundläggande åtgärder för elementet.

![](../assets/information-pane.png)

I erbjudandelistorna och beslutslistorna kan du även utföra massåtgärder för flera element. Välj önskade erbjudanden eller beslut och välj sedan den åtgärd som du vill utföra i informationsrutan.

Observera att du även kan duplicera ett befintligt erbjudande eller beslut för att skapa en kopia med **[!UICONTROL Draft]** status. Detta kan utföras antingen från informationsrutan eller från ett erbjudande eller ett besluts detaljerade vy.

## Ändringsloggar för erbjudanden och beslut {#changes-logs}

Med Erbjudandebiblioteket kan du visualisera alla ändringar som har gjorts i ett erbjudande eller ett beslut. Det gör du genom att öppna erbjudandet eller beslutet genom att klicka på namnet i listan och sedan välja **[!UICONTROL Change log]** -fliken.

Alla ändringar som har gjorts visas på den här skärmen, liksom namnet på användaren som utförde ändringarna.

![](../assets/change-logs.png)
