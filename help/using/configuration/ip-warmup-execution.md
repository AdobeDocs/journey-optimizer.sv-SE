---
solution: Journey Optimizer
product: journey optimizer
title: Kör IP-värmningsplanen
description: Lär dig hur du kör och övervakar en IP-värmeringsplan
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP, grupp, underdomäner, leveransbarhet
hide: true
hidefromtoc: true
exl-id: 0fd0ba66-8ad2-4239-a6e0-ea29ea2a4a15
source-git-commit: c7a36d895927e616591627a6afc05d1fa43b7c51
workflow-type: tm+mt
source-wordcount: '1618'
ht-degree: 0%

---

# Kör IP-värmerappen {#ip-warmup-running}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med IP-värmare](ip-warmup-gs.md)
* [Skapa IP-värmningskampanjer](ip-warmup-campaign.md)
* [Skapa en IP-värmeringsplan](ip-warmup-plan.md)
* **[Kör IP-värmerappen](ip-warmup-execution.md)**

>[!ENDSHADEBOX]

När du har [skapade en IP-värmningsplan](ip-warmup-plan.md) och laddade upp filen som har förberetts med din leveranskonsult, kan du definiera faserna och köra i din plan.

Varje fas består av flera körningar, som ni tilldelar en enda kampanj till.

## Definiera faserna {#define-phases}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_campaigns_excluded"
>title="Uteslut kampanjmålgrupper"
>abstract="Välj de målgrupper från andra kampanjer som du vill utesluta från den aktuella fasen. Detta är för att förhindra att tidigare kontaktade profiler från andra faser eller andra IP-uppvärmningsplaner målas igen."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_domains_excluded"
>title="Uteslut domängrupper"
>abstract="Välj de domäner som du vill utesluta från den aktuella fasen. Domänundantag kräver en icke-körd fas, så du kan behöva dela en pågående fas för att lägga till undantag."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/implement-ip-warmup-plan/ip-warmup-execution.html#split-phase" text="Dela en fas"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_phases"
>title="Definiera faserna i din plan"
>abstract="Varje fas består av flera körningar, som ni tilldelar en enda kampanj till."

<!--You need to associate the campaign and audience at phase level and turns on some settings as needed for all runs associated with a single creative/campaign

At phase level, system ensures that previously targeted + new profiles are picked up AND at iteration level, system ensures that each run is having unique profiles and the count matches what is stated in plan-->

<!--![](assets/ip-warmup-plan-phase-1.png)-->

