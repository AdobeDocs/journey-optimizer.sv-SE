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
exl-id: b774e34f-8225-41a0-a2ec-b91d3a86cf2b
badge: label="Beta" type="Informative"
source-git-commit: 8b966ddc9f96485e27cc7e9aa360d6d2ead84153
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Skapa ett meddelande i appen på en resa {#create-in-app-journey}

1. Öppna din resa och dra och släpp en **[!UICONTROL In-app]** aktivitet från **[!UICONTROL Actions]** på paletten.

   När en profil når slutet av sin resa kommer alla meddelanden i appen som visas för dem automatiskt att upphöra att gälla. Av den anledningen läggs en Wait-aktivitet automatiskt till efter aktiviteten i appen för att säkerställa korrekt timing.

   ![](assets/in_app_journey_1.png)

1. Ange **[!UICONTROL Label]** och **[!UICONTROL Description]** för ditt meddelande.

1. Välj [Yta i appen](inapp-configuration.md) att använda.

   ![](assets/in_app_journey_2.png)

1. Nu kan du börja designa ditt innehåll med **[!UICONTROL Edit content]** -knappen. [Läs mer](design-in-app.md)

1. Klicka **[!UICONTROL Edit trigger]** för att konfigurera utlösaren.

   ![](assets/in_app_journey_4.png)

1. Från **[!UICONTROL In-app message trigger]** väljer du de händelser och villkor som ska utlösa meddelandet:

   1. Klicka **[!UICONTROL Add condition]** om du vill att utlösaren ska ta hänsyn till flera händelser eller villkor.
   1. Från **[!UICONTROL Select an event]** väljer du typ av händelse för utlösaren.
   1. Välj hur dina händelser ska länkas, t.ex. välj **[!UICONTROL And]** om du vill **båda** utlösare är true för att ett meddelande ska kunna visas eller väljas **[!UICONTROL Or]** om du vill att meddelandet ska visas om **antingen** av utlösarna är sanna.
   1. Klicka **[!UICONTROL Make group]** för att gruppera utlösare tillsammans.

   ![](assets/in_app_journey_3.png)

1. Välj hur ofta utlösaren ska visas när meddelandet i appen är aktivt:

   * **[!UICONTROL Every time]**: Visa alltid meddelandet när de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Once]**: Visa endast det här meddelandet första gången de händelser som markerats i **[!UICONTROL Mobile app trigger]** inträffar.
   * **[!UICONTROL Until click through]**: Visa det här meddelandet när händelser har markerats i **[!UICONTROL Mobile app trigger]** nedrullningsbar meny inträffar tills en interaktionshändelse skickas av SDK med åtgärden&quot;klickad&quot;.
   * **[!UICONTROL X number of times]**: Visa bara meddelandet ett visst antal gånger, som bestäms av värdet i **[!UICONTROL Times to display]** fält.

1. Välj veckodag och den tidpunkt då du vill att ditt meddelande i appen ska utlösas och klicka på **[!UICONTROL Save]**.

1. Slutför vid behov kundresan genom att dra och släppa ytterligare åtgärder eller händelser. [Läs mer](../building-journeys/about-journey-activities.md)

1. När ditt meddelande i appen är klart slutför du konfigurationen och publicerar din resa för att aktivera den.

Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md).

## Aktivitetsbegränsningar i appen {#in-app-activity-limitations}

* Den här funktionen är för närvarande inte tillgänglig för vårdkunder.

* Personalisering kan bara innehålla profilattribut.

* Visning i appen är knuten till resans livscykel, vilket innebär att när resan avslutas för en profil kommer alla meddelanden i appen under resan inte att visas för den profilen.  Det är därför inte möjligt att stoppa ett meddelande i appen direkt från en reseaktivitet. I stället måste du avsluta hela kundresan för att stoppa visningen av meddelanden i appen från att visas i profilen.

* I testläge beror visningen i appen på resans livslängd. Justera **[!UICONTROL Wait time]** värde för **[!UICONTROL Wait]** verksamhet.

* **[!UICONTROL Reaction]** -aktiviteter kan inte användas för att reagera på en öppning eller klickning i appen.

* En aktiveringsfördröjning kan uppstå från det att en användarprofil når en aktivitet i appen på arbetsytan till dess att meddelandet visas i appen.

**Relaterade ämnen:**

* [Design In-app-meddelande](design-in-app.md)
* [Testa och skicka meddelandet i appen](send-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)
* [Konfiguration i appen](inapp-configuration.md)
