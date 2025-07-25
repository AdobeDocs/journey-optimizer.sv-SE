---
solution: Journey Optimizer
product: journey optimizer
title: Lägga till en kanalaktivitet i en flerstegskampanj
description: Lär dig hur du lägger till en kanalaktivitet i en flerstegskampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: ffe1e77c-6c4f-4f23-9183-d715a4c7c402
source-git-commit: 3c3ef1555c587b3e50e3b70596fbac98e87d414e
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 1%

---

# Kanalaktiviteter {#channel}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_email"
>title="E-postaktivitet"
>abstract="Med e-postaktiviteten kan du skicka e-postmeddelanden inom din samordnade kampanj, både för engångs- och återkommande meddelanden. Den automatiserar processen för att skicka e-post till ett mål som beräknas inom samma samordnade kampanj. Ni kan kombinera kanalaktiviteter till en kampanjarbetsyta i flera steg för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_sms"
>title="SMS-aktivitet"
>abstract="Med SMS-aktiviteten kan du skicka SMS i din samordnade kampanj, både för enstaka och återkommande meddelanden. Den automatiserar processen för att skicka SMS till ett mål som beräknas inom samma samordnade kampanj. Ni kan kombinera kanalaktiviteter i en flerstegskampanj för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push"
>title="Push-aktivitet"
>abstract="Med aktiviteten Push kan du skicka push-meddelanden som en del av din samordnade kampanj. Det gör det möjligt att leverera både engångskampanjer och återkommande samordnade kampanjer, och automatisera sändning av push-meddelanden till ett fördefinierat mål inom samma samordnade kampanj. Ni kan kombinera kanalaktiviteter i kampanjarbetsytan för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data."

<!--
UNUSED IDs in BJ

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push_ios"
>title="Push iOS activity"
>abstract="The Push iOS activity let you send iOS Push notifications as part of your orchestrated campaign. It enables the delivery of both one-time and recurring orchestrated campaigns, automating the sending iOS Push notifications to a predefined target within the same workflow. You can combine channel activities into the campaign canvas to create cross-channel campaigns that can trigger actions based on customer behavior and data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_push_android"
>title="Push Android activity"
>abstract="The Push Android activity ket you send Android Push notifications as part of your orchestrated campaign. It enables the delivery of both one-time and recurring messages, automating the sending Android Push notifications to a predefined target within the same orchestrated campaign. You can combine channel activities into the orchestrated campaign canvas to create cross-channel campaigns that can trigger actions based on customer behavior and data."

-->

>[!CONTEXTUALHELP]
>id="ajo_orchestration_directmail"
>title="Aktivitet för direktreklam"
>abstract="Med aktiviteten Direktutskick blir det lättare att skicka direktreklam inom ramen för den orkestrerade kampanjen, både för enstaka och återkommande meddelanden. Den automatiserar processen för att generera extraheringsfilen som krävs av direktreklamleverantörer. Ni kan kombinera kanalaktiviteter i den samordnade kampanjarbetsytan för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data."


