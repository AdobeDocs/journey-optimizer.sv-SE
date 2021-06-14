---
title: Hantera listan över inaktiveringar
description: 'Lär dig hur du får åtkomst till och hanterar Journey Optimizer-listan över inaktiveringar '
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
feature: Applikationsinställningar
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 1%

---


# Hantera undertryckningslistan {#manage-suppression-list}

Med [!DNL Journey Optimizer] kan du övervaka alla e-postadresser som automatiskt utesluts från att skickas under en resa, till exempel:

* Adresser som är ogiltiga (fasta studsar) eller som konsekvent studsar på mjuk väg, och som kan påverka ditt e-postanseende negativt om du fortsätter att inkludera dem i dina leveranser.
* Mottagare som skickar skräppost av något slag mot ett av dina e-postmeddelanden.

<!--Profiles who unsubscribe from your sendings. Learn more on [opting-out](../consent.md). NOT TRUE as confirmed by eng.: "Subscribe and Unsubscribe are handled by the Consent/Subscription service. A user that opts out will not make it to the suppression list – we won’t send them emails."-->

Sådana e-postadresser samlas automatiskt in i Journey Optimizer **listan**. Läs mer i [det här avsnittet](../suppression-list.md).

## Åtkomst till listan {#access-suppression-list}

Öppna menyn **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL General]** och klicka sedan på länken **[!UICONTROL View suppression lists]** om du vill få tillgång till en detaljerad lista över utelämnade e-postadresser.

![](../assets/suppression-list-link.png)

Det finns filter som hjälper dig att bläddra igenom listan.

![](../assets/suppression-list-filters.png)

<!--suppression date,  category and reason, but on staging, only creation date filter is available-->

<!--You can also download the list as a CSV file for analysis and reporting purpose. Won't be available.-->

## Undertryckningskategorier och orsaker {#suppression-categories-and-reasons}

När ett meddelande inte kan levereras till en e-postadress avgör Journey Optimizer varför leveransen misslyckades och kopplar det till en undertryckningskategori.

Undertryckningskategorierna är följande:

* **Hård**: E-postadressen skickas omedelbart till listan över inaktiveringar.

* **Mjuk**: Mjuka fel skickar en adress till listan när felräknaren når gränsvärdet. [Läs mer om återförsök](retries.md)

* **Ignorerad**:
   * När felet inträffar för en giltig e-postadress men är känd som tillfällig, t.ex. ett misslyckat anslutningsförsök eller ett tillfälligt tekniskt problem, läggs e-postadressen till i listan när felräknaren når gränsvärdet. [Läs mer om återförsök](retries.md).
   * Om felet beror på ett skräppostklagomål skickas e-postadressen till mottagaren som skickade klagomålet omedelbart till listan över oönskade meddelanden.

<!--**Manual**: You can also manually add an email address to the suppression list. => Manual category will be available when manually adding an address to the suppression list (via API)-->

>[!NOTE]
>
>Läs mer om mjuka studsar och fasta studsar i avsnittet [Leveransfel](../suppression-list.md#delivery-failures).

För varje e-postadress som visas kan du även kontrollera **[!UICONTROL Reason]** för att utesluta den och datumet/tiden som den lades till i listan över utelämnanden.

![](../assets/suppression-list-temp.png)
<!--to replace with suppression-list.png when Manual category is available (through API)-->

Möjliga orsaker till leveransfel är:

| Orsak | Beskrivning | Undertryckningskategori |
---------|----------|--------- |
| **[!UICONTROL Undetermined]** | Det gick inte att identifiera den studsorsak som togs emot från mottagarens MTA-agent (Message Transfer Agent). | Ignorerad |
| **[!UICONTROL Invalid Recipient]** | Mottagaren är ogiltig eller finns inte. | Hård |
| **[!UICONTROL Soft Bounce]** | Meddelandet studsade på ett annat sätt än de mjuka fel som anges i den här tabellen, till exempel när det skickas över den tillåtna hastighet som rekommenderas av en Internet-leverantör. | Mjuk |
| **[!UICONTROL DNS Failure]** | Meddelandet studsade på grund av ett DNS-fel. | Mjuk |
| **[!UICONTROL Mailbox Full]** | Meddelandet studsade eftersom mottagarens postlåda är full och inte kan ta emot fler meddelanden. | Mjuk |
| **[!UICONTROL Too Large]** | Meddelandet studsade eftersom det var för stort för mottagaren. [Hämtningar ](retries.md) utförs: du kan redigera meddelandestorleken och mata in den igen för leverans. | Ignorerad |
| **[!UICONTROL Timeout]** | Meddelandet nådde sin tidsgräns (3,5 dagar), vilket innebär att det studsade på skärmen och nådde gränsen för antal nya meddelandeförsök. | Ignorerad |
| **[!UICONTROL Admin Failure]** | Meddelandet misslyckades enligt de principer som konfigurerats av den sändande systemadministratören. <!--For example, if emails are blackholed at the global, domain or binding level using the "blackhole" directive, this bounce code is used.--> | Ignorerad |
| **[!UICONTROL Generic Bounce: No RCPT]** | Det gick inte att fastställa någon mottagare för meddelandet. | Ignorerad |
| **[!UICONTROL Generic Bounce]** | Meddelandet misslyckades av ospecificerade orsaker. | Ignorerad |
| **[!UICONTROL Mail Block]** | Meddelandet blockerades av mottagaren (d.v.s. mottagare MTA). | Ignorerad |
| **[!UICONTROL Spam Block]** | Meddelandet blockerades av mottagaren eftersom det kommer från en känd skräppostkälla. Det kan till exempel vara ett sändande IP-block. | Ignorerad |
| **[!UICONTROL Spam Content]** | Meddelandeinnehållet blockerades av mottagaren (MTA-mottagaren) som skräppost. | Ignorerad |
| **[!UICONTROL Prohibited Attachment]** | Meddelandet blockerades av mottagaren eftersom det innehöll en bifogad fil. | Ignorerad |
| **[!UICONTROL Relaying Denied]** | Meddelandet blockerades av mottagaren eftersom återutläggning inte tillåts. | Mjuk |
| **[!UICONTROL Auto-Reply]** | Meddelandet är ett autosvar/semesterbrev. | Ignorerad |
| **[!UICONTROL Transient Failure]** | Meddelandeöverföringen har tillfälligt fördröjts. | Ignorerad |
| **[!UICONTROL Challenge-Response]** | Meddelandet är en frågesvarsundersökning. | Mjuk |

>[!NOTE]
>
>Användare som avbeställer prenumerationen får inte e-post från [!DNL Journey Optimizer], och deras e-postadresser kan därför inte skickas till listan över inaktiveringar. Deras val hanteras på Experience Platform-nivå. Läs mer om [avanmälan](../consent.md).

<!--
Removed from the table provided by SparkPost/Momentum:
| **[!UICONTROL Subscribe]** | The message is a subscribe request. | Ignored |
| **[!UICONTROL Unsubscribe]** | The message is an unsubscribe request. | Hard |
-->

<!--Note to add eventually: If a user is subscribed and [!DNL Journey Optimizer] fails to send emails to their subscribed email address, they will get added to the suppression list. (not sure it's possible to subscribe through AJO or need to find reference to Experience Platform doc?)-->


