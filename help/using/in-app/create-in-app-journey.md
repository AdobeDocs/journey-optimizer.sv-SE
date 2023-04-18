---
title: Skapa ett meddelande i appen på en resa
description: Lär dig hur du skapar ett meddelande i appen i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, skapa, börja
hide: true
hidefromtoc: true
source-git-commit: 0c32248d13c08a98e9298ddc932aa2e547ab2acd
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 1%

---

# Skapa ett meddelande i appen på en resa {#create-in-app-journey}

>[!AVAILABILITY]
>
>Aktiviteten i appen är för närvarande endast tillgänglig som en betaversion för utvalda användare. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.

1. Öppna din resa och dra och släpp en **[!UICONTROL In-app]** aktivitet från **[!UICONTROL Actions]** på paletten.

   När en profil når slutet av sin resa kommer alla meddelanden i appen som visas för dem automatiskt att upphöra att gälla. Av den anledningen läggs en Wait-aktivitet automatiskt till efter aktiviteten i appen för att säkerställa korrekt timing.

   ![](assets/in_app_journey_1.png)

1. Ange **[!UICONTROL Label]** och **[!UICONTROL Description]** för ditt meddelande.

1. Välj [Yta i appen](inapp-configuration.md) att använda.

   ![](assets/in_app_journey_2.png)

1. Nu kan du börja designa ditt innehåll med **[!UICONTROL Edit content]** -knappen. [Läs mer](design-in-app.md)

1. Klicka **[!UICONTROL Edit trigger]** för att konfigurera utlösaren.

   ![](assets/in_app_journey_4.png)

1. Välj hur ofta utlösaren ska visas när meddelandet i appen är aktivt:

   * **[!UICONTROL Show every time]**: Visa alltid meddelandet när de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Show once]**: Visa endast det här meddelandet första gången de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Show until click through]**: Visa det här meddelandet när händelser har markerats i **[!UICONTROL Mobile app trigger]** nedrullningsbar meny inträffar tills en interaktionshändelse skickas av SDK med åtgärden&quot;klickad&quot;.

1. Från **[!UICONTROL Mobile app trigger]** väljer du de händelser och villkor som ska utlösa meddelandet:

   1. I den vänstra listrutan väljer du den händelse som krävs för att utlösa meddelandet.
   1. Välj den validering som krävs för den valda händelsen i den högra listrutan.
   1. Klicka på **[!UICONTROL Add]** om du vill att utlösaren ska ta hänsyn till flera händelser eller villkor. Upprepa sedan stegen ovan.
   1. Välj hur dina händelser ska länkas, t.ex. välj **[!UICONTROL And]** om du vill **båda** utlösare är true för att ett meddelande ska kunna visas eller väljas **[!UICONTROL Or]** om du vill att meddelandet ska visas om **antingen** av utlösarna är sanna.
   1. Klicka **[!UICONTROL Save]** när dina utlösare har konfigurerats.

   ![](assets/in_app_journey_3.png)

1. Slutför vid behov kundresan genom att dra och släppa ytterligare åtgärder eller händelser. [Läs mer](../building-journeys/about-journey-activities.md)

1. När ditt meddelande i appen är klart slutför du konfigurationen och publicerar din resa för att aktivera den.

Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md).

## Aktivitetsbegränsningar i appen {#in-app-activity-limitations}

* Den här funktionen är för närvarande inte tillgänglig för vårdkunder.

* Personalisering kan bara innehålla profilattribut.

* Visning i appen är knuten till resans livscykel, vilket innebär att när resan avslutas för en profil kommer alla meddelanden i appen under resan att sluta visas för den profilen. Det innebär att du inte kan stoppa en app direkt från en reseaktivitet. Du måste få ett slut på den resan.
* Visning i appen är länkad till en resas livscykel, vilket innebär att när en resa har slutförts för en viss användarprofil kommer alla meddelanden i appen under resan inte att visas för den profilen. Det är därför inte möjligt att stoppa ett meddelande i appen direkt från en reseaktivitet. I stället måste du avsluta hela kundresan för att stoppa visningen av meddelanden i appen från att visas i profilen.

* Med den här funktionen kommer du ännu inte att kunna använda **[!UICONTROL Reaction]** aktiviteter för att reagera på en öppning eller klickning i appen.

* En aktiveringsfördröjning inträffar mellan den tidpunkt då en användarprofil når en aktivitet i appen på arbetsytan och den tidpunkt då meddelandet visas i appen. Den här fördröjningen kan variera från 15 minuter till 1 timme.

**Relaterade ämnen:**

* [Design In-app-meddelande](design-in-app.md)
* [Testa och skicka meddelandet i appen](send-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)
* [Konfiguration i appen](inapp-configuration.md)