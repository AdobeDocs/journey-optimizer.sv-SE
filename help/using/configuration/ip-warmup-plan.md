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
badge: label="Beta"
exl-id: c2434086-2ed4-4cd0-aecd-2eea8f0a55f6
source-git-commit: 737b7f59819d235b1f637d4a6b996e97cfddb9fe
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 0%

---

# Skapa en IP-värmeringsplan {#ip-warmup}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med planer för IP-värmare](ip-warmup-gs.md)
* [Skapa IP-värmningskampanjer](ip-warmup-campaign.md)
* **[Skapa en IP-värmeringsplan](ip-warmup-plan.md)**
* [Kör IP-värmerappen](ip-warmup-execution.md)

>[!ENDSHADEBOX]

När du har skapat en eller flera [IP-kampanjer](ip-warmup-campaign.md) med en dedikerad yta och motsvarande alternativ aktiverat, kan du börja skapa din IP-värdplan.

Om du vill komma åt, skapa, redigera och ta bort IP-beredskapsplanerna måste du ha **[!UICONTROL Deliverability Consultant]** roller eller IP-värmeringsplanerrelaterade behörigheter.

+++Lär dig hur du tilldelar rollen Deliverability Consultant eller IP Warmup-planerrelaterade behörigheter

Så här tilldelar du motsvarande behörighet till en viss **[!UICONTROL Role]**:

1. Från [!DNL Permissions] -produkt, navigera till **[!UICONTROL Roles]** och välj den roll som du vill uppdatera med den nya **[!UICONTROL IP Warmup Configurations]** behörigheter.

1. Från **[!UICONTROL Role]** kontrollpanel, klicka **[!UICONTROL Edit]**.

   ![](assets/ip_permissions_1.png)

1. Dra och släpp **[!UICONTROL IP Warmup Configurations]** resurs för att tilldela behörighet.

1. Från **[!UICONTROL IP Warmup Configurations]** i den nedrullningsbara menyn väljer du vilka behörigheter användaren behöver.

   ![](assets/ip_permissions_2.png)

1. Klicka på **[!UICONTROL Save]**.

Tilldela motsvarande roll till en **[!UICONTROL User]**:

1. Från [!DNL Permissions] -produkt, navigera till **[!UICONTROL Roles]** och väljer **[!UICONTROL Deliverability Consultant]** inbyggd roll.

1. Från **[!UICONTROL Role]** kontrollpanel, gå till **[!UICONTROL Users]** -fliken.

   ![](assets/ip_permissions_3.png)

1. Klicka **[!UICONTROL Add user]** för att tilldela **[!UICONTROL Deliverability Consultant]** inbyggd roll.

   ![](assets/ip_permissions_4.png)

1. Välj **[!UICONTROL User]** och klicka **[!UICONTROL Save]**.

   ![](assets/ip_permissions_5.png)

+++

## Förbered filen för IP-warmup-planen {#prepare-file}

Varmning av IP-adresser är en aktivitet som gradvis ökar antalet e-postmeddelanden som går ut från era IP-adresser och domäner till de viktigaste Internetleverantörerna för att etablera ert rykte som en legitim avsändare.

Denna aktivitet utförs i rätt tid med hjälp av en leveransexpert som hjälper till att ta fram en genomtänkt plan baserad på branschens domäner, användningsfall, regioner, Internet-leverantörer och olika andra faktorer.

<!--When working with the [!DNL Journey Optimizer] IP warmup feature, this plan takes the form of an Excel file that must contain a number of predefined columns.-->

Innan du kan skapa en IP-uppvärmningsplan i [!DNL Journey Optimizer] måste du fylla i en Excel-mall med alla data som matar in planen.

* I användargränssnittet kan du hämta den tomma Excel:n [Prenumerationsplanmall för IP-värmare](assets/IPWarmupPlan-Template.xlsx) fylla i.

* Du kan även hämta en [exempelplan för IP-värmare](assets/IPWarmupPlan-Sample.xlsx) som redan har fyllts i med data som du kan använda som exempel.

<!--
* From the user interface you can download the blank Excel IP warmup plan template to fill in.

* You can also download a sample IP warmup plan already filled in with some data you can use as an example.
-->

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

