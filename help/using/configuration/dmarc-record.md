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
source-git-commit: 7d5a2a9b80110505688b5bfda2e286c7a6432441
workflow-type: tm+mt
source-wordcount: '905'
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

Därför rekommenderar Adobe starkt att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i [!DNL Journey Optimizer]. Följ stegen nedan som gäller ditt ärende:

* Om du har [helt delegerad](delegate-subdomain.md#full-subdomain-delegation) Om du vill skicka underdomäner till Adobe följer du något av följande två alternativ:

   * Konfigurera DMARC på den överordnade domänen för dina delegerade underdomäner **i din värdlösning**.

   * Konfigurera DMARC för dina delegerade underdomäner **med den kommande funktionen i [!DNL Journey Optimizer] administrationsgränssnitt** - utan extra arbete med er värdlösning.

* Om du har konfigurerat [CNAME-delegering](delegate-subdomain.md#cname-subdomain-delegation) för dina sändande underdomäner, följ något av följande två alternativ:

   * Konfigurera DMARC på dina underdomäner eller på den överordnade domänen för dina underdomäner **i din värdlösning**.

   * Konfigurera DMARC för dina delegerade underdomäner **med den kommande funktionen i [!DNL Journey Optimizer] administrationsgränssnitt**. Men det kommer också att kräva att du deltar i din värdlösning. Därför bör du se till att samordna med din IT-avdelning så att de kan utföra uppdateringen så snart som [!DNL Journey Optimizer] finns (den 30 januari). <!--and be ready on February 1st, 2024-->

**Mer information om [!DNL Journey Optimizer] DMARC kommer snart.**

>[!NOTE]
>
>Läs mer om DMARC i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"} för att bättre förstå hur e-postleveransen påverkas.

## Vad är DMARC?

DMARC, som står för **Domänbaserad meddelandeautentisering, rapportering och överensstämmelse**, är en metod/ett protokoll för e-postautentisering som gör att domänägare kan skydda sin domän från obehörig användning.

Det erbjuder ett sätt att autentisera avsändarens domän och hjälper till att förhindra att oseriösa aktörer skickar e-postmeddelanden som verkar komma från din domän.

DMARC ger också feedback om e-postautentiseringsstatus och tillåter avsändare att styra vad som händer med e-postmeddelanden som inte kan autentiseras. Detta inkluderar alternativ för att övervaka, sätta i karantän eller avvisa e-post beroende på vilken DMARC-policy som har implementerats.

<!--Setting up a DMARC record involves adding a DNS TXT record to your domain's DNS settings. This record specifies your DMARC policy, such as whether to quarantine or reject messages that fail authentication. Implementing DMARC is a proactive step towards enhancing email security and protecting both your organization and your recipients from email-based threats.-->

DMARC har tre politiska alternativ:

* Monitor (p=none): Instruerar postlådeprovidern/ISP att göra vad de normalt skulle göra med meddelandet.
* Karantän (p=karantän): Instruerar postlådeprovidern/ISP att leverera e-post som inte skickar DMARC till mottagarens skräppostmapp.
* Avvisa (p=avvisa): Instruerar postlådeprovidern/ISP att blockera e-post som inte godkänns av DMARC, vilket resulterar i ett studs.

## Hur fungerar DMARC?

SPF och DKIM används båda för att associera ett e-postmeddelande med en domän och fungerar tillsammans för att autentisera e-post. DMARC tar det här steget längre och hjälper till att förhindra förfalskning genom att matcha domänen som kontrolleras av DKIM och SPF. För att skicka DMARC måste ett meddelande skicka SPF eller DKIM. Om båda dessa misslyckas kommer DMARC att misslyckas och e-postmeddelandet levereras enligt din valda DMARC-policy.

* SPF (Sender Policy Framework): DMARC använder SPF för att autentisera den avsändande e-postserverns identitet. SPF hjälper till att verifiera att e-postmeddelandet kommer från en auktoriserad källa genom att kontrollera den avsändande serverns IP-adress mot en lista över auktoriserade IP-adresser för domänen.
* DKIM (DomainKeys Identified Mail): DMARC använder också DKIM för att lägga till en digital signatur i e-postmeddelanden, vilket gör att mottagaren kan verifiera meddelandets integritet och autenticitet.

>[!NOTE]
>
>DMARC kräver justering mellan adressen Från och Retursökväg.


<!--

* DMARC helps prevent malicious actors from sending emails that appear to come from your domain. By setting up DMARC, you can specify how email providers should handle messages that fail authentication checks, reducing the likelihood that phishing emails will reach recipients.

* DMARC helps improve email deliverability by providing a clear policy for email providers to follow when encountering messages claiming to be from your domain. This can reduce the chances of legitimate emails being marked as spam or rejected.

DMARC helps protect against email spoofing, phishing, and other fraudulent activities.

It allows you to decide how a mailbox provider should handle emails that fail SPF and DKIM checks, providing a way to authenticate the sender's domain and prevent unauthorized use of the domain for malicious purposes.

-->


## Implementera DMARC {#implement-dmarc}

Följ stegen nedan för att implementera DMARC.

* Om du inte lägger till DMARC sätts du i karantän (åtminstone).

### Fullt delegerade underdomäner

Ange den åtgärd som mottagarservern ska utföra om DMARC misslyckas.

DMARC har tre politiska alternativ:

* Monitor (p=none): Instruerar postlådeprovidern/ISP att göra vad de normalt skulle göra med meddelandet. Det här är standardvärdet.
* Karantän (p=karantän): Instruerar postlådeprovidern/ISP att leverera e-post som inte skickar DMARC till mottagarens skräppostmapp.
* Avvisa (p=avvisa): Instruerar postlådeprovidern/ISP att blockera e-post som inte godkänns av DMARC, vilket resulterar i ett studs.

E-postmeddelanden som tar emot sammanställda DMARC-rapporter och kriminaltekniska DMARC-felrapporter: du kan lägga till upp till 5 adresser.

* Se till att du har en äkta inkorg där du kan ta emot - du hanterar den här inkorgen (bör inte vara Adobe inkorg)

Tillämplig procentandel av e-postmeddelanden som ska användas med DMARC:

Rapporteringsintervall: Rekommendationen är 24 eftersom det här i allmänhet är vad internetleverantörer har.
om inte, utvärdera din kapacitet/kontrollera din > chatt-GPT

Om en DMARC-post identifieras kan du kopiera och klistra in samma värden som listas eller ändra dem vid behov.

Om du inte anger något kommer standardvärden att användas.

### Underdomäner som delegerats med CNAME

för CNAME i versionsflödet måste du hämta CSV-filen igen (inte för helt delegerade)





