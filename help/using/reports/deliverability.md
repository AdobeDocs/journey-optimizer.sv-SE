---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med leverans
description: Lär dig riktlinjerna för slutprodukter
feature: Deliverability
topic: Content Management
role: Admin
level: Intermediate, Experienced
exl-id: 8f33dda7-9bd5-4293-8d0d-222205cbc7d5
source-git-commit: b8d56578aae90383092978446cb3614a4a033f80
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 0%

---

# Kom igång med leverans {#manage-deliverability}

Leverans är ett mått på hur väl leveransen når mottagarnas inkorgar.

>[!NOTE]
>
>För kunder som licensierar hälsovård använder Adobe TLS 1.2 (Transport Layer Security) för att säkra datautbytet mellan användarnas system (mottagare) och Journey Optimizer (avsändare). Om den mottagande e-postservern inte har stöd för TLS 1.2 kommer kunderna att få leveransproblem, inklusive e-poststudsar tillbaka till den ursprungliga avsändaren.

**E-postleveransen** refererar till den uppsättning egenskaper som avgör om ett meddelande kan nå sin destination via en personlig e-postadress inom en kort tid och med den förväntade kvaliteten i fråga om innehåll och format. Dessa egenskaper kan delas in i fyra huvudkategorier: datakvalitet, meddelande och innehåll, sändande infrastruktur och anseende. Tillsammans utgör de grunden för ett framgångsrikt program för e-postleverans.

**Leveransgraden** är antalet meddelanden som når mottagarnas inkorgar jämfört med antalet meddelanden som levererats. Det beror på flera faktorer, särskilt:

* Begränsade skräppostklagomål
* Låga studsfrekvenser
* Kvaliteten på måladresserna
* Meddelandeinnehåll
* Avsändarens rykte

För att optimera leveransen av dina [!DNL Journey Optimizer]-upplevelser rekommenderar vi att du använder de bästa metoderna som listas i det här avsnittet. Leveransproblem är i allmänhet kopplade till skydd mot skräppost som implementeras av Internet-leverantörer och e-postserveradministratörer.

En djupdykning i vad som kan levereras och mer information om viktiga termer, begrepp och tillvägagångssätt för leverans finns i [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=sv){target="_blank"}.

## Minska antalet klagomål {#reduce-complaint-rate}

