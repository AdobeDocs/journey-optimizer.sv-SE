---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Läs in fil
description: Lär dig hur du använder aktiviteten Läs in fil i en orkestrerad kampanj
hide: true
hidefromtoc: true
exl-id: ae0dc980-2361-4c3b-a68e-ae0bb5dc0a26
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 1%

---

# Ladda fil {#load-file}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile"
>title="Läs in filaktivitet"
>abstract="Aktiviteten **Läs in fil** är en **datahanteringsaktivitet**. Använd den här aktiviteten när du vill arbeta med data som lagras i en extern fil. Profiler och data läggs inte till i databasen, men alla fält i indatafilen är tillgängliga för anpassning, för att uppdatera profiler eller andra tabeller. "

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_outboundtransition"
>title="Avvisa utgående övergång för hantering"
>abstract="Avvisa utgående övergång för hantering"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_outboundtransition_reject"
>title="Avvisa utgående övergång för hantering av avslag"
>abstract="Avvisa utgående övergång för hantering av avslag"


Aktiviteten **Läs in fil** är en **datahanteringsaktivitet**. Använd den här aktiviteten när du vill arbeta med profiler och data som lagras i en extern fil. Profiler och data läggs inte till i databasen, men alla fält i indatafilen är tillgängliga för anpassning, för att uppdatera profiler eller andra tabeller.

>[!NOTE]
>Filformat som stöds är: text (TXT) och kommaavgränsade värden (CSV). Du kan läsa in filer som är högst 50 MB stora.

Den här aktiviteten kan användas med en [avstämningsaktivitet](reconciliation.md) för att länka oidentifierade data till befintliga resurser. Aktiviteten **Läs in fil** kan till exempel placeras före en **avstämningsaktivitet** om du importerar data som inte är standard till databasen.

## Konfigurera aktiviteten Läs in fil {#load-configuration}

Aktivitetskonfigurationen för **Läs in fil** omfattar två steg. Först måste du definiera den förväntade filstrukturen genom att överföra en exempelfil.  När du är klar kan du ange ursprunget för filen vars data ska importeras. Konfigurera aktiviteten genom att följa stegen nedan.

![](../assets/workflow-load-file.png)

### Konfigurera exempelfilen {#sample}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_samplefile"
>title="Exempelfil"
>abstract="Välj den förväntade filstrukturen genom att överföra en exempelfil."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_formatting"
>title="Formatering för aktiviteten Läs in fil"
>abstract="I avsnittet **Formatering** anger du hur filen ska formateras för att säkerställa att data importeras på rätt sätt."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_valueremapping"
>title="Värdeommappning för aktiviteten Läs in fil"
>abstract="Använd det här alternativet om du vill mappa specifika värden från de inlästa filerna med nya värden. Om kolumnen till exempel innehåller värdena &quot;Sant&quot;/&quot;Falskt&quot; kan du lägga till en mappning som automatiskt ersätter dessa värden med tecknen &quot;0&quot;/&quot;1&quot;."

Följ de här stegen för att konfigurera exempelfilen som används för att definiera den förväntade filstrukturen:

1. Lägg till en **Läs in fil**-aktivitet i din orkestrerade kampanj.

1. Välj den exempelfil som ska användas för att definiera den förväntade filstrukturen. Det gör du genom att klicka på knappen **Markera fil** i avsnittet **[!UICONTROL Sample file]** och välja den lokala fil som ska användas.

1. En förhandsgranskning av exempelfilen visas med högst 30 rader.

1. Ange om filen använder avgränsade kolumner eller kolumner med fast bredd i listrutan **[!UICONTROL File type]**.

   ![](../assets/workflow-load-file-sample.png)

1. För filtyper med avgränsade kolumner använder du avsnittet **Kolumner** för att konfigurera egenskaperna för varje kolumn.

   +++Tillgängliga alternativ för filkolumner

   * **[!UICONTROL Label]**: Etikett som ska visas för kolumnen.
   * **[!UICONTROL Data type]**: Typ av data i kolumnen.
   * **[!UICONTROL Width]** (strängdatatyp): Maximalt antal tecken som ska visas i kolumnen.
   * **[!UICONTROL Data Transformation]** (strängdatatyp): Använd omformning på värdena i kolumnen.
   * **[!UICONTROL White space management]** (strängdatatyp): Ange hur blanksteg i kolumnen ska hanteras.
   * **[!UICONTROL Separators]** (datatyperna datum, tid, heltal och tal)*: Ange de tecken som ska användas som avgränsare.
   * **[!UICONTROL Allow NULLs]**: Ange hur tomma värden i kolumnen ska hanteras.
   * **[!UICONTROL Error processing]** (strängdatatyp): Ange beteende om det finns fel på en av raderna.
   * **[!UICONTROL Value remapping]**: Med det här alternativet kan du mappa specifika värden med nya. Om kolumnen till exempel innehåller värdena &quot;Sant&quot;/&quot;Falskt&quot; kan du lägga till en mappning som automatiskt ersätter dessa värden med tecknen &quot;0&quot;/&quot;1&quot;.

