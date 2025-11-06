---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera kanalkonfigurationer
description: Lär dig konfigurera och övervaka kanalkonfigurationer
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: kanal, yta, teknik, parametrar, optimerare
exl-id: 9038528f-3da0-4e0e-9b82-b72c67b42391
source-git-commit: 722d37dc4bcb9ab7983ea336aa0b12a6a09e01dc
workflow-type: tm+mt
source-wordcount: '1739'
ht-degree: 0%

---

# Konfigurera kanalkonfigurationer {#set-up-channel-surfaces}

>[!CONTEXTUALHELP]
>id="ajo_admin_channel_surfaces"
>title="Kanalkonfiguration"
>abstract="En kanalkonfiguration är en konfiguration som har definierats av en systemadministratör. Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv."

>[!CONTEXTUALHELP]
>id="ajo_admin_marketing_action"
>title="Marknadsföringsåtgärd"
>abstract="Välj marknadsföringsåtgärderna för att länka medgivandeprinciper till meddelandena med den här inställningen. Alla profiler för samtycke som är kopplade till marknadsföringsåtgärden används för att uppfylla dina kunders önskemål."

Med [!DNL Journey Optimizer] kan du konfigurera kanalkonfigurationer (t.ex. meddelandeförinställningar) som definierar alla tekniska parametrar som krävs för dina meddelanden: e-posttyp, avsändarens e-postadress och namn, mobilappar, SMS-konfiguration med mera.

