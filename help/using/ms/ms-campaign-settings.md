---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera kampanjinställningar i flera steg
description: Lär dig konfigurera inställningar för flerstegskampanjer med Adobe Journey Optimizer
hide: true
hidefromtoc: true
source-git-commit: 00f843300a9cfe798ea4d3a92fbe89ba80e70bc5
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 0%

---


# Konfigurera kampanjinställningar i flera steg {#workflow-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_creation_properties"
>title="Egenskaper för kampanjer i flera steg"
>abstract="På den här skärmen väljer du den mall som ska användas för att skapa flerstegskampanjen och anger en etikett. Expandera avsnittet **Ytterligare alternativ** om du vill konfigurera fler inställningar, till exempel det interna namnet för kampanjen i flera steg, dess mapp, tidszon och övervakningsgrupp. Vi rekommenderar starkt att du väljer en grupp för ansvariga så att de får ett meddelande om ett fel inträffar."

När du skapar en kampanj i flera steg eller organiserar kampanjaktiviteter i flera steg på arbetsytan får du tillgång till avancerade inställningar för kampanjen i flera steg. Du kan till exempel ange en specifik tidszon för flerstegskampanjen, hantera hur flerstegskampanjen ska bete sig om fel uppstår eller hantera fördröjningen som flerstegskampanjen ska rensas efter.

Dessa inställningar är förkonfigurerade i mallen som valdes när flerstegskampanjen skapades, men kan redigeras efter behov för den här specifika flerstegskampanjen.

![](assets/workflow-settings-button.png){zoomable="yes"}{width="70%" align="left"}

## Egenskaper för kampanjer i flera steg {#properties}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_properties"
>title="Egenskaper för kampanjer i flera steg"
>abstract="I det här avsnittet finns allmänna kampanjegenskaper i flera steg som också är tillgängliga när du skapar en kampanj i flera steg. Du kan välja vilken mall som ska användas för att skapa flerstegskampanjen och ange en etikett. Expandera avsnittet Ytterligare alternativ om du vill konfigurera specifika inställningar, till exempel mappen för lagring av kampanj i flera steg eller tidszonen."

Avsnittet **[!UICONTROL Properties]** innehåller allmänna inställningar som kan konfigureras när du skapar en kampanj i flera steg. Om du vill komma åt egenskaperna för en befintlig flerstegskampanj klickar du på knappen **[!UICONTROL Settings]** i åtgärdsfältet ovanför arbetsytan för flerstegskampanjer.


![](assets/workflow-settings.png){zoomable="yes"}{width="70%" align="left"}


Dessa egenskaper är:

* **[!UICONTROL Label]** för den flerstegskampanj som visas i listan.
* **[!UICONTROL Internal name]** för flerstegskampanjen.
* **[!UICONTROL Folder]** där flerstegskampanjen ska sparas.
* Standardvärdet **[!UICONTROL Timezone]** som ska användas i alla flerstegskampanjaktiviteter. Som standard är flerstegskampanjens tidszon definierad för den aktuella kampanjoperatorn.
Möjliga värden är:
   * **Serverns tidszon** för att använda tidszonen i din Adobe Experience Platform-organisation
   * **Operatörens tidszon** använder tidszonen för operatorn som kör flerstegskampanjen
   * **Tidszon för databasen** som använder databasserverns tidszon
   * En specifik tidszon
* När en kampanj i flera steg misslyckas meddelas de operatorer som tillhör den operatörsgrupp som valts i fältet **[!UICONTROL Supervisor(s)]** via e-post.
* Du kan även ange **[!UICONTROL Description]** för din flerstegskampanj.

## Segmenteringsinställningar  {#segmentation-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_segmentation"
>title="Segmenteringsinställningar"
>abstract="I det här avsnittet kan du välja måldimension för målprofiler i flerstegskampanjen och välja att behålla arbetsflödesresultaten mellan två körningar. Det här alternativet bör endast användas i testsyfte och får aldrig aktiveras i en flerstegskampanj för produktion."

* **[!UICONTROL Targeting dimension]**: Välj måldimensionen som ska användas för målprofiler: mottagare, mottagare, operatör, prenumeranter osv.

* **[!UICONTROL Keep the result of interim populations between two executions]**: Som standard behålls endast arbetsregister för den senaste körningen av flerstegskampanjen. Arbetstabeller från tidigare körningar rensas av en teknisk flerstegskampanj som körs dagligen.

  Om det här alternativet är aktiverat behålls arbetsregister även när flerstegskampanjen har körts. Du kan använda den i testsyfte och måste därför användas **endast** i utvecklings- eller staging-miljöer. Den får aldrig checkas in i en flerstegskampanj för produktion.

