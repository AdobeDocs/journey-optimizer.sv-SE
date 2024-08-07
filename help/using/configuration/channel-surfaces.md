---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera kanalytor
description: Lär dig konfigurera och övervaka kanalytor
feature: Surface, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: kanal, yta, teknik, parametrar, optimerare
exl-id: 9038528f-3da0-4e0e-9b82-b72c67b42391
source-git-commit: 9af49f0a47ad5bc1d2cea3e822ec20e2930140d3
workflow-type: tm+mt
source-wordcount: '1694'
ht-degree: 0%

---

# Konfigurera kanalytor {#set-up-channel-surfaces}

>[!CONTEXTUALHELP]
>id="ajo_admin_channel_surfaces"
>title="Kanalyta"
>abstract="En kanalyta är en konfiguration som har definierats av en systemadministratör. Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv."

>[!CONTEXTUALHELP]
>id="ajo_admin_marketing_action"
>title="Marknadsföringsåtgärd"
>abstract="TBC"

>[!CONTEXTUALHELP]
>id="ajo_admin_app_id"
>title="Program-ID"
>abstract="TBC"

>[!CONTEXTUALHELP]
>id="ajo_admin_location"
>title="Plats på sida"
>abstract="TBC"

>[!CONTEXTUALHELP]
>id="ajo_admin_page_rule"
>title="Matchningsregel för sidor"
>abstract="TBC"

>[!CONTEXTUALHELP]
>id="ajo_admin_default_url"
>title="Standard-URL"
>abstract="TBC"

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_uri"
>title="Surface URI"
>abstract="TBC"

Med [!DNL Journey Optimizer] kan du konfigurera kanalytor (t.ex. meddelandeförinställningar) som definierar alla tekniska parametrar som krävs för dina meddelanden: e-posttyp, avsändarens e-postadress och namn, mobilappar, SMS-konfiguration med mera.

