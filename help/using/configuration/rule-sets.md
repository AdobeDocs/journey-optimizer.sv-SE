---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med regeluppsättningar
description: Lär dig hur du skapar och använder regeluppsättningar
feature: Rules
topic: Content Management
role: User
level: Intermediate
keywords: meddelande, frekvens, regler, tryck
exl-id: 07f5f0b4-417e-408e-8d9e-86615c8a3fbf
source-git-commit: 43fe7ca22a7685944b2b11ca3d1872641d1f4694
workflow-type: tm+mt
source-wordcount: '1901'
ht-degree: 0%

---

# Arbeta med regeluppsättningar {#rule-sets}

>[!CONTEXTUALHELP]
>id="ajo_business_rules_rule_sets"
>title="Regeluppsättningar"
>abstract="Använd regeluppsättningar för att tillämpa frekvensbegränsning för olika typer av marknadsföringskommunikation. Du kan också skapa regeluppsättningar för att exkludera resor till en del av målgruppen baserat på regler för frekvensbegränsning."

## Kom igång med regeluppsättningar {#gs}

### Vad är regeluppsättningar? {#what}

Förutom globala affärsregler som begränsar antalet gånger som användare får meddelanden i en eller flera kanaler, kan du med regeluppsättningar **gruppera flera regler i regeluppsättningar** och tillämpa dem på de kampanjer du väljer. Detta ger en förbättrad detaljrikedom som styr hur ofta användarna får ett meddelande beroende på kommunikationstypen.

Du kan till exempel skapa en regeluppsättning som begränsar antalet **kampanjmeddelanden** som skickas till dina kunder och en annan regeluppsättning som begränsar antalet **nyhetsbrev** som skickas till dem. Beroende på vilken typ av kampanj du skapar kan du sedan välja att använda antingen kampanjkommunikationen eller regeluppsättningen för nyhetsbrev.

