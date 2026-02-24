---
solution: Journey Optimizer
product: journey optimizer
title: Referens för felkoder
description: Lär dig mer om vanliga felkoder i [!DNL Adobe Journey Optimizer] och hur du felsöker dem
feature: Journeys, Monitoring
topic: Content Management
role: User
level: Intermediate
keywords: fel, koder, felsökning, resa, kampanj, meddelanden
exl-id: 84924153-1bb5-465a-b91c-797628fc816c
source-git-commit: 63fb247449dfb989b191254ec6d117a403edd29d
workflow-type: tm+mt
source-wordcount: '2383'
ht-degree: 0%

---

# Referens för felkoder {#error-codes}

[!DNL Adobe Journey Optimizer] använder standardiserade felkoder för att hjälpa dig att snabbt identifiera och lösa problem mellan resor, kampanjer och meddelandekonfigurationer. Om du förstår dessa felkoder kan du minska felsökningstiden avsevärt och få bättre kampanjprestanda.

## Om felkodsstrukturen {#error-code-structure}

[!DNL Adobe Journey Optimizer]-felkoder följer ett konsekvent namnmönster som hjälper till att identifiera komponenten och problemtypen:

* **Tjänstprefix**: Anger vilken [!DNL Adobe Journey Optimizer]-tjänst som genererade felet.
Exempel: CJMPTS (push/Transport Service), CJMRT (Journey Runtime), CJMMAS (Message Authoring Service), CJMCMP (Campaign), CJMTL (Transport Layer), CJMRPS (Reporting/Provisioning Service)
* **Felnummer**: Unik identifierare för det specifika felvillkoret
* **HTTP-statuskod**: HTTP-standardstatuskod (t.ex. 400, 403, 422, 500)

Exempel: `CJMRT-030012-422` indikerar ett CJMRT-fel (Journey Runtime error) med felnummer 030012 och HTTP-status 422 (Unbehandlable Entity).

## Var kan du hitta felkoder? {#find-error-codes}

Felkoder visas på flera platser inom [!DNL Adobe Journey Optimizer]:

* Rapporter och loggar för körning av resor
* Kampanjaktiveringsskärmar
* Varningar för meddelandevalidering
* Systemmeddelanden och aviseringar
* API-svar (när REST API:er används)

När ett fel inträffar bör du notera den fullständiga felkoden och eventuella tillhörande begärande-ID, eftersom dessa är viktiga för felsökning och eskalering av support.

## Vanliga felkoder efter tjänst {#error-codes-by-service}

Använd det här avsnittet för att hitta felkoder grupperade efter tjänst.

### CJMPTS: Fel i push- och transporttjänst {#cjmpts-errors}

