---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett SMS-meddelande
description: Lär dig hur du skapar ett SMS-meddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 5e5b078fa61e2c615a2242f50439c2f20ea5216a
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Skapa ett SMS-meddelande {#create-sms-bis}

>[!NOTE]
>
>I enlighet med branschens standarder och bestämmelser måste alla SMS-marknadsföringsmeddelanden innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. För att göra detta kan SMS-mottagare svara med nyckelord för deltagande och avanmälan.

## Skapa ett SMS-meddelande i en resa eller kampanj

Så här börjar du personalisera SMS-meddelandet:

>[!BEGINTABS]

>[!TAB Lägga till ett SMS-meddelande på en resa]

1. Öppna kundresan och dra och släpp en SMS-aktivitet från åtgärdsavsnittet på paletten.

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori) och välj sedan den meddelandeyta som ska användas.

   Mer information om hur du konfigurerar en resa finns i.

Nu kan du börja designa ditt SMS-meddelande via **[!UICONTROL Edit content]** -knappen.

>[!TAB Lägga till ett SMS-meddelande i en kampanj]

1. Skapa en ny schemalagd eller API-utlöst kampanj, välj **[!UICONTROL SMS]** som din åtgärd och väljer **[!UICONTROL App surface]** att använda.

1. Klicka på **[!UICONTROL Create]**.

1. Från **[!UICONTROL Properties]** redigerar du Campaigns **[!UICONTROL Title]** och **[!UICONTROL Description]**.

1. I **[!UICONTROL Actions tracking]** anger du om du vill spåra klickningar på länkar i SMS-meddelandet.

1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-segment.

1. I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** om er kampanj.

1. Från **[!UICONTROL Action triggers]** väljer du **[!UICONTROL Frequency]** av SMS-meddelandet:

   * En gång
   * Dagligen
   * Veckovis
   * Month

Nu kan du börja designa ditt SMS-meddelande via **[!UICONTROL Edit content]** -knappen.

>[!ENDTABS]

## Definiera ditt SMS-innehåll

1. Klicka på **[!UICONTROL Edit content]** för att konfigurera SMS-innehållet.

1. Klicka på **[!UICONTROL Message]** för att öppna uttrycksredigeraren.

1. Använd uttrycksredigeraren för att definiera innehåll och lägga till dynamiskt innehåll. Du kan använda alla attribut, till exempel profilnamnet eller stad.

1. Klicka **[!UICONTROL Save]** och kontrollera meddelandet i förhandsgranskningen.

1. När SMS-meddelandet är klart slutför du konfigurationen för att skicka det.

## Validera ditt SMS

>[!NOTE]
>
> För bättre leverans bör du alltid använda telefonnumren i de format som stöds av leverantören. Twilio och Sinch har till exempel bara stöd för telefonnummer i E.164-format.

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det. Om du infogade innehåll kan du kontrollera hur det visas i meddelandet med hjälp av testprofildata.

Om du vill se hur SMS-meddelandet visas på mobila enheter klickar du på **[!UICONTROL Simulate content]** -fliken. Läs mer om simulering av innehåll i.

Du måste även kontrollera varningar i den övre delen av redigeraren.  Vissa av dem är enkla varningar, men andra kan hindra dig från att använda meddelandet. Läs mer i.
