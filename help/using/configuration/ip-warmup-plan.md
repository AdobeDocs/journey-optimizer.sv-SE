---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en IP-värmeringsplan
description: Lär dig hur du skapar en IP-värmeringsplan i Journey Optimizer
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP, grupp, underdomäner, leveransbarhet
hide: true
hidefromtoc: true
exl-id: c2434086-2ed4-4cd0-aecd-2eea8f0a55f6
source-git-commit: eb4a4929de17f0b57216f69e00da6314f7b59b07
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 1%

---

# Skapa en IP-värmeringsplan {#ip-warmup}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med IP-värmare](ip-warmup-gs.md)
* [Skapa IP-värmningskampanjer](ip-warmup-campaign.md)
* **[Skapa en IP-värmeringsplan](ip-warmup-plan.md)**
* [Kör IP-värmerappen](ip-warmup-execution.md)

>[!ENDSHADEBOX]

När du har skapat en eller flera [IP-kampanjer](ip-warmup-campaign.md) med en dedikerad yta och motsvarande alternativ aktiverat, kan du börja skapa din IP-värdplan.

>[!CAUTION]
>
>Om du vill komma åt, skapa, redigera och ta bort IP-beredskapsplanerna måste du ha **[!UICONTROL Deliverability Consultant]** behörighet. <!--Learn more on managing [!DNL Journey Optimizer] users' access rights in [this section](../administration/permissions-overview.md).-->

## Förbered filen för IP-warmup-planen {#prepare-file}

Varmning av IP-adresser är en aktivitet som gradvis ökar antalet e-postmeddelanden som går ut från era IP-adresser och domäner till de viktigaste Internetleverantörerna för att etablera ert rykte som en legitim avsändare.

Denna aktivitet utförs i rätt tid med hjälp av en leveransexpert som hjälper till att ta fram en genomtänkt plan baserad på branschens domäner, användningsfall, regioner, Internet-leverantörer och olika andra faktorer.

<!--When working with the [!DNL Journey Optimizer] IP warmup feature, this plan takes the form of an Excel file that must contain a number of predefined columns.-->

Innan du kan skapa en IP-uppvärmningsplan i [!DNL Journey Optimizer] måste du fylla i en Excel-mall med alla data som matar in planen.

>[!CAUTION]
>
>Arbeta med din leveranskonsult för att säkerställa att din IP-värmerappningsfil är korrekt konfigurerad.
>
>Se till att du använder det format som finns i mallen.

Nedan visas ett exempel på en fil som innehåller en IP-värmerapport.

![](assets/ip-warmup-sample-file.png)

>[!NOTE]
>
>För tillfället bör du lämna **Egenskaper** och **Värde** rörliga celler.

### Fliken IP Warmup Plan {#ip-warmup-plan-tab}

* I det här exemplet har en plan förberetts som sträcker sig över 17 dagar (kallas&quot;**körningar**&quot;) för att nå en målvolym på över en miljon profiler.

* Detta planerade arbete pågår till sex **faser**, som alla innehåller minst en omgång.

