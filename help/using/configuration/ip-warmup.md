---
solution: Journey Optimizer
product: journey optimizer
title: Implementera en IP-värmerappsplan
description: Lär dig hur du implementerar en IP-värmeringsplan
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP, pooler, grupp, underdomäner, leveransbarhet
hide: true
hidefromtoc: true
source-git-commit: 1ac68f1b3a9657ce71a653011ab92fb817ca80b0
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 1%

---

# Implementera en IP-värmerappsplan {#ip-warmup}

<!--
>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_plan"
>title="Define your IP warmup plan"
>abstract="You can perform IP warmup workflows directly from the Journey Optimizer interface in a standardized and efficient way that follows the best practices for optimal deliverability."
-->

>[!AVAILABILITY]
>
>IP-värmerfunktionen är för närvarande endast tillgänglig som betaversion för utvalda användare. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.

Med [!DNL Journey Optimizer]kan du enkelt utföra arbetsflöden för IP-värmare direkt från användargränssnittet på ett standardiserat och effektivt sätt som följer bästa praxis för optimal leverans.

>[!CAUTION]
>
>Den här funktionen gäller endast för e-postkanalen.

När e-postmeddelanden skickas via en ny plattform, är Internetleverantörer (ISP) misstänkta för IP-adresser som inte känns igen. Om stora mängder e-postmeddelanden plötsligt skickas markerar internetleverantörerna dem ofta som skräppost.

För att undvika att markeras som skräppost kan du öka volymen som skickas stegvis med funktionen för IP-uppvärmningsplan. Med ett nytt alternativ på menyn Administration kan du göra det smidigare i stället för att skapa komplexa resor. Detta bör säkerställa en smidig utveckling av startfasen och göra det möjligt att minska den totala frekvensen av ogiltiga adresser.

>[!NOTE]
>
>Lär dig mer om hur du kan förbättra ditt e-postanseende med IP-uppvärmning i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html).

<!--
Here are the main steps:

1. You get a deliverability plan from the deliverability consulting team.