➡️ [Upptäck den här funktionen i en video](#video)

### Behörigheter {#permissions-frequency-rules}

Om du vill arbeta med affärsregler behöver du följande behörigheter:

* **[!UICONTROL View Frequency Rules]**: Få åtkomst till och visa affärsregler.
* **[!UICONTROL Manage Frequency Rules]**: Skapa, redigera eller ta bort affärsregler.

Läs mer om behörigheter i [det här avsnittet](../administration/high-low-permissions.md).

### Globala och anpassade regeluppsättningar {#global-custom}

När du använder regeluppsättningar för första gången från menyn **[!UICONTROL Administration]** > **[!UICONTROL Business rules]** skapas en standardregeluppsättning och är aktiv: **Global standardregeluppsättning**.

Den här regeluppsättningen innehåller globala regler som du kan tillämpa för att styra hur ofta användare tar emot meddelanden i en eller flera kanaler, på samma sätt som nuvarande affärsregler fungerar. Alla regler som definieras i den här regeluppsättningen gäller för alla valda kanaler, oavsett om kommunikationen skickas från en resa eller en kampanj. [Lär dig arbeta med affärsregler](../conflict-prioritization/rule-sets.md)

Utöver den här regeluppsättningen Global standardregeluppsättning kan du skapa **anpassade regeluppsättningar** som du kan tillämpa på alla kampanjer för att begränsa antalet meddelanden som skickas inom kampanjen. [Lär dig skapa anpassade regeluppsättningar](#create)

![](assets/rule-sets-default.png)

### Kanaler och resor {#domain}

>[!CONTEXTUALHELP]
>id="ajo_rule_set_domain"
>title="Regeluppsättningsdomän"
>abstract="När du skapar en regeluppsättning måste du ange om reglerna i regeluppsättningen ska tillämpa regler för appning som är specifika för kommunikationskanaler eller för resor."

När du skapar en regeluppsättning måste du ange om reglerna i regeluppsättningen ska tillämpa regler för appning som är specifika för kommunikationskanaler eller för resor. Detta gör du genom att välja en kanal- eller resedomän för regeluppsättningen när du skapar den. [Lär dig skapa en regeluppsättning](#create)

* **Kanal**-domän: tillämpa regler för begränsning för kommunikationskanaler. Skicka till exempel inte mer än 1 e-post eller SMS-kommunikation per dag.
* **Resa**-domän: Använd regler för start och begränsning av samtidighet på en resa. Ange till exempel inte profiler i mer än en resa samtidigt.

## Skapa din första anpassade regeluppsättning {#create-rule-set}

### Skapa regeluppsättningen och välj dess domän {#create}

Följ stegen nedan för att skapa en regeluppsättning.

>[!NOTE]
>
>Du kan skapa upp till 10 aktiva lokala regeluppsättningar för varje kanaldomän och för resedomänen.

1. Öppna listan **[!UICONTROL Rules sets]** och klicka sedan på **[!UICONTROL Create rule set]**.

   ![](assets/rule-sets-create-button.png)

1. Definiera ett unikt namn för regeluppsättningen och lägg till en beskrivning.

1. Välj regeluppsättningens domän. Domänen tillåter dig att ange om regeluppsättningen ska innehålla regler för appning som är specifika för kommunikationskanaler eller resor. [Läs mer om regler för att appa kanaler och resor](#domain)

   ![](assets/rule-sets-create.png)

1. Klicka på **[!UICONTROL Save]**.

1. Nu kan du [definiera reglerna](#create-new-rule) som du vill lägga till i den här regeluppsättningen.

### Lägg till regler i regeluppsättningen {#create-new-rule}

>[!CONTEXTUALHELP]
>id="ajo_rule_sets_category"
>title="Välj meddelanderegelkategori"
>abstract="När det aktiveras och används för ett meddelande, kommer alla frekvensregler som matchar den valda kategorin automatiskt att tillämpas på det här meddelandet. För närvarande är endast marknadsföringskategorin tillgänglig."

<!--NOT USED?
[!CONTEXTUALHELP]
>id="ajo_rule_sets_capping"
>title="Set the capping for your rule"
>abstract="Specify the maximum number of messages sent to a customer profile within the chosen time frame. The frequency cap will be based on the selected calendar period and will be reset at the beginning of the corresponding time frame."-->

>[!CONTEXTUALHELP]
>id="ajo_rule_sets_channel"
>title="Definiera de kanaler som regeln gäller för"
>abstract="Välj minst en kanal. Taket tillämpas över alla kanaler som ett totalt antal."

>[!CONTEXTUALHELP]
>id="ajo_rule_sets_duration"
>title="Välj meddelanderegelkategori"
>abstract="När det aktiveras och används för ett meddelande, kommer alla frekvensregler som matchar den valda kategorin automatiskt att tillämpas på det här meddelandet. För närvarande är endast marknadsföringskategorin tillgänglig."

>[!CONTEXTUALHELP]
>id="ajo_rule_set_rule_capping"
>title="Regelfästning"
>abstract="Ange begränsning för din regel. Beroende på regeluppsättningsdomänen och valet i fältet Regeltyp kan det här fältet definiera det maximala antalet meddelanden som kan skickas till en profil, eller det högsta antal resor som profilen kan ange eller registreras samtidigt."

Om du vill lägga till en regel i en regeluppsättning öppnar du regeluppsättningen och klickar på **[!UICONTROL Add rule]**.

Vilka parametrar som är tillgängliga för regeln beror på vilken regeluppsättningsdomän som valdes när regeln skapades.

+++Konfigurera regler för kanalbegränsning (**Kanal** domän)

![](assets/rule-set-channels.png)

1. Definiera ett unikt namn för regeln.

1. Fältet **Kategori** anger vilken meddelandekategori regeln gäller för. För tillfället är det här fältet skrivskyddat eftersom endast kategorin **[!UICONTROL Marketing]** är tillgänglig.

1. I listrutan **[!UICONTROL Duration]** väljer du om du vill att capping ska användas varje månad, vecka eller dag. Frekvensgränsen baseras på den valda kalenderperioden. Den återställs i början av motsvarande tidsram.

   ![](assets/rule-set-capping-duration.png)

   Räknaren för varje period har följande förfallodatum:

   * **[!UICONTROL Monthly]**: Frekvensgränsen gäller till den sista dagen i månaden vid 23:59:59 UTC. Månadsförfallodatumet för januari är till exempel 01-31 23:59:59 UTC.

   * **[!UICONTROL Weekly]**: Frekvensgränsen gäller till lördag :59:&lbrace;59 UTC den veckan när kalenderveckan börjar på söndag. Utgångsdatumet gäller oavsett när regeln skapades. Om regeln till exempel skapas på torsdag gäller den till lördag den 23:59:59.

   * **[!UICONTROL Daily]**: Den dagliga frekvensen gäller för dagen till 23:59:59 UTC och återställs till 0 i början av nästa dag.

     >[!CAUTION]
     > 
     >Se till att du väljer det namnutrymme som har högst prioritet när du skapar en kampanj eller resa, så att reglerna för den dagliga takten är korrekta. Läs mer om namnområdesprioritet i [Handboken för Platform Identity Service](https://experienceleague.adobe.com/sv/docs/experience-platform/identity/features/identity-graph-linking-rules/namespace-priority){target="_blank"}

   Observera att profilräknarvärdet uppdateras när kommunikationen har skickats. Tänk på det här när du skickar stora mängder kommunikation eftersom dataflödet kan resultera i att mottagaren får e-postminuterna eller till och med timmar efter att kommunikationen har startats (om du skickar miljontals meddelanden samtidigt).

   Detta gäller om en mottagare får två kommunikationer nära ihop. Vi föreslår att kommunikationen ska hållas isär med minst två timmar om det är möjligt, så att mottagaren får tillräckligt med tid för att kunna ta emot kommunikationen och räkningsvärdet för att kunna uppdatera den.

1. Ange begränsningen för din regel, vilket innebär det maximala antalet meddelanden som kan skickas till en enskild användarprofil varje månad, vecka eller dag enligt vad du väljer ovan.

1. Markera kanalen som du vill använda för den här regeln: **[!UICONTROL Email]**, **[!UICONTROL SMS]**, **[!UICONTROL Push notification]** eller **[!UICONTROL Direct mail]**.

   >[!NOTE]
   >
   >Du måste välja minst en kanal för att kunna skapa regeln.

1. Markera flera kanaler om du vill tillämpa begränsning för alla markerade kanaler som ett totalt antal.

   Ange till exempel 5 som capping och markera både e-postkanalen och sms-kanalen. Om en profil redan har fått 3 marknadsföringsmeddelanden och 2 marknadsföringsmeddelanden för den valda perioden, kommer profilen att uteslutas från nästa leverans av marknadsföringsmeddelanden eller sms.

+++

+++Konfigurera regler för begränsning av kundresan (**Resa** domän)

![](assets/rule-set-journey.png)

1. Ange ett unikt namn för regeln.

1. Ange regelns typ av begränsning i listrutan **[!UICONTROL Rule Type]**.

   * **[!UICONTROL Journey Entry Cap]**: Begränsar antalet poster i resan under en viss period för en profil.
   * **[!UICONTROL Journey Concurrency Cap]**: Begränsar hur många resor en profil kan registreras samtidigt.

1. Detaljerad information om hur du konfigurerar regler för att appa resan finns i avsnittet [Resebegränsning och medling](../conflict-prioritization/journey-capping.md).

+++

1. Klicka på **[!UICONTROL Save]** för att bekräfta att regeln har skapats. Meddelandet läggs till i regeluppsättningen med statusen **[!UICONTROL Draft]**.

   ![](assets/rule-set-rule-created.png)

1. Upprepa stegen ovan om du vill lägga till så många regler som behövs i regeluppsättningen.

Nu måste du aktivera varje regel innan den kan tillämpas på alla meddelanden. [Läs mer](#activate-rule)

### Aktivera reglerna och regeluppsättningen {#activate-rule}

När en regel skapas har den statusen **[!UICONTROL Draft]** och påverkar ännu inte något meddelande. Om du vill aktivera den klickar du på knappen **[!UICONTROL More actions]** bredvid regeln och väljer **[!UICONTROL Activate]**.

![](assets/rule-set-activate-rule.png)

Du måste också aktivera regeluppsättningen för att kunna komma åt den i kampanjer/resor och använda den i dina meddelanden.

![](assets/rule-set-activate-set.png)

>[!NOTE]
>
>Det kan ta upp till 10 minuter för en regel eller regeluppsättning att aktiveras fullständigt. Du behöver inte ändra meddelanden eller publicera om resor för att en regel ska börja gälla.

<!--Currently, once a rule set is activated, no more rules can be added to that rule set.-->

Om du vill inaktivera en regel eller en regeluppsättning klickar du på knappen **[!UICONTROL More actions]** bredvid det önskade objektet och väljer **[!UICONTROL Deactivate]**.

![](assets/rule-set-inactive-rule.png)

Dess status ändras till **[!UICONTROL Inactive]** och regeln gäller inte för framtida meddelandekörningar. Meddelanden som körs just nu påverkas inte.

>[!NOTE]
>
>När du inaktiverar en regel eller regeluppsättning påverkas eller återställs inte antalet enskilda profiler.

## Få åtkomst till och hantera regeluppsättningar {#access-rule-sets}

Alla skapade regeluppsättningar visas på menyn **[!UICONTROL Administration]** > **[!UICONTROL Business rules]**. De sorteras efter senaste ändringsdatum.

![](assets/rule-sets-list.png)

Klicka på ett regeluppsättningsnamn om du vill visa och redigera innehållet. Alla regler i den regeluppsättningen visas. Med snabbmenyn uppe till höger kan du:

* Redigera regeluppsättningens namn och beskrivning
* Aktivera regeluppsättningen - [läs mer](#activate-rule)
* Ta bort regeluppsättningen

![](assets/rule-set-example.png)

För varje regel i regeluppsättningen kan du med knappen **[!UICONTROL More actions]**:

* Redigera regeln
* Aktivera regeln [läs mer](#activate-rule)
* Ta bort regeln

![](assets/rule-set-example-rules.png)

## Använd regeluppsättningar för ett meddelande eller en resa {#apply-frequency-rule}

Du kan tillämpa en regeluppsättning på ett meddelande eller en resa, beroende på vilken domän som valts när regeluppsättningen skapades. Expandera avsnitten nedan om du vill ha mer information.

+++ Använda en regeluppsättning i ett meddelande

1. När du skapar en [kampanj](../campaigns/create-campaign.md) väljer du en av de kanaler som du har definierat för regeluppsättningen och redigerar innehållet i meddelandet.

1. Klicka på knappen **[!UICONTROL Add Business Rule]** på skärmen för innehållsutgåva.

1. Välj den [regeluppsättning du skapade](#create-rule-set).

   ![](assets/rule-set-campaign-add-rule-button.png)

   >[!NOTE]
   >
   >Endast [aktiverade](#activate-rule) regeluppsättningar visas i listan.

   <!--Messages where the category selected is **[!UICONTROL Transactional]** will not be evaluated against business rules.-->

1. Innan du aktiverar kampanjen måste du schemalägga att den ska köras minst 10 minuter framåt.

   Detta ger tillräckligt med tid för att fylla i räknarvärdena för profilen för affärsregeln som du har valt. Om du aktiverar kampanjen direkt fylls inte regeluppsättningens räknarvärden i mottagarnas profiler och meddelandet räknas inte mot deras regler för frekvensbegränsning för anpassade regeluppsättningar.

   ![](assets/rule-set-schedule-campaign.png)

1. Du kan visa antalet profiler som har uteslutits från leverans i [Customer Journey Analytics-rapporten](../reports/report-gs-cja.md) och i [Live-rapporten](../reports/live-report.md), där frekvensreglerna listas som en möjlig orsak för användare som har uteslutits från leverans.

>[!NOTE]
>
>Flera regler kan gälla för samma kanal, men när den nedre gränsen har nåtts utesluts profilen från nästa leverans.

<!--
## Example: combine several rules {#frequency-rule-example}

You can combine several message frequency rules, such as described in the example below.

1. [Create a rule](#create-new-rule) called *Overall Marketing Capping*:

   * Select all channels.
   * Set capping to 12 monthly.

   ![](assets/message-rules-ex-overall-cap.png)

1. To further restrict the number of marketing-based push notifications that a user is sent, create a second rule called *Push Marketing Cap*:

   * Select Push channel.
   * Set capping to 4 monthly.

   ![](assets/message-rules-ex-push-cap.png)

1. Save and [activate](#activate-rule) the rule.

1. [Create a message](../building-journeys/journeys-message.md) for every channel you want to communicate through and select the **[!UICONTROL Marketing]** category for each message. [Learn how to apply a frequency rule](#apply-frequency-rule)

   ![](assets/journey-message-category.png)

In this scenario, an individual profile:
* can receive up to 12 marketing messages per month;
* but will be excluded from marketing push notifications after they have received 4 push notifications.-->

När du testar frekvensregler rekommenderar vi att du använder en ny [testprofil](../audience/creating-test-profiles.md) eftersom det inte finns något sätt att återställa räknaren förrän nästa period när en profils frekvensgräns har nåtts. Om du inaktiverar en regel kan mappade profiler ta emot meddelanden, men inga räknarsteg tas bort eller tas bort.

+++

+++ Tillämpa en regeluppsättning på en resa

Om du vill tillämpa en begränsningsregel på en resa får du åtkomst till resan och öppnar dess egenskaper. Välj den relevanta regeluppsättningen i listrutan **[!UICONTROL Capping rules]**.

![](../conflict-prioritization//assets/journey-capping-apply.png)

>[!IMPORTANT]
>
>Om en resa aktiveras omedelbart kan det ta upp till 10 minuter för systemet att börja inaktivera kunder. Du kan schemalägga din resa så att den börjar minst 10 minuter framåt för att förhindra den här möjligheten.

+++

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3444730?quality=12&captions=swe)