* I det här exemplet har en plan förberetts som sträcker sig över 17 dagar (kallas&quot;**körningar**&#39;) för att nå en målvolym på över en miljon profiler.

* Detta planerade arbete pågår till sex **faser**, som alla innehåller minst en omgång.

* Du kan ha så många kolumner du vill för de domäner du vill leverera till. I det här exemplet är planen uppdelad i sex kolumner:

   * Fyra av dessa motsvarar **färdiga domängrupper** som du kan använda i din plan (Gmail, Microsoft, Yahoo och Orange).
   * Den ena motsvarar en anpassad domängrupp (som du måste lägga till med [Anpassad domängrupp](#custom-domain-group-tab) -fliken).
   * Den sjätte kolumnen, **Övriga**, innehåller alla återstående adresser från andra domäner som inte uttryckligen omfattas av planen. Den här kolumnen är valfri: om den utelämnas kommer e-post endast att skickas till de angivna domänerna.
* The **Förlovningsdagar** kolumn visar att det endast är profilerna som interagerar med ert varumärke under den senaste angivna perioden som är målinriktade.

Tanken är att stegvis öka antalet måladresser i varje körning och samtidigt minska antalet körningar för varje fas.

De färdiga huvuddomängrupperna som du kan lägga till i din plan visas nedan:

<!--
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
-->

+++ Gmail gmail.com;google.com;googlemail.com;googlemail.co.uk
+++

+++WP wp.pl;o2.pl
+++

+++Comcast comcast.net
+++

+++Yahoo aol.fi;games.com;cs.com;yahoo.com.in;y7mail.com;yahoo.co.uk;yahoo.hu;yahoo.co.hu;yahoo.cn;yahoogroups.com.sg;yahoogroups.com.au;aol.es;yahoo.com.au;yahoo.com.vn;yahoo.ca;aol.hk;dina aktiviteter;åolpoland.pl;aolnorge.no;din tur;yahoo.fi;dina;öppningar;öppningar;ååååååååååååååååååååååååå;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;er;yahoo.hr;aol.cz;yahoo.ee;aol.be;aolcom.tr;yahoo.si;din tur;aol.it;din tur;yahoo.es;yahoo.dk;yahoogroups.ca;din tur;aol.kr;yahoo.ie;aol.jp;din hoo.lt;din tur;aol.nl;din tur;yahoo.bg;din tur;din tur;aol.se;din tur;yahoo.de;din tur;din tur;yahoo.nl;din tur;aol.dk;din tur;åhoo.cz;din;din o.sk;inrapportering;yahoogroups.de;yahoo.gr;inrapportering;inrapportering;yahoo.ro;inrapportering;yahoo.at;inrapportering;inrapportering;aol.fr;yahoo.in;aol.in;din inrapportering;yahoo.rs;aol.de;din indelning;inrapportering;inrapportering;yahoo.se;myaol.jp;åååå.pt;ååååå;ååååå;ååååå.dk;yahoo.fr;åååå;ååååå;åååååå;åååååå;ååååå;ååååå;åååååå;åååååå.cl;ååååååååååååå;ååååååååååååååååååååååååå;åå;åååååååååååååååååå;åå;ååååååååååå;åååååååååååååååå;åå;ååååå100;inrapportering;inrapportering;yahoo.be;inrapportering;aol.tw;inrapportering;inrapportering;inrapportering;inrapportering;inrapportering;inrapportering;aol.ru;inrapportering;inrapportering;yahoo.lv;aolpolska.pl;aol.at;yahoo.pl
+++

+++Bigpond bigpond.com;bigpond.com.au;bigpond.net;telstra.com;bigpond.net.au
+++

+++Orange voila.com;francetelecom.com;orange.com;orange.fr;wanadoo.fr;voila.fr
+++

+++Softbank c.vodafone.ne.jp;jp-h.ne.jp;k.vodafone.ne.jp;;jp-d.ne.jp;jp-c.ne.jp;t.vodafone.ne.jp;h.vodafone.ne.jp;r.vodafone.ne.jp;q.vodafone.ne.jp;jp-t.ne.jp;bud;bud;bud;bud;kontrakt;kontrakt;bud;kontrakt;kontrakt;kontrakt
+++

+++Docomo docomo.ne.jp
+++

+++United Internet gmx.de;1and1.com;gmx.fr;mail.com;1und1.de;gmx.com;gmx.net;gmx.at;web.de;gmx.ch
+++

+++Microsoft hotmail.com.tr;live.de;live.ru;live.nl;windowslive.com;live.jp;mts.net;xbox.com;hotmail.fr;hotmail.cl;hotmail.jp;live.cl;live.at;live.com.au;live.hk;hotmail.com.au;hotmail.co.th;hotmail.com;hotmail.co.kr;live.ie;dina tjänster;hotmail.dk;dina aktiviteter;din;din;utlook;utlook.ie;ie;ie;ie;ie;ie;klart.ie.ie;ie;klart;klart;in;in;in;se.se.se;in;in;in;in;in;live.se;live;live.se;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live;live livd.cn;priser;hotmail.es;live.fr;live.no;live.dk;hotmail.it;din tur;livd.se;livd.be;din livesändning;livesändning;livesändning;hotmail.ch;din tur;din tur;hotmail.gr;livesändning;hotmail.ca;din;livesändning;hotmail.de.de
+++

+++KDDI au.com;ezweb.ne.jp;uqmobile.jp
+++

+++Italia Online inwind.it;blu.it;virgilio.it;giallo.it;iol.it;libero.it
+++

+++La Poste laposte.net
+++

+++Apple mac.com;icloud.com;apple.com;me.com
+++

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

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP warmup plans]** -menyn. Alla IP-uppvärmningsplaner som har skapats hittills visas.

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
>abstract="Fyll i Excel-mallen med alla data som kommer att mata din plan, som IP-värmersfaser och målantal profiler, och överför den här."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/implement-ip-warmup-plan/ip-warmup-plan.html#prepare-file" text="Förbered filen för IP-warmup-planen"

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
   >Om överföringen misslyckas bör du kontrollera att du använder rätt format (.xls eller .xlsx). Använd [mall](assets/IPWarmupPlan-Template.xlsx) som tillhandahålls av Adobe.

1. Klicka på **[!UICONTROL Create]**. Alla faser, körningar, kolumner och deras innehåll som definieras i den överförda filen visas automatiskt i [!DNL Journey Optimizer] gränssnitt.

   ![](assets/ip-warmup-plan-uploaded.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Targeted]** kolumn visar summan av alla profiler som är avsedda för varje körning, vilket betyder alla profiler från varje domängrupp som du har definierat, inklusive **Övriga** kolumn om sådan finns.

Du är nu redo att genomföra din IP-värmeringsplan. [Läs mer](ip-warmup-execution.md)