Dessa fel inträffar vid leverans av push-meddelanden och meddelandetransporter.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMPTS-1410-500** | Internt serverfel vid push/channel-sändningsåtgärd | Kanalserveravbrott, utgångna autentiseringsuppgifter, felkonfigurering eller providerfel | &#x200B;1. Försök igen efter fördröjning<br/>2. Kontrollera providerkonfigurationer och kvoter <br/>3. Verifiera att push-autentiseringsuppgifterna är giltiga<br/>4. Testa med en alternativ kanal <br/>5. Om den är beständig kontaktar du Adobe Support med begärande-ID <br/><br/>**Relaterad dokumentation**: [Push-konfiguration](../push/push-configuration.md) |
| **CJMPTS-1006-404** | Push/SMS misslyckas med resursen hittades inte | Den refererade providern/kanalen finns inte, är felstavad eller har deetablerats | &#x200B;1. Granska och korrigera provider/kanalreferenser och ID:n<br/>2. Granska sandlådan/organisationskonfigurationen<br/>3. Verifiera att kanalkonfigurationerna är aktiva<br/>4. Skapa om kanalkonfigurationen om det behövs <br/><br/>**Relaterad dokumentation**: [Kanalytor](../configuration/channel-surfaces.md) |
| **CJMPTS-1510-500** | Internt serverfel vid push-kanalssändning | Backend-fel i tryck/transport, providerfel eller infrastrukturfel | &#x200B;1. Kontrollera inställningarna för kanaletablering <br/>2. Verifiera att push-autentiseringsuppgifterna är giltiga<br/>3. Försök igen med åtgärden <br/>4. Om den är beständig kontaktar du Adobe Support med begärande-ID <br/><br/>**Relaterad dokumentation**: [Push-konfiguration](../push/push-configuration.md) |
| **CJMPTS-1023-500** | Internt serverfel under push-sändning/process (tredjepartsgateways) | Tillfälligt molnfel eller okänt tjänstfel | &#x200B;1. Verifiera provider-/kanalkonfiguration<br/>2. Kontrollera gatewaystatus från tredje part <br/>3. Försök igen efter några minuter<br/>4. Granska loggar för ytterligare kontext <br/><br/>**Relaterad dokumentation**: [Push-meddelanden](../push/create-push.md) |
| **CJMPTS-1310-500** | Internt fel från återgivningstjänsten (förhandsgranskning eller direktsändning) | Det gick inte att återge mallen i det föregående, vanligtvis på grund av JSON-/mallsyntaxproblem | &#x200B;1. Validera mallens syntax och struktur <br/>2. Kontrollera att alla personaliseringsvariabler är giltiga<br/>3. Använd en testnyttolast för att identifiera problemet <br/>4. Förenkla mallens komplexitet om det behövs <br/><br/>**Relaterad dokumentation**: [Meddelandemallar](../content-management/content-templates.md), [Personalization-syntax](../personalization/personalization-syntax.md) |

### CJMRT: Journey Runtime- och API-fel {#cjmrt-errors}

