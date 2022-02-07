---
title: Skapa en prenumerationslista
description: Lär dig hur du ställer in en prenumerationslista i Journey Optimizer
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
hidefromtoc: true
hide: true
exl-id: 5e5419a0-5121-4aa7-a975-b1f08e2918c9
source-git-commit: 4609b071e6011bb2c28156b9638f40b7d6f29249
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 2%

---

# Prenumerationslistor {#create-subscription-list}

## Vad är en prenumerationslista? {#subscription-list-definition}

En prenumerationstjänst avser marknadsföringsvaror och marknadsföringstjänster som tillhandahålls kunder som har valt att ta emot meddelanden om ett visst ämne/evenemang/intresse/osv. fortlöpande. I [!DNL Journey Optimizer], samlas dessa kunder i en prenumerationslista.

En prenumerationstjänst kan vara:

* ett nyhetsbrev, till exempel: &quot;Löpande serier&quot;
* en händelse, till exempel: &quot;Summit 2021&quot;
* ett webbinarium, till exempel: &quot;Läs mer om kryptering&quot;
* intresse för en viss produkt/sport/tjänst/etc., t.ex. &quot;Intresserad av att köpa ett hus de kommande 12 månaderna&quot;
* en inställning för hur meddelanden ska meddelas, till exempel: &quot;Få nya låtmeddelanden via e-post&quot;

Profilerna kan läggas till i en prenumerationslista via en [landningssida](create-lp.md). Ett exempel presenteras i [det här avsnittet](lp-use-cases.md#subscription-to-a-service).

## Definiera en prenumerationslista {#define-subscription-list}

Följ stegen nedan för att skapa en prenumerationslista.

1. Välj **[!UICONTROL Customer]** > **[!UICONTROL Subscription list]**.

   ![](../assets/lp_subscription-lists.png)

1. Markera knappen **[!UICONTROL Create subscription list]**.

   ![](../assets/lp_create-subscription-list.png)

1. Lägg till ett namn och en beskrivning. Dessa fält är obligatoriska.

1. Du kan definiera ett startdatum och ett slutdatum.

   ![](../assets/lp_subscription-list-dates.png)

1. Klicka på **[!UICONTROL Save]**.

I listan visas alla prenumerationslistor som skapats. Du kan filtrera dem baserat på skapandedatum eller ändringsdatum och deras status.

![](../assets/lp_subscription-filters.png)

Möjliga statusvärden är följande:

* **[!UICONTROL Not started]**: Du definierade ett startdatum som är senare än den aktuella dagen. De prenumererade profilerna kommer ännu inte att få några meddelanden om den här prenumerationslistan.
* **[!UICONTROL Live]**: Den aktuella dagen ligger mellan prenumerationslistans startdatum och slutdatum, eller så har du inte definierat slut-/startdatum, vilket innebär att prenumerationslistan alltid är aktiv.
* **[!UICONTROL Expired]**: Slutdatumet har passerats och prenumerationslistan är därför inte längre giltig. Prenumerationsprofiler får inte mer information om prenumerationslistan.

När prenumerationslistan har skapats kan du använda den på en landningssida. De profiler som anmäler sig via landningssidans formulär läggs till i listan. [Läs mer](design-lp.md)

Du kan också använda prenumerationslistor som segment när [byggnadsresor](../building-journeys/journey-gs.md#jo-build) och lägga till personalisering.

>[!NOTE]
>
>Du kan övervaka hur din prenumerationslista påverkas genom specifika rapporter. [Läs mer](subscription-report.md)

<!--

**Questions**

* Can't see the newly created subscription list in UI because their name included spacing > bug - to follow up (should be fixed for Dec. release)

* Can you update the subscription list in a way other than through a LP? Not in UI but with APIs > to follow up with Fred

-->