## Körningsinställningar  {#exec-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_execution"
>title="Körningsinställningar"
>abstract="I det här avsnittet kan du konfigurera inställningar som är relaterade till körningen av arbetsflödet, t.ex. antalet dagar som flerstegskampanjhistoriken sparas."

* **[!UICONTROL History in days]**: Anger efter hur många dagar som historiken måste rensas. Historiken innehåller element som är relaterade till flerstegskampanjen: loggar, uppgifter, händelser (tekniska objekt som är kopplade till flerstegskampanjen). Standardvärdet är 30 dagar för färdiga mallar för flerstegskampanjer. Rensning av historiken utförs av den tekniska flerstegskampanjen för databasrensning, som körs som standard varje dag

  >[!IMPORTANT]
  >
  >Om fältet **[!UICONTROL History in days]** lämnas tomt betraktas dess värde som 1, vilket innebär att historiken rensas efter 1 dag.

* **[!UICONTROL Default affinity]**: Om din installation innehåller flera kampanjservrar i flera steg använder du det här fältet för att ange vilken server som kampanjen i flera steg ska köras på. Detta framtvingar körning av den flerstegskampanjen på en viss server. Du kan välja ett befintligt tillhörighetsnamn, men se till att du inte använder blanksteg eller skiljetecken. Om du använder olika servrar anger du olika namn, avgränsade med kommatecken.

  >[!IMPORTANT]
  >
  >Om det värde som definieras i det här fältet inte finns på någon server, kommer kampanjen i flera steg att förbli väntande.


* **[!UICONTROL Save SQL queries in log]**: Markera det här alternativet om du vill spara SQL-frågorna från den pågående kampanjen i flera steg i loggarna. Den här funktionen är reserverad för avancerade användare. Det gäller flerstegskampanjer som innehåller målinriktningsaktiviteter som **[!UICONTROL Build audience]**. När det här alternativet är aktiverat visas de SQL-frågor som skickas till databasen under körning av flerstegskampanjer i loggarna för flerstegskampanjer, så att du kan analysera dem för att optimera frågor eller diagnostisera problem.

## Inställningar för felhantering  {#error-settings}

>[!CONTEXTUALHELP]
>id="ajo_workflow_settings_error"
>title="Inställningar för felhantering"
>abstract="I det här avsnittet kan du definiera hur flerstegskampanjen ska hantera fel under körningen. Du kan välja att pausa processen, ignorera ett visst antal fel eller stoppa kampanjkörningen i flera steg."

* **[!UICONTROL Error management]**: I det här fältet kan du definiera de åtgärder som ska vidtas om en kampanjaktivitet i flera steg innehåller fel. Det finns tre möjliga alternativ:

   * **[!UICONTROL Suspend the process]**: Flerstegskampanjen pausas automatiskt och dess status ändras till **[!UICONTROL Failed]**. När problemet är löst kan du återuppta flerstegskampanjen med **[!UICONTROL Resume]**-knapparna.
   * **[!UICONTROL Ignore]**: Statusen för aktiviteten som utlöste felet ändras till **[!UICONTROL Failed]**, men flerstegskampanjen behåller statusen **[!UICONTROL Started]**. <!-- TO ADD ONCE SCHEUDLER IS AVAILABLE This configuration is relevant for recurring tasks: if the branch includes a scheduler, it will start normally next time the workflow is executed.-->
   * **[!UICONTROL Abort the process]**: Flerstegskampanjen stoppas automatiskt och dess status ändras till **[!UICONTROL Failed]**. När problemet är löst startar du om flerstegskampanjen med **[!UICONTROL Start]**-knapparna.

* **[!UICONTROL Consecutive errors]**: Det här fältet blir tillgängligt när värdet **[!UICONTROL Ignore]** har valts i fältet **[!UICONTROL In case of errors]**. Du kan ange antalet fel som kan ignoreras innan processen stoppas. När det här numret har nåtts ändras kampanjstatusen för flera steg till **[!UICONTROL Failed]**. Om värdet för det här fältet är 0 stoppas aldrig flerstegskampanjen oavsett antalet fel.

## Initieringsskript {#initialization-script}

Med **initieringsskriptet** kan du initiera variabler eller ändra aktivitetsegenskaper. Klicka på knappen **Redigera kod** och skriv det kodfragment som ska köras. Skriptet anropas när flerstegskampanjen körs. Se avsnittet som rör [händelsevariabler](event-variables.md).