Dessa fel inträffar under körning, händelsebearbetning och API-åtgärder.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMRT-110001-500** | Maximalt antal körningar har överskridits för arbetsflödessteg (t.ex. timeout för IP-tillhörighetsetablering) | Arbetsflödes-/provisioneringsjobbet slutfördes inte inom tillåtna återförsök/tid, ofta på grund av infrastrukturs-/tjänstfördröjning eller tillfälligt serverdelsproblem | &#x200B;1. Försök igen efter en tid.<br/>2. Kontrollera [Adobe-status](https://status.adobe.com/) om det finns avbrott<br/>3. Eskalera till Adobe Support med information om arbetsflöde, jobb och organisation<br/>4. Ange loggar och nätverksinhämtningar om de är tillgängliga <br/><br/>**Relaterad dokumentation**: [Felsökning av resan](troubleshooting.md) |
| **CJMRT-00071-400** | Felaktig begäran under resa/testhändelse eller API-anrop | Nyttolasten/parametrarna har fel format eller saknas. Indata refererar till en icke-existerande eller inaktiv resurs | &#x200B;1. Granska texten i begäran för felinformation<br/>2. Korrigera referens/parameter<br/>3. Ta bort avancerad konfiguration och försök igen<br/>4. Lägg till funktioner en i taget för att identifiera problemet <br/><br/>**Relaterad dokumentation**: [Felsökning på resan](troubleshooting.md), [Konfiguration av händelser](../event/about-events.md) |
| **CJMRT-000013-401** | Oauktoriserat fel under meddelandekörning/API-händelse | Autentiseringsfel: token har upphört att gälla, behörigheter saknas eller så har integreringen/användaren förlorat miljöåtkomst | &#x200B;1. Verifiera behörigheter och roller<br/>2. Uppdatera autentiseringstoken<br/>3. Använd ett känt användar-/tjänstkonto<br/>4. Granska produktprofiltilldelningar <br/><br/>**Relaterad dokumentation**: [Behörigheter](../administration/permissions.md) |
| **CJMRT-080605-400** | Felaktig begäran från körningsmiljön (t.ex. nodutlösare, åtgärd) | Konfigurationen refererar till en borttagen/namnändrad eller inaktuell funktion/mall/kanal | &#x200B;1. Verifiera alla resursreferenser<br/>2. Granska konfigurationen av resan och funktionsflaggor<br/>3. Uppdatera brutna referenser<br/>4. Granska senaste systemuppdateringar och migreringar <br/><br/>**Relaterad dokumentation**: [Reseskapande](journey-gs.md) |
| **CJMRT-030012-422** | Obearbetbar entitet - misslyckades åtgärd, ogiltig händelse eller felaktig nyttolast | Ogiltiga indata (t.ex. obefintlig publik, händelse eller attribut) | &#x200B;1. Dubbelkontrollera nyttolaststrukturen för indata/händelser<br/>2. Kontrollera att refererade objekt (målgrupper, datauppsättningar) finns och är aktiva<br/>3. Verifiera att alla obligatoriska fält finns tillgängliga<br/>4. Testa med en fungerande nyttolast <br/><br/>**Relaterad dokumentation**: [Felsökning på resan](troubleshooting.md), [Händelsekonfiguration](../event/about-events.md) |
| **CJMRT-130004-400** | Felaktig begäran - felaktigt formaterad inmatning i kundnod eller kanalkonfiguration | Resursnyttolast eller konfigurationsreferenser har tagits bort/ogiltig resurs | &#x200B;1. Granska konfigurationen av resenoden <br/>. . Kontrollera att alla refererade resurser (meddelanden, målgrupper, åtgärder) finns<br/>3. Korrigera eller uppdatera brutna referenser<br/>4. Återskapa resekonfigurationen om det behövs <br/><br/>**Relaterad dokumentation**: [Reseskapande](journey-gs.md), [Anpassade åtgärder](../action/about-custom-action-configuration.md) |
| **CJMRT-000032-409** | Konflikt - resursen finns redan | Försök att skapa en resurs med duplicerat ID eller namn | &#x200B;1. Använd unika ID:n och namn för alla resurser <br/>2. Kontrollera om det finns befintliga resurser med samma identifierare <br/>3. Ta bort eller byt namn på objekt som är i konflikt <br/>4. Granska namnkonventioner <br/><br/>**Relaterad dokumentation**: [Reseskapande](journey-gs.md) |
| **CJMRT-170016-400** | Felaktig begäran vid konfiguration/förhandsgranskning av resan | Nödvändigt beroende eller trasig malllänk saknas för nyttolast | &#x200B;1. Verifiera att alla nödvändiga resurser är aktiva<br/>2. Kontrollera att mallar och innehållsblock har publicerats<br/>3. Kontrollera att alla beroenden är korrekt länkade<br/>4. Granska resultat av resetestläge <br/><br/>**Relaterad dokumentation**: [Testar resor](testing-the-journey.md), [Reseberoenden](journey-gs.md) |
| **CJMRT-080608-400** | Felaktig begäran i domän/kanal/delegering | Nödvändiga DNS-poster eller e-post-/SMS-konfiguration saknas | &#x200B;1. Slutför DNS-konfigurationen för e-postdomäner<br/>2. Verifiera att delegering av underdomän har slutförts<br/>3. Kör konfigurationsguiderna igen<br/>4. Tillåt tid för DNS-spridning (upp till 72 timmar)<br/><br/>**Relaterad dokumentation**: [Kanalytor](../configuration/channel-surfaces.md), [Delegering via underdomän](../configuration/delegate-subdomain.md) |
| **CJMRT-110100-500** | Internt fel vid nyttolast | Fel i backend-data/konfiguration eller konfiguration som inte stöds | &#x200B;1. Försök igen med åtgärden <br/>2. Förenkla konfigurationen om du använder avancerade funktioner<br/>3. Eskalera till Adobe Support med begärande-ID och exakt nyttolast <br/>4. Kontrollera om det finns kända fel i versionsinformationen <br/><br/>**Relaterad dokumentation**: [Felsökning på resan](troubleshooting.md) |

