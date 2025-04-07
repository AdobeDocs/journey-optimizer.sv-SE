---
solution: Journey Optimizer
product: journey optimizer
title: Lägga till en kanalaktivitet i en flerstegskampanj
description: Lär dig hur du lägger till en kanalaktivitet i en flerstegskampanj
hide: true
hidefromtoc: true
exl-id: ffe1e77c-6c4f-4f23-9183-d715a4c7c402
source-git-commit: 47185cdcfb243d7cb3becd861fec87abcef1f929
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%

---

# Kanalaktiviteter {#channel}

Med Adobe Journey Optimizer kan ni automatisera och genomföra marknadsföringskampanjer i både inkommande och utgående kanaler. Ni kan kombinera kanalaktiviteter i kampanjarbetsytan i flera steg för att skapa flerkanaliga kampanjer som kan utlösa åtgärder baserat på kundbeteende och data. Kanaler som stöds visas på [den här sidan](../../channels/gs-channels.md).

Du kan till exempel skapa en välkomstkampanj för e-post som innehåller en serie meddelanden i olika kanaler, som e-post, SMS, push och direktreklam. Du kan också skicka ett uppföljningsmeddelande via e-post när en kund har slutfört ett köp eller skicka ett personligt födelsedagmeddelande till en kund via SMS.

Genom att använda kanalaktiviteter kan ni skapa omfattande och personaliserade kampanjer som engagerar kunder över flera kontaktytor och driver konverteringar.

## Förhandskrav {#channel-activity-prereq}

Börja bygga en flerstegskampanj med relevanta aktiviteter:

* Innan du infogar en kanalaktivitet måste du definiera målgruppen. Målgruppen är huvudmålet för leveransen: de profiler som tar emot meddelandena.

* Om du vill skicka en återkommande leverans startar du din flerstegskampanj med en **schemaläggaraktivitet**. Du kan också använda en **schemaläggaraktivitet** för engångsleveranser för att ange kontaktdatum för den leveransen. Kontaktdatumet kan även anges i leveransinställningarna. Se [det här avsnittet](scheduler.md).

## Konfigurera en kanalaktivitet {#create-a-delivery-in-a-workflow}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_email"
>title="E-postaktivitet"
>abstract="Med e-postaktiviteten kan du skicka e-postmeddelanden i din flerstegskampanj, både för engångs- och återkommande meddelanden. Den automatiserar processen för att skicka e-post till ett mål som beräknas inom samma flerstegskampanj. Ni kan kombinera kanalaktiviteter till en kampanjarbetsyta i flera steg för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_sms"
>title="SMS-aktivitet"
>abstract="Med SMS-aktiviteten kan du skicka SMS i din flerstegskampanj, både för engångs- och återkommande meddelanden. Den automatiserar processen för att skicka SMS till ett mål som beräknas inom samma flerstegskampanj. Ni kan kombinera kanalaktiviteter i en flerstegskampanj för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push_ios"
>title="Push iOS activity"
>abstract="Med aktiviteten Push iOS kan du skicka push-meddelanden från iOS som en del av din flerstegskampanj. Det gör det möjligt att leverera både engångskampanjer och återkommande flerstegskampanjer, och automatisera sändning av iOS Push-meddelanden till ett fördefinierat mål inom samma arbetsflöde. Du kan kombinera kanalaktiviteter i arbetsytan för arbetsflöden för att skapa flerkanaliga arbetsflöden som kan utlösa åtgärder baserat på kundbeteende och data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push_android"
>title="Push Android activity"
>abstract="Med aktiviteten Push Android skickar du push-meddelanden från Android som en del av din flerstegskampanj. Det gör det möjligt att leverera både engångs- och återkommande meddelanden, och automatiserar utskicksmeddelandena från Android Push till ett fördefinierat mål inom samma flerstegskampanj. Ni kan kombinera kanalaktiviteter i en flerstegskampanj för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_directmail"
>title="Aktivitet för direktreklam"
>abstract="Med aktiviteten Direktutskick blir det lättare att skicka direktreklam i en flerstegskampanj, både för enstaka och återkommande meddelanden. Den automatiserar processen för att generera extraheringsfilen som krävs av direktreklamleverantörer. Ni kan kombinera kanalaktiviteter i en flerstegskampanj för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data."

