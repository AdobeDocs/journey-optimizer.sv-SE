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
source-git-commit: 49cb9734d66dc1aa2a3531c71a687aac00834d82
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# DMARC-post {#dmarc-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_record"
>title="Ange DMARC-posten"
>abstract="Ange DMARC-post för att undvika leveransproblem med Internet-leverantörer"

>[!CAUTION]
>
>Efter de senaste Gmail- och Yahoo-meddelandena om bulkavsändare har Journey Optimizer nu stöd för DMARC-autentiseringstekniken. //Du måste uppdatera alla underdomäner som du redan har skapat i instansen så att de inkluderar DMARC-stöd.//

Det är viktigt att du gör det senast 1 februari Dokument kommer snart

Startar

Du har två alternativ:

* Gör det nu på egen hand: konfigurera det med din IT-avdelning - när du vill

* Gör det i AJO - men i så fall måste du vänta till 30 jan

   * Fullständig delegering: du kan göra det den 30 januari (AJO-version)

   * CNAME planerar den hos IT-avdelningen så att den inte är tidskrävande, men du måste planera den

Som en del av deras branschledande praxis kommer både Google och Yahoo att kräva att du har en DMARC-post för alla domäner du använder för att skicka e-post till dem. Det nya kravet börjar på **1 februari 2024**.

Läs mer om Google och Yahoos krav på DMARC-registrering i [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

Läs mer om ändringarna på Google och Yahoo på [den här sidan](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

DMARC, som står för **Domänbaserad meddelandeautentisering, rapportering och överensstämmelse**, är ett autentiseringsprotokoll för e-post som hjälper till att skydda mot e-postförfalskning, nätfiske och andra bedrägliga aktiviteter.

* E-postautentisering:

   * SPF (Sender Policy Framework): DMARC använder SPF för att autentisera den avsändande e-postserverns identitet. SPF hjälper till att verifiera att e-postmeddelandet kommer från en auktoriserad källa genom att kontrollera den avsändande serverns IP-adress mot en lista över auktoriserade IP-adresser för domänen.
   * DKIM (DomainKeys Identified Mail): DMARC använder också DKIM för att lägga till en digital signatur i e-postmeddelanden, vilket gör att mottagaren kan verifiera meddelandets integritet och autenticitet.

* DMARC hjälper till att förhindra att oseriösa aktörer skickar e-postmeddelanden som verkar komma från din domän. Genom att konfigurera DMARC kan du ange hur e-postleverantörer ska hantera meddelanden som inte godkänns i autentiseringskontrollerna, vilket minskar sannolikheten för att nätfiskemeddelanden når mottagare.

* DMARC hjälper till att förbättra e-postleveransen genom att tillhandahålla en tydlig policy som e-postleverantörer kan följa när de stöter på meddelanden som sägs vara från din domän. Detta kan minska risken för att legitima e-postmeddelanden markeras som skräppost eller avvisas.

* Genom att implementera DMARC kan ni skydda ert varumärke genom att säkerställa att obehöriga parter inte kan missbruka er domän för nätfiske eller andra skadliga aktiviteter. Detta är särskilt viktigt för företag och organisationer som förlitar sig på e-postkommunikation med kunder och partners.

När du konfigurerar en DMARC-post lägger du till en DNS TXT-post i domänens DNS-inställningar. Den här posten anger din DMARC-princip, till exempel om meddelanden som inte kan autentiseras ska karantäneras eller avvisas. Implementering av DMARC är ett proaktivt steg mot att förbättra e-postsäkerheten och skydda både organisationen och mottagarna mot e-postbaserade hot.

[Läs mer om DMARC i Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"} för att bättre förstå hur DMARC påverkar e-postleveransen.

Om du inte lägger till DMARC sätts du i karantän (åtminstone).

kontrollera att du har en äkta inkorg där du kan ta emot - du hanterar den här inkorgen (bör inte vara Adobe inkorg)

Rekommendationen är 24 eftersom du vanligtvis, om den är mindre, utvärderar din kapacitet/kontrollerar din > chatt-GPT

Google och Yahoo, och förmodligen alla andra viktiga internetleverantörer

för CNAME i versionsflödet måste du hämta CSV-filen igen (inte för helt delegerade)

ny DMARC-post

In RN > put it first All subdomains must update with DMARC support