### CJMAS: Fel i meddelanderedigeringstjänsten {#cjmmas-errors}

Dessa fel inträffar när meddelanden, förinställningar och innehåll skapas, redigeras eller publiceras.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMAS-1732-500** | Beviset misslyckades - Alla resurser som inte publicerades när du skickade korrektur/test med AEM-mediefil | Den nyligen publicerade resursen finns inte i AJO ännu; fel i resurs-ID; korsrepoanvändning; AEM synkroniseringsfördröjning | &#x200B;1. Använd bara publicerade resurs-ID:n från rätt databas/miljö<br/>2. Tillåt synkroniseringstid mellan AEM och AJO<br/>3. Försök igen med en känd bra resurs <br/>4. Verifiera publiceringsstatus för resurser i AEM <br/><br/>**Relaterad dokumentation**: [Assets-integrering](../integrations/assets.md) |
| **CJMAS-1069-500** | Internt fel när meddelandemallen sparades eller publicerades | Backend-undantag (infrastrukturfel/tjänstfel eller innehållsproblem); kod/funktion som inte stöds | &#x200B;1. Förenkla eller minska mallens komplexitet<br/>2. Lägg till innehåll igen i steg för att identifiera problemet <br/>3. Kontrollera [Adobe-statussidan](https://status.adobe.com/)<br/>4. Ta bort funktioner eller markeringar som inte stöds <br/><br/>**Relaterad dokumentation**: [Innehållsmallar](../content-management/content-templates.md) |
| **CJMAS-1149-400** | Felaktig begäran när meddelande, förinställning eller variant sparas | Obligatoriska fält saknas i meddelandet eller konfigurationen är felaktig | &#x200B;1. Fyll i alla obligatoriska fält (markerade med asterisk)<br/>2. Validera meddelande-/förinställd konfiguration<br/>3. Kontrollera fältvärdeformat och begränsningar<br/>4. Granska valideringsmeddelanden i användargränssnittet <br/><br/>**Relaterad dokumentation**: [E-postkanal](../email/get-started-email.md), [Kanalytor](../configuration/channel-surfaces.md) |
| **CJMAS-2073-422** | Enhet som inte kan bearbetas i redigering av meddelandeförinställning | Valideringsfel, fält som inte stöds eller felaktig syntax | &#x200B;1. Korrigera syntax-/fältfel enligt <br/>2. Jämför med en fungerande konfiguration<br/>3. Använd verifiering av meddelandeanvändargränssnitt innan du sparar<br/>4. Granska fältkrav i dokumentation <br/><br/>**Relaterad dokumentation**: [Meddelandeförinställningar](../configuration/channel-surfaces.md), [E-postinställningar](../email/email-settings.md) |
| **CJMAS-1300-500** | Internt fel vid meddelanderedigering | Serverkrasch på grund av infrastrukturproblem, stort innehåll eller driftstopp | &#x200B;1. Förenkla mall/innehåll (minska storlek/komplexitet)<br/>2. Försök igen med åtgärden <br/>3. Spara ditt arbete stegvis<br/>4. Om den är beständig eskalerar du till Adobe Support <br/><br/>**Relaterad dokumentation**: [Innehållsmallar](../content-management/content-templates.md) |
| **CJMAS-2001-200** | Status lyckades, men felbanderoll: länk för avanmälan saknas | Nödvändig länk för att avbryta prenumerationen saknas i e-postvarianten | &#x200B;1. Lägg till länk för avanmälan/avanmälan till alla e-postvarianter<br/>2. Kontrollera att det finns en länk i alla språkversioner<br/>3. Använd hjälpen för personalisering för att infoga länken för avanmälan <br/> 4. Testa alla varianter innan du publicerar <br/><br/>**Relaterad dokumentation**: [Hantering av avanmälan](../privacy/opt-out.md), [E-postdesign](../email/content-from-scratch.md) |
| **CJMAS-1603-403** | Ej tillåtet vid uppdatering/publicering av mall eller förinställning | Användaren saknar nödvändig behörighet/roll, eller åtgärden tillåts inte i det aktuella läget | &#x200B;1. Kontrollera att användaren har rätt behörigheter (Message Manager, Author, etc.)<br/>2. Kontrollera förinställning/mallstatus (utkast, publicerad, arkiverad)<br/>3. Begär åtkomst från administratören vid behov<br/>4. Granska produktprofiltilldelningar <br/><br/>**Relaterad dokumentation**: [Behörigheter](../administration/permissions.md), [Åtkomstkontroll](../administration/permissions-overview.md) |

