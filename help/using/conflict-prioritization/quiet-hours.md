---
solution: Journey Optimizer
product: journey optimizer
title: Ange tysta timmar
description: Lär dig hur du skapar och tillämpar tysta timmar
feature: Rules
topic: Content Management
role: User
level: Intermediate
keywords: meddelande, frekvens, regler, tryck
source-git-commit: a7d2557790054e7c6e28ca3ffa937f454c4b004c
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 0%

---


# Ange tysta timmar {#quiet-hours}

## Vad är tysta timmar?

Med **tysta timmar** kan du definiera tidsbaserade undantag för kanalerna **Email**, **SMS**, **Push** och **WhatsApp**. De ser till att inga meddelanden skickas under särskilda tidsperioder och hjälper er att följa kundönskemål och krav på regelefterlevnad.

Du kan använda tysta timmar genom **regeluppsättningar**, som kan tilldelas enskilda åtgärder i kampanjer eller resor för exakt kontroll.

Genom att effektivisera dessa processer kan ni förbättra kundupplevelsen, spara tid och säkerställa att kommunikationsreglerna följs:

* **Vakna inte upp din kund** - *Rätt kund, rätt kanal, rätt tid* är många marknadsförares mantra, så det är rimligt att timing är en viktig del av kundresan. Genom att ställa in en regel för tysta timmar får varumärken bättre kontroll över när kontakter tar emot meddelanden och ser till att de får dem när de är mer benägna att vidta åtgärder i ditt meddelande.
* **Praktisk** - Interagera enkelt kommunikationen över kampanjer och resor när du behöver förhindra att en publik får ett meddelande utan att behöva stoppa hela resan eller kampanjen.
* **Tidsbesparande** - Hantera undantag på ett ställe genom att skapa en **tidsbaserad regel** i stället för att lägga till flera villkorsnoder med anpassade uttryck.\
  <!--* **Extra Safeguard** - Benefit from an extra safeguard in case audience criteria or time-window configurations were incorrectly set, ensuring individuals are still excluded when they should be.-->

