---
title: Innehållsmärkning
description: Lär dig mer om xxxx
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
source-git-commit: 364861beb52e5663389a254ba145b31431b696ac
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# Skapa meddelandeförinställningar

Med [!DNL Journey Optimizer] kan du konfigurera meddelandeförinställningar som definierar alla tekniska parametrar som krävs för e-post och push-meddelanden (e-posttyp, avsändarens e-postadress och namn, mobilappar osv.).

Du kan ställa in så många meddelandeförinställningar som du vill, beroende på vilka olika varumärken du behöver kommunicera för.

När meddelandeförinställningarna har konfigurerats kan du välja dem när du skapar meddelanden från **[!UICONTROL Presets]**-listan.

## Skapa en meddelandeförinställning {#create-message-preset}

Så här skapar du en meddelandeförinställning:

1. Gå till menyn **[!UICONTROL Channels]** / **[!UICONTROL Message presets]** och klicka sedan på **[!UICONTROL Create Message preset]**.

   ![](../assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för förinställningen och ange sedan de kanaler som du vill konfigurera.

   ![](../assets/preset-general.png)

1. Konfigurera inställningar för e-post och push-meddelanden:

   Ange följande för e-postkanalen:

   * Den typ av kommunikation som skickas med förinställningen (transaktions- eller marknadsföringsmeddelanden).
   * [underdomänen](about-subdomain-delegation.md) som ska användas för att skicka e-postmeddelanden,
   * [IP-poolen](ip-pools.md) som ska associeras med förinställningen,
   * Huvudparametrarna som ska användas för e-postmeddelanden som skickas med förinställningen.

   ![](../assets/preset-email.png)

   Ange vilka IOS- och/eller Android-mobilprogram som ska användas för dina meddelanden i push-meddelandekanalen. Mer information om hur du konfigurerar miljön för att skicka push-meddelanden finns i [det här avsnittet](../push-configuration.md).

   ![](../assets/preset-push.png)

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara meddelandeförinställningen som utkast och återuppta konfigurationen senare.

   ![](../assets/preset-submit.png)

1. När meddelandeförinställningen har skapats visas den i listan med statusen **[!UICONTROL Processing]**.

   Under det här steget kommer flera kontroller att utföras för att verifiera att den har konfigurerats korrekt. Bearbetningstiden är mellan 48 och 72 timmar och kan ta upp till 7-10 dagar.

   Dessa kontroller omfattar leveranstester som utförs av Adobe-avdelningen:

   * SPF-validering,
   * DKIM-validering,
   * MX-postvalidering,
   * Kontrollera IP-svartlistning,
   * Helovärdkontroll,
   * IP-poolverifiering,
   * A/PTR-post, t/m/res-underdomänverifiering.

1. När kontrollerna är slutförda får meddelandeförinställningen statusen **[!UICONTROL Active]**. Den är klar att användas för att leverera meddelanden.

   <!-- later on, users will be notified in Pulse -->

   ![](../assets/preset-active.png)

## Övervaka meddelandeförinställningar

Alla meddelandeförinställningar visas på menyn **[!UICONTROL Channels]** / **[!UICONTROL Message presets]**. Det finns filter som hjälper dig att bläddra igenom listan (kanaltyp, användare, status).

![](../assets/preset-filters.png)

Meddelandeförinställningar kan ha följande status:

* **[!UICONTROL Draft]**: Meddelandeförinställningen har sparats som ett utkast och har inte skickats ännu. Öppna den för att återuppta konfigurationen.
* **[!UICONTROL Processing]**: Meddelandeförinställningen har skickats och genomgår flera verifieringssteg.
* **[!UICONTROL Active]**: Meddelandeförinställningen har verifierats och kan väljas för att skapa meddelanden.
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under verifieringen av meddelandeförinställningen.
* **[!UICONTROL De-activated]**: Meddelandeförinställningen inaktiveras. Det kan inte användas för att skapa nya meddelanden.

## Redigera meddelandeförinställningar

Om du vill redigera en meddelandeförinställning måste du först avaktivera den så att den inte är tillgänglig för att skapa nya meddelanden (publicerade meddelanden som använder den här förinställningen påverkas inte och fortsätter att fungera). Du måste sedan duplicera meddelandeförinställningen för att skapa en ny version som du använder för att skapa nya meddelanden:

1. Öppna listan med meddelandeförinställningar och inaktivera sedan den meddelandeförinställning som du vill redigera.

   ![](../assets/preset-deactivate.png)

1. Duplicera den inaktiverade meddelandeförinställningen. En kopia med statusen **[!UICONTROL Draft]** läggs automatiskt till i listan.

   ![](../assets/preset-duplicated.png)

1. Öppna den duplicerade meddelandeförinställningen, ändra den efter dina behov och skicka sedan ändringarna. Meddelandeförinställningen går igenom samma valideringscykel som under [skapandesteget](#create-message-preset).

1. När den har validerats får den statusen **[!UICONTROL Active]** och är klar att användas för att skapa nya meddelanden.

   >[!NOTE]
   >
   >Det går inte att ta bort förinställningar för inaktiverade meddelanden för att undvika problem i resor med dessa förinställningar för att skicka meddelanden.

<!-- To add when questions are answered + add link to this section in Create message presets section.

## Header parameters

The fields below allow you to enter information necessary to elaborate email message headers. This information can be personalized??

>[!NOTE]
>
>All fields are required.


To define the name and address of the sender which will appear in the header of messages sent, edit the settings below:

**[!UICONTROL Sender email]**: Address of the sender

**[!UICONTROL Sender name]**: Name of the sender. you can change the sender name

**[!UICONTROL Reply to (email)]**: The email address to use when the recipient clicks the Reply button in their e-mail client software,

**[!UICONTROL Reply to (name)]**: The name, which is customizable, that will be used when the recipient clicks the Reply button in their e-mail client software,

**[!UICONTROL Reply to (forward email)]**:
Cf. https://jira.corp.adobe.com/browse/CJM-9824

**[!UICONTROL Error email]**: Email address of messages with errors. This is the technical address used to handle bounce mail, including emails received by the AJO server due to non-existent target addresses.
This fields is automatically populated with the value you add in the Reply to (forward email) field.

>[!NOTE]
>
>The sender’s address will be used for replies by default.
>The header parameters must not be empty. By default, they contain the values input >when configuring the deployment wizard??
>The sender’s address is mandatory to allow an email to be sent (RFC standard).
Journey Optimizer checks the syntax of email addresses entered.

>[!CAUTION]
>
>In the context of the checks implemented by Internet Access Providers (ISPs) to combat unsolicited email (spam), Adobe recommends creating email accounts that correspond to the addresses specified for deliveries and replies. Check with your messaging system administrator.-->

