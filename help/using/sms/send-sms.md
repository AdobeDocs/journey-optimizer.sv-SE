---
solution: Journey Optimizer
product: journey optimizer
title: Kontrollera och testa dina textmeddelanden
description: Lär dig hur du kontrollerar och skickar textmeddelanden i Journey Optimizer
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: 47482adb84e05fe41eb1c50479a8b50e00469ec4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---

# Kontrollera och skicka textmeddelanden (SMS/MMS){#send-sms}

## Förhandsgranska textmeddelandet {#preview-sms}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska innehållet. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet med hjälp av testprofildata.

Det gör du genom att klicka på **[!UICONTROL Simulate content]** och sedan lägga till en testprofil för att kontrollera meddelandet med hjälp av testprofildata.

![](assets/sms_preview_2.png)

Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehåll finns i avsnittet [Innehållshantering](../content-management/preview-test.md).

## Validera ditt innehåll {#sms-validate}

Du måste kontrollera varningar i den övre delen av redigeraren. Vissa av dem är enkla varningar, men andra kan hindra dig från att skicka meddelandet. Två typer av varningar kan inträffa: varningar och fel.

![](assets/sms-alert-button.png)

* **Varningar** hänvisar till rekommendationer och bästa praxis. Ett varningsmeddelande visas till exempel om ditt textmeddelande är tomt.

* **Fel** hindrar dig från att testa eller aktivera resan, eller publicera kampanjen, så länge som de inte har lösts. Ett felmeddelande varnar dig till exempel när ämnesraden saknas.


>[!NOTE]
>
> Använd telefonnumren i de format som stöds av leverantören för att förbättra leveransmöjligheterna. Twilio och Sinch har till exempel bara stöd för telefonnummer i E.164-format.

## Skicka dina textmeddelanden {#sms-send}

>[!IMPORTANT]
>
>Från och med versionen från september kan ni med en ny kampanjupplevelse och upplevelse av aktivering av resor hantera hela godkännandeprocessen och säkerställa att kampanjer och resor granskas noggrant och godkänns av lämpliga intressenter innan de publiceras. Den här funktionen är tillgänglig med begränsad tillgänglighet. [Läs mer](../test-approve/gs-approval.md)

När textmeddelandet är klart slutför du konfigurationen av din [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md) för att skicka det.

**Relaterade ämnen**

* [Konfigurera SMS-kanal](sms-configuration.md)
* [SMS-/MMS-rapporter](../reports/journey-global-report-cja-sms.md)
* [Skapa ett textmeddelande](create-sms.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