Internetleverantörer har vanligtvis ett framträdande sätt att rapportera ett mottaget meddelande som skräppost. Detta gör det möjligt att identifiera otillförlitliga källor. Genom att snabbt följa avanmälningsbegäranden och därmed visa att du är en tillförlitlig avsändare kan ni minska antalet klagomål. [Läs mer om hantering av avanmälan](../privacy/opt-out.md#opt-out-decision-management)

Som allmän regel ska du inte försöka hindra mottagare som vill avanmäla sig genom att kräva att de fyller i fält som e-postadress eller namn, till exempel. Startsidan för den sista prenumerationen bör bara ha en valideringsknapp.

Betala extra försiktighet när du begär ytterligare bekräftelse: en användare kan ha två e-postadresser omdirigerade till samma ruta (till exempel: firstname.lastname@club.com och firstname.lastname@internet-club.com). Om profilen bara kommer ihåg den första adressen och vill avbeställa prenumerationen via ett meddelande som skickas till den andra, kommer formuläret att avslå detta eftersom den krypterade identifieraren och den angivna e-postadressen inte matchar.

## Utnyttja undertryckningslistor {#suppression-lists}

[!DNL Journey Optimizer] hanterar en undertryckningslista som samlar in skräppostklagomål, hårda studsar och mjuka studsar som sker på ett konsekvent sätt.

För att skydda leveransen utesluts de mottagare vars adresser finns med i listan över undertryckningar som standard från alla framtida leveranser, eftersom det kan skada ditt sändningsanseende om du skickar till dessa kontakter.

[Läs mer om listan över inaktiveringar](suppression-list.md)

## Använd övervakningsverktyg {#monitoring-tools}

Använd rapportfunktionerna från [!DNL Journey Optimizer] för att övervaka din leveransbarhet.

Med kampanjrapporter och reserapporter kan ni kontrollera hur era leveranser fungerar med hjälp av en uppsättning realtidsindikatorer. De visar bland annat:

* Antalet meddelanden som har körts, skickats och levererats.
* Antalet meddelanden som har öppnats och antalet meddelanden/länkar som har klickats.

Läs mer om [live-rapport](../reports/live-report.md) och [heltidsrapport](../reports/report-gs-cja.md)

## Anpassa meddelandeinnehåll {#adapt-message-content}

I mindre utsträckning kan innehållet i vissa meddelanden identifieras som skräppost.

Om du vill förbättra leveransgraden och se till att dina e-postmeddelanden når dina mottagare ska du följa principerna nedan när du utformar meddelandeinnehållet:

* **Avsändarens namn och adress**: Adressen måste explicit identifiera avsändaren. Domänen måste ägas av och registreras hos avsändaren. Domänregistret får inte privatiseras.

* **Avbeställ länk- och landningssida**: Avbeställningslänken är viktig. Den måste vara synlig och giltig och formuläret måste vara funktionellt.

[Läs mer om hur du utformar e-postinnehåll](../email/get-started-email-design.md)

## Ange ditt rykte som avsändare {#reputation}

Om du nyligen har flyttat till en annan e-postleverantör, IP-adress, e-postdomän eller underdomän måste du ange ditt rykte som avsändare. Annars kan leveranserna blockeras eller flyttas till skräppostmappen i mottagarens postlåda.

När du skickar e-post till en helt ny IP-adress kan du nu enkelt utföra arbetsflöden för IP-värmare direkt från användargränssnittet.

Adobe Journey Optimizer erbjuder ett standardiserat och effektivt sätt att värma upp era IP-adresser som följer de bästa metoderna för optimal leverans.

[Läs mer om planer för IP-värmare](../configuration/ip-warmup-gs.md)

<!--To warm up your IP, you can gradually ramp up the number of your deliveries. Learn more in this [use case](../building-journeys/ramp-up-deliveries-uc.md).-->

## Implementera DMARC {#dmarc}

För att minska risken för att legitima e-postmeddelanden markeras som skräppost eller avvisas, och för att förhindra leveransproblem, kan du med [!DNL Journey Optimizer] konfigurera DMARC-posten för alla underdomäner som du delegerar till Adobe.

Domänbaserad meddelandeautentisering, rapportering och överensstämmelse (DMARC) är en e-postautentiseringsmetod som gör att domänägare kan skydda sin domän från obehörig användning av skadliga aktörer.

[Läs mer om inspelning av DMARC](../configuration/dmarc-record.md)

## Lär dig mer om feedback-loopar {#feedback-loops}

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain_list"
>title="Vissa underdomäner kanske inte är tillgängliga"
>abstract="Vissa underdomäner är för närvarande inte tillgängliga för val på grund av väntande registrering av feedbackloop. Den här processen kan ta upp till 10 arbetsdagar. När du är klar kan du välja bland alla tillgängliga underdomäner."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/delegate-subdomains/about-subdomain-delegation" text="Kom igång med delegering till underdomäner"

En feedbackslinga (FBL) är en tjänst som erbjuds av vissa Internet-leverantörer som gör att e-postavsändaren automatiskt kan meddelas när den användare som tar emot ett e-postmeddelande väljer att markera det som skräppost (kallas även för ett klagomål).

När en slutanvändare har genererat ett klagomål som skickas tillbaka till Adobe av Internet-leverantören, läggs e-postadressen automatiskt till i [listan över inaktiveringar](../reports/suppression-list.md) och tas inte med i kommande leveranser. Om du skickar e-post till användare som har markerat dem som skräppost påverkas avsändarens anseende negativt, vilket kan orsaka leveransproblem. [Läs mer om skräppostklagomål](../reports/suppression-list.md#spam-complaints)

>[!IMPORTANT]
>
>Alla Internet-leverantörer tillhandahåller inte en traditionell FBL, som Gmail. Gmail ger inte feedback på individnivå och kan inte användas för att spåra skräppostklagomål till enskilda mottagare, utan istället fokusera på aggregerad nivårapportering i sina Google Postmaster Tools. [Läs mer](https://support.google.com/a/answer/6254652?hl=en){target="_blank"}

Alla Adobe-kunder registreras automatiskt i de traditionella FBL:erna hos följande Internet-leverantörer:

* 1&amp;1

* AOL

* BlueTie

* Comcast

* Fastmail

* Gandi

* Italia Online

* La Poste

* Liberty Global (Chello, UPC, Unity Media)

* Locaweb

* Mail.RU

* Microsoft

* OpenSRS

* Rackspace

* SEZNM

* SFR

* SilverSky

* Swisscom

* Synacor

* Telecom Italia

* Telenet

* Telenor

* Telstra

* Terra

* UO

* Virgin Media

* Yahoo

* Ziggo

Adobe granskar dessa FBL:er regelbundet för att säkerställa att de senaste tillgängliga FBL:erna läggs till.

## Använd SMTP-relä {#smtp-relay}

[!DNL Journey Optimizer] använder Adobe-ägda MTA-agenter (Mail Transfer Agents) och IP-adresser för att leverera dina e-postmeddelanden till Internet-leverantörer. I vissa fall kanske du vill skicka e-postleveranser via dina egna MTA och IP-adresser, eller utföra slutgiltiga valideringar av e-postmeddelanden innan du skickar dem till mottagarna.

I det här fallet kan du välja att få dina e-postmeddelanden skickade till SMTP-servrar som din organisation är värd för i stället för att skickas direkt från Journey Optimizer till Internet-leverantörer.

>[!AVAILABILITY]
>
>SMTP-reläkapaciteten är tillgänglig vid behov - kontakta din Adobe-representant.
