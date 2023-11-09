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
source-git-commit: 8db5ae5b3cbef245dfe7cd11a95355c072bc3ef8
workflow-type: tm+mt
source-wordcount: '1566'
ht-degree: 0%

---

# Konfigurera kanalytor {#set-up-channel-surfaces}

>[!CONTEXTUALHELP]
>id="ajo_admin_channel_surfaces"
>title="Yta"
>abstract="En yta är en konfiguration som har definierats av en systemadministratör. Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv."

Med [!DNL Journey Optimizer]kan du konfigurera kanalytor (t.ex. meddelandeförinställningar) som definierar alla tekniska parametrar som krävs för dina meddelanden: e-posttyp, avsändarens e-postadress och namn, mobilappar, SMS-konfiguration med mera.

>[!CAUTION]
>
> * Om du vill skapa, redigera och ta bort kanalytor måste du ha [Hantera meddelandeförinställningar](../administration/high-low-permissions.md#administration-permissions) behörighet.
>
> * Du måste utföra [E-postkonfiguration](../email/get-started-email-config.md), [Push-konfiguration](../push/push-configuration.md) och [SMS-konfiguration](../sms/sms-configuration.md) innan du skapar kanalytor.

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

Så här skapar du en kanalyta:

1. Öppna **[!UICONTROL Channels]** > **[!UICONTROL Branding]** > **[!UICONTROL Channel surfaces]** menyn och klicka sedan på **[!UICONTROL Create channel surface]**.

   ![](assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för ytan och välj sedan de kanaler som ska konfigureras.

   ![](assets/preset-general.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

1. Om du valde **[!UICONTROL Email]** kanal, konfigurera dina inställningar enligt beskrivningen i [det här avsnittet](../email/email-settings.md).

   ![](assets/preset-email.png)

1. För **[!UICONTROL Push Notification]** välj minst en plattform -  **iOS** och/eller **Android** - och de mobilapplikationer som ska användas för varje plattform.

   ![](assets/preset-push.png)

   >[!NOTE]
   >
   >Mer information om hur du konfigurerar miljön för att skicka push-meddelanden finns i [det här avsnittet](../push/push-gs.md).

1. För **[!UICONTROL SMS]** kanal, ange dina inställningar enligt [det här avsnittet](../sms/sms-configuration.md#message-preset-sms).

   ![](assets/preset-sms.png)

   >[!NOTE]
   >
   >Mer information om hur du konfigurerar miljön för att skicka SMS-meddelanden finns i [det här avsnittet](../sms/sms-configuration.md).

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalytan som ett utkast och återuppta konfigurationen senare.

   ![](assets/preset-submit.png)

   >[!NOTE]
   >
   >Du kan inte fortsätta skapa en yta medan den valda IP-poolen är under [utgåva](ip-pools.md#edit-ip-pool) (**[!UICONTROL Processing]** status) och har aldrig kopplats till den valda underdomänen. [Läs mer](#subdomains-and-ip-pools)
   >
   >Spara ytan som utkast och vänta tills IP-poolen har **[!UICONTROL Success]** status för att återuppta skapande av yta.

1. När kanalytan har skapats visas den i listan med **[!UICONTROL Processing]** status.

   Under det här steget kommer flera kontroller att utföras för att verifiera att den har konfigurerats korrekt. <!--The processing time is around **48h-72h**, and can take up to **7-10 business days**.-->

   >[!NOTE]
   > När du skapar en e-postyta för en underdomän varierar bearbetningstiden enligt följande:
   >
   > * För **nya underdomäner** kan processen för att skapa den första kanalytan ta **10 till 10 dagar**.
   > * För **icke-produktionssandlådor** eller om den valda underdomänen är **används redan** i en annan godkänd kanalyta, tar processen bara upp till **3 timmar**.


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
   >Om kontrollerna inte lyckas kan du läsa mer om orsakerna till eventuella fel i [det här avsnittet](#monitor-channel-surfaces).

1. När kontrollerna är klara får kanalytan **[!UICONTROL Active]** status. Den är klar att användas för att leverera meddelanden.

   ![](assets/preset-active.png)

## Skärmkanalsytor {#monitor-channel-surfaces}

Alla kanalytor visas i **[!UICONTROL Channels]** > **[!UICONTROL Channel surfaces]** -menyn. Det finns filter som hjälper dig att bläddra igenom listan (kanal, användare, status).

![](assets/preset-filters.png)

När kanalytorna har skapats kan de ha följande status:

* **[!UICONTROL Draft]**: Kanalytan har sparats som ett utkast och har inte skickats ännu. Öppna den för att återuppta konfigurationen.
* **[!UICONTROL Processing]**: Kanalytan har skickats och genomgår flera verifieringssteg.
* **[!UICONTROL Active]**: Kanalytan har verifierats och kan väljas för att skapa meddelanden.
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under verifieringen av kanalens yta.
* **[!UICONTROL Deactivated]**: Kanalytan är inaktiverad. Det kan inte användas för att skapa nya meddelanden.

Om det inte går att skapa en kanalyta beskrivs detaljerna för varje möjlig felorsak nedan.

Om något av dessa fel inträffar, kontakta [Adobe kundtjänst](https://helpx.adobe.com/se/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"} för att få hjälp.

* **SPF-valideringen misslyckades**: SPF (Sender Policy Framework) är ett autentiseringsprotokoll för e-post som tillåter att auktoriserade IP-adresser kan skicka e-post från en viss underdomän. SPF-valideringsfel innebär att IP-adresserna i SPF-posten inte matchar IP-adresserna som används för att skicka e-post till postlådeprovidern.

* **DKIM-validering misslyckades**: DKIM (DomainKeys Identified Mail) gör det möjligt för mottagarservern att verifiera att det mottagna meddelandet skickades av den äkta avsändaren av den associerade domänen och att innehållet i det ursprungliga meddelandet inte ändrades. DKIM-valideringsfel innebär att de mottagande e-postservrarna inte kan verifiera meddelandeinnehållets autenticitet och dess koppling till den sändande domänen:

* **MX-postvalideringen misslyckades**: MX-postvalideringsfel (Mail eXchange) innebär att de e-postservrar som ansvarar för att ta emot inkommande e-post för en viss underdomän inte är korrekt konfigurerade.

* **Konfigurationer för slutbarhet misslyckades**: Fel i leveranskonfigurationer kan uppstå på grund av någon av följande orsaker:
   * Blockeringslistning av tilldelade IP-adresser
   * Ogiltig `helo` name
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
   >Om en kanalyta har **[!UICONTROL Active]** status, **[!UICONTROL Name]**, **[!UICONTROL Select channel]** och **[!UICONTROL Subdomain]** fält är nedtonade och kan inte redigeras.

1. Klicka **[!UICONTROL Submit]** för att bekräfta dina ändringar.

   >[!NOTE]
   >
   >Du kan också spara kanalytan som utkast och återuppta uppdateringen senare.

När ändringarna har skickats går kanalytan igenom en valideringscykel som liknar den som finns när [skapa en kanalyta](#create-channel-surface). Versionshanteringstiden kan ta upp till **3 timmar**.

>[!NOTE]
>
>Om du bara redigerar **[!UICONTROL Description]**, **[!UICONTROL Email type]** och/eller **[!UICONTROL Email retry parameters]** uppdateras uppdateringen omedelbart.

### Uppdatera information {#update-details}

För kanalytor som har **[!UICONTROL Active]** status kan du kontrollera uppdateringens information. För att göra detta:

Klicka på **[!UICONTROL Recent update]** -ikonen som visas bredvid det aktiva ytnamnet.

![](assets/preset-recent-update-icon.png)

<!--You can also access the update details from an active channel surface while update is in progress.-->

På **[!UICONTROL Recent update]** visas information som uppdateringsstatus och listan över begärda ändringar.

<!--![](assets/preset-recent-update-screen.png)-->

### Uppdatera status {#update-statuses}

En uppdatering av en kanalyta kan ha följande status:

* **[!UICONTROL Processing]**: Kanalytans uppdatering har skickats och genomgår flera verifieringssteg.
* **[!UICONTROL Success]**: Den uppdaterade kanalytan har verifierats och kan väljas för att skapa meddelanden.
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under uppdateringsverifieringen av kanalytan.

Varje status visas nedan.

#### Bearbetar {#surface-processing}

Flera leveranskontroller kommer att utföras för att kontrollera att ytan har uppdaterats på rätt sätt.

>[!NOTE]
>
>Om du bara redigerar **[!UICONTROL Description]**, **[!UICONTROL Email type]** och/eller **[!UICONTROL Email retry parameters]** uppdateras uppdateringen omedelbart.

Bearbetningstiden kan ta upp till **3 timmar**. Läs mer om kontroller som utförts under valideringscykeln i [det här avsnittet](#create-channel-surface).

Om du redigerar en yta som redan var aktiv:

* Dess status kvarstår **[!UICONTROL Active]** när valideringsprocessen pågår.

* The **[!UICONTROL Recent update]** visas bredvid namnet på ytan i kanalens ytlista.

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

Skapa en **[!UICONTROL Active]** Kanalytan är inte tillgänglig för att skapa nya meddelanden. Du kan inaktivera den. Resebudskap som för närvarande använder denna yta kommer dock inte att påverkas och kommer att fortsätta fungera.

>[!NOTE]
>
>Du kan inte inaktivera en kanalyta medan en uppdatering bearbetas. Du måste vänta tills uppdateringen har slutförts eller misslyckats. Läs mer på [redigera kanalytor](#edit-channel-surface) och [uppdateringsstatus](#update-statuses).

1. Öppna listan över kanalytor.

1. Klicka på **[!UICONTROL More actions]** -knappen.

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
