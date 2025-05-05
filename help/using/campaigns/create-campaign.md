---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en kampanj
description: Lär dig skapa kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: skapa, optimera, kampanj, yta, meddelanden
exl-id: 617d623c-e038-4b5b-a367-5254116b7815
source-git-commit: 47185cdcfb243d7cb3becd861fec87abcef1f929
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 3%

---

# Skapa en kampanj {#create-campaign}

Om du vill skapa en ny kampanj bläddrar du till menyn **[!UICONTROL Campaigns]** till vänster och klickar sedan på **[!UICONTROL Create campaign]**. Du kan också duplicera en befintlig livekampanj och skapa en ny. [Lär dig hur](modify-stop-campaign.md#duplicate).

Läs igenom kampanjkraven på [den här sidan](get-started-with-campaigns.md#before-starting-campaign-prerequisites) innan du startar.

## Välj kampanjtyp {#campaigntype}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="Kampanjtyp"
>abstract="**Schemalagda kampanjer** körs omedelbart eller på ett angivet datum och är avsedda att skicka meddelanden av marknadsföringstyp. **API-utlösta** kampanjer körs med ett API-anrop. Syftet är att skicka antingen marknadsföringsmeddelanden (reklammeddelanden som kräver användarens samtycke) eller transaktionsmeddelanden (icke-kommersiella meddelanden, som också kan skickas till profiler som inte längre prenumererar i specifika sammanhang)."

När du skapar en ny kampanj måste du först välja kampanjtyp. Det finns tre typer av kampanjer:

1. **[!UICONTROL Scheduled - Marketing]** - Dessa kampanjer körs omedelbart eller på ett angivet datum. Schemalagda kampanjer syftar till att skicka **marknadsföringsmeddelanden** eller skapa inkommande åtgärder. De konfigureras och körs från användargränssnittet.

1. **[!UICONTROL API-triggered - Marketing]** - Dessa kampanjer körs med ett API-anrop. Välj den här typen av kampanj för att skicka personaliserad marknadskommunikation till målgrupper.  [Lär dig hur du utlöser en kampanj med API:er](api-triggered-campaigns.md)

1. **[!UICONTROL API-triggered - Transactional]** - Samma som för API-utlösta - marknadsföringskampanjer körs de här kampanjerna med ett API-anrop. API-utlösta transaktionskampanjer syftar till att skicka **transaktionsmeddelanden**, d.v.s. meddelanden som skickas ut efter en åtgärd som utförts av en individ: lösenordsåterställning, kundvagn, osv.  [Lär dig hur du utlöser en kampanj med API:er](api-triggered-campaigns.md)

   ![](assets/create-campaign-modal.png)

## Definiera kampanjegenskaperna {#create}

När kampanjen har skapats måste du definiera dess egenskaper. Följ stegen nedan:

1. Ange kampanjens namn och en beskrivning i avsnittet **[!UICONTROL Properties]**.

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../content-management/content-experiment.md).-->

1. (valfritt) Använd fältet **Taggar** för att tilldela enhetliga Adobe Experience Platform-taggar till kampanjen. På så sätt kan ni enkelt klassificera dem och förbättra sökningen från kampanjlistan. [Lär dig arbeta med taggar](../start/search-filter-categorize.md#tags).

1. (valfritt) Du kan begränsa åtkomsten till den här kampanjen baserat på åtkomstetiketter. Om du vill lägga till en åtkomstbegränsning bläddrar du till knappen **[!UICONTROL Manage access]** högst upp på sidan. Se till att endast markera etiketter som du har behörighet för. [Läs mer om åtkomstkontroll på objektnivå](../administration/object-based-access.md).

## Definiera kampanjmålgruppen {#audience}

Nu kan ni välja målgrupp för er kampanj. En målgrupp är en uppsättning personer som har liknande beteenden och/eller egenskaper.

>[!IMPORTANT]
>
>* Användning av målgrupper och attribut från [målgruppskomposition](../audience/get-started-audience-orchestration.md) är för närvarande inte tillgängligt för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.
>
>* För API-utlösta kampanjer måste målgruppen anges via API-anrop.

Så här definierar du målgruppen för en schemalagd marknadsföringskampanj:

1. Klicka på knappen **[!UICONTROL Select audience]** i avsnittet **Målgrupp** för att visa en lista över tillgängliga Adobe Experience Platform-målgrupper. Läs mer om målgrupper i [det här avsnittet](../audience/about-audiences.md).

1. I fältet **[!UICONTROL Identity type]** väljer du vilken typ av nyckel som ska användas för att identifiera personer från den valda målgruppen. Du kan antingen använda en befintlig identitetstyp eller skapa en ny med hjälp av Adobe Experience Platform identitetstjänst. Standardidentitetsnamnutrymmen visas på [den här sidan](https://experienceleague.adobe.com/sv/docs/experience-platform/identity/features/namespaces#standard){target="_blank"}.

   Endast en identitetstyp tillåts per kampanj. Individer som tillhör ett segment som inte har den valda identitetstypen bland sina olika identiteter kan inte omfattas av kampanjen.

   ![](assets/create-campaign-namespace.png)

   Läs mer om identitetstyper och namnutrymmen i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=sv){target="_blank"}.

   <!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->


## Välj kanalen {#channel}

Nu kan du välja kanalen och dess konfiguration. Följ stegen nedan:

1. Välj kommunikationskanalen i avsnittet **[!UICONTROL Action]**.

   Listan över tillgängliga kanaler beror på din licensmodell och tillägg. För API-utlösta kampanjer är endast e-post-, SMS- och push-meddelandekanaler tillgängliga.

1. Välj kanalkonfiguration.

   En konfiguration definieras av en [systemadministratör](../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Läs mer](../configuration/channel-surfaces.md).

   Endast kanalkonfigurationer som är kompatibla med marknadsföringskampanjtypen visas i listrutan.

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >Om du skapar en kampanj för push-meddelanden kan du aktivera **[!UICONTROL Rapid delivery mode]**, som är ett Journey Optimizer-tillägg som tillåter mycket snabba push-meddelanden som skickas i stora volymer. [Läs mer](../push/create-push.md#rapid-delivery)

## Redigera innehållet {#content}

Du kan nu definiera innehållet i meddelandet från knappen **[!UICONTROL Edit content]**. Hur du skapar innehåll beror på vilken kanal du har valt.

Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sidor:


<table style="table-layout:fixed"><tr style="border: 0;">
<td><a href="../email/create-email.md"><img alt="e-post" src="../channels/assets/do-not-localize/email.png"></a>
<div align="center"><a href="../email/create-email.md"><strong>E-post</strong></a></div></td>
<td><a href="../sms/create-sms.md"><img alt="sms" src="../channels/assets/do-not-localize/sms.png"></a>
<div align="center"><a href="../sms/create-sms.md"><strong>SMS</strong></a></div></td>
<td><a href="../push/create-push.md"><img alt="push" src="../channels/assets/do-not-localize/push.png"></a>
<div align="center"><a href="../push/create-push.md"><strong>Push-meddelande</strong></a></div></td>
<td><a href="../direct-mail/create-direct-mail.md"><img alt="direktreklam" src="../channels/assets/do-not-localize/direct-mail.jpg"></a>
<div align="center"><a href="../direct-mail/create-direct-mail.md"><strong>Direktutskick</strong></a></div></td>
</tr></table>

<table style="table-layout:fixed"><tr style="border: 0;">
<td><a href="../in-app/create-in-app.md"><img alt="i appen" src="../channels/assets/do-not-localize/inapp.jpg"></a>
<div align="center"><a href="../in-app/create-in-app.md"><strong>I appen</strong></a></div></td>
<td><a href="../web/create-web.md"><img alt="webb" src="../channels/assets/do-not-localize/web.jpg"></a>
<div align="center"><a href="../web/create-web.md"><strong>Webb</strong></a></div></td>
<td><a href="../code-based/create-code-based.md"><img alt="kodbaserad upplevelse" src="../channels/assets/do-not-localize/code.png"></a>
<div align="center"><a href="../code-based/create-code-based.md"><strong>Kodbaserad upplevelse</strong></a></div></td>
<td><a href="../content-card/create-content-card.md"><img alt="innehållskort" src="../channels/assets/do-not-localize/cards.png"></a>
<div align="center"><a href="../content-card/create-content-card.md"><strong>Innehållskort</strong></a></div></td>
</tr></table>

När innehållet har definierats kan du använda knappen **[!UICONTROL Simulate content]** för att förhandsgranska och testa innehållet med testprofiler eller exempelindata som har överförts från en CSV-/JSON-fil, eller lägga till manuellt. [Läs mer](../content-management/preview-test.md). Klicka på vänsterpilen om du vill gå tillbaka till skärmen där kampanjen skapades.

![](assets/create-campaign-design.png)

Förutom själva meddelandeinnehållet kan du konfigurera följande inställningar:

1. (valfritt) I avsnittet **[!UICONTROL Content experiment]** kan du använda knappen **[!UICONTROL Create experiment]** för att testa vilket innehåll som fungerar bäst. Funktionerna för innehållsexperimenterande beskrivs i [det här avsnittet](../content-management/content-experiment.md).

1. I avsnittet **[!UICONTROL Actions tracking]** anger du om du vill spåra hur mottagarna svarar på leveransen: du kan spåra klick och/eller öppningar.

   Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts. [Läs mer om kampanjrapporter](../reports/campaign-global-report-cja.md)

## Schemalägg kampanjen {#schedule}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="Kampanjschema"
>abstract="Som standard börjar kampanjer vid manuell aktivering och avslutas omedelbart efter att meddelandet har skickats en gång. Du kan ange ett specifikt datum och en speciell tid för meddelandet som ska skickas. Dessutom kan du ange ett slutdatum för återkommande eller API-utlösta kampanjer. I åtgärdsutlösarna kan du även konfigurera meddelandets sändningsfrekvens så att den passar dina inställningar."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_start"
>title="Kampanjstart"
>abstract="Ange ett datum och en tidpunkt då meddelandet ska skickas."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_end"
>title="Kampanjslut"
>abstract="Ange när en återkommande kampanj ska sluta köras."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_triggers"
>title="Kampanjåtgärdsutlösare"
>abstract="Definiera en frekvens som kampanjens meddelande ska skickas med."

Som standard startar schemalagda kampanjer när de aktiveras manuellt och avslutas så snart meddelandet har skickats en gång.

Om du inte vill köra kampanjen direkt efter aktiveringen kan du ange ett datum och en tidpunkt då meddelandet ska skickas med alternativet **[!UICONTROL Campaign start]**. Med alternativet **[!UICONTROL Campaign end]** kan du ange när en kampanj ska sluta köras.

![](assets/create-campaign-schedule.png)

För e-post-, SMS- och push-meddelandekampanjer kan du definiera en frekvens som kampanjens meddelande ska skickas med. Det gör du genom att använda alternativen **[!UICONTROL Action triggers]** på skärmen för att skapa kampanjer för att ange om kampanjen ska köras varje dag, varje vecka eller varje månad.

>[!NOTE]
>
>När du schemalägger kampanjer i [!DNL Adobe Journey Optimizer] måste du se till att startdatumet/starttiden är i linje med den önskade första leveransen. Om den initiala schemalagda tiden redan har passerat för återkommande kampanjer kommer kampanjerna att föras över till nästa tillgängliga tidsrymd enligt reglerna för återkommande kampanjer.

## Andra inställningar {#settings}

Vissa inställningar är specifika för den kommunikationskanal som har valts för kampanjen eller används för särskilda användningsfall. De beskrivs nedan.

* För e-postmeddelanden kan ni skapa specifika aktiveringskampanjer för IP-warmup-plan. Läs mer i [det här avsnittet](../configuration/ip-warmup-campaign.md).
* För webben, appar och kodbaserade kanaler kan ni tilldela kampanjens prioritetspoäng. Läs mer i [det här avsnittet](../conflict-prioritization/priority-scores.md).
* För innehållskortkampanjer kan du aktivera ytterligare leveransregler för att välja vilka händelser och villkor som utlöser meddelandet. Läs mer i [det här avsnittet](../content-card/create-content-card.md).
* För meddelanden i programmet kan du använda knappen **[!UICONTROL Edit triggers]** för att välja händelser och villkor som utlöser meddelandet. Läs mer i [det här avsnittet](../in-app/create-in-app.md).

## Nästa steg {#next}

När kampanjens konfiguration och innehåll är klart kan du granska och aktivera det. [Läs mer](review-activate-campaign.md)
