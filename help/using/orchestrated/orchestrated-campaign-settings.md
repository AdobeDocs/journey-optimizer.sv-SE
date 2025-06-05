---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera inställningar för samordnade kampanjer
description: Lär dig konfigurera samordnade kampanjinställningar med Adobe Journey Optimizer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: a9bb3782-a4d1-43fe-ae2a-aef3f17ba588
source-git-commit: 5872e192c849b7a7909f0b50caa1331b15490d79
workflow-type: tm+mt
source-wordcount: '1057'
ht-degree: 0%

---

# Konfigurera inställningar för samordnade kampanjer {#workflow-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_creation_properties"
>title="Samordnade kampanjegenskaper"
>abstract="På den här skärmen väljer du den mall som ska användas för att skapa den orkestrerade kampanjen och anger en etikett. Expandera avsnittet **Ytterligare alternativ** om du vill konfigurera fler inställningar, till exempel det interna namnet för den orkestrerade kampanjen, dess mapp, tidszon och övervakningsgrupp. Vi rekommenderar starkt att du väljer en grupp för ansvariga så att de får ett meddelande om ett fel inträffar."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](send-messages.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](activities/and-join.md) - [Skapa målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kombinera](activities/combine.md) - [Ta bort dubbletter](activities/deduplication.md) - [Förbättra](activities/enrichment.md) - [Förena](activities/fork.md) - [Förena&lbrace;1 ](activities/reconciliation.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

När du skapar en orkestrerad kampanj eller organiserar orkestrerade kampanjaktiviteter på arbetsytan får du tillgång till avancerade inställningar för den orkestrerade kampanjen. Du kan till exempel ange en specifik tidszon för den orkestrerade kampanjen, hantera hur den orkestrerade kampanjen ska bete sig vid fel eller hantera den fördröjning efter vilken den orkestrerade kampanjhistoriken ska rensas.

Dessa inställningar är förkonfigurerade i mallen som valdes när den orkestrerade kampanjen skapades, men kan redigeras efter behov för den här specifika orkestrerade kampanjen.

![](assets/workflow-settings-button.png){zoomable="yes"}{width="70%" align="left"}

## Samordnade kampanjegenskaper {#properties}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_properties"
>title="Samordnade kampanjegenskaper"
>abstract="I det här avsnittet finns generiska orkestrerade kampanjegenskaper som också är tillgängliga när du skapar den orkestrerade kampanjen. Du kan välja vilken mall som ska användas för att skapa den orkestrerade kampanjen och ange en etikett. Expandera avsnittet Ytterligare alternativ om du vill konfigurera specifika inställningar, till exempel lagringsmappen för den orkestrerade kampanjen eller tidszonen."

Avsnittet **[!UICONTROL Properties]** innehåller allmänna inställningar som kan konfigureras när du skapar en orchestrerad kampanj. Om du vill komma åt egenskaperna för en befintlig orkestrerad kampanj klickar du på knappen **[!UICONTROL Settings]** i åtgärdsfältet ovanför arbetsytan för den orkestrerade kampanjen.


![](assets/workflow-settings.png){zoomable="yes"}{width="70%" align="left"}


Dessa egenskaper är:

* **[!UICONTROL Label]** för den orkestrerade kampanj som visas i listan.
* **[!UICONTROL Internal name]** för den orkestrerade kampanjen.
* **[!UICONTROL Folder]** där den orchestrerade kampanjen ska sparas.
* Standardvärdet **[!UICONTROL Timezone]** som ska användas i alla de orkestrerade kampanjaktiviteterna. Som standard är tidszonen för den orkestrerade kampanjen den som är definierad för den aktuella kampanjoperatorn.
Möjliga värden är:
   * **Serverns tidszon** för att använda tidszonen i din Adobe Experience Platform-organisation
   * **Operatörens tidszon** använder tidszonen för operatorn som kör den orkestrerade kampanjen
   * **Tidszon för databasen** som använder databasserverns tidszon
   * En specifik tidszon
* När en orkestrerad kampanj misslyckas meddelas de operatorer som tillhör den operatorgrupp som valts i fältet **[!UICONTROL Supervisor(s)]** via e-post.
* Du kan även ange en **[!UICONTROL Description]** av din samordnade kampanj.

## Segmenteringsinställningar  {#segmentation-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_segmentation"
>title="Segmenteringsinställningar"
>abstract="I det här avsnittet kan du välja måldimensionen för målprofiler i den samordnade kampanjen och välja att behålla arbetsflödesresultaten mellan två körningar. Det här alternativet bör endast användas i testsyfte och får aldrig aktiveras i en produktionsstrukturerad kampanj."

* **[!UICONTROL Targeting dimension]**: Välj måldimensionen som ska användas för målprofiler: mottagare, mottagare, operatör, prenumeranter osv.

* **[!UICONTROL Keep the result of interim populations between two executions]**: Som standard behålls bara arbetsregister för den senaste körningen av den orchestrerade kampanjen. Arbetstabeller från tidigare avrättningar rensas av en teknisk, strukturerad kampanj som körs dagligen.

  Om det här alternativet är aktiverat behålls arbetsregister även efter att den orkestrerade kampanjen har körts. Du kan använda den i testsyfte och måste därför användas **endast** i utvecklings- eller staging-miljöer. Den får aldrig checkas in i en produktionsstrukturerad kampanj.

## Körningsinställningar  {#exec-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_execution"
>title="Körningsinställningar"
>abstract="I det här avsnittet kan du konfigurera inställningar som är relaterade till körningen av arbetsflödet, t.ex. antalet dagar som den orkestrerade kampanjhistoriken sparas."

* **[!UICONTROL History in days]**: Anger efter hur många dagar som historiken måste rensas. Historiken innehåller element som är relaterade till den orkestrerade kampanjen: loggar, uppgifter, händelser (tekniska objekt som är kopplade till den orkestrerade kampanjåtgärden). Standardvärdet är 30 dagar för färdiga mallar för riktade kampanjer. Rensning av historiken utförs av den tekniska rensningskampanj som körs som standard varje dag

  >[!IMPORTANT]
  >
  >Om fältet **[!UICONTROL History in days]** lämnas tomt betraktas dess värde som 1, vilket innebär att historiken rensas efter 1 dag.

* **[!UICONTROL Default affinity]**: Om din installation innehåller flera orkestrerade kampanjservrar använder du det här fältet för att ange på vilken server den orkestrerade kampanjen ska köras. Detta tvingar fram körningen av den samordnade kampanjen på en viss server. Du kan välja ett befintligt tillhörighetsnamn, men se till att du inte använder blanksteg eller skiljetecken. Om du använder olika servrar anger du olika namn, avgränsade med kommatecken.

  >[!IMPORTANT]
  >
  >Om värdet som definieras i det här fältet inte finns på någon server, kommer den orkestrerade kampanjen att förbli väntande.


* **[!UICONTROL Save SQL queries in log]**: Markera det här alternativet om du vill spara SQL-frågorna från den pågående kampanjen i flera steg i loggarna. Den här funktionen är reserverad för avancerade användare. Det gäller för samordnade kampanjer som innehåller målinriktningsaktiviteter som **[!UICONTROL Build audience]**. När det här alternativet är aktiverat visas de SQL-frågor som skickas till databasen under den orkestrerade kampanjkörningen i loggarna för den orkestrerade kampanjen, så att du kan analysera dem för att optimera frågor eller diagnostisera problem.

## Inställningar för felhantering  {#error-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_error"
>title="Inställningar för felhantering"
>abstract="I det här avsnittet kan du definiera hur den samordnade kampanjen ska hantera fel under körningen. Du kan välja att pausa processen, ignorera ett visst antal fel eller stoppa den samordnade kampanjkörningen."

* **[!UICONTROL Error management]**: I det här fältet kan du definiera de åtgärder som ska vidtas om en orkestrerad kampanjaktivitet innehåller fel. Det finns tre möjliga alternativ:

   * **[!UICONTROL Suspend the process]**: Den orkestrerade kampanjen pausas automatiskt och dess status ändras till **[!UICONTROL Failed]**. När problemet är löst kan du återuppta den samordnade kampanjen med knapparna **[!UICONTROL Resume]**.
   * **[!UICONTROL Ignore]**: Statusen för aktiviteten som utlöste felet ändras till **[!UICONTROL Failed]**, men den orkestrerade kampanjen behåller statusen **[!UICONTROL Started]**. <!-- TO ADD ONCE SCHEUDLER IS AVAILABLE This configuration is relevant for recurring tasks: if the branch includes a scheduler, it will start normally next time the workflow is executed.-->
   * **[!UICONTROL Abort the process]**: Den orkestrerade kampanjen stoppas automatiskt och dess status ändras till **[!UICONTROL Failed]**. När problemet är löst startar du om den orkestrerade kampanjen med knapparna **[!UICONTROL Start]**.

* **[!UICONTROL Consecutive errors]**: Det här fältet blir tillgängligt när värdet **[!UICONTROL Ignore]** har valts i fältet **[!UICONTROL In case of errors]**. Du kan ange antalet fel som kan ignoreras innan processen stoppas. När det här numret har nåtts ändras kampanjstatusen till **[!UICONTROL Failed]**. Om värdet för det här fältet är 0 stoppas aldrig den orkestrerade kampanjen oavsett antalet fel.


