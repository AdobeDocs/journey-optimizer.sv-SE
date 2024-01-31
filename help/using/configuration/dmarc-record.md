---
solution: Journey Optimizer
product: journey optimizer
title: DMARC-post
description: Lär dig hur du ställer in DMARC-post i Journey Optimizer
feature: Subdomains, Channel Configuration, Deliverability
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, domän, e-post, marc, post
source-git-commit: f1f57e1b7398e0c235e5ecb80b58a8b7761d0e55
workflow-type: tm+mt
source-wordcount: '1353'
ht-degree: 0%

---

# DMARC-post {#dmarc-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_record"
>title="Ange DMARC-post"
>abstract="DMARC är en autentiseringsmetod för e-post som gör att domänägare kan skydda sin domän från obehörig användning och undvika leveransproblem med postlådeprovidrar.<br>Som en del av deras branschledande praxis kräver både Google och Yahoo att du har en DMARC-post för alla domäner du använder för att skicka e-post till dem."

## Vad är DMARC? {#what-is-dmarc}

Domänbaserad Message Authentication, Reporting och Conformance (DMARC) är en autentiseringsmetod som gör att domänägare kan skydda sin domän från obehörig användning. Genom att erbjuda en tydlig profil till e-postleverantörer/Internet-leverantörer hjälper den till att förhindra att oseriösa aktörer skickar e-postmeddelanden som påstår sig vara från din domän. Implementering av DMARC minskar risken för att legitima e-postmeddelanden markeras som skräppost eller avvisas, och förbättrar e-postleveransen.

