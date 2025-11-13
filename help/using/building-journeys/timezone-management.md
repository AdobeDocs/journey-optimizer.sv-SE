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
version: Journey Orchestration
source-git-commit: 7822e9662d03e6c6b2d5bc5ecb9ca85dc32f0942
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 1%

---

# Hantering av tidszoner {#timezone_management}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_time_zone"
>title="Tidszon"
>abstract="Välj resetid. När en fast tidszon används är det samma för alla personer som reser in på resan."


Du kan definiera en tidszon i [egenskaperna](../building-journeys/journey-properties.md#timezone) för din resa.

Om du vill visa färgegenskaperna väljer du pennikonen i skärmens övre högra hörn.

Den här tidszonen kommer att användas för varje aktivitet i resan som innehåller ett tidselement som:

* [Tidsvillkor](../building-journeys/condition-activity.md#time_condition)
* [Datumvillkor](../building-journeys/condition-activity.md#date_condition)
* [Anpassad väntetid](../building-journeys/wait-activity.md#custom)

<!--
* [Fixed date wait](../building-journeys/wait-activity.md#fixed_date)
-->

Du kan välja en [fast tidszon](#fixed-timezone) eller välja att använda tidszonen [som definieras i användarprofilen](#timezone-from-profiles).

## Definiera en fast tidszon {#fixed-timezone}

Tidszonen kan korrigeras. Rensa den fördefinierade tidszonen och välj en i listrutan. Om du använder en fast tidszon är den densamma för alla personer som deltar i resan.

Gör detta genom att markera en tidszon i rutan **[!UICONTROL Journey Properties]**.

![Listruta för val av tidszon i resans egenskaper](assets/journey72.png)

## Använd profilens tidszon {#timezone-from-profiles}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_profile_time_zone"
>title="Använd profilens tidszon"
>abstract="Markera kryssrutan om du vill använda tidszonen för realtidsprofilen i väntan- och villkorsaktiviteter. Om en tidszon har definierats för en profil hämtas den och används av resan. Annars är tidszonen den som definieras i tidszonsfältet ovan."

Om resans inträde-händelse har ett namnutrymme, vilket innebär att resan kan nå kundprofiltjänsten i realtid i Adobe Experience Platform, kanske du vill använda den tidszon som har definierats på profilnivån. Om du vill göra det går du till **Egenskaper** och markerar **Använd profiltidszon i väntetider och villkor**. Det här alternativet är inte markerat som standard.

Om en tidszon har definierats för en profil hämtas den och används av resan. Om så inte är fallet används tidszonen som definieras i tidszonsfältet.

![Profilens tidszonskonfiguration i datakällor för anpassad timing](assets/journey73.png)

>[!NOTE]
>
>Profilens tidszon fungerar med fältet **timeZone** som finns i fältgruppen **Inställningsinformation**.

## Använd tidszoner i uttryck {#timezone-in-expressions}

Start- och slutdatum för en resa kan inte länkas till en viss tidszon. De kopplas automatiskt till instansens tidszon.