>[!CAUTION]
>
> * Om du vill skapa, redigera och ta bort kanalkonfigurationer måste du ha behörigheten [Hantera meddelandeförinställningar](../administration/high-low-permissions.md#administration-permissions) .
>
> * Du måste utföra stegen [E-postkonfiguration](../email/get-started-email-config.md), [push-konfiguration](../push/push-configuration.md), [SMS-konfiguration](../sms/sms-configuration.md), [konfiguration i programmet](../in-app/inapp-configuration.md), [kodbaserad konfiguration](../code-based/code-based-configuration.md), [Webbkonfiguration](../web/web-configuration.md) och [Direkt e-postkonfiguration](../direct-mail/direct-mail-configuration.md) innan du skapar kanalkonfigurationer.

När kanalkonfigurationer har konfigurerats kan du välja dem när du skapar meddelanden från en resa eller en kampanj.

Du kan också använda konfigurationen av den guidade kanalen för att automatisera och validera kanalkonfigurationen i en enhetlig upplevelse, vilket snabbar upp processen att komma igång med Journey Optimizer. [Läs mer](set-mobile-config.md)

<!--
➡️ [Learn how to create and use email configurations in this video](#video-presets)
-->

## Skapa en kanalkonfiguration {#create-channel-surface}

>[!CONTEXTUALHELP]
>id="ajo_admin_message_presets_header"
>title="Kanalkonfigurationsinställningar"
>abstract="När du konfigurerar en kanalkonfiguration väljer du den kanal som den gäller för och definierar alla tekniska parametrar som krävs för din sändning, till exempel e-posttyp, avsändarnamn, mobilappar, SMS-konfiguration och mycket mer."

>[!CONTEXTUALHELP]
>id="ajo_admin_message_presets"
>title="Kanalkonfigurationsinställningar"
>abstract="För att kunna skapa åtgärder som e-post från en resa eller en kampanj måste du först skapa en kanalkonfiguration som definierar alla tekniska inställningar som krävs för dina meddelanden. Du måste ha behörighet att hantera meddelandeförinställningar för att kunna skapa, redigera och ta bort kanalkonfigurationer."

>[!CONTEXTUALHELP]
>id="ajo_surface_marketing_action"
>title="Välj en marknadsföringsåtgärd"
>abstract="Välj en marknadsföringsåtgärd i konfigurationen för att koppla en medgivandeprincip till meddelandet."

Så här skapar du en kanalkonfiguration:

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]** och klicka sedan på **[!UICONTROL Create channel configuration]**.

   ![](assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen och välj sedan den kanal som ska konfigureras.

   ![](assets/preset-general.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela anpassade eller grundläggande dataanvändningsetiketter till konfigurationen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Välj kanal.

1. Välj **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper till meddelanden som använder den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

   >[!NOTE]
   >
   >Samtyckespolicyer är för närvarande bara tillgängliga för organisationer som har köpt tilläggen **Healthcare Shield** och **Privacy and Security Shield**.

   ![](assets/surface-marketing-action.png)

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalkonfigurationen som utkast och återuppta konfigurationen senare.

   ![](assets/preset-submit.png)

   >[!NOTE]
   >
   >Du kan inte fortsätta med att skapa e-postkonfigurationer medan den valda IP-poolen är under [utgåva](ip-pools.md#edit-ip-pool) (**[!UICONTROL Processing]** status) och har aldrig associerats med den valda underdomänen. [Läs mer](#subdomains-and-ip-pools)
   >
   >Spara konfigurationen som utkast och vänta tills IP-poolen har statusen **[!UICONTROL Success]** för att återuppta konfigurationsskapandet.

1. När kanalkonfigurationen har skapats visas den i listan med statusen **[!UICONTROL Processing]**.

   Under det här steget kommer flera kontroller att utföras för att verifiera att den har konfigurerats korrekt. <!--The processing time is around **48h-72h**, and can take up to **7-10 business days**.-->

   >[!NOTE]
   > När du skapar en e-postkonfiguration för en underdomän varierar bearbetningstiden enligt följande:
   >
   > * För **nya underdomäner** kan processen för att skapa den första kanalkonfigurationen ta **10 minuter till 10 dagar**.
   > * För **icke-produktionssandlådor**, eller om den valda underdomänen **redan används** i en annan godkänd kanalkonfiguration, tar processen bara upp till **3 timmar**.


   Dessa kontroller omfattar konfigurations- och tekniska tester som utförs av Adobe-teamet:

   * SPF-validering
   * DKIM-validering
   * MX-postvalidering
   * Kontrollera IP-adresser som blocklist
   * Kontroll av värddator
   * Verifiering av IP-pool
   * A/PTR-post, t/m/res-underdomänverifiering
   * FBL-registrering (den här kontrollen utförs endast första gången en e-postkonfiguration skapas för en viss underdomän)

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om möjliga felorsaker i [det här avsnittet](#monitor-channel-surfaces).

1. När kontrollerna har slutförts får kanalkonfigurationen statusen **[!UICONTROL Active]**. Den är klar att användas för att leverera meddelanden.

   ![](assets/preset-active.png)

## Konfiguration av monitorkanal {#monitor-channel-surfaces}

Alla kanalkonfigurationer visas på menyn **[!UICONTROL Channels]** > **[!UICONTROL Channel configurations]**. Det finns filter som hjälper dig att bläddra igenom listan (kanal, användare, status).

![](assets/preset-filters.png)

När kanalkonfigurationerna har skapats kan de ha följande status:

* **[!UICONTROL Draft]**: Kanalkonfigurationen har sparats som ett utkast och har inte skickats ännu. Öppna den för att återuppta konfigurationen.
* **[!UICONTROL Processing]**: Kanalkonfigurationen har skickats och genomgår flera verifieringssteg.
* **[!UICONTROL Active]**: Kanalkonfigurationen har verifierats och kan väljas för att skapa meddelanden.
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under verifieringen av kanalkonfigurationen.
* **[!UICONTROL Deactivated]**: Kanalkonfigurationen har inaktiverats. Det kan inte användas för att skapa nya meddelanden.

### Orsaker till misslyckad kanalkonfiguration {#channel-config-failure}

Om det inte går att skapa en kanalkonfiguration beskrivs informationen om varje möjlig felorsak nedan.

Kontakta [Adobe kundtjänst](https://helpx.adobe.com/se/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"} om något av dessa fel inträffar.

* **SPF-validering misslyckades**: SPF (Sender Policy Framework) är ett autentiseringsprotokoll för e-post som tillåter att auktoriserade IP-adresser kan skicka e-post från en angiven underdomän. SPF-valideringsfel innebär att IP-adresserna i SPF-posten inte matchar IP-adresserna som används för att skicka e-post till postlådeprovidern.

* **DKIM-validering misslyckades**: Med DKIM (DomainKeys Identified Mail) kan mottagarservern verifiera att det mottagna meddelandet skickades av den äkta avsändaren av den associerade domänen och att innehållet i det ursprungliga meddelandet inte ändrades på väg. DKIM-valideringsfel innebär att de mottagande e-postservrarna inte kan verifiera meddelandeinnehållets autenticitet och dess koppling till den sändande domänen:

* **MX-postvalidering misslyckades**: MX-postvalideringsfel (eXchange) innebär att de e-postservrar som ansvarar för att ta emot inkommande e-post för en viss underdomän inte är korrekt konfigurerade.

* **Leveranskonfigurationer misslyckades**: Fel i leveranskonfigurationer kan inträffa på grund av någon av följande orsaker:
   * Blockeringslistning av tilldelade IP-adresser
   * Ogiltigt `helo`-namn
   * E-postmeddelanden som skickas från andra IP-adresser än de som anges i IP-poolen för motsvarande konfiguration
   * Det går inte att leverera e-postmeddelanden till inkorg hos viktiga Internet-leverantörer

## Redigera en kanalkonfiguration {#edit-channel-surface}

Om du vill redigera en kanalkonfiguration följer du stegen nedan.

>[!NOTE]
>
>Du kan inte redigera **[!UICONTROL Push notification settings]**. Om en kanalkonfiguration bara är konfigurerad för push-meddelandekanalen går det inte att redigera den.

1. Klicka på ett kanalkonfigurationsnamn i listan för att öppna den.

   ![](assets/preset-name.png)

1. Redigera egenskaperna efter behov.

   >[!NOTE]
   >
   >Om en kanalkonfiguration har statusen **[!UICONTROL Active]** är fälten **[!UICONTROL Name]**, **[!UICONTROL Select channel]** och **[!UICONTROL Subdomain]** nedtonade och kan inte redigeras.

1. Klicka på **[!UICONTROL Submit]** för att bekräfta ändringarna.

   >[!NOTE]
   >
   >Du kan också spara kanalkonfigurationen som utkast och återuppta uppdateringen senare.

När ändringarna har skickats går kanalkonfigurationen igenom en valideringscykel som liknar den som fanns när [en kanalkonfiguration &#x200B;](#create-channel-surface) skapades. Versionens bearbetningstid kan ta upp till **3 timmar**.

>[!NOTE]
>
>Om du bara redigerar fälten **[!UICONTROL Description]**, **[!UICONTROL Email type]** och/eller **[!UICONTROL Email retry parameters]** uppdateras uppdateringen omedelbart.

### Uppdatera information {#update-details}

För kanalkonfigurationer som har statusen **[!UICONTROL Active]** kan du kontrollera informationen om uppdateringen. För att göra detta:

Klicka på ikonen **[!UICONTROL Recent update]** som visas bredvid det aktiva konfigurationsnamnet.

![](assets/preset-recent-update-icon.png)

<!--You can also access the update details from an active channel configuration while update is in progress.-->

På skärmen **[!UICONTROL Recent update]** kan du se information som uppdateringsstatus och listan över begärda ändringar.

<!--![](assets/preset-recent-update-screen.png)-->

### Uppdatera status {#update-statuses}

En kanalkonfigurationsuppdatering kan ha följande status:

* **[!UICONTROL Processing]**: Kanalkonfigurationsuppdateringen har skickats och genomgår flera verifieringssteg.
* **[!UICONTROL Success]**: Den uppdaterade kanalkonfigurationen har verifierats och kan väljas för att skapa meddelanden.
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under verifieringen av kanalkonfigurationsuppdateringen.

Varje status visas nedan.

#### Bearbetar {#surface-processing}

Flera leveranskontroller kommer att utföras för att verifiera att konfigurationen har uppdaterats korrekt.

>[!NOTE]
>
>Om du bara redigerar fälten **[!UICONTROL Description]**, **[!UICONTROL Email type]** och/eller **[!UICONTROL Email retry parameters]** uppdateras uppdateringen omedelbart.

Bearbetningstiden kan ta upp till **3 timmar**. Läs mer om de kontroller som har utförts under valideringscykeln i [det här avsnittet](#create-channel-surface).

Om du redigerar en konfiguration som redan var aktiv:

* Dess status är fortfarande **[!UICONTROL Active]** medan verifieringsprocessen pågår.

* Ikonen **[!UICONTROL Recent update]** visas bredvid namnet på konfigurationen i kanalkonfigurationslistan.

* Under valideringsprocessen används fortfarande den äldre versionen av konfigurationen för meddelanden som konfigurerats med den här konfigurationen.

>[!NOTE]
>
>Du kan inte ändra en kanalkonfiguration medan uppdateringen pågår. Du kan fortfarande klicka på namnet, men alla fält är nedtonade. Ändringarna visas inte förrän uppdateringen har slutförts.

#### Lyckades {#success}

När valideringsprocessen har slutförts används den nya versionen av konfigurationen automatiskt i alla meddelanden som använder den här konfigurationen. Du kan dock behöva vänta:

* några minuter innan det konsumeras av enhetsmeddelanden,
* till nästa batch för att konfigurationen ska vara effektiv i batchmeddelanden.

#### Misslyckades {#failed}

Om valideringsprocessen misslyckas kommer den äldre versionen av konfigurationen fortfarande att användas.

Läs mer om möjliga felorsaker i [det här avsnittet](#monitor-channel-surfaces).

När uppdateringen misslyckas kan konfigurationen redigeras igen. Du kan klicka på dess namn och uppdatera inställningarna som behöver korrigeras.

## Inaktivera en kanalkonfiguration {#deactivate-a-surface}

Om du vill göra en **[!UICONTROL Active]**-kanalkonfiguration otillgänglig för att skapa nya meddelanden kan du inaktivera den. Resebudskap som för närvarande använder den här konfigurationen kommer dock inte att påverkas och kommer att fortsätta fungera.

>[!NOTE]
>
>Du kan inte inaktivera en kanalkonfiguration medan en uppdatering bearbetas. Du måste vänta tills uppdateringen har slutförts eller misslyckats. Läs mer om [redigering av kanalkonfigurationer](#edit-channel-surface) och om [uppdateringsstatus](#update-statuses).

1. Öppna listan Kanalkonfigurationer.

1. Klicka på knappen **[!UICONTROL More actions]** om du vill se den aktiva konfigurationen.

1. Välj **[!UICONTROL Deactivate]**.

   ![](assets/preset-deactivate.png)

>[!NOTE]
>
>Det går inte att ta bort inaktiverade kanalkonfigurationer för att undvika problem under resor som använder dessa konfigurationer för att skicka meddelanden.

Du kan inte redigera en inaktiverad kanalkonfiguration direkt. Du kan dock duplicera den och redigera kopian för att skapa en ny version som du använder för att skapa nya meddelanden. Du kan även aktivera den igen och vänta tills uppdateringen har redigerats.

![](assets/preset-activate.png)

## Lägga till taggar i en kanalkonfiguration {#channel-config-tags}

1. Öppna listan Kanalkonfigurationer.

1. Klicka på knappen **[!UICONTROL More actions]** om du vill se den aktiva konfigurationen.

1. Klicka på **[!UICONTROL Edit Tags]**.

1. Välj Adobe Experience Platform-taggar i listan för att kategorisera kanalkonfigurationen för bättre sökning. [Lär dig arbeta med enhetliga taggar](../start/search-filter-categorize.md#tags)

   ![](assets/config-edit-tags.png)

1. När du har tilldelat taggar till kanalkonfigurationerna kan du [filtrera](../start/search-filter-categorize.md#filter-on-tags) dem på taggar.

## Instruktionsvideo{#video-presets}

Lär dig vilka kanalkonfigurationer som är och hur de används i Adobe Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/3433124/?learn=on)
