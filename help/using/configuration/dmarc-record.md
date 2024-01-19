---
solution: Journey Optimizer
product: journey optimizer
title: DMARC-post
description: Lär dig hur du ställer in DMARC-post i Journey Optimizer
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, domän, e-post, marc, post
source-git-commit: f9d3234a64ad659660c2d2c4ad24ab5c240cb857
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 0%

---

# DMARC-post {#dmarc-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_record"
>title="Ange DMARC-posten"
>abstract="Ställ in DMARC-posten för att undvika leveransproblem med Internet-leverantörer. Som en del av deras branschledande praxis kräver både Google och Yahoo att du har en DMARC-post för alla domäner du använder för att skicka e-post till dem."

>[!CAUTION]
>
>Efter de senaste Gmail- och Yahoo-meddelandena om bulkavsändare har Journey Optimizer nu stöd för DMARC-autentiseringstekniken.

<!--TO ADD TO AJO HOME PAGE (first tab)

>[!TAB Mandatory DMARC update]

As part of their enforcing industry best practices, Google and Yahoo will both be requiring that you have a DMARC record for any domain you use to send email to them, starting on **February 1st, 2024**. Make sure that you have DMARC record set up for all the subdomains that you have delegated to Adobe in Journey Optimizer.

[![image](using/assets/do-not-localize/learn-more-button.svg)](using/configuration/dmarc-record-update.md)
-->

Som en del av deras branschledande praxis kommer Google och Yahoo att kräva att ni har en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem. Det nya kravet börjar på **1 februari 2024**.

Läs mer om Google och Yahoos krav i [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

>[!CAUTION]
>
>Om detta nya krav från Gmail och Yahoo inte uppfylls förväntas det leda till att e-postmeddelanden landar i skräppostmappen eller blockeras.

Därför rekommenderar Adobe starkt att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i [!DNL Journey Optimizer]. Följ något av de två alternativen nedan:

* Konfigurera DMARC i dina underdomäner eller i den överordnade domänen för dina underdomäner, **i din värdlösning**.

* Konfigurera DMARC för dina delegerade underdomäner **med den nya funktionen i [!DNL Journey Optimizer] administrationsgränssnitt** - utan extra arbete med er värdlösning. [Läs mer](#implement-dmarc)

  >[!CAUTION]
  >
  >Om du har konfigurerat [CNAME-delegering](delegate-subdomain.md#cname-subdomain-delegation) för dina sändande underdomäner, kommer det också att kräva att du deltar i din värdlösning. Se till att du samarbetar med din IT-avdelning så att de kan utföra uppdateringen så fort som [!DNL Journey Optimizer] finns (30 januari 2024). <!--and be ready on February 1st, 2024-->

>[!NOTE]
>
>Läs mer om DMARC i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"} för att bättre förstå hur e-postleveransen påverkas.

## Vad är DMARC?

DMARC, som står för **Domänbaserad meddelandeautentisering, rapportering och överensstämmelse**, är ett autentiseringsprotokoll för e-post som hjälper till att skydda mot e-postförfalskning, nätfiske och andra bedrägliga aktiviteter.

* E-postautentisering:

   * SPF (Sender Policy Framework): DMARC använder SPF för att autentisera den avsändande e-postserverns identitet. SPF hjälper till att verifiera att e-postmeddelandet kommer från en auktoriserad källa genom att kontrollera den avsändande serverns IP-adress mot en lista över auktoriserade IP-adresser för domänen.
   * DKIM (DomainKeys Identified Mail): DMARC använder också DKIM för att lägga till en digital signatur i e-postmeddelanden, vilket gör att mottagaren kan verifiera meddelandets integritet och autenticitet.

* DMARC hjälper till att förhindra att oseriösa aktörer skickar e-postmeddelanden som verkar komma från din domän. Genom att konfigurera DMARC kan du ange hur e-postleverantörer ska hantera meddelanden som inte godkänns i autentiseringskontrollerna, vilket minskar sannolikheten för att nätfiskemeddelanden når mottagare.

* DMARC hjälper till att förbättra e-postleveransen genom att tillhandahålla en tydlig policy som e-postleverantörer kan följa när de stöter på meddelanden som sägs vara från din domän. Detta kan minska risken för att legitima e-postmeddelanden markeras som skräppost eller avvisas.

* Genom att implementera DMARC kan ni skydda ert varumärke genom att säkerställa att obehöriga parter inte kan missbruka er domän för nätfiske eller andra skadliga aktiviteter. Detta är särskilt viktigt för företag och organisationer som förlitar sig på e-postkommunikation med kunder och partners.

När du konfigurerar en DMARC-post lägger du till en DNS TXT-post i domänens DNS-inställningar. Den här posten anger din DMARC-princip, till exempel om meddelanden som inte kan autentiseras ska karantäneras eller avvisas. Implementering av DMARC är ett proaktivt steg mot att förbättra e-postsäkerheten och skydda både organisationen och mottagarna mot e-postbaserade hot.

## Implementera DMARC {#implement-dmarc}

* Om du inte lägger till DMARC sätts du i karantän (åtminstone).

* Se till att du har en äkta inkorg där du kan ta emot - du hanterar den här inkorgen (bör inte vara Adobe inkorg)

Rekommendationen är 24 eftersom det här i allmänhet är vad internetleverantörer har.
om inte, utvärdera din kapacitet/kontrollera din > chatt-GPT

Om en DMARC-post identifieras kan du kopiera och klistra in samma värden som listas eller ändra dem vid behov.

Om du inte anger något kommer standardvärden att användas.

### Fullt delegerade underdomäner

### Underdomäner som delegerats med CNAME

för CNAME i versionsflödet måste du hämta CSV-filen igen (inte för helt delegerade)