1. Create a campaign - marketer [Learn more](#create-ip-warmup-campaign)

1. Your associated practitioner (customer's practitioner/ACS consultant/partner consultant) creates a IP warmup object in project and uploads a plan.

    The CSV manifests itself like below with numbers showing up with/without domain bifurcation. Below screen shows one phase (creative) with associated runs (The plan obviously has more such phases)

1. Practitioner associates the campaign and audience at phase level and turns on some settings as needed for all runs associated with a single creative/campaign

1. Then start to execute on every day basis by simply clicking the play button

1. Reports will continue to show up at campaign level with similar capabilities as today. NO enhancements in BETA. But the IP warmup plan also serves as a consolidated report at one single place of how many executions were done and so on

Benefits are as follows:

* No more creation of daily journeys and associated testing

* Standardization on Campaign which will be easy for practitioners too

* No more pain of creating queries, audiences and testing those as system will create the audiences. At phase level, system ensures that previously targeted + new profiles are picked up AND at iteration level, system ensures that each run is having unique profiles and the count matches what is stated in plan

* Ease of excluding domains and changing the plan with help of simple toggles to exclude OR by editing numbers inline or create new phases or reupload plan if drastic change. No more pain of editing audience definitions, journey conditions

* Single place to manage and view how IP warm is progressing.

* Consolidated report at creative/campaign level as all runs for a phase 

* There is an expectation that with this, it will ease around 30% of effort and will be much better experience for consultant/partner/practitioner - right from planning to execution to reporting
-->

De viktigaste stegen för att implementera en plan för IP-uppvärmning är följande:

* [Skapa IP-värmningskampanjer](#create-ip-warmup-campaign)
* [Definiera en IP-värmare](#define-ip-warmup-plan)

## Skapa IP-värmningskampanjer {#create-ip-warmup-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="Aktivera alternativet för IP-värmningsplan"
>abstract="Välj aktiveringsalternativet för IP-warmup-plan. När kampanjen är aktiv kan den kopplas till en IP-värmeringsplan."

Du måste skapa en eller flera kampanjer med ett visst alternativ aktiverat, så att de kan användas i en IP-uppvärmningsplan. Följ stegen nedan.

1. Skapa en [yta](channel-surfaces.md) för domänen och IP-adresserna som du har identifierat för din värdplan.

1. Skapa en [kampanj](../campaigns/create-campaign.md) och väljer [E-post](../email/create-email.md#create-email-journey-campaign) åtgärd.

1. Välj den yta som du skapade för IP-värmare.

   <!--You must use the same surface as the one that will be used for the asociated IP warmup plan. [Learn how to create an IP warmup plan](#create-ip-warmup-plan)-->

1. Klicka på **[!UICONTROL Create]**.

1. Välj **[!UICONTROL IP warmup plan activation]** i avsnittet **[!UICONTROL Schedule]**.

   ![](assets/ip-warmup-campaign-plan-activation.png)

   Kampanjen [schema](../campaigns/create-campaign.md#schedule) styrs av den IP-värmeringsplan som den kommer att kopplas till, vilket innebär att schemat inte definieras mer i själva kampanjen.

1. [Aktivera](../campaigns/review-activate-campaign.md) kampanjen. När den är klar att användas i en IP-värmerapport är den klar att användas.

>[!NOTE]
>
>För en livekampanj med aktiverad IP-uppvärmningsplan **[!UICONTROL Delete]** knappen är tillgänglig tills den är associerad med en IP-värmeringsplan.

Mer information om hur du konfigurerar en kampanj finns i [den här sidan](../campaigns/get-started-with-campaigns.md).

## Definiera en IP-värmare {#define-ip-warmup-plan}

### Hantera planer för IP-värmare {#manage-ip-warmup-plans}

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP warmup plans]**-menyn. Alla IP-uppvärmningsplaner som har skapats hittills visas.

   ![](assets/ip-warmup-filter-list.png)

1. Du kan filtrera efter status. De olika statusvärdena är:

   * **Inte startat**: ingen körning har inträffat
   * **Pågår**: när en körning har startats <!--or is done?-->
   * **Pausad**
   * **Slutförd**: alla körningar i planen är klara

1. Om du vill ta bort en IP-uppvärmningsplan väljer du **[!UICONTROL Delete]** -ikonen bredvid ett listobjekt och bekräfta borttagningen.

   ![](assets/ip-warmup-delete-plan.png)

   >[!CAUTION]
   >
   >Den valda IP-warmup-planen tas bort permanent.

### Skapa en IP-värmeringsplan {#create-ip-warmup-plan}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_upload"
>title="Ange din IP-värmerammanslutning"
>abstract="Ladda ned CSV-mallen och fyll den med data för IP-värmare och målantal profiler."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_surface"
>title="Välj en marknadsföringsyta"
>abstract="Du måste välja samma yta som den som valts i kampanjen som du vill associera med din IP-värmerappsplan."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html" text="Konfigurera kanalytor"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html" text="Skapa IP-värmningskampanjer"

>[!CAUTION]
>
>Om du vill skapa, redigera och ta bort IP-beredskapsplanerna måste du ha **[!UICONTROL Deliverability Consultant]** behörighet.
<!--Learn more on managing [!DNL Journey Optimizer] users' access rights in [this section](../administration/permissions-overview.md).-->

När en eller flera livekampanjer med **[!UICONTROL IP warmup plan activation]** aktiverat alternativ aktiveras, du kan koppla dem till en IP-värmeringsplan.

>[!CAUTION]
>
>Arbeta med din leveranskonsult för att säkerställa att din mall för IP-värmerapport är korrekt konfigurerad. <!--TBC-->

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP warmup plans]** menyn och klicka sedan på **[!UICONTROL Create IP warmup plan]**.

   ![](assets/ip-warmup-create-plan.png)

1. Fyll i information om IP-beredskapsplanen: ge den ett namn och en beskrivning.

   ![](assets/ip-warmup-plan-details.png)

1. Välj en [yta](channel-surfaces.md). Endast marknadsföringsytor är tillgängliga för urval. [Läs mer om e-posttyp](../email/email-settings.md#email-type)

   >[!CAUTION]
   >
   >Du måste välja samma yta som den som valts i kampanjen som du vill associera med din IP-värmerappsplan. [Lär dig hur du skapar en IP-värmerskampanj](#create-ip-warmup-campaign)

1. Överför den Excel-fil som innehåller din IP-värmeringsplan<!--which formats are allowed?-->. Du kan använda mallen som tillhandahålls av leveransgruppen.<!--TBC?--> [Läs mer](#upload-plan)
   <!--
    You can also download the Excel template from the [!DNL Journey Optimizer] user interface and upload it after filling it with the IP warmup details.-->

   ![](assets/ip-warmup-upload-success.png)

1. Klicka på **[!UICONTROL Create]**. Antalet faser som definieras i filen som du överförde visas automatiskt för varje fas. [Läs mer](#upload-plan)

   ![](assets/ip-warmup-plan-phases.png)

### Ladda upp en IP-värdplan igen {#re-upload-plan}

Du kan överföra ytterligare en IP-värmeringsplan med motsvarande knapp.

![](assets/ip-warmup-re-upload-plan.png)

>[!NOTE]
>
>Information om IP-värmeringsplanen ändras enligt den nyligen överförda filen. Hela körningen och de aktiverade körningarna påverkas inte.

### Överför filen som innehåller planen {#upload-plan}

Nedan visas ett exempel på en fil som innehåller en IP-värmerapport.

![](assets/ip-warmup-sample-file.png)

Varje fas motsvarar en period som består av flera körningar, som ni tilldelar en enda kampanj till.

För varje körning har du ett visst antal mottagare och du anger ett datum när körningen ska köras.

Du kan ha så många kolumner du vill för de domäner du vill leverera till. I det här exemplet har du tre kolumner: Gmail, Adobe och Övrigt, vilket innebär att

Tanken är att fler ska köras under de första faserna och att antalet riktade adresser ska ökas stegvis samtidigt som antalet ska minskas.

### Definiera faserna {#define-phases}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_campaigns_excluded"
>title="Välj vilka kampanjer som ska uteslutas"
>abstract="Välj de målgrupper från andra kampanjer som du vill utesluta från den aktuella fasen."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_domains_excluded"
>title="Välj vilka domängrupper som ska exkluderas"
>abstract="Välj de domäner som du vill utesluta från den aktuella fasen."

1. För varje fas väljer du den kampanj som du vill associera med den här fasen i IP-värmerapporten.

   ![](assets/ip-warmup-plan-select-campaign.png)

   Observera följande:

   * Bara kampanjer med **[!UICONTROL IP warmup plan activation]** option enabled <!--and live?--> kan väljas. [Läs mer](#create-ip-warmup-campaign)

   * Du måste välja en kampanj som använder samma yta som den som valts för den aktuella IP-värmerapporten.

   * Du kan inte välja en kampanj som redan används i en annan IP-värmare.

1. För varje fas gäller följande:

   * **[!UICONTROL Profile exclusion]** - Profilerna från tidigare körningar av den fasen exkluderas alltid. Om till exempel serie 1 Leo blev täckt av de första 6300 personerna som är riktade, ser systemet automatiskt till att Leo inte får posten i serie 2.

   * **[!UICONTROL Campaign audiences excluded]** - Välj målgrupper från andra <!--executed/live?-->kampanjer som du vill utesluta från den aktuella fasen.

     Du kanske kör en fas och måste dela upp den av någon anledning. I så fall, i fas 2, vill ni inkludera kampanjen som används i fas 1 i detta avsnitt så att tidigare kontaktade personer från fas 1 inte inkluderas i fas 2. Detta kan göras inte bara med kampanjer som används i samma IP-värmeringsplan, utan även från en annan IP-värmeringsplan.

   * **[!UICONTROL Domains groups excluded]** - Välj de domäner som du vill utesluta från den fasen, till exempel Gmail. <!--??-->

     Efter att ha kört IP-warmup i några dagar inser du att ISP:s rykte med en domän säger att hotmail inte är bra och du vill lösa det med ISP men inte vill stoppa IP-warmup-planen. I så fall kan du placera domängruppens hotmail i kategorin Undantagna.

     >[!NOTE]
     >
     >Domänundantag kräver en icke-körd fas så du kan behöva dela en pågående fas för att lägga till undantag. Om domängruppen inte är en OOTB-domängrupp kan du behöva skapa domängruppen i Excel och överföra och sedan exkludera den.

   ![](assets/ip-warmup-plan-phase-1.png)

1. Du kan lägga till en fas om det behövs - den läggs till efter den senaste aktuella fasen. Använd **[!UICONTROL Delete phase]** för att ta bort oönskade faser.

   ![](assets/ip-warmup-plan-add-delete-phases.png)

   >[!CAUTION]
   >
   >Du kan inte ångra **[!UICONTROL Delete]** åtgärd.
   >
   >Om du tar bort alla faser från IP-beredskapsplanen rekommenderar vi att du överför en plan igen.

### Definiera körningarna {#define-runs}

1. Välj ett schema för varje körning. <!--which is actually a window of opportunity. meaning? how many hours? shall we specify that to clarify?-->

   ![](assets/ip-warmup-plan-send-time.png)

1. Välj en sluttid, vilket i princip innebär det fönster inom vilket vi kan genomföra en kampanj om det blir några förseningar i målgruppsarbetet. Om inget anges försöker vi vid starttiden och misslyckas. Om sluttid anges kör vi körningen mellan det fönstret.

1. Aktivera varje körning. Se till att du schemalägger en tid som är tillräckligt lång för att segmenteringsjobbet ska kunna köras. <!--explain how you can evaluate a proper time-->

   >[!CAUTION]
   >
   >Varje körning måste aktiveras minst 12 timmar före den faktiska sändningstiden. I annat fall kanske inte segmenteringen är klar. <!--How do you know when segmentation is complete? Is there a way to prevent user from scheduling less than 12 hours before the segmentation job?-->

1. Om kampanjkörningen inte har startat kan du stoppa en körning.

   När kampanjkörningen har startat **[!UICONTROL Stop]** knappen blir otillgänglig. <!--TBC in UI-->

   ![](assets/ip-warmup-plan-stop-run.png)

1. Om du vill lägga till en körning väljer du **[!UICONTROL Add a run below]** från ikonen med tre punkter.

   ![](assets/ip-warmup-plan-run-more-actions.png)

1. Om du vill använda en annan kampanj från en viss körning väljer du **[!UICONTROL Split to a new phase option]** från ikonen med tre punkter. En ny fas skapas för de återstående körningarna i den aktuella fasen. Följ stegen [ovan](#define-phases) för att definiera den nya fasen.

   Om du t.ex. väljer det här alternativet för körning nr 4 flyttas körning nr 4 till nr 8 till en ny fas.

<!--
You don't have to decide the campaign upfront. You can do a split later. It's a work in progress plan: you activate one run at a time with a campaign and you always have the flexibility to modify it while working on it.

But need to explain in which case you want to modify campaigns, provide examples
-->

En körning kan ha följande status<!--TBC with Medha-->:

* **[!UICONTROL Completed]**:
* **[!UICONTROL Failed]**:
* **[!UICONTROL Cancelled]**: du stoppade körningen innan kampanjkörningen startade.

