---
solution: Journey Optimizer
product: journey optimizer
title: Kontrollera och testa dina WhatsApp-meddelanden
description: Lär dig hur du kontrollerar och skickar dina WhatsApp-meddelanden i Journey Optimizer
feature: Whatsapp
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
badge: label="Beta" type="Informative"
source-git-commit: 22664437fb1f548f4c1524ea5fa7ac9e7fdc7f59
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Kontrollera och skicka dina meddelanden om whatsApp {#send-whatsapp}

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* [Kom igång med whatsApp-meddelanden](get-started-whatsapp.md)
* [Kom igång med konfigurationen för whatsApp](whatsapp-configuration.md)
* [Skapa ett WhatsApp-meddelande](create-whatsapp.md)
* **[Kontrollera och skicka dina WhatsApp-meddelanden](send-whatsapp.md)**

>[!ENDSHADEBOX]

## Förhandsgranska meddelandet WhatsApp {#preview-whatsapp}

När meddelandeinnehållet har definierats kan du använda testprofiler eller exempelindata som har överförts från en CSV-/JSON-fil, eller lägga till manuellt för att förhandsgranska innehållet. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet. [Lär dig hur du testar innehåll med exempelindata](../test-approve/simulate-sample-input.md)

Om du vill göra det klickar du på **[!UICONTROL Simulate content]** och kontrollerar sedan meddelandet med testprofildata.

Detaljerad information om hur du förhandsgranskar och testar innehåll finns i avsnittet [Innehållshantering](../content-management/preview-test.md).

## Validera ditt innehåll {#whatsapp-validate}

Du måste kontrollera varningar i den övre delen av redigeraren. Vissa av dem är enkla varningar, men andra kan hindra dig från att skicka meddelandet. Två typer av varningar kan inträffa: varningar och fel.

* **Varningar** hänvisar till rekommendationer och bästa praxis. Ett varningsmeddelande visas till exempel om ditt textmeddelande är tomt.

* **Fel** hindrar dig från att testa eller aktivera resan, eller publicera kampanjen, så länge som de inte har lösts. Ett felmeddelande varnar dig till exempel när ämnesraden saknas.

## Skicka meddelanden i whatsApp {#whatsapp-send}

>[!IMPORTANT]
>
> Om din kampanj omfattas av en policy för godkännande måste du begära godkännande för att kunna skicka dina textmeddelanden. [Läs mer](../test-approve/gs-approval.md)

När whatsApp-meddelandet är klart slutför du konfigurationen av din [resa](../building-journeys/publishing-the-journey.md) eller [kampanj](../campaigns/review-activate-campaign.md) för att skicka det.
