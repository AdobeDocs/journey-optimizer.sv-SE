---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en IP-värmeringsplan
description: Lär dig hur du skapar en IP-värmeringsplan
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP, pooler, grupp, underdomäner, leveransbarhet
hide: true
hidefromtoc: true
source-git-commit: 1ec2c406e777e08de97c3ad53cee5986afeb3c44
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 1%

---

# Skapa en IP-värmeringsplan {#ip-warmup}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med IP-värmare](ip-warmup-gs.md)
* [Skapa IP-värmningskampanjer](ip-warmup-campaign.md)
* **[Skapa en IP-värmeringsplan](ip-warmup-plan.md)**
* [Kör IP-värmningsplanen](ip-warmup-running.md)

>[!ENDSHADEBOX]

När du har skapat en eller flera [IP-kampanjer](ip-warmup-campaign.md) med en dedikerad yta och motsvarande alternativ aktiverat, kan du börja skapa din IP-värdplan.

## Fyll i IP-värmermallen {#upload-plan}

Innan du kan skapa en IP-uppvärmningsplan i Journey Optimizer-gränssnittet måste du fylla i en mall i Excel-format med alla data som matar in planen.

>[!CAUTION]
>
>Arbeta med din leveranskonsult för att säkerställa att din IP-värmerappningsfil är korrekt konfigurerad.

Nedan visas ett exempel på en fil som innehåller en IP-värmerapport.

![](assets/ip-warmup-sample-file.png)

### Fliken IP Warmup Plan

Varmning av IP-adresser är en aktivitet som gradvis ökar antalet e-postmeddelanden som går ut från era IP-adresser och domäner till de viktigaste Internetleverantörerna för att etablera ert rykte som en legitim avsändare.

Denna aktivitet utförs i rätt tid med hjälp av en konsult eller expert som arbetar med en genomtänkt plan baserad på bransch, användningsfall, region, Internet-leverantörer och olika andra faktorer.

* I det här exemplet har en plan förberetts för att sträcka sig över 17 dagar och nå en målvolym på xxx-profiler.

* Detta är planerat för 6 faser.

* Du kan ha så många kolumner du vill för de domäner du vill leverera till. I det här exemplet är planen uppdelad i fyra kolumner som motsvarar de domängrupper som ska användas i din plan: Gmail, Adobe, Yahoo med flera.

Tanken är att fler ska köras under de första faserna och att antalet riktade adresser ska ökas stegvis samtidigt som antalet ska minskas.

Listan med färdiga domäner är följande:

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

Du kan också lägga till fler kolumner med dina anpassade domängrupper.

Använd **[!UICONTROL Custom Domain Group]** för att definiera en ny domän och för varje domän kan du lägga till alla underdomäner som den omfattar.<!--TBC-->

## Få åtkomst till och hantera IP-värmerelayouter {#manage-ip-warmup-plans}

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP warmup plans]**-menyn. Alla IP-uppvärmningsplaner som har skapats hittills visas.

   ![](assets/ip-warmup-filter-list.png)

1. Du kan filtrera efter status. De olika statusvärdena är:

   * **Inte startat**: ingen körning har aktiverats ännu. [Läs mer](ip-warmup-running.md#define-runs)
   * **Pågår/Live**: planen får denna status så snart den första körningen i den första fasen har aktiverats. [Läs mer](ip-warmup-running.md#define-runs)
   * **Slutförd**: planen har markerats som slutförd. Det här alternativet är bara tillgängligt om alla körningar i planen finns **[!UICONTROL Succeeded]** eller **[!UICONTROL Draft]** status (ingen körning kan utföras) **[!UICONTROL Live]**). [Läs mer](ip-warmup-running.md#define-runs#mark-as-completed)
   * **Pausad**<!--: to check (user action)-->

1. Om du vill ta bort en IP-uppvärmningsplan väljer du **[!UICONTROL Delete]** -ikonen bredvid ett listobjekt och bekräfta borttagningen.

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

## Ladda upp en IP-värdplan igen {#re-upload-plan}

Du kan överföra ytterligare en IP-värmeringsplan med motsvarande knapp.

![](assets/ip-warmup-re-upload-plan.png)

>[!NOTE]
>
>Information om IP-värmeringsplanen ändras enligt den nyligen överförda filen. Hela körningen och de aktiverade körningarna påverkas inte.