+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](../gs-schemas.md)</li><li>[Manuellt schema](../manual-schema.md)</li><li>[Filöverföringsschema](../file-upload-schema.md)</li><li>[Ingest data](../ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](../access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa en orkestrerad kampanj](../gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](../create-orchestrated-campaign.md)<br/><br/>[Orchestrate-aktiviteter](../orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med regelbyggaren](../orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md)<br/><br/>[Återmarknadsföring](../retarget.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - <b>[Kanalaktiviteter](channels.md)</b> - [Kombinera](combine.md) - [Deduplicering](deduplication.md) - [Enrichment](enrichment.md) - [Fork](fork.md)  - [Avstämning](reconciliation.md) - [Spara målgrupp](save-audience.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Med [!DNL Adobe Journey Optimizer] kan du automatisera och köra marknadsföringskampanjer över flera kanaler - e-post, SMS och push-meddelanden. Ni kan kombinera de här kanalaktiviteterna i kampanjarbetsytan för att skapa flerkanaliga samordnade kampanjer som kan utlösa åtgärder baserat på kundbeteende och data.

Exempel:
* Skicka en välkomstserie via e-post, SMS och push.
* Skicka ett uppföljningsmejl efter köpet.
* Skicka personliga födelsedagshälsningar via SMS.

Genom att använda kanalaktiviteter kan ni skapa omfattande och personaliserade kampanjer som engagerar kunder över flera kontaktytor och driver konverteringar.

>[!PREREQUISITES]
>
>Definiera målgruppen med en [Bygg målgruppsaktivitet](build-audience.md) innan du lägger till en kanalaktivitet.

## Lägga till en kanalaktivitet och definiera dess egenskaper {#add}

1. Lägg till en kanalaktivitet på arbetsytan. De tillgängliga kanalaktiviteterna är **[!UICONTROL Email]**, **[!UICONTROL SMS]** och **[!UICONTROL Push]**.

   ![bild som visar arbetsytan med tillgängliga aktiviteter](../assets/channel-add.png)

1. Markera aktiviteten och klicka på **[!UICONTROL Edit email]**, **[!UICONTROL Edit SMS]** eller **[!UICONTROL Edit Push]** beroende på vald kanal.

   ![bild som visar arbetsytan med en e-postaktivitet](../assets/channel-edit.png)

1. På fliken **[!UICONTROL Properties]** anger du en beskrivning och växlar sedan till fliken **[!UICONTROL Actions]** för att konfigurera aktiviteten.

## Ställ in kanalkonfiguration och inställningar {#configuration}

Använd fliken **[!UICONTROL Actions]** för att välja en kanalkonfiguration för meddelandet och konfigurera ytterligare inställningar som spårning, innehållsexperiment eller flerspråkigt innehåll.

1. **Välj en kanalkonfiguration**

   En konfiguration definieras av en [systemadministratör](../../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Lär dig hur du konfigurerar kanalkonfigurationer](../../configuration/channel-surfaces.md).

   ![bild som visar avsnittet Åtgärder](../assets/channel-actions.png)

1. **Använd regler för begränsning**

   I listrutan **[!UICONTROL Rule set]** väljer du en kanalregeluppsättning för att tillämpa appningsregler på kampanjen. Genom att utnyttja kanalregeluppsättningar kan ni ange frekvensbegränsning efter kommunikationstyp för att förhindra att kunder med liknande meddelanden överbelastas. [Lär dig arbeta med regeluppsättningar](../conflict-prioritization/rule-sets.md)

1. **Spåra engagemang** (e-post och SMS)

   Använd avsnittet **[!UICONTROL Action tracking]** för att spåra hur dina mottagare svarar på dina e-post- eller SMS-leveranser. Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts. [Läs mer om kampanjrapporter](../../reports/campaign-global-report-cja.md)

1. **Aktivera läget Snabb leverans** (push)

   Snabb leverans är ett [!DNL Journey Optimizer]-tillägg som tillåter mycket snabba push-meddelanden som skickas i stora volymer via kampanjer. Snabba leveranser används när fördröjningar i meddelandeleverans är affärskritiska när du vill skicka en snabb push-varning på mobiltelefoner, till exempel nyheter till användare som har installerat din nyhetskanalapp. Mer information om prestanda när du använder läget Snabb leverans finns i [Adobe Journey Optimizer produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/adobe-journey-optimizer.html).

1. **Skapa ett innehållsexperiment**

   Använd avsnittet **[!UICONTROL Content experiment]** för att definiera flera leveransbehandlingar för att mäta vilken som fungerar bäst för målgruppen. Klicka på knappen **[!UICONTROL Create experiment]** och följ sedan stegen som beskrivs i det här avsnittet: [Skapa ett innehållsexperiment](../../content-management/content-experiment.md).

1. **Lägg till flerspråkigt innehåll**

   Använd avsnittet **[!UICONTROL Languages]** för att skapa innehåll på flera språk i kampanjen. Om du vill göra det klickar du på knappen **[!UICONTROL Add languages]** och väljer önskad **[!UICONTROL Language settings]**. Detaljerad information om hur du konfigurerar och använder flerspråkiga funktioner finns i det här avsnittet: [Kom igång med flerspråkigt innehåll](../../content-management/multilingual-gs.md)

   ![bild som visar avsnittet om innehållsexperiment](../assets/channel-experiment.png)

När kanalaktiviteten har konfigurerats väljer du fliken **[!UICONTROL Content]** för att definiera dess innehåll.

## Definiera innehållet {#content}

Växla till fliken **[!UICONTROL Content]** för att skapa meddelandet. Stegen varierar beroende på den valda kanalen. Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sidor.

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;" >
<td><a href="../../email/create-email.md"><img alt="e-post" src="../../channels/assets/do-not-localize/email.png"></a><br/><a href="../../email/create-email.md"><strong>Skapa ett e-postmeddelande</strong></a></td>
<td><a href="../../sms/create-sms.md"><img alt="sms" src="../../channels/assets/do-not-localize/sms.png"></a><br/><a href="../../sms/create-sms.md"><strong>Skapa ett SMS</strong></a></td>
<td><a href="../../push/create-push.md"><img alt="push" src="../../channels/assets/do-not-localize/push.png"></a><a href="../../push/create-push.md"><strong>Skapa ett push-meddelande</strong></a></td>
</tr></table>

## Lägg till personalisering

Personalization i samordnade kampanjer fungerar ungefär som andra **[!UICONTROL Journey Optimizer]**-kampanjer eller resor, men med några viktiga skillnader som är specifika för den orkestrerade arbetsytan.

När du öppnar personaliseringsredigeraren från en orchestrerad kampanj innehåller två huvudmappar tillgängliga attribut för personalisering som anges nedan.

* **[!UICONTROL Profile attributes]**

  Den här mappen innehåller alla profilrelaterade data från [!DNL Adobe Experience Platform]. Det här är standardattribut som namn, e-postadress, plats eller andra egenskaper som har hämtats i användarprofilen.

* **[!UICONTROL Target attributes]** (gäller endast samordnade kampanjer)

  Den här mappen är unik för samordnade kampanjer. Den innehåller attribut som beräknas direkt i kampanjarbetsytan. Den innehåller två undermappar:

   * **`<Targeting dimension>`** (t.ex. &quot;Mottagare&quot;, &quot;Inköp&quot;): Innehåller alla attribut som är relaterade till den dimension som kampanjen riktar sig till.

   * **`Enrichment`**: Inkluderar data som lagts till via **[!UICONTROL Enrichment]** aktiviteter på arbetsytan. På så sätt kan ni personalisera meddelanden baserat på externa datauppsättningar eller ytterligare logik som integrerats under orkestreringen. [Lär dig använda en anrikningsaktivitet](../activities/enrichment.md)

En detaljerad översikt om hur du använder personaliseringsredigeraren finns i [Kom igång med personalisering](../../personalization/personalize.md)

## Kontrollera och testa innehållet

När innehållet har skapats kan du använda knappen **[!UICONTROL Simulate Content]** för att förhandsgranska och testa innehållet med testprofiler eller exempelindata som har överförts från en CSV-/JSON-fil, eller lägga till manuellt. [Läs mer](../../content-management/preview-test.md)

![bild som visar knappen Simulera innehåll](../assets/channel-simulate.png)

## Nästa steg {#next}

När meddelandeinnehållet är klart går du tillbaka till den orkestrerade kampanjen med pilen **[!UICONTROL Back]**. Du kan sedan slutföra aktivitetssamordningen på arbetsytan och publicera kampanjen för att börja skicka meddelanden. [Lär dig hur du startar och övervakar samordnade kampanjer](../start-monitor-campaigns.md)

![bild som visar bakåtknappen](../assets/channel-back.png)

<!--
## Examples {#cross-channel-workflow-sample}

Here is a cross-channel orchestrated campaign example with a segmentation and two deliveries. The orchestrated campaign targets all customers who live in Paris and who are interested in coffee machines. Among this population, an email is sent to the regular customers and an SMS is sent to the VIP clients.

![](../assets/workflow-channel-example.png)

<!--
description, which use case you can perform (common other activities that you can link before of after the activity)

how to add and configure the activity

example of a configured activity within a workflow
The Email delivery activity allows you to configure the sending an email in a workflow. 

-->

<!--You can also create a recurring orchestrated campaign to send a personalized SMS every first day of the month at 8 PM to all customers living in Paris.

![](../assets/workflow-channel-example2.png)-->

<!-- Scheduled emails available?

This can be a single send email and sent just once, or it can be a recurring email.
* Single send emails are standard emails, sent once.
* Recurring emails allow you to send the same email multiple times to different targets over a defined period. You can aggregate the deliveries per period in order to get reports that correspond to your needs.

When linked to a scheduler, you can define recurring emails.
Email recipients are defined upstream of the activity in the same workflow, via an Audience targeting activity.

-->


<!--The message preparation is triggered according to the workflow execution parameters. From the message dashboard, you can select whether to request or not a manual confirmation to send the message (required by default). You can start the workflow manually or place a scheduler activity in the workflow to automate execution.-->