➡️ [Upptäck den här funktionen i en video](#video)

## Skyddsritningar och begränsningar

* **Kanaler som stöds** - E-post, SMS, push och WhatsApp.
* **Samordnade kampanjer** - Tysta timmar stöds inte för orkestrerade kampanjer.
* **Spridningsfördröjning** - Det kan ta upp till 12 timmar att tillämpa uppdateringar av en regel för tysta timmar för kanalåtgärder som redan använder den regeln.
* **Högvolymsfördröjning** - Vid kommunikation med stora volymer kan det ta ytterligare tid innan systemet kan börja framtvinga tyst timmes-inaktiveringar.

<!--* **Custom actions** – For custom actions, only quiet hours rules are enforced. If a rule set also includes other rules (e.g., frequency capping), those rules are ignored.-->
<!--* **Pre-suppression window** – The system begins suppressing communications 30 minutes before quiet hours start, ensuring that no messages are delivered once the quiet period begins.-->

## Skapa regler för tysta timmar

Om du vill ange tysta timmar skapar du en regel inuti en anpassad regeluppsättning. [Lär dig skapa regeluppsättningar](../conflict-prioritization/rule-sets.md#Create). Följ de här stegen:

1. Navigera till **[!UICONTROL Business rules]** för att komma åt lagret för regeluppsättningar.

1. Välj en befintlig anpassad regeluppsättning eller skapa en ny:

   +++Skapa en tysta timmars regel i en befintlig regeluppsättning

   Välj regeluppsättningen från lagret. Regler för tysta timmar kan bara läggas till i regeluppsättningar med domänen &quot;channel&quot;. Du kan kontrollera informationen i kolumnen **[!UICONTROL Domain]**.

   ![](assets/journey-capping-list.png)

   +++

   +++Skapa en tysta timmars regel i en ny regeluppsättning

   Klicka på **[!UICONTROL Create rule set]**, ange ett unikt namn och välj Kanal i listrutan **[!UICONTROL Rule Set Domain]**.

   ![](assets/rule-sets-create.png)

   +++

   >[!NOTE]
   >
   >Tysta timmar kan bara definieras i **anpassade regeluppsättningar**. Den globala regeluppsättningen stöder inte konfiguration för tysta timmar.

1. Klicka på **[!UICONTROL Add Rule]** på skärmen för regeluppsättningen och ange ett unikt namn för regeln.

1. Fältet **Kategori** anger vilken meddelandekategori regeln gäller för. För tillfället är det här fältet skrivskyddat och standardvärdet är **[!UICONTROL Marketing]**.

1. Välj **[!UICONTROL Rule type]** i listrutan **[!UICONTROL Quiet hours]**.

   ![](assets/quiet-hours-type.png)

1. I avsnittet **[!UICONTROL Dates & times]** anger du när tysta timmar ska användas:

   1. I listrutan **[!UICONTROL Time zone]** använder du en standardtidszon för alla mottagare i målgruppen, oavsett deras enskilda tidszoner.

      Välj **[!UICONTROL Use recipients local time zone]** om du vill använda tidszonsfältet från varje profil. [Läs mer om hantering av tidszoner under resor](../building-journeys/timezone-management.md#timezone-from-profiles)

      >[!IMPORTANT]
      >
      >Om en profil inte har något tidszonsvärde används inga tysta timmar för den profilen.

   1. Ange den tidsperiod under vilken tysta timmar ska gälla.

      * **[!UICONTROL Weekly]** - Välj specifika veckodagar och en tidsrymd. Du kan också använda regeln **[!UICONTROL All day]**.

        ![](assets/quiet-hours-weekly.png)

      * **[!UICONTROL Custom date]** - Välj specifika datum i kalendern och en tidsrymd. Du kan också använda regeln **[!UICONTROL All day]**.

        ![](assets/quiet-hours-custom.png)

   1. Klicka på knappen **[!UICONTROL Add more dates]** om du vill lägga till upp till fem separata perioder.

      ![](assets/quiet-hours-date.png)

1. I avsnittet **[!UICONTROL Handling actions during quiet hours]** väljer du hur meddelanden ska behandlas under den valda tidsperioden:

   ![](assets/quiet-hours-queue.png)

   * **[!UICONTROL Queue message]** - Meddelanden skickas när den tysta timperioden har slutförts, om inte läget Pausad har aktiverats.

     >[!NOTE]
     >
     >Om ett meddelande står i kö för en profil i mer än 7 dagar kommer meddelandet att ignoreras.

   * **[!UICONTROL Discard message]** - Meddelanden skickas aldrig.

     >[!NOTE]
     >
     >Om du väljer **[!UICONTROL Discard]** och tillämpar den här regeln på en reseåtgärd tas profilen bort från meddelandeleveransen och avslutas från resan.

Regeln visas nu i regeluppsättningen. Du kan markera den om du vill visa information om den i egenskapspanelen.

![](assets/quiet-hours-preview.png)

Om regeln är klar aktiverar du den och slutför konfigurationen av regeluppsättningen. [Lär dig skapa och aktivera regeluppsättningar](../conflict-prioritization/rule-sets.md#Create)

## Använd tysta timmar på resor och kampanjer {#apply}

När regeln har sparats och regeluppsättningen har aktiverats kan du använda den på åtgärder under resor och kampanjer. Kanaler som stöds: **Email, SMS, Push, WhatsApp**. Mer information finns på flikarna nedan.

>[!BEGINTABS]

>[!TAB Använd kanalåtgärder för tysta timmar i resor]

1. Öppna din resa, välj en [kanalåtgärd](../building-journeys/journeys-message.md) och redigera innehållet i meddelandet.
1. Klicka på knappen **[!UICONTROL Add Business Rule]** och markera regeluppsättningen som innehåller regeln Tysta timmar.

   ![](assets/quiet-hours-apply.png)

   >[!NOTE]
   >
   >Endast [aktiverade](#activate-rule) regeluppsättningar visas i listan.

1. Aktivera din resa.

>[!TAB Använd tysta timmar för kampanjåtgärder]

1. Redigera kampanjen och gå till fliken **[!UICONTROL Actions]**.
1. I avsnittet **[!UICONTROL Business rules]** väljer du den regeluppsättning som innehåller regeln Tysta timmar.

   ![](assets/quiet-hours-campaign.png)

   >[!NOTE]
   >
   >Endast [aktiverade](#activate-rule) regeluppsättningar visas i listan.

1. Aktivera kampanjen.

>[!ENDTABS]

## Nästa steg

När din resa eller dina kampanjer har aktiverats och körts kan du visa antalet profiler som har uteslutits från kommunikationen i [Customer Journey Analytics-rapporten](../reports/report-gs-cja.md) och i [Live-rapporten](../reports/live-report.md), där reglerna för tysta timmar listas som en möjlig orsak för användare som har uteslutits från leverans.

![](assets/quiet-hours-report.png)





<!--

>[!TAB Apply Quiet hours to custom actions]

1. Open your journey and add or select a custom action in the canvas.

1. In the **[!UICONTROL Business rules]** section, select the rule set containing the Quiet hours rule.

   ![](assets/quiet-hours-custom-action.png)

   >[!NOTE]
   >
   >Only [activated](#activate-rule) rule sets display in the list.

1. Activate your journey.

-->


## Instruktionsvideo {#video}

Lär dig hur du använder funktionen för tysta timmar i Adobe Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/3475856?captions=swe&quality=12)