1. För varje fas väljer du den kampanj som du vill associera med den här fasen i IP-värmerapporten.

   ![](assets/ip-warmup-plan-select-campaign.png)

   Observera följande:

   * Bara kampanjer med **[!UICONTROL IP warmup plan activation]** option enabled <!--and live?--> kan väljas. [Läs mer](#create-ip-warmup-campaign)

   * Du måste välja en kampanj som använder samma yta som den som valts för den aktuella IP-värmerapporten.

   * Du kan inte välja en kampanj som redan används i en annan IP-värmare.

1. I **[!UICONTROL Profile exclusion]** ser du att profilerna från tidigare körningar av den fasen alltid är exkluderade. Om en profil i Kör 1 till exempel täcks av de första 4 800 målpersonerna, ser systemet automatiskt till att samma profil inte får e-postmeddelandet i Kör 2.

1. Från **[!UICONTROL Campaign audiences excluded]** väljer du målgrupper från andra <!--executed/live?-->kampanjer som du vill utesluta från den aktuella fasen.

   ![](assets/ip-warmup-plan-exclude-campaigns.png)

   När du till exempel utförde fas 1 var du tvungen att [dela den](#split-phase) av någon anledning. Därför kan ni utesluta kampanjen som används i fas 1 så att de tidigare kontaktade profilerna från fas 1 inte inkluderas i fas 2. Du kan även utesluta kampanjer från andra IP-värmeringsplaner.

1. Från **[!UICONTROL Domain groups excluded]** markerar du de domäner du vill utesluta från den fasen.

   >[!NOTE]
   >
   >Domänundantag kräver en fas som inte har körts, så du kan behöva [dela en pågående fas](#split-phase) för att lägga till undantag.

   ![](assets/ip-warmup-plan-exclude-domains.png)

   När du har kört IP-värmning i några dagar inser du att ditt ISP-rykte med en domän (till exempel Adobe) inte är bra och du vill lösa det utan att stoppa IP-värmningsplanen. I så fall kan du utesluta domängruppen Adobe.

   >[!NOTE]
   >
   >Om domänen inte är en färdig domängrupp måste du samarbeta med din leveranskonsult för att lägga till domänen i [Planfil för IP-värmare](ip-warmup-plan.md#prepare-file) och [ladda upp den igen](#re-upload-plan) för att kunna utesluta den domänen.

1. Du kan lägga till en fas om det behövs. Den läggs till efter den sista aktuella fasen.

   ![](assets/ip-warmup-plan-add-phase.png)

1. Använd **[!UICONTROL Delete phase]** för att ta bort oönskade faser.

   ![](assets/ip-warmup-plan-delete-phase.png)

   >[!CAUTION]
   >
   >Du kan inte ångra **[!UICONTROL Delete]** åtgärd.
   >
   >Om du tar bort alla faser från IP-beredskapsplanen rekommenderar vi att du överför en plan igen. [Läs mer](#re-upload-plan)

## Definiera körningarna {#define-runs}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_run"
>title="Definiera varje körning"
>abstract="Definiera och aktivera varje körning för alla faser."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_last_engagement"
>title="Filtrera efter engagemang"
>abstract="Den här kolumnen är till exempel ett filter som endast riktar sig till användare som har interagerat med ert varumärke under de senaste 20 dagarna. Du kan även ändra den här inställningen via **Redigera körning** alternativ."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_retry"
>title="Ange ett tidsfönster"
>abstract="Du kan definiera ett tidsfönster under vilket IP-uppvärmningskampanjen kan köras om segmenteringsjobbet försenas."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_pause"
>title="Avbryt körs med målgruppsfel"
>abstract="Välj det här alternativet om du vill avbryta en körning om de kvalificerade profilerna är mindre än målprofilerna när målgruppen har utvärderats för den körningen."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_qualified"
>title="Visa kvalificerade profiler"
>abstract="I den här kolumnen visas antalet kvalificerade profiler. När målgruppen har utvärderats för en körning körs körningen fortfarande om det finns fler målprofiler än kvalificerade profiler, såvida inte **Pausa vid fel** är aktiverat. I det här fallet avbryts körningen."

1. Välj ett schema för varje körning.

   ![](assets/ip-warmup-plan-send-time.png)

1. Du kan också definiera ett tidsfönster under vilket IP-uppvärmningskampanjen kan köras om segmenteringsjobbet försenas. Om du vill göra det klickar du på egenskapsikonen uppe till vänster, bredvid namnet på planen, och använder **[!UICONTROL Retry run time]** för att välja en varaktighet - upp till 240 minuter (4 timmar).

   ![](assets/ip-warmup-plan-retry-run-time.png)

   Om du till exempel ställer in en sändningstid på en viss dag kl. 20 och väljer 120 minuter som återförsökskörningstid, kommer detta att ge ett fönster med en möjlighet på 2 timmar för att segmenteringsjobbet ska kunna köras.

   >[!NOTE]
   >
   >Om inget tidsfönster anges görs ett försök att köra vid sändningstiden och misslyckas om segmenteringsjobbet inte slutförs.

1. Välj vid behov **[!UICONTROL Edit run]** från ikonen Fler åtgärder. Där kan du uppdatera antalet adresser i varje kolumn. Du kan även uppdatera **[!UICONTROL Last engagement]** för att t.ex. rikta sig till de användare som varit engagerade med ert varumärke under de senaste 20 dagarna.

   ![](assets/ip-warmup-plan-edit-run.png)

1. Välj **[!UICONTROL Pause for errors]** om du vill avbryta en körning om de kvalificerade profilerna är mindre än målprofilerna när målgruppen har utvärderats för den körningen.

   ![](assets/ip-warmup-plan-pause.png)

1. **[!UICONTROL Activate]** körningen. [Läs mer](#activate-run)

1. Status för den här körningen ändras till **[!UICONTROL Live]**. De olika körningsstatusarna listas i [det här avsnittet](#monitor-plan). Om kampanjkörningen inte har startat kan du stoppa en direktkörning.<!--why?-->

   ![](assets/ip-warmup-plan-stop-run.png)

   >[!NOTE]
   >
   >När kampanjkörningen har startat **[!UICONTROL Stop]** knappen blir otillgänglig.

1. Om du vill lägga till en körning väljer du **[!UICONTROL Add a run below]** från ikonen med tre punkter.

   ![](assets/ip-warmup-plan-run-more-actions.png)

## Aktivera en körning {#activate-run}

Om du vill aktivera en körning väljer du **[!UICONTROL Activate]** -knappen.

Se till att du har schemalagt tillräckligt med tid för att segmenteringsjobbet ska kunna utföras.

![](assets/ip-warmup-plan-activate.png)

>[!CAUTION]
>
>Varje körning måste aktiveras minst 12 timmar före den faktiska sändningstiden. I annat fall kanske inte segmenteringen är klar.

När du aktiverar en körning skapas flera segment automatiskt:

* Om du aktiverar den första körningen av en fas:

   * Ett segment skapas för de uteslutna kampanjmålgrupperna (om sådana finns).
   * Ett annat segment skapas för de domängrupper som exkluderats (om sådana finns).

* Vid aktivering av körningar:

   * Ett annat segment skapas för det senaste engagemangsfiltret.
   * En målgruppskomposition skapas som motsvarar den målgrupp som kampanjen ska skickas till.

<!--How do you know when segmentation is complete? Is there a way to prevent user from scheduling less than 12 hours before the segmentation job?-->

<!--Sart to execute on every day basis by simply clicking the play button > for each run? do you have to come back every day to activate each run? or can you schedule them one after the other?)-->

<!--Upon activation, when the segment evaluation happens, more segments will be created by the IP warmup service and will be leveraged in an audience composition and a new audience will be created for each run splitted into the different selected domains.-->


## Hantera din plan {#manage-plan}

Om IP-värmningsplanen inte fungerar som förväntat kan du vidta åtgärderna nedan.

### Dela en fas {#split-phase}

Om du vill lägga till en ny fas med början från en viss körning väljer du **[!UICONTROL Split to a new phase option]** från ikonen med tre punkter.

![](assets/ip-warmup-plan-run-split-run.png)

En ny fas skapas för de återstående körningarna i den aktuella fasen.

Om du t.ex. väljer det här alternativet för Kör #4 flyttas körningarna #4 till #8 till en ny fas precis efter den aktuella fasen.

Följ stegen [ovan](#define-phases) för att definiera den nya fasen.

* Du kan använda **[!UICONTROL Replace campaign]** alternativ för den nya fasen.

* Du kan också utesluta den tidigare kampanjen eller en domän som inte fungerar som den ska. Läs mer i [det här avsnittet](#define-phases).

<!--
You don't have to decide the campaign upfront. You can do a split later. It's a work in progress plan: you activate one run at a time with a campaign and you always have the flexibility to modify it while working on it.

But need to explain in which case you want to modify campaigns, provide examples
-->

### Markera en plan som slutförd {#mark-as-completed}

Om din plan inte fungerar tillräckligt bra eller om du vill släppa den för att skapa en till, kan du markera den som slutförd.

Klicka på **[!UICONTROL More]** överst till höger i IP-värmningsplanen och välj **[!UICONTROL Mark as completed]**.

![](assets/ip-warmup-plan-mark-completed.png)

Det här alternativet är bara tillgängligt om alla körningar i planen finns **[!UICONTROL Completed]** eller **[!UICONTROL Draft]** status. Om en körning **[!UICONTROL Live]**, är alternativet nedtonat.

De olika körningsstatusarna listas i [det här avsnittet](#monitor-plan).

### Ladda upp en IP-värdplan igen {#re-upload-plan}

Om din IP-warmup-plan inte fungerar som förväntat (till exempel om du observerar att vissa Internet-leverantörer markerar dina meddelanden som skräppost) kan du be din leveransexpert att ställa in en annan IP-warmup-planfil och överföra den igen med motsvarande knapp.

![](assets/ip-warmup-re-upload-plan.png)

Alla tidigare körningar är skrivskyddade. Den nya planen visas under den första planen.

Följ stegen [ovan](#define-phases) för att definiera faserna i den nya planen.

>[!NOTE]
>
>Information om IP-värmeringsplanen ändras enligt den nyligen överförda filen. Tidigare körningar (oavsett deras [status](#monitor-plan)) påverkas inte.

Låt oss ta ett exempel:

* I den initiala IP-värmerappen hade fas 2 nio körningar.

* Fyra körningar utfördes (oavsett om de misslyckas, slutförs eller avbryts - så länge som ett körningsförsök har gjorts körs körningen).

* Om du överför en ny plan på nytt kommer fas 2 med de första fyra körningarna att gå in i skrivskyddat läge.

* De återstående 5 körningarna (som är i utkastläge) flyttas till en ny fas (fas 3) som visas enligt den nyligen överförda planen.

## Övervaka planen {#monitor-plan}

Om du vill mäta effekten av din plan kan du kontrollera resultatet för dina IP-uppvärmningskampanjer med hjälp av [!DNL Journey Optimizer] kampanjrapporter. För varje slutförd körning kan du klicka på **[!UICONTROL View reports]** -knappen. Läs mer i e-postmeddelandet om kampanjen [live-rapport](../reports/campaign-live-report.md#email-live) och [global rapport](../reports/campaign-global-report.md##email-global).

![](assets/ip-warmup-plan-reports.png)

Själva beredskapsplanen för IP fungerar också som en konsoliderad rapport på ett enda ställe. Du kan kontrollera element som antalet **[!UICONTROL Live]** eller **[!UICONTROL Completed]** körs för varje fas och du kan se hur din plan för IP-uppvärmning fortskrider.

En körning kan ha följande status:

* **[!UICONTROL Draft]** : när en körning skapas, antingen när [skapa en ny plan](ip-warmup-plan.md) eller [lägga till en körning](#define-runs) från användargränssnittet tar **[!UICONTROL Draft]** status.
* **[!UICONTROL Live]**: varje gång du aktiverar en körning tar det **[!UICONTROL Live]** status.
* **[!UICONTROL Completed]**: kampanjkörningen för den här körningen har slutförts. <!--i.e. campaign execution has started, no error happened and emails have reached users? to check with Sid-->
* **[!UICONTROL Cancelled]**: a **[!UICONTROL Live]** körningen avbröts med **[!UICONTROL Stop]** -knappen. Den här knappen är bara tillgänglig om kampanjkörningen inte har startats. [Läs mer](#define-runs)
* **[!UICONTROL Failed]**: ett fel påträffades av systemet eller kampanjen som användes för den aktuella fasen stoppades. Om en körning misslyckas kan du schemalägga en ny körning för nästa dag.