+++

1. I avsnittet **Formatering** anger du hur filen ska formateras för att säkerställa att data importeras på rätt sätt.

### Definiera målfilen som ska överföras {#target}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_targetfile"
>title="Målfil för aktiviteten Läs in fil"
>abstract="I avsnittet **[!UICONTROL Target file]** anger du hur filen ska hämtas till servern."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_nameofthefile"
>title="Filens namn"
>abstract="Ange namnet på fältet som ska överföras till servern. Klicka på ikonen **[!UICONTROL Open personalization dialog]** om du vill använda uttrycksredigeraren, inklusive händelsevariabler, för att beräkna filnamnet."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_targetdb"
>title="Måldatabas"
>abstract="Om du använder en **[!UICONTROL Load file]**-aktivitet som redan har konfigurerats, finns ytterligare ett **[!UICONTROL Target database]**-avsnitt tillgängligt om du har konfigurerat aktiviteten att överföra filen till en extern databas."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_command"
>title="Kommandot Läs in fil"
>abstract="Att tillåta godtyckligt kommando för förbehandling är ett säkerhetsproblem, inaktivera säkerhetsalternativet XtkSecurity_Disable_Preproc för att tvinga fram användning av en fördefinierad lista med kommandon."

>[!CAUTION]
>
>Innan du läser in målfilen kontrollerar du att den följer exempelfilens formatering. Eventuella avvikelser i filformat, kolumnstruktur eller antal kolumner kan leda till fel under kampanjkörningen.

Så här definierar du målfilen som ska överföras:

1. I avsnittet **[!UICONTROL Target file]** anger du vilken åtgärd som ska utföras när filen som ska överföras till servern hämtas.

   * **[!UICONTROL Upload file from local machine]**: Välj den fil som ska överföras från datorn.

   * **[!UICONTROL Specified in the transition]**: Överför filen som anges i den inkommande övergången som kommer från en tidigare aktivitet som **[!UICONTROL Transfer file]**.

   * **[!UICONTROL Pre-process the file]**: Överför filen som angavs i föregående övergång och använd ett förbehandlingskommando på den, till exempel **[!UICONTROL Decompression]** eller **[!UICONTROL Decrypt]**.

   * **[!UICONTROL Calculated]**: Överför filen vars namn anges i fältet **[!UICONTROL File name]**. Klicka på ikonen **[!UICONTROL Open personalization dialog]** om du vill använda uttrycksredigeraren, inklusive händelsevariabler, för att beräkna filnamnet.

   ![](../assets/workflow-load-file-config.png)

   >[!NOTE]
   >
   >Om du använder en **[!UICONTROL Load file]**-aktivitet som redan har konfigurerats visas ytterligare ett **[!UICONTROL Target database]**-avsnitt om du har konfigurerat aktiviteten att överföra filen till en extern databas. Du kan ange om du vill överföra filen på Campaign-servern eller i den externa databasen.

### Ytterligare alternativ {#options}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_rejectmgt"
>title="Avvisa hantering för Läs in filaktivitet"
>abstract="I avsnittet **Avvisningshantering** anger du hur aktiviteten ska fungera om fel uppstår. Du kan definiera det maximala antalet fel som tillåts och växla **[!UICONTROL Keep rejects in a file]**-alternativet för att hämta en fil som innehåller felen som inträffade under importen till servern."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_loadfile_delete"
>title="Ta bort fil efter import"
>abstract="Om du vill ta bort originalfilen från servern efter att filen har importerats växlar du mellan **Ta bort filen efter importen**."


1. I avsnittet **Avvisningshantering** anger du hur aktiviteten ska fungera om fel uppstår:

   * I fältet **[!UICONTROL Number of errors allowed]** anger du det maximala antalet fel som tillåts när filen som ska läsas in bearbetas. Om värdet till exempel är 20 misslyckas den samordnade kampanjkörningen om det finns fler än 20 fel när filen läses in.

   * Om du vill behålla felen som uppstod när filen lästes in aktiverar du alternativet **[!UICONTROL Keep rejects in a file]** och anger önskat namn för filen i fältet **[!UICONTROL Rejection File]**.

     När du har aktiverat det här alternativet läggs ytterligare en utdataövergång till som heter &quot;Komplettera&quot; efter aktiviteten. Alla fel som inträffar under importen lagras i den angivna filen på servern.

1. Om du vill ta bort den överförda filen från servern efter att den orkestrerade kampanjen har körts, växlar du alternativet **[!UICONTROL Delete file after import]**.

   ![](../assets/workflow-load-file-options.png)

1. Klicka på **Bekräfta** när inställningarna är korrekta.

## Exempel {#load-example}

Ett exempel på en extern filinläsning som används med aktiviteten **Avstämning** finns i [det här avsnittet](reconciliation.md#reconciliation-example).