>[!CAUTION]
>
> * Om du vill skapa, redigera och ta bort kanalytor måste du ha behörigheten [Hantera meddelandeförinställningar](../administration/high-low-permissions.md#administration-permissions) .
>
> * Du måste utföra stegen för [e-postkonfigurationen](../email/get-started-email-config.md), [push-konfigurationen](../push/push-configuration.md), [SMS-konfigurationen](../sms/sms-configuration.md) och [Direct mail configuration](../direct-mail/direct-mail-configuration.md) innan du skapar kanalytor.

När kanalytorna har konfigurerats kan du välja dem när du skapar meddelanden från en resa eller en kampanj.

<!--
➡️ [Learn how to create and use email surfaces in this video](#video-presets)
-->

## Skapa en kanalyta {#create-channel-surface}

>[!CONTEXTUALHELP]
>id="ajo_admin_message_presets_header"
>title="Kanalytans inställningar"
>abstract="När du konfigurerar en kanalyta väljer du den kanal som den ska användas på och definierar alla tekniska parametrar som krävs för din sändning, till exempel e-posttyp, avsändarnamn, mobilappar, SMS-konfiguration med mera."

>[!CONTEXTUALHELP]
>id="ajo_admin_message_presets"
>title="Kanalytans inställningar"
>abstract="För att kunna skapa åtgärder som e-post från en resa eller en kampanj måste du först skapa en kanalyta som definierar alla tekniska inställningar som krävs för dina meddelanden. Du måste ha behörighet att hantera meddelandeförinställningar för att skapa, redigera och ta bort kanalytor."

>[!CONTEXTUALHELP]
>id="ajo_surface_marketing_action"
>title="Välj en marknadsföringsåtgärd"
>abstract="Välj en marknadsföringsåtgärd i fältet för att koppla en medgivandepolicy till meddelandet."

Så här skapar du en kanalyta:

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL Branding]** > **[!UICONTROL Channel surfaces]** och klicka sedan på **[!UICONTROL Create channel surface]**.

   ![](assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för ytan och välj sedan de kanaler som ska konfigureras.

   ![](assets/preset-general.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela etiketter för anpassad eller viktig dataanvändning till ytan kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Om du valde **[!UICONTROL Email]**-kanalen konfigurerar du inställningarna enligt beskrivningen i [det här avsnittet](../email/email-settings.md).

   ![](assets/preset-email.png)

1. För **[!UICONTROL Push Notification]**-kanalen väljer du minst en plattform - **iOS** och/eller **Android** - och de mobilprogram som ska användas för varje plattform.

   ![](assets/preset-push.png)

   >[!NOTE]
   >
   >Mer information om hur du konfigurerar miljön för att skicka push-meddelanden finns i [det här avsnittet](../push/push-gs.md).

1. För **[!UICONTROL SMS]**-kanalen definierar du dina inställningar så som beskrivs i [det här avsnittet](../sms/sms-configuration.md).

   ![](assets/preset-sms.png)

   >[!NOTE]
   >
   >Mer information om hur du konfigurerar miljön för att skicka SMS-meddelanden finns i [det här avsnittet](../sms/sms-configuration.md).

1. Välj en **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper med de meddelanden som använder den här ytan. Alla policyer för samtycke som är kopplade till den marknadsföringsåtgärden utnyttjas för att ta hänsyn till era kunders preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

   >[!NOTE]
   >
   >Samtyckespolicyer är för närvarande bara tillgängliga för organisationer som har köpt tilläggen **Healthcare Shield** och **Privacy and Security Shield**.

   ![](assets/surface-marketing-action.png)

   >[!NOTE]
   >
   >Du kan bara välja en marknadsföringsåtgärd.

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalytan som ett utkast och återuppta konfigurationen senare.

   ![](assets/preset-submit.png)

   >[!NOTE]
   >
   >Du kan inte fortsätta med att skapa e-postyta medan den valda IP-poolen är under [utgåva](ip-pools.md#edit-ip-pool) (**[!UICONTROL Processing]** status) och har aldrig associerats med den valda underdomänen. [Läs mer](#subdomains-and-ip-pools)
   >
   >Spara ytan som utkast och vänta tills IP-poolen har statusen **[!UICONTROL Success]** för att återuppta skapandet av ytan.

1. När kanalytan har skapats visas den i listan med statusen **[!UICONTROL Processing]**.

   Under det här steget kommer flera kontroller att utföras för att verifiera att den har konfigurerats korrekt. <!--The processing time is around **48h-72h**, and can take up to **7-10 business days**.-->

   >[!NOTE]
   > När du skapar en e-postyta för en underdomän varierar bearbetningstiden enligt följande:
   >
   > * För **nya underdomäner** kan processen för att skapa den första kanalytan ta **10 minuter till 10 dagar**.
   > * För **icke-produktionssandlådor**, eller om den valda underdomänen **redan används** i en annan godkänd kanalyta, tar processen bara upp till **3 timmar**.


   Dessa kontroller omfattar konfigurations- och tekniska tester som utförs av Adobe-teamet:

   * SPF-validering
   * DKIM-validering
   * MX-postvalidering
   * Kontrollera IP-adresser som blocklist
   * Kontroll av värddator
   * Verifiering av IP-pool
   * A/PTR-post, t/m/res-underdomänverifiering
   * FBL-registrering (den här kontrollen utförs endast första gången en e-postyta skapas för en viss underdomän)

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om möjliga felorsaker i [det här avsnittet](#monitor-channel-surfaces).

1. När kontrollerna har slutförts får kanalytan statusen **[!UICONTROL Active]**. Den är klar att användas för att leverera meddelanden.

   ![](assets/preset-active.png)

## Skärmkanalsytor {#monitor-channel-surfaces}

Alla dina kanalytor visas på menyn **[!UICONTROL Channels]** > **[!UICONTROL Channel surfaces]**. Det finns filter som hjälper dig att bläddra igenom listan (kanal, användare, status).

![](assets/preset-filters.png)

När kanalytorna har skapats kan de ha följande status:

* **[!UICONTROL Draft]**: Kanalytan har sparats som ett utkast och har inte skickats ännu. Öppna den för att återuppta konfigurationen.
* **[!UICONTROL Processing]**: Kanalytan har skickats och genomgår flera verifieringssteg.
* **[!UICONTROL Active]**: Kanalytan har verifierats och kan väljas för att skapa meddelanden.
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under verifieringen av kanalens yta.
* **[!UICONTROL Deactivated]**: Kanalytan är inaktiverad. Det kan inte användas för att skapa nya meddelanden.

Om det inte går att skapa en kanalyta beskrivs detaljerna för varje möjlig felorsak nedan.

Kontakta [Adobe kundtjänst](https://helpx.adobe.com/se/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"} om något av dessa fel inträffar.

* **SPF-validering misslyckades**: SPF (Sender Policy Framework) är ett autentiseringsprotokoll för e-post som tillåter att auktoriserade IP-adresser kan skicka e-post från en angiven underdomän. SPF-valideringsfel innebär att IP-adresserna i SPF-posten inte matchar IP-adresserna som används för att skicka e-post till postlådeprovidern.

* **DKIM-validering misslyckades**: DKIM (DomainKeys Identified Mail) gör det möjligt för mottagarservern att verifiera att det mottagna meddelandet skickades av den äkta avsändaren av den associerade domänen och att innehållet i det ursprungliga meddelandet inte ändrades. DKIM-valideringsfel innebär att de mottagande e-postservrarna inte kan verifiera meddelandeinnehållets autenticitet och dess koppling till den sändande domänen:

* **MX-postvalidering misslyckades**: MX-postvalideringsfel (eXchange) innebär att de e-postservrar som ansvarar för att ta emot inkommande e-post för en viss underdomän inte är korrekt konfigurerade.

* **Leveranskonfigurationer misslyckades**: Fel i leveranskonfigurationer kan inträffa på grund av någon av följande orsaker:
   * Blockeringslistning av tilldelade IP-adresser
   * Ogiltigt `helo`-namn
   * E-postmeddelanden skickas från andra IP-adresser än de som anges i IP-poolen för motsvarande yta
   * Det går inte att leverera e-postmeddelanden till inkorg hos viktiga Internet-leverantörer

## Redigera en kanalyta {#edit-channel-surface}

Om du vill redigera en kanalyta följer du stegen nedan.

>[!NOTE]
>
>Du kan inte redigera **[!UICONTROL Push notification settings]**. Om en kanalyta bara är konfigurerad för Push-meddelandekanalen går det inte att redigera den.

1. Öppna en kanalyta genom att klicka på dess namn i listan.

   ![](assets/preset-name.png)

1. Redigera egenskaperna efter behov.

   >[!NOTE]
   >
   >Om en kanalyta har statusen **[!UICONTROL Active]** är fälten **[!UICONTROL Name]**, **[!UICONTROL Select channel]** och **[!UICONTROL Subdomain]** nedtonade och kan inte redigeras.

1. Klicka på **[!UICONTROL Submit]** för att bekräfta ändringarna.

   >[!NOTE]
   >
   >Du kan också spara kanalytan som utkast och återuppta uppdateringen senare.

När ändringarna har skickats går kanalytan igenom en valideringscykel som liknar den som fanns när [en kanalyta skapades](#create-channel-surface). Versionens bearbetningstid kan ta upp till **3 timmar**.

>[!NOTE]
>
>Om du bara redigerar fälten **[!UICONTROL Description]**, **[!UICONTROL Email type]** och/eller **[!UICONTROL Email retry parameters]** uppdateras uppdateringen omedelbart.

### Uppdatera information {#update-details}

För kanalytor med statusen **[!UICONTROL Active]** kan du kontrollera uppdateringens information. För att göra detta:

Klicka på ikonen **[!UICONTROL Recent update]** som visas bredvid namnet på den aktiva ytan.

![](assets/preset-recent-update-icon.png)

<!--You can also access the update details from an active channel surface while update is in progress.-->

På skärmen **[!UICONTROL Recent update]** kan du se information som uppdateringsstatus och listan över begärda ändringar.

<!--![](assets/preset-recent-update-screen.png)-->

### Uppdatera status {#update-statuses}

En uppdatering av en kanalyta kan ha följande status:

* **[!UICONTROL Processing]**: Kanalytans uppdatering har skickats och genomgår flera verifieringssteg.
* **[!UICONTROL Success]**: Den uppdaterade kanalytan har verifierats och kan väljas för att skapa meddelanden.
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under verifieringen av kanalytans uppdatering.

Varje status visas nedan.

#### Bearbetar {#surface-processing}

Flera leveranskontroller kommer att utföras för att kontrollera att ytan har uppdaterats på rätt sätt.

>[!NOTE]
>
>Om du bara redigerar fälten **[!UICONTROL Description]**, **[!UICONTROL Email type]** och/eller **[!UICONTROL Email retry parameters]** uppdateras uppdateringen omedelbart.

Bearbetningstiden kan ta upp till **3 timmar**. Läs mer om de kontroller som har utförts under valideringscykeln i [det här avsnittet](#create-channel-surface).

Om du redigerar en yta som redan var aktiv:

* Dess status är fortfarande **[!UICONTROL Active]** medan verifieringsprocessen pågår.

* Ikonen **[!UICONTROL Recent update]** visas bredvid namnet på ytan i kanalens ytlista.

* Under valideringsprocessen används fortfarande den äldre versionen av ytan för meddelanden som konfigurerats med den här ytan.

>[!NOTE]
>
>Du kan inte ändra en kanalyta medan uppdateringen pågår. Du kan fortfarande klicka på namnet, men alla fält är nedtonade. Ändringarna visas inte förrän uppdateringen har slutförts.

#### Lyckades {#success}

När valideringsprocessen har slutförts används den nya versionen av ytan automatiskt i alla meddelanden som använder den här ytan. Du kan dock behöva vänta:
* några minuter innan det konsumeras av enhetsmeddelanden,
* tills nästa omgång för att ytan ska vara effektiv i gruppmeddelanden.

#### Misslyckades {#failed}

Om valideringsprocessen misslyckas kommer den äldre versionen av ytan fortfarande att användas.

Läs mer om möjliga felorsaker i [det här avsnittet](#monitor-channel-surfaces).

När uppdateringen misslyckas blir ytan redigerbar igen. Du kan klicka på dess namn och uppdatera inställningarna som behöver korrigeras.

## Inaktivera en kanalyta {#deactivate-a-surface}

Om du vill göra en **[!UICONTROL Active]**-kanalyta otillgänglig för att skapa nya meddelanden kan du inaktivera den. Resebudskap som för närvarande använder denna yta kommer dock inte att påverkas och kommer att fortsätta fungera.

>[!NOTE]
>
>Du kan inte inaktivera en kanalyta medan en uppdatering bearbetas. Du måste vänta tills uppdateringen har slutförts eller misslyckats. Läs mer om att [redigera kanalytor](#edit-channel-surface) och om [uppdatera status](#update-statuses).

1. Öppna listan över kanalytor.

1. Klicka på knappen **[!UICONTROL More actions]** om du vill se den aktiva ytan.

1. Välj **[!UICONTROL Deactivate]**.

   ![](assets/preset-deactivate.png)

>[!NOTE]
>
>Inaktiverade kanalytor kan inte tas bort för att undvika problem i resor som använder dessa ytor för att skicka meddelanden.

Du kan inte redigera en inaktiverad kanalyta direkt. Du kan dock duplicera den och redigera kopian för att skapa en ny version som du använder för att skapa nya meddelanden. Du kan även aktivera den igen och vänta tills uppdateringen har redigerats.

![](assets/preset-activate.png)

<!--
## How-to video{#video-presets}

Learn how to create channel surfaces, how to use them and how to delegate a subdomain and create an IP pool.

>[!VIDEO](https://video.tv.adobe.com/v/334343?quality=12)
-->
