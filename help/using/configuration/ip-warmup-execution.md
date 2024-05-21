---
solution: Journey Optimizer
product: journey optimizer
title: Kör IP-värmningsplanen
description: Lär dig hur du kör och övervakar en IP-värmeringsplan
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP, grupp, underdomäner, leveransbarhet
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 752ffd7f-09c2-4aa3-a067-2dbe0634709c
source-git-commit: c400104c86e1a9a2de819db7743b3f77153ad90b
workflow-type: tm+mt
source-wordcount: '2392'
ht-degree: 0%

---

# Kör IP-värmerappen {#ip-warmup-running}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med planer för IP-värmare](ip-warmup-gs.md)
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
>abstract="Välj kampanjer för att exkludera deras målgrupper från den aktuella fasen. Detta är för att förhindra att tidigare kontaktade profiler från andra faser eller andra IP-uppvärmningsplaner målas igen."

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

   >[!NOTE]
   >
   >Du kan inte välja en kampanj som redan används i en annan IP-uppvärmningsplan. Men samma kampanj kan användas i en eller flera faser i samma IP-värpportplan.

   ![](assets/ip-warmup-plan-select-campaign.png)

   >[!IMPORTANT]
   >
   >* Bara kampanjer med **[!UICONTROL IP warmup plan activation]** aktiverat alternativ är tillgängligt för markering. [Läs mer](#create-ip-warmup-campaign)
   >
   >* Du måste välja en kampanj som använder samma yta som den som valts för den aktuella IP-värmerapporten.

1. När en kampanj har valts för den aktuella fasen visas avsnitten för att utesluta profiler, kampanjmålgrupper och domängrupper.

   >[!NOTE]
   >
   >När en körning har aktiverats kan undantag inte ändras längre om du inte [dela körningen](#split-phase) till en ny fas.

   1. Från **[!UICONTROL Domain groups excluded]** markerar du de domäner du vill utesluta från den fasen.

      >[!NOTE]
      >
      >Domänundantag kräver en fas som inte har körts, så du kan behöva [dela en pågående fas](#split-phase) för att lägga till undantag.

      ![](assets/ip-warmup-plan-exclude-domains.png)

      När du har kört IP-värmning i några dagar inser du att ditt ISP-rykte med en domän (till exempel Adobe) inte är bra och du vill lösa det utan att stoppa IP-värmningsplanen. I så fall kan du utesluta domängruppen Adobe.

      >[!NOTE]
      >
      >Du kan bara utesluta en anpassad domängrupp som har lagts till i [Prenumerationsplanmall för IP-värmare](ip-warmup-plan.md#prepare-file). Om så inte är fallet uppdaterar du mallen med den anpassade domängruppen som du vill utesluta och [ladda upp planen igen](#re-upload-plan).

   1. Från **[!UICONTROL Campaign for exclusion of profiles]** väljer du de kampanjer som målgrupper ska uteslutas från den aktuella fasen.

      ![](assets/ip-warmup-plan-exclude-campaigns.png)

      När du till exempel utförde fas 1 var du tvungen att [dela den](#split-phase) av någon anledning. Därför kan ni utesluta kampanjen som används i fas 1 så att de tidigare kontaktade profilerna från fas 1 inte inkluderas i fas 2. Du kan även utesluta kampanjer från andra IP-värmeringsplaner.

   1. Från **[!UICONTROL Journeys for exclusion of profiles]** väljer du de resor med målgrupper som du vill utesluta från den aktuella fasen.

+++ Om du vill använda alternativet Journeys för att exkludera profiler måste du upprätta en relation mellan AJO Message Feedback Event och AJO Entity Record Schemas.

      1. Skapa en egen **Namnutrymme** som fungerar som identitetstyp för stegen nedan.

      1. Öppna Adobe Experience Platform från **Scheman** väljer du **Schema för AJO-entitetspost** och ange **_id** som primär identitet och välj det namnutrymme som skapats tidigare som **Namnutrymme för identitet**.

      1. Från **Scheman** väljer du **Schema för AJO Message Feedback-händelse** och navigera till **_messageID** fält. Välj **Lägg till relation** och välja **Schema för AJO-entitetspost** som **Referensschema** och det namnutrymme som du skapade tidigare som **Namnutrymme för referensidentitet**.
+++

   1. I **[!UICONTROL Profiles targeted in previous runs]** ser du att profilerna från tidigare körningar av den fasen alltid är exkluderade. Om en profil i Kör 1 till exempel täcks av de första 4 800 målpersonerna, ser systemet automatiskt till att samma profil inte får e-postmeddelandet i Kör 2.

      >[!NOTE]
      >
      >Det här avsnittet kan inte redigeras.

1. Vid behov kan du ersätta kampanjen med **[!UICONTROL Replace]** -knappen. Du kan även rensa den valda kampanjen med **[!UICONTROL Clear]** -knappen. Du kan sedan välja en ny kampanj antingen direkt eller vid ett senare tillfälle.

   ![](assets/ip-warmup-plan-replace-campaign.png)

   >[!NOTE]
   >
   >Den här åtgärden är bara möjlig innan den första körningen av fasen aktiveras. När en körning har aktiverats kan kampanjen inte ersättas, såvida du inte [dela körningen](#split-phase) till en ny fas.

1. Du kan lägga till en fas om det behövs. Den läggs till efter den sista aktuella fasen.

   ![](assets/ip-warmup-plan-add-phase.png)

1. Använd **[!UICONTROL Delete phase]** för att ta bort oönskade faser. Den här åtgärden är bara tillgänglig om ingen körning körs i en fas. <!--Once a run is executed, deletion is not allowed.-->

   >[!CAUTION]
   >
   >Du kan inte ångra **[!UICONTROL Delete phase]** åtgärd.

   ![](assets/ip-warmup-plan-delete-phase.png)

   >[!NOTE]
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
>abstract="I den här kolumnen visas antalet kvalificerade profiler. När målgruppen har utvärderats för en körning körs körningen fortfarande om det finns fler målprofiler än kvalificerade profiler, såvida inte **Avbryt aktiverade körningar vid fel** är aktiverat. I det här fallet avbryts körningen."

1. Välj ett schema för varje körning för att se till att den körs vid den angivna tidpunkten.

   ![](assets/ip-warmup-plan-send-time.png)

1. Du kan också definiera ett tidsfönster under vilket IP-warmup-kampanjen kan köras om det uppstår några förseningar i [målgruppsutvärdering](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#how-segmentation-works){target="_blank"}. Om du vill göra det klickar du på egenskapsikonen uppe till vänster, bredvid namnet på planen, och använder **[!UICONTROL Retry run time]** för att välja en varaktighet - upp till 240 minuter (4 timmar).

   >[!NOTE]
   >
   >Försök görs var 30:e minut till slutet av det definierade tidsfönstret.

   ![](assets/ip-warmup-plan-retry-run-time.png)

   Om du t.ex. anger en sändningstid på en viss dag kl. 9.00 och väljer 120 minuter som körningstid för nya försök, kan du använda detta för att skapa ett fönster med en tidsrymd på 2 timmar (9.00-11.00) så att körningen kan utföras vid oväntade fördröjningar i målgruppsutvärderingen.

   >[!NOTE]
   >
   >Om inget tidsfönster anges görs ett försök att köra vid sändningstiden och detta misslyckas om målgruppsutvärderingen inte slutförs.

1. Välj vid behov **[!UICONTROL Edit run]** från ikonen Fler åtgärder. Där kan du uppdatera antalet adresser i varje kolumn. Du kan även uppdatera **[!UICONTROL Last engaged]** för att t.ex. rikta sig till de användare som varit engagerade med ert varumärke under de senaste 20 dagarna.

   >[!NOTE]
   >
   >Vi rekommenderar att du ändrar numren i samråd med din produktexpert.

   ![](assets/ip-warmup-plan-edit-run.png)

   >[!NOTE]
   >
   >Om du inte vill tillämpa någon åtagandeperiod på en körning anger du 0 i dialogrutan **[!UICONTROL Last engaged]** fält.

1. Välj **[!UICONTROL Cancel activated runs in case of errors]** om du vill avbryta en körning om de kvalificerade profilerna är mindre än målprofilerna när målgruppen har utvärderats för den körningen. I så fall tar körningen **[!UICONTROL Failed]** status.

   ![](assets/ip-warmup-plan-pause.png)

1. **[!UICONTROL Activate]** körningen. [Läs mer](#activate-run)

1. Status för den här körningen ändras till **[!UICONTROL Live]**, vilket innebär att systemet har accepterat begäran om att schemalägga körningen.

   >[!NOTE]
   >
   >De olika körningsstatusarna listas i [det här avsnittet](#monitor-plan).

1. Om kampanjkörningen inte har startats kan du avbryta en direktkörning. Den här åtgärden avbryter faktiskt körningsschemat - det stoppar inte sändningen.

   ![](assets/ip-warmup-plan-stop-run.png)

1. Om du vill duplicera ett utkast, en direktkörning eller en slutförd körning väljer du **[!UICONTROL Duplicate run]**. Vid duplicering visas menyn Redigera, vilket gör att användare kan justera **[!UICONTROL Total target profiles]** och **[!UICONTROL Send time]** efter behov.

   ![](assets/ip-warmup-duplicate.png)

## Aktivera körningar {#activate-run}

Om du vill aktivera en körning väljer du **[!UICONTROL Activate]** -knappen. Sedan kan du aktivera nästa körning dagligen.

När du kör flera IP-värdskapsplaner samtidigt, som alla har samma IP-pool och domäner som mål, är det viktigt att förutse de potentiella konsekvenserna. Om en Internet-leverantör till exempel har en daglig gräns på 100 e-postmeddelanden, kan detta tröskelvärde överskridas om flera planer för samma domäner körs.

Se till att du har schemalagt tillräckligt med tid för att tillåta [målgruppsutvärdering](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#how-segmentation-works){target="_blank"} som ska köras.

![](assets/ip-warmup-plan-activate.png)

>[!CAUTION]
>
>Varje körning måste aktiveras minst 12 timmar före den faktiska sändningstiden. I annat fall kanske inte målgruppsutvärderingen slutförs.

När du aktiverar en körning skapas flera målgrupper automatiskt.

* Om du aktiverar den första körningen av en fas:

   * An [publik](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html){target="_blank"} har skapats för de uteslutna kampanjmålgrupperna (om sådana finns), med följande namnkonvention: `<warmupName>_Phase<phaseNo>-Audience Exclusion`.

   * En annan målgrupp skapas för de domängrupper som har undantagits (om det finns några), med följande namnkonvention: `<warmupName>_Phase<phaseNo>-Domain Exclusion`.

  >[!NOTE]
  >
  >Målgrupperna rensas bort efter att vårdsplanen markerats som slutförd.
  >
  >Systemet skapar inte en ny målgrupp om det inte sker någon förändring i de uteslutna kampanjmålgrupperna eller domängrupperna för efterföljande faser.

* Vid aktivering av körningar:

   * En annan målgrupp skapas för det senaste interaktionsfiltret, med följande namnkonvention: `<warmupName>_Phase<phaseNo>_Run<runNo>-Engagement Filter`.

     >[!NOTE]
     >
     >Publiken städas upp efter att vårmningsplanen markerats som slutförd.
     >
     >Systemet skapar inte en ny målgrupp om det inte sker någon förändring i det senaste interaktionsfiltret för efterföljande faser.

   * An [publiksammansättning](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/audience-composition.html){target="_blank"} skapas för den målgrupp som kampanjen ska skickas till, med följande namnkonvention: `<warmupName>-Phase<phaseNo>-Run<runNo>`.

     >[!NOTE]
     >
     >En ny målgruppskomposition skapas för varje omgång. Med en begränsning på 10 måste användare som kör flera kampanjer, resor och IP-uppvärmningsplaner samtidigt och använder publicerade målgruppskompositioner planera i förväg för att hålla sig inom denna gräns för parallella operationer.
     >
     >Publiken (och därmed målgruppen) rensas bort när nästa iteration aktiveras.

<!--How do you know when segmentation is complete? Is there a way to prevent user from scheduling less than 12 hours before the segmentation job?-->

<!--Sart to execute on every day basis by simply clicking the play button > for each run? do you have to come back every day to activate each run? or can you schedule them one after the other?)-->

<!--Upon activation, when the segment evaluation happens, more segments will be created by the IP warmup service and will be leveraged in an audience composition and a new audience will be created for each run splitted into the different selected domains.-->

## Övervaka planen {#monitor-plan}

Om du vill kunna genomföra din IP-värmeringsplan måste du övervaka rapporterna, aktivera körningar och kontrollera deras status dagligen.

### Använda avsnittet Högdagrar {#highlights}

När den första körningen har aktiverats för en fas, **[!UICONTROL Highlights]** -avsnittet visas.

Den ger en snabb översikt över den aktuella körningen och den kommande körningen. I det här avsnittet kan du också redigera och aktivera nästa körning.

![](assets/ip-warmup-plan-highlights.png)

### Kontrollera körningsstatus {#run-statuses}

Själva IP-värmningsplanen fungerar som en konsoliderad rapport på ett enda ställe. Du kan kontrollera element som antalet **[!UICONTROL Live]** eller **[!UICONTROL Completed]** körs för varje fas och du kan se hur din plan för IP-uppvärmning fortskrider.

>[!NOTE]
>
>Det är en god praxis att övervaka din IP-värmningsplan varje dag.

En körning kan ha följande status:

* **[!UICONTROL Draft]** : när en körning skapas, antingen när [skapa en ny plan](ip-warmup-plan.md) eller [lägga till en körning](#define-runs) från användargränssnittet tar **[!UICONTROL Draft]** status.
* **[!UICONTROL Live]**: varje gång du aktiverar en körning tar det **[!UICONTROL Live]** status. Det innebär att systemet har accepterat begäran om att schemalägga körningen, inte att sändningen har startats. I det här skedet kan du se live-körningens status genom att klicka på **[!UICONTROL View status]** i tabellen. På så sätt kan ni spåra hur många målprofiler som faktiskt är kvalificerade.
* **[!UICONTROL Completed]**: kampanjkörningen för den här körningen har slutförts. Du får tillgång till en detaljerad körningsrapport genom att klicka på **[!UICONTROL View report]** i tabellen. Med det här alternativet kan du spåra körningens e-postleveransstatus, inklusive uppdelningar som är specifika för domängrupper för förbättrad övervakning. [Läs mer](#reports)
* **[!UICONTROL Cancelled]**: a **[!UICONTROL Live]** körningen avbröts med **[!UICONTROL Stop]** eller aktiverade **[!UICONTROL Cancel activated runs in case of errors]** och ett fel inträffade. [Läs mer](#define-runs)
* **[!UICONTROL Failed]**: ett fel påträffades av systemet eller kampanjen som användes för den aktuella fasen stoppades. Om en körning misslyckas kan du schemalägga en ny körning för nästa dag.

### Använd rapporter {#reports}

Mer generellt kan du mäta effekten av din plan genom att kontrollera resultatet för IP-värmerkampanjer med [!DNL Journey Optimizer] kampanjrapporter. För varje slutförd körning kan du klicka på **[!UICONTROL View reports]** -knappen. Läs mer i e-postmeddelandet om kampanjen [live-rapport](../reports/campaign-live-report.md#email-live) och [global rapport](../reports/campaign-global-report.md#email-global).

![](assets/ip-warmup-plan-reports.png)

Du kan även komma åt rapporterna från [Menyn Kampanjer](../campaigns/modify-stop-campaign.md#access) så att planen kan använda olika kampanjer.


## Hantera din plan {#manage-plan}

Om IP-värmningsplanen inte fungerar som förväntat kan du vidta åtgärderna nedan.

### Dela en fas {#split-phase}

Om du vill lägga till en ny fas med början från en viss körning väljer du **[!UICONTROL Split runs to a new phase]** från ikonen Fler åtgärder.

![](assets/ip-warmup-plan-run-split-run.png)

En ny fas skapas för de återstående körningarna i den aktuella fasen.

Om du t.ex. väljer det här alternativet för Kör #4 flyttas körningarna #4 till #8 till en ny fas precis efter den aktuella fasen.

Följ stegen [ovan](#define-phases) för att definiera den nya fasen.

* Du kan använda **[!UICONTROL Replace]** eller **[!UICONTROL Clear]** alternativ för den nya fasen.

* Du kan också utesluta den tidigare kampanjen eller en domän som inte fungerar som den ska. Läs mer i [det här avsnittet](#define-phases).

<!--
You don't have to decide the campaign upfront. You can do a split later. It's a work in progress plan: you activate one run at a time with a campaign and you always have the flexibility to modify it while working on it.

But need to explain in which case you want to modify campaigns, provide examples
-->

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

* 4 körningar utfördes (oavsett om de misslyckades, slutfördes eller avbröts)<!--as long as a run has been attempted, it is an executed run-->).

* Om du överför en ny plan på nytt kommer fas 2 med de första fyra körningarna att gå in i skrivskyddat läge.

* De återstående 5 körningarna (som är i utkastläge) flyttas till en ny fas (fas 3) som visas enligt den nyligen överförda planen.

### Markera en plan som slutförd {#mark-as-completed}

Om din plan inte fungerar tillräckligt bra eller om du vill släppa den för att skapa en till, kan du markera den som slutförd.

Klicka på **[!UICONTROL More]** överst till höger i IP-värmningsplanen och välj **[!UICONTROL Mark as completed]**.

![](assets/ip-warmup-plan-mark-completed.png)

Det här alternativet är bara tillgängligt om alla körningar i planen finns **[!UICONTROL Completed]** eller **[!UICONTROL Draft]** status. Om en körning **[!UICONTROL Live]**, är alternativet nedtonat.

De olika körningsstatusarna listas i [det här avsnittet](#monitor-plan).

