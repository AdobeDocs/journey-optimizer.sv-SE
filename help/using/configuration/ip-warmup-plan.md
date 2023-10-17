---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en IP-värmeringsplan
description: Lär dig hur du skapar en IP-värmeringsplan i Journey Optimizer
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: IP, grupp, underdomäner, leveransbarhet
hide: true
hidefromtoc: true
exl-id: c2434086-2ed4-4cd0-aecd-2eea8f0a55f6
source-git-commit: 82c189545ab4f37a2e4b1044c0b8cfeb539aed13
workflow-type: tm+mt
source-wordcount: '797'
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

## Förbered filen för IP-warmup-planen {#prepare-file}

Varmning av IP-adresser är en aktivitet som gradvis ökar antalet e-postmeddelanden som går ut från era IP-adresser och domäner till de viktigaste Internetleverantörerna för att etablera ert rykte som en legitim avsändare.

Denna aktivitet utförs i rätt tid med hjälp av en leveransexpert som hjälper till att ta fram en genomtänkt plan baserad på branschens domäner, användningsfall, regioner, Internet-leverantörer och olika andra faktorer.

När du arbetar med [!DNL Journey Optimizer] IP-värmerfunktionen, den här planen har formen av en Excel-fil som måste innehålla ett antal fördefinierade kolumner. Innan du kan skapa en IP-uppvärmningsplan i [!DNL Journey Optimizer] måste du fylla i den här mallen med alla data som kommer att mata in din plan.

>[!CAUTION]
>
>Arbeta med din leveranskonsult för att säkerställa att din IP-värmerappningsfil är korrekt konfigurerad.

Nedan visas ett exempel på en fil som innehåller en IP-värmerapport.

![](assets/ip-warmup-sample-file.png)

### Fliken IP Warmup Plan

* I det här exemplet har en plan förberetts som sträcker sig över 17 dagar (kallas&quot;**körningar**&quot;) för att nå en målvolym på över 1 miljon profiler.

* Planerad till 6 **faser**, som alla innehåller minst en omgång.

* Du kan ha så många kolumner du vill för de domäner du vill leverera till. I det här exemplet är planen uppdelad i sex kolumner: 5 av vilka motsvarar **huvuddomängrupper** som du kan använda i din plan (Gmail, Microsoft, Yahoo, Orange och Apple) och i den sjätte kolumnen, **Övriga**, innehåller alla återstående adresser från andra domäner.
* The **Förlovningsdagar** kolumn visar att det endast är de profiler som är engagerade med ert varumärke under de senaste 30 dagarna som är målinriktade.

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

### Fliken Anpassad domängrupp

Du kan också lägga till fler kolumner i din plan genom att ta med anpassade domängrupper.

Använd **[!UICONTROL Custom Domain Group]** för att definiera en ny domängrupp. För varje domän kan du lägga till alla underdomäner som den omfattar.<!--TBC-->

Om du till exempel lägger till den anpassade domänen Luma vill du att följande underdomäner ska inkluderas: luma.com, luma.co.uk, luma.it, luma.fr, luma.de osv.

![](assets/ip-warmup-sample-file-custom.png)

## Få åtkomst till och hantera IP-värmerelayouter {#manage-ip-warmup-plans}

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP warmup plans]**-menyn. Alla IP-uppvärmningsplaner som har skapats hittills visas.

   ![](assets/ip-warmup-filter-list.png)

1. Du kan filtrera efter status. De olika statusvärdena är:

   * **Inte startat**: ingen körning har aktiverats ännu. [Läs mer](ip-warmup-execution.md#define-runs)
   * **Live**: planen ändras till den här statusen så snart den första körningen i den första fasen har aktiverats. [Läs mer](ip-warmup-execution.md#define-runs)
   * **Slutförd**: planen har markerats som slutförd. Det här alternativet är bara tillgängligt om alla körningar i planen finns **[!UICONTROL Completed]** eller **[!UICONTROL Draft]** status (ingen körning kan utföras) **[!UICONTROL Live]**). [Läs mer](ip-warmup-execution.md#mark-as-completed)
     <!--* **Paused**: to check (user action)-->

1. Om du vill ta bort en IP-uppvärmningsplan väljer du **[!UICONTROL Delete]** -ikonen bredvid namnet på en plan och bekräfta borttagningen.

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

När en eller flera livekampanjer med **[!UICONTROL IP warmup plan activation]** aktiverat alternativ aktiveras, du kan koppla dem till en IP-värmeringsplan.

>[!CAUTION]
>
>Om du vill skapa, redigera och ta bort IP-beredskapsplanerna måste du ha **[!UICONTROL Deliverability Consultant]** behörighet. <!--Learn more on managing [!DNL Journey Optimizer] users' access rights in [this section](../administration/permissions-overview.md).-->

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP warmup plans]** menyn och klicka sedan på **[!UICONTROL Create IP warmup plan]**.

   ![](assets/ip-warmup-create-plan.png)

1. Fyll i information om IP-beredskapsplanen: ge den ett namn och en beskrivning.

   ![](assets/ip-warmup-plan-details.png)

1. Välj en [yta](channel-surfaces.md). Endast marknadsföringsytor är tillgängliga för urval. [Läs mer om e-posttyp](../email/email-settings.md#email-type)

   >[!CAUTION]
   >
   >Du måste välja samma yta som den som valts i kampanjen som du vill associera med din IP-värmerappsplan. [Lär dig hur du skapar en IP-värmerskampanj](ip-warmup-campaign.md)

1. Överför den Excel-fil som innehåller din IP-värmeringsplan. [Läs mer](#prepare-file)

   <!--
    You can also download the Excel template from the [!DNL Journey Optimizer] user interface and upload it after filling it with the IP warmup details.-->

   ![](assets/ip-warmup-upload-success.png)

1. Klicka på **[!UICONTROL Create]**. Alla faser, körningar, kolumner och deras innehåll som definieras i den överförda filen visas automatiskt i [!DNL Journey Optimizer] gränssnitt. [Läs mer](ip-warmup-execution.md)

   ![](assets/ip-warmup-plan-uploaded.png)
