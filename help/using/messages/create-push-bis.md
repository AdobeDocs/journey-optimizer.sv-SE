---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera ett push-meddelande
description: Lär dig hur du skapar ett push-meddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 5e5b078fa61e2c615a2242f50439c2f20ea5216a
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# Skapa ett push-meddelande {#create-push-notification-bis}

## Skapa push-meddelanden i en resa eller kampanj

Så här skapar du ett push-meddelande:

>[!BEGINTABS]

>[!TAB Lägg till en push-funktion på en resa]

1. Öppna resan och dra och släpp en push-aktivitet från funktionsmakroavsnittet på paletten.

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori) och välj sedan den meddelandeyta som ska användas.

   Mer information om hur du konfigurerar en resa finns i

1. På skärmen för konfiguration av resan klickar du på **[!UICONTROL Edit content]** för att konfigurera push-innehållet.

1. När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det.

1. Slutför konfigurationen av din push-funktion för att skicka den när din push-funktion är klar.

   Om du vill spåra mottagarnas beteende genom push-öppningar och/eller interaktioner kontrollerar du att de dedikerade alternativen i spårningsavsnittet är aktiverade i .

>[!TAB Lägga till en push-knapp i en kampanj]

1. Skapa en ny schemalagd eller API-utlöst kampanj, välj **[!UICONTROL Push notification]** som din åtgärd och väljer **[!UICONTROL App surface]** att använda.

1. Klicka på **[!UICONTROL Create]**.

1. Från **[!UICONTROL Properties]** redigerar du Campaigns **[!UICONTROL Title]** och **[!UICONTROL Description]**.

1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-segment.

1. I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** om er kampanj.

1. Från **[!UICONTROL Action triggers]** väljer du **[!UICONTROL Frequency]** av ditt push-meddelande:

   * En gång
   * Dagligen
   * Veckovis
   * Månadsvis

1. Klicka på knappen **[!UICONTROL Edit content]** för att konfigurera push-innehållet.

1. När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det.

1. Slutför konfigurationen av din push-funktion för att skicka den när din push-funktion är klar.

   Om du vill spåra mottagarnas beteende genom push-öppningar och/eller interaktioner kontrollerar du att de dedikerade alternativen i spårningsavsnittet är aktiverade i ).

>[!ENDTABS]

## Snabb leverans

Snabb leverans, som tidigare kallades Burst-läge under resor, är ett [!DNL Journey Optimizer] tillägg som gör det möjligt att skicka mycket snabba push-meddelanden i stora volymer via kampanjer.

Snabba leveranser används när fördröjningar i meddelandeleverans är affärskritiska när du vill skicka en snabb push-varning på mobiltelefoner, till exempel nyheter till användare som har installerat din nyhetskanalapp.

Mer information om prestanda när du använder läget Snabb leverans finns i.

### Förutsättningar

Snabba leveransmeddelanden innehåller följande krav:

* Snabb leverans av **[!UICONTROL Scheduled]** endast kampanjer och inte för API-utlösta kampanjer,
* Ingen personalisering tillåts i push-meddelandet,
* Målgruppen måste innehålla färre än 30M profiler,
* Du kan köra upp till 5 kampanjer samtidigt i läget Snabb leverans.

### Aktivera läget Snabb leverans

1. Skapa en push-meddelandekampanj och aktivera **[!UICONTROL Rapid delivery]** alternativ.

1. Konfigurera meddelandeinnehållet och välj målgrupp.

   >[!IMPORTANT]
   >
   >Se till att meddelandeinnehållet inte innehåller någon personalisering och att målgruppen innehåller färre än 30 miljoner profiler.

1. Granska och aktivera kampanjen som vanligt. Observera att i testläge skickas inga meddelanden via läget Snabb leverans.