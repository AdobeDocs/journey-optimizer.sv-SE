---
solution: Journey Optimizer
product: journey optimizer
title: Kör IP-värmningsplanen
description: Lär dig hur du kör och övervakar en IP-värmeringsplan
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP, pooler, grupp, underdomäner, leveransbarhet
hide: true
hidefromtoc: true
source-git-commit: 11bdb3ddc666d2025133f70ab522c4ce2d676aa6
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%

---

# Kör IP-värmningsplanen {#ip-warmup-running}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med IP-värmare](ip-warmup-gs.md)
* [Skapa IP-värmningskampanjer](ip-warmup-campaign.md)
* [Skapa en IP-värmeringsplan](ip-warmup-plan.md)
* **[Kör IP-värmningsplanen](ip-warmup-running.md)**

>[!ENDSHADEBOX]

## Definiera faserna {#define-phases}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_campaigns_excluded"
>title="Välj vilka kampanjer som ska uteslutas"
>abstract="Välj de målgrupper från andra kampanjer som du vill utesluta från den aktuella fasen."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_domains_excluded"
>title="Välj vilka domängrupper som ska exkluderas"
>abstract="Välj de domäner som du vill utesluta från den aktuella fasen."

Du måste associera kampanjen och målgruppen på fasnivå och aktivera vissa inställningar efter behov för alla körningar som är kopplade till en enda kreativ/kampanjrelaterad

På fasnivå ser systemet till att tidigare riktade + nya profiler plockas upp OCH på iterationsnivå säkerställer systemet att varje körning har unika profiler och att antalet matchar det som anges i planen

1. För varje fas väljer du den kampanj som du vill associera med den här fasen i IP-värmerapporten.

   ![](assets/ip-warmup-plan-select-campaign.png)

   Observera följande:

   * Bara kampanjer med **[!UICONTROL IP warmup plan activation]** option enabled <!--and live?--> kan väljas. [Läs mer](#create-ip-warmup-campaign)

   * Du måste välja en kampanj som använder samma yta som den som valts för den aktuella IP-värmerapporten.

   * Du kan inte välja en kampanj som redan används i en annan IP-värmare.

1. I **[!UICONTROL Profile exclusion]** ser du att profilerna från tidigare körningar av den fasen alltid är exkluderade. Om en profil i Kör 1 till exempel täcks av de första 4 800 målpersonerna, ser systemet automatiskt till att samma profil inte får e-postmeddelandet i Kör 2.

1. Från **[!UICONTROL Campaign audiences excluded]** väljer du målgrupper från andra <!--executed/live?-->kampanjer som du vill utesluta från den aktuella fasen.

   ![](assets/ip-warmup-plan-exclude-campaigns.png)

   När du till exempel utförde fas 1 var du tvungen att [dela den](#split-phase) av någon anledning. Därför kan ni utesluta kampanjen som används i fas 1 så att tidigare kontaktade profiler från fas 1 inte inkluderas i fas 2. Du kan även utesluta kampanjer från andra IP-värmeringsplaner.

1. Från **[!UICONTROL Domains groups excluded]** markerar du de domäner du vill utesluta från den fasen.

   ![](assets/ip-warmup-plan-exclude-domains.png)

   När du har kört IP-värmning i några dagar inser du att ISP-anseende med en domän (t.ex. Adobe) inte är bra och du vill lösa det utan att stoppa IP-värmningsplanen. I så fall kan du utesluta domängruppen Adobe.

   >[!NOTE]
   >
   >Domänundantag kräver en icke-körd fas, så du kan behöva dela en pågående fas för att lägga till undantag. Om domängruppen inte är en OOTB-domängrupp måste du lägga till den här domängruppen i Excel-filen, överföra den och sedan exkludera domänen.

   ![](assets/ip-warmup-plan-phase-1.png)

1. Du kan lägga till en fas om det behövs. Den läggs till efter den sista aktuella fasen.

1. Använd **[!UICONTROL Delete phase]** för att ta bort oönskade faser.

   ![](assets/ip-warmup-plan-add-delete-phases.png)

   >[!CAUTION]
   >
   >Du kan inte ångra **[!UICONTROL Delete]** åtgärd.
   >
   >Om du tar bort alla faser från IP-beredskapsplanen rekommenderar vi att du överför en plan igen.

## Definiera körningarna {#define-runs}

1. Välj ett schema för varje körning. <!--which is actually a window of opportunity. meaning? how many hours? shall we specify that to clarify?-->

   ![](assets/ip-warmup-plan-send-time.png)

1. Välj en sluttid, som definierar det fönster inom vilket IP-värmerskampanjen kan köras om det uppstår några förseningar i jobbkörningen för målgruppssegmentering. Om ingen sluttid anges görs ett försök att utföra körningen vid starttiden och misslyckas om segmenteringen inte slutfördes.

1. Aktivera varje körning. Se till att du schemalägger en tid som är tillräckligt lång för att segmenteringsjobbet ska kunna köras. <!--explain how you can evaluate a proper time-->

   >[!CAUTION]
   >
   >Varje körning måste aktiveras minst 12 timmar före den faktiska sändningstiden. I annat fall kanske inte segmenteringen är klar. <!--How do you know when segmentation is complete? Is there a way to prevent user from scheduling less than 12 hours before the segmentation job?-->

   <!--Sart to execute on every day basis by simply clicking the play button > for each run? do you have to come back every day to activate each run? or can you schedule them one after the other?)-->

1. Om kampanjkörningen inte har startat kan du stoppa en körning.<!--why?-->

   >[!NOTE]
   >
   >När kampanjkörningen har startat **[!UICONTROL Stop]** knappen blir otillgänglig. <!--TBC in UI-->

   ![](assets/ip-warmup-plan-stop-run.png)

1. Om du vill lägga till en körning väljer du **[!UICONTROL Add a run below]** från ikonen med tre punkter.

   ![](assets/ip-warmup-plan-run-more-actions.png)

## Dela en fas {#split-phase}

Om du vill använda en annan kampanj från en viss körning väljer du **[!UICONTROL Split to a new phase option]** från ikonen med tre punkter.

En ny fas skapas för de återstående körningarna i den aktuella fasen. Följ stegen [ovan](#define-phases) för att definiera den nya fasen.

Om du t.ex. väljer det här alternativet för Kör nr 4 flyttas körningsversionerna nr 4 till nr 8 till en ny fas.

<!--
You don't have to decide the campaign upfront. You can do a split later. It's a work in progress plan: you activate one run at a time with a campaign and you always have the flexibility to modify it while working on it.

But need to explain in which case you want to modify campaigns, provide examples
-->

## Övervaka planen

En körning kan ha följande status<!--TBC with Medha-->:

* **[!UICONTROL Completed]**:
* **[!UICONTROL Failed]**:
* **[!UICONTROL Cancelled]**: du stoppade körningen innan kampanjkörningen startade.

Fördelar :

* Rapporterna kommer att fortsätta visas på kampanjnivå med liknande funktioner som idag. Men IP-värmerapporten fungerar också som en konsoliderad rapport på en enda plats om hur många avrättningar som gjorts och så vidare.

* En enda plats för att hantera och se hur IP-värmen utvecklas.

* Konsoliderad rapport på kreativ nivå/kampanjnivå som alla körs under en fas