* Du kan ha så många kolumner du vill för de domäner du vill leverera till. I det här exemplet är planen uppdelad i sex kolumner:

   * Fyra av dessa motsvarar **färdiga domängrupper** som du kan använda i din plan (Gmail, Microsoft, Yahoo och Orange).
   * Den ena motsvarar en anpassad domängrupp (som du måste lägga till med [Anpassad domängrupp](#custom-domain-group-tab) -fliken).
   * Den sjätte kolumnen, **Övriga**, innehåller alla återstående adresser från andra domäner som inte uttryckligen omfattas av planen. Den här kolumnen är valfri: om den utelämnas kommer e-post endast att skickas till de angivna domänerna.
* The **Förlovningsdagar** kolumn visar att det endast är profilerna som interagerar med ert varumärke under den senaste angivna perioden som är målinriktade.

Tanken är att stegvis öka antalet måladresser i varje körning och samtidigt minska antalet körningar för varje fas.

De färdiga huvuddomängrupperna som du kan lägga till i din plan visas nedan:

* Gmail
* Adobe
* WP
* Comcast
* Yahoo
* Bigpond
* Orange
* Softbank
* Docomo
* United Internet
* Microsoft
* KDDI
* Italia Online
* La Poste
* Apple

<!--
+++ Gmail
gmail.com;gmail.fr;gmail.de;gmail.co.uk;gmail.it
+++

+++ Adobe
adobe.com;adobe.fr;adobe.es
+++

+++WP
+++

+++Comcast
+++

+++Yahoo
+++

+++Bigpond
+++

+++Orange
+++

+++Softbank
+++

+++Docomo
+++

+++United Internet
+++

+++Microsoft
+++

+++KDDI
+++

+++Italia Online
+++

+++La Poste
+++
-->

### Fliken Anpassad domängrupp {#custom-domain-group-tab}

Du kan också lägga till fler kolumner i din plan genom att ta med anpassade domängrupper.

Använd **[!UICONTROL Custom Domain Group]** för att definiera en ny domängrupp. För varje domän kan du lägga till alla underdomäner som den omfattar.<!--TBC-->

Om du till exempel lägger till den anpassade domänen Luma vill du att följande underdomäner ska inkluderas: luma.com, luma.co.uk, luma.it, luma.fr, luma.de osv.

![](assets/ip-warmup-sample-file-custom.png)

### Exempel {#example}

Säg att du vill ha två anpassade domängrupper:

* En för Hotmail-domäner.
* En för alla andra domäner i domängruppen Microsoft (och utesluter därmed alla Hotmail-domäner).

Observera att alla andra domäner samlas i **[!UICONTROL Others]** kolumn.

1. I **[!UICONTROL Custom Domain Group]** -fliken, skapa **Hotmail** domängrupp.

1. Lägg till alla Hotmail-domäner på samma rad.

   Du kan [kopiera och klistra in](#copy-paste) alla Hotmail-domäner som listas i [Fliken IP Warmup Plan](#ip-warmup-plan-tab) -avsnitt.

1. Lägg till en till rad.

1. Skapa **Microsoft_X** domängrupp.

1. Lägg till alla Microsoft-domäner som inte är Hotmail på samma rad. På samma sätt kan du kopiera och klistra in dem från listan ovan. [Läs mer](#copy-paste)

1. Gå tillbaka till **[!UICONTROL IP Warmup Plan]** -fliken.

1. Skapa tre kolumner: en för **Hotmail**, en för **Microsoft_X** och en för **Övriga**.

1. Fyll i kolumnerna efter behov.

>[!NOTE]
>
>När IP-värmningsplanen har överförts till [!DNL Journey Optimizer]behöver du inte utesluta Microsoft domängrupper.

<!--Only the domain groups listed in the **[!UICONTROL IP Warmup Plan]** tab will be taken into account.-->

### Kopiera och klistra in standarddomäner {#copy-paste}

Om du vill skapa en anpassad domängrupp som innehåller alla Hotmail-domäner, till exempel, kan du kopiera och klistra in domänerna från standardlistan [ovan](#ip-warmup-plan-tab).

Använd sedan Excel-konverteringsverktyget för att konvertera text till kolumner:

1. Välj **[!UICONTROL Data]** > **[!UICONTROL Text to columns...]**, välja **[!UICONTROL Delimited]** och markera **[!UICONTROL Next]**.

1. Välj **[!UICONTROL Semicolon]**, klicka **[!UICONTROL Next]** och **[!UICONTROL Finish]**.

Varje domän visas nu i en egen kolumn på samma rad.

## Få åtkomst till och hantera IP-värmerelayouter {#manage-ip-warmup-plans}

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP warmup plans]**-menyn. Alla IP-uppvärmningsplaner som har skapats hittills visas.

   ![](assets/ip-warmup-filter-list.png)

1. Du kan filtrera efter status. De olika statusvärdena är:

   * **Inte startat**: ingen körning har aktiverats ännu. [Läs mer](ip-warmup-execution.md#define-runs)
   * **Live**: planen ändras till den här statusen så snart den första körningen i den första fasen har aktiverats. [Läs mer](ip-warmup-execution.md#define-runs)
   * **Slutförd**: planen har markerats som slutförd. <!--This option is only available if all the runs in the plan are in **[!UICONTROL Completed]** or **[!UICONTROL Draft]** status (no run can be **[!UICONTROL Live]**).--> [Läs mer](ip-warmup-execution.md#mark-as-completed)
     <!--* **Paused**: to check (user action)-->

1. Om du vill ta bort en IP-uppvärmningsplan väljer du **[!UICONTROL Delete]** -ikonen bredvid namnet på en plan och bekräfta borttagningen.

   >[!NOTE]
   >
   >Endast planer med **Inte startat** kan tas bort.

   ![](assets/ip-warmup-delete-plan.png)

   >[!CAUTION]
   >
   >Den valda IP-warmup-planen tas bort permanent.

## Skapa en IP-värmeringsplan {#create-ip-warmup-plan}

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

Följ stegen nedan om du vill skapa en IP-värmeringsplan.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP warmup plans]** menyn och klicka sedan på **[!UICONTROL Create IP warmup plan]**.

   ![](assets/ip-warmup-create-plan.png)

1. Fyll i information om IP-beredskapsplanen: ge den ett namn och en beskrivning.

   ![](assets/ip-warmup-plan-details.png)

1. Välj [yta](channel-surfaces.md) som du vill värma upp. Endast marknadsföringsytor är tillgängliga för urval. [Läs mer om e-posttyp](../email/email-settings.md#email-type)

   >[!NOTE]
   >
   >De kampanjer som du vill associera med din IP-värmeringsplan måste använda samma yta. [Lär dig hur du skapar en IP-värmerskampanj](ip-warmup-campaign.md)

1. Överför den Excel-fil som innehåller din IP-värmeringsplan. [Läs mer](#prepare-file)

   <!--
    You can also download the Excel template from the [!DNL Journey Optimizer] user interface and upload it after filling it with the IP warmup details.-->

   ![](assets/ip-warmup-upload-success.png)

   >[!NOTE]
   >
   >Om överföringen misslyckas bör du kontrollera att du använder rätt format (.xls eller .xlsx). Använd exemplet från Adobe.

1. Klicka på **[!UICONTROL Create]**. Alla faser, körningar, kolumner och deras innehåll som definieras i den överförda filen visas automatiskt i [!DNL Journey Optimizer] gränssnitt.

   ![](assets/ip-warmup-plan-uploaded.png)

Du är nu redo att genomföra din IP-värmeringsplan. [Läs mer](ip-warmup-execution.md)