### CJMCMP: Kampanjfel {#cjmcmp-errors}

Dessa fel inträffar när kampanjer skapas, konfigureras och aktiveras.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMCMP-6003-400** | &quot;Det finns minst en felaktig kampanj&quot; vid publicering/testläge, resa/meddelande | Noden refererar till en saknad, opublicerad eller ogiltig kampanj. Äldre eller klonad resa skapar inte infogade länkar | &#x200B;1. Öppna varje meddelandenod och verifiera konfigurationen<br/>. . Länka om eller lägg till om meddelandenoder<br/>3. Aktivera testläge om du vill framtvinga skapande av infogade kampanjer <br/>. Gå till den nya reseguiden om det ofta uppstår problem <br/><br/>**Relaterad dokumentation**: [Reseskapande](journey-gs.md), [Testa resor](testing-the-journey.md) |
| **CJMCMP-2003-400** | Gränssnittsbanderoll: &quot;Experimentet är felaktigt&quot; i e-post-Designer | Inaktuell eller saknad experimentell leverantör/dataleverantör; misslyckades med experimentell rensning, felaktig schemaläggning eller gränssnittsvalideringsfel | &#x200B;1. Ta bort oanvända experimentfält<br/>2. Validera schema- och dataleverantörsanslutningar<br/>3. Läs in användargränssnittet igen och rensa webbläsarcachen<br/>4. Återskapa nod/e-post om problemet är olöst <br/><br/>**Relaterad dokumentation**: [Innehållsexperiment](../content-management/content-experiment.md) |
| **CJMCMP-3001-400** | Simulering/förhandsvisning av&quot;felaktigt filter för yttyp&quot; | Nod som skapats med äldre struktur skickar type=surfaceId, backend förväntar sig brandingPresetId | &#x200B;1. Ta bort och återskapa den påverkade noden <br/>2. Använd den nya reseversionen/mallen<br/>3. Använd testläge för att rensa konfigurationen <br/> . Återskapa noder gruppvis om problemet är utbrett <br/><br/>**Relaterad dokumentation**: [Kanalytor](../configuration/channel-surfaces.md), [Meddelandesimulering](../content-management/preview.md) |
| **CJMCMP-2050-400** | Felaktig begäran om kampanjaktivering eller godkännande | Kampanjreferenser är ogiltiga/saknar princip eller segment | &#x200B;1. Granska alla kampanjnodskonfigurationer<br/>. . Verifiera att princip-/segmentlänkar är aktuella och giltiga<br/>3. Uppdatera med rätt konfiguration <br/> 4. Testa kampanjen igen före aktivering <br/><br/>**Relaterad dokumentation**: [Skapa kampanj](../campaigns/create-campaign.md), [Godkännande av kampanj](../test-approve/gs-approval.md) |

### CJMTL: Fel i transportlager {#cjmtl-errors}

