---
solution: Journey Optimizer
product: journey optimizer
title: Frekvensregler
description: Lär dig hur du definierar frekvensregler
feature: Rules
topic: Content Management
role: User
level: Intermediate
keywords: meddelande, frekvens, regler, tryck
exl-id: 49248fb6-5a91-45b2-9de8-2f078d59c0fc
source-git-commit: 949e7cd05a2b1125e13615814f6501b3906e470c
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 0%

---

# Regler för meddelandefrekvens {#frequency-rules}

[!DNL Journey Optimizer] Med kan du styra hur ofta användare ska få ett meddelande eller delta i en resa genom att ställa in flerkanalsregler som automatiskt utesluter överbegärda profiler från meddelanden och åtgärder.

För ett varumärke kan till exempel en regel vara att inte skicka mer än fyra marknadsföringsmeddelanden per månad till sina kunder. För att göra detta kan du använda en frekvensregel som begränsar antalet meddelanden som skickas baserat på en eller flera kanaler under en månadskalenderperiod.

![](assets/do-not-localize/sms-dm-rules.gif)

>[!NOTE]
>
>Reglerna för meddelandefrekvens skiljer sig från reglerna för avanmälningshantering, som gör det möjligt för användare att avbryta prenumerationen på meddelanden från ett varumärke. [Läs mer](../privacy/opt-out.md#opt-out-management)

➡️ [Upptäck den här funktionen i video](#video)

## Åtkomstregler {#access-rules}

Regler är tillgängliga från **[!UICONTROL Administration]** > **[!UICONTROL Rules]** -menyn. Alla regler visas sorterade efter ändringsdatum.

Använd filterikonen för att filtrera efter kategori, status och/eller kanal. Du kan också söka på meddelandeetiketten.

![](assets/message-rules-filter.png)

### Behörigheter{#permissions-frequency-rules}

Om du vill komma åt, skapa, redigera eller ta bort regler för meddelandefrekvens måste du ha **[!UICONTROL Manage frequency rules]** behörighet.

Användare med **[!UICONTROL View frequency rules]** behörighet kan visa regler, men inte ändra eller ta bort dem.

![](assets/message-rules-access.png)

Läs mer om behörigheter i [det här avsnittet](../administration/high-low-permissions.md).

## Skapa en regel {#create-new-rule}

>[!CONTEXTUALHELP]
>id="ajo_rules_category"
>title="Välj meddelanderegelkategori"
>abstract="När det aktiveras och används för ett meddelande, kommer alla frekvensregler som matchar den valda kategorin automatiskt att tillämpas på det här meddelandet. För närvarande är endast marknadsföringskategorin tillgänglig."

>[!CONTEXTUALHELP]
>id="ajo_rules_capping"
>title="Ange begränsning för din regel"
>abstract="Ange det maximala antalet meddelanden som skickas till en kundprofil inom den valda tidsramen. Frekvensgränsen baseras på den valda kalenderperioden och återställs i början av motsvarande tidsram."

>[!CONTEXTUALHELP]
>id="ajo_rules_channel"
>title="Definiera de kanaler som regeln gäller för"
>abstract="Välj minst en kanal. Taket tillämpas över alla kanaler som ett totalt antal."

Följ stegen nedan för att skapa en ny regel.

1. Öppna **[!UICONTROL Message frequency rules]** lista och klicka sedan på **[!UICONTROL Create rule]**.

   ![](assets/message-rules-create.png)

1. Definiera regelnamnet och markera meddelanderegelkategorin.

   >[!NOTE]
   >
   >Endast **[!UICONTROL Marketing]** finns tillgänglig.

   ![](assets/message-rules-details.png)

1. Från **[!UICONTROL Duration]** i den nedrullningsbara listan väljer du en tidsram för den begränsning som ska användas. [Läs mer](#frequency-cap)

1. Ange begränsningen för regeln, vilket innebär det maximala antalet meddelanden som kan skickas till en enskild användarprofil varje månad eller vecka <!--or day--> - enligt dina val ovan.

   <!--![](assets/message-rules-capping.png)-->

1. Markera kanalen som du vill använda för den här regeln: **[!UICONTROL Email]**, **[!UICONTROL Push notification]**, **[!UICONTROL SMS]** eller **[!UICONTROL Direct mail]**.

   ![](assets/message-rules-channels.png)

   >[!NOTE]
   >
   >Du måste välja minst en kanal för att kunna skapa regeln.

1. Markera flera kanaler om du vill tillämpa begränsning för alla markerade kanaler som ett totalt antal.

   Ange till exempel 15 som capping och markera både e-post- och push-kanalerna. Om en profil redan har fått 10 marknadsföringsmeddelanden och 5 push-meddelanden för marknadsföring under den valda perioden, kommer den här profilen inte att ingå i nästa leverans av marknadsföringsmeddelanden eller push-meddelanden.

1. Klicka **[!UICONTROL Save as draft]** för att bekräfta att regeln har skapats. Ditt meddelande läggs till i regellistan med **[!UICONTROL Draft]** status.

   ![](assets/message-rules-created.png)

### Frekvenslock {#frequency-cap}

Från **[!UICONTROL Duration]** väljer du om du vill att capping ska användas månads- eller veckovis.

>[!NOTE]
>
>Daglig frekvens finns också tillgänglig vid behov. [Läs mer](#daily-frequency-cap)

Frekvensgränsen baseras på den valda kalenderperioden. Den återställs i början av motsvarande tidsram.

![](assets/message-rules-capping-duration.png)

Räknaren för varje period har följande förfallodatum:

* **[!UICONTROL Monthly]**: Frekvensbegränsningen gäller till den sista dagen i månaden vid 23:59:59 UTC. Månadsförfallodatumet för januari är till exempel 01-31 23:59:59 UTC.

* **[!UICONTROL Weekly]**: Frekvensbegränsningen gäller till lördag 23:59:59 UTC den veckan då kalenderveckan börjar på söndag. Utgångsdatumet är oberoende av hur regeln skapas. Om regeln till exempel skapas på torsdag gäller den till lördag den 23:59:59.

### Daglig frekvensbegränsning {#daily-frequency-cap}

Förutom månatligt och veckovis finns daglig frekvens tillgänglig vid behov. Kontakta din Adobe-representant om du vill veta mer.

Den dagliga frekvensen gäller för dagen till 23:59:59 UTC och återställer till 0 i början av nästa dag.

>[!NOTE]
>
>Vid hantering av [gruppsegmentering](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#batch){target="_blank"}, the daily counters may not accurately reflect the current values as the daily counter snapshot is taken at midnight UTC the night before. Consequently, relying on daily counters in this scenario becomes impractical, as the snapshot does not reflect the most up-to-date counter values on the profile. To ensure accuracy for daily frequency capping rules, the use of [streaming segmentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/streaming-segmentation.html){target="_blank"} rekommenderas. Läs mer om metoder för målgruppsutvärdering i [det här avsnittet](../audience/about-audiences.md#evaluation-method-in-journey-optimizer).

## Aktivera en regel {#activate-rule}

När en regel för meddelandefrekvens skapas har den **[!UICONTROL Draft]** status och påverkar ännu inte något meddelande. Om du vill aktivera den klickar du på ellipsen bredvid regeln och väljer **[!UICONTROL Activate]**.

![](assets/message-rules-activate.png)

Om du aktiverar en regel påverkas alla meddelanden som gäller för nästa körning. Lär dig hur [tillämpa en frekvensregel på ett meddelande](#apply-frequency-rule).

>[!NOTE]
>
>Det kan ta upp till 10 minuter innan en regel aktiveras helt. Du behöver inte ändra meddelanden eller publicera om resor för att en regel ska börja gälla.

Om du vill inaktivera en regel för meddelandefrekvens klickar du på ellipsen bredvid regeln och väljer **[!UICONTROL Deactivate]**.

![](assets/message-rules-deactivate.png)

Regelens status ändras till **[!UICONTROL Inactive]** och regeln gäller inte för framtida meddelandekörningar. Meddelanden som körs just nu påverkas inte.

>[!NOTE]
>
>När du inaktiverar en regel påverkas eller återställs inte antalet enskilda profiler.

## Tillämpa en frekvensregel på ett meddelande {#apply-frequency-rule}

Följ stegen nedan för att tillämpa en frekvensregel på ett meddelande.

1. När en [resa](../building-journeys/journey-gs.md)lägger du till ett meddelande genom att välja någon av de kanaler som du har definierat för regeln.

1. Välj den kategori som du har definierat för [regel som du skapade](#create-new-rule).

   ![](assets/journey-message-category.png)

   >[!NOTE]
   >
   >För närvarande bara **[!UICONTROL Marketing]** finns för regler för meddelandefrekvens.

1. Du kan klicka på **[!UICONTROL Frequency rule]** om du vill visa skärmen med frekvensregler på en ny flik. [Läs mer](#access-rules)

   Alla frekvensregler som matchar den valda kategorin och kanalen/kanalerna tillämpas automatiskt på det här meddelandet.

   >[!NOTE]
   >
   >Meddelanden där den valda kategorin är **[!UICONTROL Transactional]** utvärderas inte mot frekvensregler.

1. Du kan visa antalet profiler som har uteslutits från leverans i [Global rapport](../reports/global-report.md)och i [Live-rapport](../reports/live-report.md), där frekvensreglerna listas som en möjlig orsak för användare som inte får leverera.

>[!NOTE]
>
>Flera regler kan gälla för samma kanal, men när den nedre gränsen har nåtts utesluts profilen från nästa leverans.

## Exempel: kombinera flera regler {#frequency-rule-example}

Du kan kombinera flera regler för meddelandefrekvens, som beskrivs i exemplet nedan.

1. [Skapa en regel](#create-new-rule) anropad *Total marknadsföringstak*:

   * Markera alla kanaler.
   * Ställ in capping på 12 månatliga.

   ![](assets/message-rules-ex-overall-cap.png)

1. Om du vill begränsa antalet marknadsföringsbaserade push-meddelanden som en användare skickas vidare skapar du en andra regel som kallas *Push Marketing Cap*:

   * Välj Push-kanal.
   * Ställ in capping på 4 månatliga.

   ![](assets/message-rules-ex-push-cap.png)

1. Spara och [activate](#activate-rule) regeln.

1. [Skapa ett meddelande](../building-journeys/journeys-message.md) för varje kanal som du vill kommunicera genom och välja **[!UICONTROL Marketing]** kategori för varje meddelande. [Lär dig hur du använder en frekvensregel](#apply-frequency-rule)

   ![](assets/journey-message-category.png)


<!--
Learn how to create a message for the different channels in the following sections:
* [Create an email](../email/create-email.md)
* [Create a push notification](../push/create-push.md)
* [Create an SMS](../sms/create-sms.md)
* [Create a direct mail](../direct-mail/create-direct-mail.md)

Create an email and select the **[!UICONTROL Marketing]** category for that message. [Learn more](../email/create-email.md)

Create a push notification and select the **[!UICONTROL Marketing]** category for that message. [Learn more](../push/create-push.md)

Create an SMS and select the **[!UICONTROL Marketing]** category for that message. [Learn more](../sms/create-sms.md)

Create a direct mail and select the **[!UICONTROL Marketing]** category for that message. [Learn more](../direct-mail/create-direct-mail.md)
-->

I det här scenariot finns en enskild profil:
* kan ta emot upp till 12 marknadsföringsmeddelanden per månad,
* men utesluts från push-meddelanden om marknadsföring när de har fått 4 push-meddelanden.

>[!NOTE]
>
>När du testar frekvensregler bör du använda en ny [testprofil](../audience/creating-test-profiles.md)eftersom det inte finns något sätt att återställa räknaren förrän nästa månad när en profils övre gräns för frekvens har nåtts. Om du inaktiverar en regel kan mappade profiler ta emot meddelanden, men inga räknarsteg tas bort eller tas bort.

## Instruktionsvideo {#video}

Lär dig hur du skapar, aktiverar, testar och rapporterar frekvensregler.

>[!VIDEO](https://video.tv.adobe.com/v/344451?quality=12)