DMARC erbjuder också rapporter om meddelanden som inte kan autentiseras, tillsammans med kontroll över hanteringen av e-postmeddelanden som inte godkänns vid DMARC-validering. Beroende på implementerat [DMARC-policy](#dmarc-policies)kan dessa e-postmeddelanden övervakas, ställas i karantän eller avvisas. Dessa funktioner gör att du kan vidta åtgärder för att minska och åtgärda potentiella fel.

<!--To help you prevent deliverability issues by allowing ISPs to authenticate your sending domains - while gaining visibility and control over mail that fail this authentication, [!DNL Journey Optimizer] will soon be supporting the DMARC technology directly in its administration interface.-->

För att förhindra leveransproblem och samtidigt få kontroll över e-post som inte kan autentiseras, [!DNL Journey Optimizer] kommer snart att stödja DMARC-tekniken direkt i administrationsgränssnittet. [Läs mer](#implement-dmarc)

### Hur fungerar DMARC? {#how-dmarc-works}

SPF och DKIM används båda för att associera ett e-postmeddelande med en domän och fungerar tillsammans för att autentisera e-post. DMARC tar det här steget längre och hjälper till att förhindra förfalskning genom att matcha domänen som kontrolleras av DKIM och SPF.

>[!NOTE]
>
>I Journey Optimizer är SPF och DKIM konfigurerade för dig.

För att skicka DMARC måste ett meddelande skicka SPF eller DKIM:

* SPF (Sender Policy Framework) hjälper till att verifiera att e-postmeddelandet kommer från en auktoriserad källa genom att kontrollera den avsändande serverns IP-adress mot en lista över auktoriserade IP-adresser för domänen.
* DKIM (DomainKeys Identified Mail) lägger till en digital signatur i e-postmeddelanden, vilket gör att mottagaren kan verifiera meddelandets integritet och autenticitet.

Om båda eller någon av dessa inte kan autentiseras, kommer DMARC att misslyckas och e-postmeddelandet levereras enligt din valda DMARC-policy.

<!--DMARC requires alignment between the 'From" and 'Return-Path' address.-->

### DMARC-policyer {#dmarc-policies}

Om ett e-postmeddelande inte kan verifieras med DMARC kan du bestämma vilken åtgärd som ska utföras för det meddelandet. DMARC har tre politiska alternativ:

* Monitor (p=none): Instruerar postlådeprovidern/ISP att göra vad de normalt skulle göra med meddelandet.
* Karantän (p=karantän): Instruerar postlådeprovidern/ISP att leverera e-post som inte skickar DMARC till mottagarens skräppostmapp.
* Avvisa (p=avvisa): Instruerar postlådeprovidern/ISP att blockera e-post som inte godkänns av DMARC, vilket resulterar i ett studs.

>[!NOTE]
>
>Lär dig hur du ställer in DMARC-policyn med [!DNL Journey Optimizer] in [det här avsnittet](#set-up-dmarc).

## Uppdatering av DMARC-krav {#dmarc-update}

Som en del av deras branschledande praxis kommer Google och Yahoo att kräva att ni har en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem. Det nya kravet börjar på **1 februari 2024**.

Läs mer om Google och Yahoos krav i [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html#dmarc){target="_blank"}.

>[!CAUTION]
>
>Om detta nya krav från Gmail och Yahoo inte uppfylls förväntas det leda till att e-postmeddelanden landar i skräppostmappen eller blockeras. [Läs mer](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html#how-will-this-impact-me-as-a-marketer%3F){target="_blank"}

Adobe rekommenderar därför att du vidtar följande åtgärder:

* Se till att du har **DMARC-post** konfigurera för **alla underdomäner som du redan har delegerat** till Adobe in [!DNL Journey Optimizer]. [Lär dig mer](#check-subdomains-for-dmarc)

* När **delegera en ny underdomän** till Adobe kommer du snart att kunna **konfigurera DMARC** direkt **i [!DNL Journey Optimizer] administrationsgränssnitt**. [Lär dig mer](#implement-dmarc)

## Implementera DMARC i [!DNL Journey Optimizer] {#implement-dmarc}

The [!DNL Journey Optimizer] Med administrationsgränssnittet kan du konfigurera DMARC-posten för alla underdomäner som du redan har delegerat eller delegerar till Adobe. De detaljerade stegen beskrivs nedan.

### Kontrollera dina befintliga underdomäner för DMARC {#check-subdomains-for-dmarc}

För att vara säker på att du har ställt in en DMARC-post för alla underdomäner som du har delegerat i [!DNL Journey Optimizer]följer du stegen nedan.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Subdomains]** menyn och klicka sedan på **[!UICONTROL Set up subdomain]**.

1. Kontrollera för varje delegerad underdomän **[!UICONTROL DMARC Record]** kolumn. Om ingen post hittades för en viss underdomän visas en varning.

   ![](assets/dmarc-record-alert.png)

   >[!CAUTION]
   >
   >För att uppfylla det nya kravet från Gmail och Yahoo och undvika leveransproblem med de främsta Internet-leverantörerna, rekommenderar vi att du skapar en DMARC-post för alla delegerade underdomäner. [Läs mer](dmarc-record-update.md)

1. Välj en underdomän utan associerad DMARC-post och fyll i **[!UICONTROL DMARC record]** -sektion efter organisationens behov. Stegen för att fylla i DMARC-postfält beskrivs i [det här avsnittet](#implement-dmarc).

1. Tänk på de två alternativen nedan:

   * Om du redigerar en underdomän som har konfigurerats med [CNAME](delegate-subdomain.md#cname-subdomain-delegation)måste du kopiera DNS-posten för DMARC till din värdlösning för att generera matchande DNS-poster.

     ![](assets/dmarc-record-edit-cname.png)

     Kontrollera att DNS-posten har genererats i din domänvärdslösning och markera kryssrutan Jag bekräftar...

   * Om du redigerar en underdomän [helt delegerad](delegate-subdomain.md#full-subdomain-delegation) Adobe fyller du bara i **[!UICONTROL DMARC record]** fält som anges i [det här avsnittet](#implement-dmarc). Ingen ytterligare åtgärd krävs.

     ![](assets/dmarc-record-edit-full.png)

1. Spara ändringarna.

### Konfigurera DMARC för nya underdomäner {#set-up-dmarc}

När nya underdomäner delegeras till Adobe i [!DNL Journey Optimizer]skapas en DMARC-post i DNS för din domän. Följ stegen nedan för att implementera DMARC.

>[!CAUTION]
>
>För att uppfylla det nya kravet från Gmail och Yahoo och undvika leveransproblem med de främsta Internet-leverantörerna, rekommenderar vi att du skapar en DMARC-post för alla delegerade underdomäner. [Läs mer](dmarc-record-update.md)

<!--If you fail to comply with the new requirement from Gmail and Yahoo to have DMARC record for all sending domains, your emails are expected to land into the spam folder or to get blocked.-->

1. Konfigurera en ny underdomän. [Lär dig mer](delegate-subdomain.md)

1. Gå till **[!UICONTROL DMARC record]** -avsnitt.

   Om underdomänen har en befintlig DMARC-post och om den hämtas av [!DNL Journey Optimizer]kan du använda samma värden som de som är markerade i gränssnittet eller ändra dem efter behov.

   ![](assets/dmarc-record-found.png)

   >[!NOTE]
   >
   >Om du inte lägger till några värden används de förfyllda standardvärdena.

1. Definiera åtgärden som mottagarservern ska utföra om DMARC misslyckas. Beroende på [DMARC-policy](#dmarc-policies) Välj något av följande tre alternativ:

   * **[!UICONTROL None]** (standardvärde): Uppmanar mottagaren att inte utföra några åtgärder mot meddelanden som inte godkänns vid DMARC-autentisering, men ändå skicka e-postrapporter till avsändaren.
   * **[!UICONTROL Quarantine]**: Anger att den mottagande e-postservern ska karantän-skicka e-post som inte godkänns vid DMARC-autentisering, vilket vanligtvis innebär att meddelandena placeras i mottagarens skräppostmapp.
   * **[!UICONTROL Reject]**: Anger att mottagaren helt ska neka (studsa) e-post för domänen som inte kan autentiseras. När den här principen är aktiverad har bara e-post som verifieras som 100 % autentiserad av din domän en chans att placeras i inkorgen.

   >[!NOTE]
   >
   >Det är en god praxis att långsamt införa DMARC-implementering genom att trappa upp DMARC-policyn från **Ingen**, till **Karantän**, till **Avvisa** som ni förstår DMARC:s potentiella inverkan.

1. Om du vill kan du lägga till en eller flera e-postadresser för att ange var **DMARC-rapporter** i e-postmeddelanden som [ej godkänd autentisering](#how-dmarc-works) bör ingå i er organisation. Du kan lägga till upp till fem adresser för varje rapport.

   >[!NOTE]
   >
   >Kontrollera att du har en äkta inkorg (inte Adobe) där du kan ta emot rapporterna.

   Det finns två olika rapporter som genereras av Internet-leverantörer och som avsändare kan ta emot via RUA/RUF-taggarna i deras DMARC-policy:

   * **Sammanställningsrapporter** (RUA): De innehåller inga PII-filer (personligt identifierbar information) som kan vara GDPR-känsliga.
   * **Rapporter om kriminaltekniska fel** (RUF): De innehåller GDPR-känsliga e-postadresser. Kontrollera internt hur man hanterar information som måste uppfylla GDPR innan informationen används.

   >[!NOTE]
   >
   >Dessa mycket tekniska rapporter ger en översikt över e-postmeddelanden som försöker förfalskas. De smälter bäst in via ett verktyg från tredje part.

1. Välj **tillämpbar procent** e-postmeddelanden för DMARC.

   Den här procentandelen beror på ditt förtroende för e-postinfrastrukturen och toleransen för falska positiva svar (legitima e-postmeddelanden markeras som bedrägliga). Det är vanligt att organisationer börjar med en DMARC-policy som är inställd på **Ingen**, ökar den procentuella andelen av DMARC:s policy gradvis och övervakar noga effekten på den legitima e-postleveransen.

   >[!NOTE]
   >
   >Samarbeta med e-postadministratörer och IT-team för att gradvis öka procentandelen när ni får förtroende för era rutiner för e-postautentisering.

   Som en god praxis bör man sträva efter en hög nivå på DMARC-efterlevnad, helst nära 100 %, för att maximera säkerhetsfördelarna samtidigt som man minimerar risken för falskt positiva resultat.

1. Välj en **rapporteringsintervall** mellan 24 och 168 timmar. Det gör det möjligt för domänägare att få regelbundna uppdateringar om resultaten av e-postautentiseringen och vidta nödvändiga åtgärder för att förbättra e-postsäkerheten.

   <!--The DMARC reporting interval is specified in the DMARC policy published in the DNS (Domain Name System) records for a domain. The reporting interval can be set to daily, weekly, or another specified frequency, depending on the domain owner's preferences.

    The default value (24 hours) is generally the email providers' expectation.-->


<!--

Setting up a DMARC record involves adding a DNS TXT record to your domain's DNS settings. This record specifies your DMARC policy, such as whether to quarantine or reject messages that fail authentication. Implementing DMARC is a proactive step towards enhancing email security and protecting both your organization and your recipients from email-based threats.

DMARC helps prevent malicious actors from sending emails that appear to come from your domain. By setting up DMARC, you can specify how email providers should handle messages that fail authentication checks, reducing the likelihood that phishing emails will reach recipients.

DMARC helps improve email deliverability by providing a clear policy for email providers to follow when encountering messages claiming to be from your domain. This can reduce the chances of legitimate emails being marked as spam or rejected.

DMARC helps protect against email spoofing, phishing, and other fraudulent activities.

It allows you to decide how a mailbox provider should handle emails that fail SPF and DKIM checks, providing a way to authenticate the sender's domain and prevent unauthorized use of the domain for malicious purposes.

## What are the benefits of DMARC? {#dmarc-benefits}

The key benefits or DMARC are as folllows:

* DMARC allows email receivers to easily identify the authentication of emails, which could potentially improve delivery.

* It offers reporting on which messages fail SPF and/or DKIM, enabling senders to gain visibility.

* This increased visibility allows for steps to be taken to mitigate further errors. It gives senders a degree of control over what happens with mail that does not pass either of these authentication methods.

-->