Dessa fel inträffar under meddelandetransport och leverans.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMTL-010018-422** | &quot;Personalization tillåts inte i domännamn&quot; när innehåll sparas/skickas | Överdrivet strikt validering orsakade tillfälligt dynamisk href-domänpersonalisering | &#x200B;1. Reaktorlänkar om domänvariabler <br/> används. Kontrollera att den senaste AJO-versionen används<br/>3. Försök igen med åtgärden <br/>4. Använd statiska domäner om problemet kvarstår <br/><br/>**Relaterad dokumentation**: [Personalization-syntax](../personalization/personalization-syntax.md), [E-postdesign](../email/content-from-scratch.md) |
| **CJMTL-010011-422** | Obearbetbar entitet - Skicka/SMS/E-post misslyckas, säger&quot;ogiltigt fält&quot; | Nyttolast eller mottagar-/kontaktdata saknas eller är ogiltiga | &#x200B;1. Sök i loggarna efter specifika fältfel<br/>2. Korrigera profil-/kontaktinformation<br/>3. Validera med testprofil <br/> 4. Nyttolastformatet för reaktorn efter behov <br/><br/>**Relaterad dokumentation**: [Profilhantering](../audience/get-started-profiles.md), [Testprofiler](../audience/creating-test-profiles.md) |

### CJMRPS: Rapporterings- och provisioneringstjänstfel {#cjmrps-errors}

Dessa fel inträffar vid konfiguration av rapporter och provisionering av datauppsättningar.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMRPS-1047-409** | &quot;Konflikt. Datauppsättningen har redan lagts till när rapportdatauppsättningen lades till | Försöker lägga till en datauppsättning som redan har etablerats | &#x200B;1. Granska datauppsättningskonfigurationen i rapportinställningarna<br/>2. Lägg inte till datamängder som redan finns<br/>3 igen. Använd checklistor för officiell migrering för att rapportera migrering <br/>4. Ta bort dubblettdatamängdsreferenser <br/><br/>**Relaterad dokumentation**: [Rapporteringsöversikt](../reports/gs-reports.md), [Kampanjrapporter](../reports/campaign-global-report-cja.md), [Resursrapporter](../reports/journey-global-report-cja.md) |

## Allmän felsökningsmetod {#troubleshooting-approach}

När du stöter på en felkod ska du följa detta systematiska tillvägagångssätt:

1. **Identifiera felet**: Observera den fullständiga felkoden, HTTP-statusen och eventuella tillhörande meddelande- eller fråge-ID:n.

2. **Hitta tjänsten**: Använd tjänstprefixet (CJMPTS, CJMRT, CJMMAS, CJMCMP, CJMTL, CJMRPS) för att identifiera vilken komponent som påverkas.

3. **Kontrollera statuskoden**:
   * **400 (Ogiltig begäran)**: Granska indata och konfiguration
   * **403 (Ej tillåtet)**: Kontrollera behörigheter och åtkomsträttigheter
   * **409 (Konflikt)**: Sök efter dubbletter eller resurser som är i konflikt
   * **422 (Enhet som inte kan bearbetas)**: Verifiera data mot schemakrav
   * **500 (internt serverfel)**: Försök igen och eskalera eventuellt för att få stöd

4. **Granska de senaste ändringarna**: Överväg vad som har ändrats nyligen (reseuppdateringar, nya kampanjer, konfigurationsändringar osv.).

5. **Läs dokumentationen**: Använd länkarna i den här guiden för att få tillgång till detaljerad dokumentation om den berörda funktionen.

6. **Försök igen när det är lämpligt**: För 500-seriefel löser ett enkelt försök efter några minuter ofta övergående problem.

