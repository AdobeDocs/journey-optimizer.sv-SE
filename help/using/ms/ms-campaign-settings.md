---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera inställningar för samordnade kampanjer
description: Learn how to configure orchestrated campaign settings with Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: a9bb3782-a4d1-43fe-ae2a-aef3f17ba588
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 0%

---

# Konfigurera inställningar för samordnade kampanjer {#workflow-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_creation_properties"
>title="Samordnade kampanjegenskaper"
>abstract="På den här skärmen väljer du den mall som ska användas för att skapa den orkestrerade kampanjen och anger en etikett. Expandera avsnittet **Ytterligare alternativ** om du vill konfigurera fler inställningar, till exempel det interna namnet för den orkestrerade kampanjen, dess mapp, tidszon och övervakningsgrupp. Vi rekommenderar starkt att du väljer en grupp för ansvariga så att de får ett meddelande om ett fel inträffar."

When creating an orchestrated campaign or orchestrating orchestrated campaign activities in the canvas, you can access advanced settings related to the orchestrated campaign. For example, you can set a specific timezone for the orchestrated campaign, manage how the orchestrated campaign should behave in case of error, or manage the delay after which the orchestrated campaign history should be purged.

These settings are pre-configured in the template selected when creating the orchestrated campaign, but can be edited as needed for this specific orchestrated campaign.

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
* Den **[!UICONTROL Internal name]** orkestrerade kampanjen.
* Den **[!UICONTROL Folder]** plats där den orkestrerade kampanjen ska sparas.
* Standardvärdet **[!UICONTROL Timezone]** som ska användas i alla aktiviteter i den orkestrerade kampanjen. Som standard är den orkestrerade kampanjens tidszon den som definierats för den aktuella kampanjoperatorn.
Möjliga värden är:
   * **Serverns tidszon** för att använda tidszonen i din Adobe Experience Platform-organisation
   * **Operator time zone** to uses the time zone of the operator who executes the orchestrated campaign
   * **Tidszon för databasen** som använder databasserverns tidszon
   * A specific time zone
* När en orkestrerad kampanj misslyckas meddelas operatörerna som tillhör den operatörsgrupp som **[!UICONTROL Supervisor(s)]** valts i fältet via e-post.
* Du kan också ange en **[!UICONTROL Description]** av din orkestrerade kampanj.

## Inställningar för segmentering  {#segmentation-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_segmentation"
>title="Segmenteringsinställningar"
>abstract="I det här avsnittet kan du välja måldimensionen för målprofiler i den samordnade kampanjen och välja att behålla arbetsflödesresultaten mellan två körningar. Det här alternativet bör endast användas i testsyfte och får aldrig aktiveras i en produktionsstrukturerad kampanj."

* **[!UICONTROL Targeting dimension]**: Select the targeting dimension to use to target profiles: recipients, contract beneficiaries, operator, subscribers, etc.

* **[!UICONTROL Keep the result of interim populations between two executions]**: By default, only the working tables of the last execution of the orchestrated campaign are kept. Working tables from previous executions are purged by a technical orchestrated campaign, which runs on a daily basis.

  Om det här alternativet är aktiverat behålls arbetsregister även efter att den orkestrerade kampanjen har körts. Du kan använda den i testsyfte och måste därför användas **endast** i utvecklings- eller staging-miljöer. Den får aldrig checkas in i en produktionsstrukturerad kampanj.

## Körningsinställningar  {#exec-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_execution"
>title="Körningsinställningar"
>abstract="I det här avsnittet kan du konfigurera inställningar som är relaterade till körningen av arbetsflödet, t.ex. antalet dagar som den orkestrerade kampanjhistoriken sparas."