Följ stegen nedan för att konfigurera en leverans i samband med en flerstegskampanj:

1. Lägg till en kanalaktivitet: **[!UICONTROL Email]**, **[!UICONTROL SMS]**, **[!UICONTROL Push notification (Android)]**, **[!UICONTROL Push notification (iOS)]** eller **[!UICONTROL Direct mail]**.

1. Välj **Typ av leverans**: enkel eller återkommande.

   * En **enskild leverans** är en engångsleverans, som bara skickas en gång, till exempel ett svartvitt e-postmeddelande på fredag.
   * En **återkommande leverans** skickas flera gånger baserat på dess körningsfrekvens som definierats i en [schemaläggaraktivitet](scheduler.md). Varje gång flerstegskampanjen körs beräknas målgruppen om och leveransen skickas till den uppdaterade målgruppen med det uppdaterade innehållet. Det här kan till exempel vara ett veckonyhetsbrev eller ett återkommande födelsedagskalender.

1. Välj en **leveransmall**. Mallar är förkonfigurerade leveransinställningar som är specifika för en kanal. En inbyggd mall är tillgänglig för varje kanal och förfylld som standard.

   ![](../assets/delivery-activity-in-wf.png)

   Du kan välja mallen i det vänstra fönstret för kanalaktivitetskonfigurationen. Om den tidigare valda publiken inte är kompatibel med kanalen kan du inte välja en mall. Du löser detta genom att uppdatera aktiviteten **Bygg målgrupp** och välja en målgrupp med rätt målmappning.

1. Klicka på **Skapa leverans**. Du kan sedan definiera meddelandeinställningar och innehåll på samma sätt som du skapar en fristående leverans. Du kan också testa och simulera innehållet.

1. Gå tillbaka till arbetsflödet. Om du vill fortsätta med arbetsflödet växlar du till alternativet **Generera en utgående övergång** för att lägga till en övergång efter kanalaktiviteten.

1. Klicka på **Start** för att starta din flerstegskampanj.

   Som standard utlöses meddelandeförberedelsefasen när en kampanj i flera steg startas, utan att meddelandet skickas omedelbart.

1. Öppna din kanalaktivitet för att bekräfta sändningen från knappen **Granska och skicka**.

1. Klicka på **Skicka** på kontrollpanelen för leverans.

## Exempel {#cross-channel-workflow-sample}

Här är ett exempel på flerkanaliga kampanjer med segmentering och två leveranser. Flerstegskampanjen riktar sig till alla kunder som bor i Paris och som är intresserade av kaffemaskiner. Bland dessa personer skickas ett e-postmeddelande till de vanliga kunderna och ett SMS skickas till VIP-klienterna.

![](../assets/workflow-channel-example.png)

<!--
description, which use case you can perform (common other activities that you can link before of after the activity)

how to add and configure the activity

example of a configured activity within a workflow
The Email delivery activity allows you to configure the sending an email in a workflow. 

-->

Du kan också skapa en återkommande flerstegskampanj för att skicka ett personaliserat SMS varje dag i månaden kl. 20.00 till alla kunder som bor i Paris.

![](../assets/workflow-channel-example2.png)

<!-- Scheduled emails available?

This can be a single send email and sent just once, or it can be a recurring email.
* Single send emails are standard emails, sent once.
* Recurring emails allow you to send the same email multiple times to different targets over a defined period. You can aggregate the deliveries per period in order to get reports that correspond to your needs.

When linked to a scheduler, you can define recurring emails.
Email recipients are defined upstream of the activity in the same workflow, via an Audience targeting activity.

-->


<!--The message preparation is triggered according to the workflow execution parameters. From the message dashboard, you can select whether to request or not a manual confirmation to send the message (required by default). You can start the workflow manually or place a scheduler activity in the workflow to automate execution.-->