7. **Eskalera vid behov**: Om felet kvarstår efter följande lösningssteg, [kontaktar du Adobe Support](../start/user-interface.md#support-ticket-guidelines) med den fullständiga felkoden, ID för begäran (om tillgängligt), steg för att återskapa samt relevant konfigurationsinformation.

## Bästa tillvägagångssätt för att undvika vanliga fel {#best-practices}

Använd dessa metoder för att minska antalet fel som kan undvikas och förbättra tillförlitligheten.

### Aktivering före resan {#journey-best-practices}

* **Verifiera alla resurser**: Kontrollera att alla refererade målgrupper, händelser, datakällor och anpassade åtgärder är korrekt konfigurerade
* **Testa noggrant**: Använd testläge för att identifiera problem före publicering ([Läs mer](testing-the-journey.md))
* **Verifiera volymer**: Använd torr körning för att validera målgruppens räckvidd och grenlogik innan du aktiverar ([Läs mer](journey-dry-run.md))
* **Kontrollera behörigheter**: Kontrollera att du har nödvändiga åtkomstbehörigheter för alla komponenter
* **Granska beroenden**: Se till att alla länkade meddelanden och allt innehåll publiceras

### När meddelanden skapas {#message-best-practices}

* **Fyll i obligatoriska fält**: Fyll alltid i alla obligatoriska fält innan du sparar
* **Inkludera länkar för avanmälan**: Lägg till länkar för avanmälan till alla e-postvarianter ([Läs mer](../privacy/opt-out.md))
* **Verifiera personalisering**: Testa allt dynamiskt innehåll med exempelprofiler ([Läs mer](../personalization/personalization-build-expressions.md))
* **Behåll mallar hanterbara**: Undvik alltför komplexa mallar som kan orsaka återgivningsproblem

### För kampanjhantering {#campaign-best-practices}

* **Verifiera målgruppsdata**: Kontrollera att målgrupperna är korrekt konfigurerade och ifyllda
* **Kontrollera godkännandestatus**: Förstå godkännandekraven innan du försöker aktivera ([Läs mer](../test-approve/gs-approval.md))
* **Bildskärmskonfigurationer**: Granska regelbundet kanalytor och förinställningar för giltighet
* **Planera DNS-ändringar**: Tillåt tillräckligt med tid för DNS-spridning vid uppdatering av domäner

## Ytterligare resurser {#additional-resources}

* [Felsökning av resor](troubleshooting.md)
* [Felsökning av körning](troubleshooting-execution.md)
* [Felsökning av inkommande aktiviteter](troubleshooting-inbound.md)
* [Felsökning av anpassade åtgärder](../action/troubleshoot-custom-action.md)
* [Vanliga frågor om resan](journey-faq.md)
* [Skyddsritningar och begränsningar](../start/guardrails.md)

## Support {#getting-support}

Om du stöter på bestående fel som inte kan åtgärdas med den här guiden:

1. **Samla in information**: Samla in felkoden, begärande-ID, tidsstämplar och steg för att återskapa
2. **Kontrollera systemstatus**: Besök [Adobe-status](https://status.adobe.com/){target="_blank"} för information om kända tjänstproblem
3. **Sökdokumentation**: [Adobe Experience League](https://experienceleague.adobe.com/docs/journey-optimizer.html){target="_blank"} innehåller lösningar
4. **Engagemangsgrupp**: Skicka frågor i [[!DNL Adobe Journey Optimizer] community](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer/ct-p/journey-optimizer){target="_blank"}
5. **Kontakta Adobe Support**: [Skicka in en supportanmälan](../start/user-interface.md#support-ticket-guidelines) med all relevant information

>[!NOTE]
>
>Den här felkodsreferensen uppdateras kontinuerligt när nya koder identifieras och dokumenteras. Den senaste informationen finns i [[!DNL Adobe Journey Optimizer] Community-bloggarna](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/bg-p/journey-optimizer-blogs){target="_blank"} regelbundet.

**Relaterade ämnen**

* [Demystifiera [!DNL Adobe Journey Optimizer] Felkoder: Del 1](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/demystifying-adobe-journey-optimizer-error-codes-root-causes-and/ba-p/760884){target="_blank"}
* [Demystifiera [!DNL Adobe Journey Optimizer] Felkoder: Del 2](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/demystifying-adobe-journey-optimizer-error-codes-root-causes-and/bc-p/782661){target="_blank"}