* **[!UICONTROL History in days]**: Anger efter hur många dagar som historiken måste rensas. Historiken innehåller element som är relaterade till den orkestrerade kampanjen: loggar, uppgifter, händelser (tekniska objekt som är länkade till den orkestrerade kampanjåtgärden). Standardvärdet är 30 dagar för färdiga orkestrerade kampanjmallar. Rensning av historiken utförs av den tekniska orkestrerade kampanjen för databasrensning, som körs som standard varje dag

  >[!IMPORTANT]
  >
  >**[!UICONTROL History in days]** Om fältet lämnas tomt kommer dess värde att betraktas som &quot;1&quot;, vilket innebär att historiken kommer att rensas efter 1 dag.

* **[!UICONTROL Default affinity]**: Om din installation innehåller flera orkestrerade kampanjservrar använder du det här fältet för att ange på vilken server den orkestrerade kampanjen ska köras. Detta tvingar fram körningen av den samordnade kampanjen på en viss server. Du kan välja ett befintligt tillhörighetsnamn, men se till att du inte använder blanksteg eller skiljetecken. Om du använder olika servrar anger du olika namn, avgränsade med kommatecken.

  >[!IMPORTANT]
  >
  >If the value defined in this field does not exist on any server, the orchestrated campaign will remain pending.


* **[!UICONTROL Save SQL queries in log]**: Markera det här alternativet för att spara SQL-frågorna från workflmulti-step-kampanjen i loggarna. Den här funktionen är reserverad för avancerade användare. Det gäller för orkestrerade kampanjer som innehåller målinriktade aktiviteter som **[!UICONTROL Build audience]**. När det här alternativet är aktiverat visas de SQL-frågor som skickas till databasen under den orkestrerade kampanjkörningen i den orkestrerade kampanjens loggar, så att du kan analysera dem för att optimera frågor eller diagnostisera problem.

## Inställningar för felhantering  {#error-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_error"
>title="Inställningar för felhantering"
>abstract="I det här avsnittet kan du definiera hur den samordnade kampanjen ska hantera fel under körningen. Du kan välja att pausa processen, ignorera ett visst antal fel eller stoppa den samordnade kampanjkörningen."

* **[!UICONTROL Error management]**: I det här fältet kan du definiera de åtgärder som ska vidtas om en orkestrerad kampanjaktivitet innehåller fel. Det finns tre möjliga alternativ:

   * **[!UICONTROL Suspend the process]**: Den orkestrerade kampanjen pausas automatiskt och dess status ändras till **[!UICONTROL Failed]**. När problemet är löst kan du återuppta den samordnade kampanjen med knapparna **[!UICONTROL Resume]**.
   * **[!UICONTROL Ignore]**: Statusen för aktiviteten som utlöste felet ändras till **[!UICONTROL Failed]**, men den orkestrerade kampanjen behåller statusen **[!UICONTROL Started]**. <!-- TO ADD ONCE SCHEUDLER IS AVAILABLE This configuration is relevant for recurring tasks: if the branch includes a scheduler, it will start normally next time the workflow is executed.-->
   * **[!UICONTROL Abort the process]**: Den orkestrerade kampanjen stoppas automatiskt och dess status ändras till **[!UICONTROL Failed]**. När problemet är löst startar du om den orkestrerade kampanjen med hjälp av **[!UICONTROL Start]** knapparna.

* **[!UICONTROL Consecutive errors]**: Det här fältet blir tillgängligt när **[!UICONTROL Ignore]** värdet är markerat i **[!UICONTROL In case of errors]** fältet. Du kan ange hur många fel som kan ignoreras innan processen stoppas. När det här numret har nåtts ändras den orkestrerade kampanjstatusen till **[!UICONTROL Failed]**. Om värdet i det här fältet är 0 kommer den orkestrerade kampanjen aldrig att stoppas oavsett antalet fel.

## Skript för initiering {#initialization-script}

Med **initieringsskriptet** kan du initiera variabler eller ändra aktivitetsegenskaper. Klicka på knappen **Redigera kod** och skriv det kodfragment som ska köras. The script is called when the orchestrated campaign executes. Se avsnittet som rör [händelsevariabler](event-variables.md).
