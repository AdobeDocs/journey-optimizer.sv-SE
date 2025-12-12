---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en prenumerationslista
description: Lär dig hur du ställer in en prenumerationslista i Journey Optimizer
feature: Subscriptions
topic: Content Management
role: User
level: Beginner
keywords: landning, landningssida, lista, prenumeration, service
exl-id: 5e5419a0-5121-4aa7-a975-b1f08e2918c9
source-git-commit: c18f6f450bdc37f7ffbe87befb8601a920e46171
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# Prenumerationslistor {#create-subscription-list}

>[!CONTEXTUALHELP]
>id="ajo_subscription_list"
>title="Konfigurera en prenumerationslista"
>abstract="Skapa en prenumerationslista för att samla in profiler som har valt att ta emot meddelanden om ett visst ämne eller evenemang. "
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/content-management/landing-pages/subscription-list.html#define-subscription-list" text="Skapa en prenumerationslista"

En prenumerationstjänst avser marknadsföringsvaror och marknadsföringstjänster som tillhandahålls kunder som har valt att ta emot meddelanden om ett visst ämne/evenemang/intresse/osv. fortlöpande. I [!DNL Journey Optimizer] samlas de här kunderna i en prenumerationslista.

En prenumerationstjänst kan användas för:

* ett nyhetsbrev, till exempel:&quot;Serie som körs&quot;
* en händelse, till exempel:&quot;Summit 2021&quot;
* ett webbinarium, till exempel:&quot;Läs mer om krypto&quot;
* en ränta på en viss produkt/sport/tjänst/osv., t.ex.:&quot;Intresserad att köpa ett hus under de kommande 12 månaderna&quot;
* en inställning för hur du ska meddelas, till exempel:&quot;Få nya låtmeddelanden via e-post&quot;

Profilerna kan läggas till i en prenumerationslista via en [landningssida](create-lp.md). Ett exempel visas i [det här avsnittet](lp-use-cases.md#subscription-to-a-service).

## Skapa en prenumerationslista {#define-subscription-list}

>[!NOTE]
>
>När du skapar en prenumerationslista genereras ett associerat direktuppspelningssegment automatiskt i Adobe Experience Platform. För att direktuppspelningssegmentet ska kunna skapas måste alternativet **Active-On-Edge** vara aktiverat i sammanfogningsprincipen. Läs mer om villkoren för att direktuppspela segment i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/methods/streaming-segmentation).

Följ stegen nedan för att skapa en prenumerationslista.

1. Välj **[!UICONTROL Customer]** > **[!UICONTROL Subscription list]** om du vill få tillgång till prenumerationslistorna.

   ![](assets/lp_subscription-lists.png)

1. Markera knappen **[!UICONTROL Create subscription list]**.

   ![](assets/lp_create-subscription-list.png)

1. Lägg till en titel och en beskrivning. Dessa fält är obligatoriska.

   ![](assets/lp_subscription-list-name.png)

   >[!CAUTION]
   >
   >För närvarande kan du inte använda avstånd eller ange ett namn som redan finns för en annan prenumerationslista i fältet **[!UICONTROL Title]**.

1. Du kan definiera ett startdatum och ett slutdatum.

   ![](assets/lp_subscription-list-dates.png)

1. Välj eller skapa Adobe Experience Platform-taggar från fältet **[!UICONTROL Tags]** för att kategorisera landningssidan för förbättrad sökning. [Läs mer](../start/search-filter-categorize.md#tags)

1. Klicka på **[!UICONTROL Save]**.

## Använda en prenumerationslista {#use-subscription-lists}

När prenumerationslistan har skapats kan du:

* Lägga till profiler i prenumerationslistan

  Du kan bjuda in personer till **att gå med i listan** genom att prenumerera på ett nyhetsbrev eller registrera sig för en händelse. Du kan också **skicka personliga meddelanden** till prenumeranterna.

  Om du till exempel vill bjuda in en publik att registrera sig för ett evenemang eller prenumerera på ett nyhetsbrev kan du skicka ett meddelande till dem med en länk till en landningssida så att de kan gå med i evenemanget eller prenumerationen. Profiler som anmäler sig via landningssidformuläret läggs till i den prenumerationslista som du skapade för detta ändamål.

* Skicka meddelanden till prenumeranter

  Du kan också använda prenumerationslistor som målgrupper när du skapar resor och lägger till personalisering.

  När en kund prenumererar på en direktuppspelningstjänst kan den till exempel utlösa ett omedelbart utskick av en välkomstserie, som uppmanar dem att logga in i appen för första gången och ange sina visningsinställningar.

Lär dig hur du använder din prenumerationslista i [det här användningsexemplet](lp-use-cases.md#subscription-to-a-service).


## Bläddra i dina prenumerationslistor {#browse-subscription-lists}

I listan visas alla prenumerationslistor som skapats. Du kan filtrera dem baserat på datum när de skapades eller ändrades och deras status.

![](assets/lp_subscription-filters.png)

Möjliga statusvärden är följande:

* **[!UICONTROL Not started]**: Du definierade ett startdatum som är senare än den aktuella dagen. De prenumererade profilerna kommer ännu inte att få någon information om den här prenumerationslistan.
* **[!UICONTROL Live]**: Den aktuella dagen ligger mellan prenumerationslistans startdatum och slutdatum, eller så har du inte definierat slut-/startdatum, vilket innebär att prenumerationslistan alltid är aktiv.
* **[!UICONTROL Expired]**: Slutdatumet har passerats, vilket innebär att prenumerationslistan inte längre är giltig. Prenumerationsprofiler får inte mer information om den här prenumerationslistan.


## Övervaka dina prenumerationslistor {#monitor-subscription-lists}

Ni kan övervaka hur din prenumerationslista påverkas genom dedikerade rapporter. Du kan komma åt två typer av rapporter:

* Live-rapport om prenumerationslista

  Live-rapporter, som du kommer åt från fliken Senaste 24 timmarna, visar händelser som har inträffat under de senaste 24 timmarna, med ett tidsintervall på minst två minuter från händelseförekomsten. [Läs mer](../reports/subscription-report-live.md)

* Prenumerationslista Alla tidsrapporter, med Customer Journey Analytics

  Dessa rapporter fokuserar på händelser som inträffade för minst två timmar sedan och täcker händelser under en viss tidsperiod. **Prenumerationsrapporten** innehåller viktiga insikter om profilernas prenumerationer och avbeställningar som är kopplade till vissa listor, vilket hjälper dig att förstå hur effektiva olika prenumerationskampanjer och -initiativ är när det gäller att öka engagemanget och konverteringarna. [Läs mer](../reports/subscription-report-global-cja.md)
