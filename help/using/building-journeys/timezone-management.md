---
solution: Journey Optimizer
product: journey optimizer
title: Hantering av tidszoner
description: Läs mer om hantering av tidszoner
feature: Journeys, Profiles
topic: Content Management
role: User
level: Intermediate
keywords: tidszon, egenskaper, resa, villkor, tid, datum, anpassad
exl-id: 3bcc08d6-1210-4ff9-92f4-edee8285b469
source-git-commit: 21b53c72976d1a65651bc142e23ba847dc40a305
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Hantering av tidszoner {#timezone_management}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_time_zone"
>title="Tidszon"
>abstract="Välj resetid. När en fast tidszon används är det samma för alla personer som reser in på resan."


Du kan definiera en tidszon i dialogrutan [egenskaper](../building-journeys/journey-properties.md#timezone) av din resa.

Klicka på pennikonen i skärmens övre högra hörn för att få åtkomst till reseegenskaperna.

Den här tidszonen kommer att användas för varje aktivitet i resan som innehåller ett tidselement som:

* [Tidsvillkor](../building-journeys/condition-activity.md#time_condition)
* [Datumvillkor](../building-journeys/condition-activity.md#date_condition)
* [Anpassad väntetid](../building-journeys/wait-activity.md#custom)

<!--
* [Fixed date wait](../building-journeys/wait-activity.md#fixed_date)
-->

Du kan välja en [tidszon](#fixed-timezone) eller välj att använda tidszonen [definieras i användarprofilen](#timezone-from-profiles).

## Definiera en fast tidszon {#fixed-timezone}

Tidszonen kan korrigeras. Rensa den fördefinierade tidszonen och välj en i listrutan. Om du använder en fast tidszon är den densamma för alla personer som deltar i resan.

Om du vill göra det går du till **[!UICONTROL Journey Properties]** väljer du en tidszon.

![](assets/journey72.png)

## Använd profilens tidszon {#timezone-from-profiles}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_profile_time_zone"
>title="Använd profilens tidszon"
>abstract="Markera kryssrutan om du vill använda tidszonen för realtidsprofilen i väntan- och villkorsaktiviteter. Om en tidszon har definierats för en profil hämtas den och används av resan. Annars är tidszonen den som definieras i tidszonsfältet ovan."

Om resans inträde-händelse har ett namnutrymme, vilket innebär att resan kan nå kundprofiltjänsten i realtid i Adobe Experience Platform, kanske du vill använda den tidszon som har definierats på profilnivån. Gör så här: **Egenskaper**, kontrollera **Använd profilens tidszon i väntetider och villkor**. Det här alternativet är inte markerat som standard.

Om en tidszon har definierats för en profil hämtas den och används av resan. Om så inte är fallet används tidszonen som definieras i tidszonsfältet.

![](assets/journey73.png)

>[!NOTE]
>
>Tidszonen för profilen fungerar med **timeZone** fältet finns i **Inställningsinformation** fältgrupp.

## Använd tidszoner i uttryck {#timezone-in-expressions}

Start- och slutdatum för en resa kan inte länkas till en viss tidszon. De kopplas automatiskt till instansens tidszon.
