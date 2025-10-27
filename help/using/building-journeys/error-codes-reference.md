---
solution: Journey Optimizer
product: journey optimizer
title: Referens för felkoder
description: Läs om vanliga felkoder i Adobe Journey Optimizer och hur du felsöker dem
feature: Journeys, Monitoring
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
keywords: fel, koder, felsökning, resa, kampanj, meddelanden
source-git-commit: bf6cc008acba9df44b239e8ac2425c9ffe700229
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 0%

---


# Referens för felkoder {#error-codes}

Adobe Journey Optimizer använder standardiserade felkoder för att hjälpa er att snabbt identifiera och lösa problem mellan resor, kampanjer och meddelandekonfigurationer. Om du förstår dessa felkoder kan du minska felsökningstiden avsevärt och få bättre kampanjprestanda.

## Om felkodsstrukturen {#error-code-structure}

Adobe Journey Optimizer-felkoder följer ett konsekvent namngivningsmönster som hjälper till att identifiera komponenten och problemtypen:

* **Tjänstprefix**: Anger vilken Adobe Journey Optimizer-tjänst som genererade felet (t.ex. CJMPTS för push-/transporttjänsten, CJMRT för körningsmiljön på resan, CJMMAS för meddelanderedigeringstjänsten)
* **Felnummer**: Unik identifierare för det specifika felvillkoret
* **HTTP-statuskod**: HTTP-standardstatuskod (t.ex. 400, 403, 422, 500)

Exempel: `CJMRT-030012-422` indikerar ett CJMRT-fel (Journey Runtime error) med felnummer 030012 och HTTP-status 422 (Unbehandlable Entity).

## Var kan du hitta felkoder? {#find-error-codes}

Felkoder visas på flera platser i Adobe Journey Optimizer:

* Rapporter och loggar för körning av resor
* Kampanjaktiveringsskärmar
* Varningar för meddelandevalidering
* Systemmeddelanden och aviseringar
* API-svar (när REST API:er används)

När ett fel inträffar bör du notera den fullständiga felkoden och eventuella tillhörande begärande-ID, eftersom dessa är viktiga för felsökning och eskalering av support.

## Vanliga felkoder efter tjänst {#error-codes-by-service}

### CJMPTS: Fel i push- och transporttjänst {#cjmpts-errors}

Dessa fel inträffar vid leverans av push-meddelanden och meddelandetransporter.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMPTS-1510-500** | Internt serverfel vid push-kanalssändning | Backend-fel i tryck/transport, providerfel eller infrastrukturfel | &#x200B;1. Kontrollera inställningarna för kanaletablering <br/>2. Verifiera att push-autentiseringsuppgifterna är giltiga<br/>3. Försök igen med åtgärden <br/>4. Om den är beständig kontaktar du Adobe Support med begärande-ID <br/><br/>**Relaterad dokumentation**: [Push-konfiguration](../push/push-configuration.md) |
| **CJMPTS-1023-500** | Internt serverfel under push-sändning/process (tredjepartsgateways) | Tillfälligt molnfel eller okänt tjänstfel | &#x200B;1. Verifiera provider-/kanalkonfiguration<br/>2. Kontrollera gatewaystatus från tredje part <br/>3. Försök igen efter några minuter<br/>4. Granska loggar för ytterligare kontext <br/><br/>**Relaterad dokumentation**: [Push-meddelanden](../push/create-push.md) |
| **CJMPTS-1310-500** | Internt fel från återgivningstjänsten (förhandsgranskning eller direktsändning) | Det gick inte att återge mallen i det föregående, vanligtvis på grund av JSON-/mallsyntaxproblem | &#x200B;1. Validera mallens syntax och struktur <br/>2. Kontrollera att alla personaliseringsvariabler är giltiga<br/>3. Använd en testnyttolast för att identifiera problemet <br/>4. Förenkla mallens komplexitet om det behövs <br/><br/>**Relaterad dokumentation**: [Meddelandemallar](../content-management/content-templates.md), [Personalization-syntax](../personalization/personalization-syntax.md) |

### CJMRT: Journey Runtime- och API-fel {#cjmrt-errors}

Dessa fel inträffar under körning, händelsebearbetning och API-åtgärder.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMRT-030012-422** | Obearbetbar entitet - misslyckades åtgärd, ogiltig händelse eller felaktig nyttolast | Ogiltiga indata (t.ex. obefintlig publik, händelse eller attribut) | &#x200B;1. Dubbelkontrollera nyttolaststrukturen för indata/händelser<br/>2. Kontrollera att refererade objekt (målgrupper, datauppsättningar) finns och är aktiva<br/>3. Verifiera att alla obligatoriska fält finns tillgängliga<br/>4. Testa med en fungerande nyttolast <br/><br/>**Relaterad dokumentation**: [Felsökning på resan](troubleshooting.md), [Händelsekonfiguration](../event/about-events.md) |
| **CJMRT-130004-400** | Felaktig begäran - felaktigt formaterad inmatning i kundnod eller kanalkonfiguration | Resursnyttolast eller konfigurationsreferenser har tagits bort/ogiltig resurs | &#x200B;1. Granska konfigurationen av resenoden <br/>. . Kontrollera att alla refererade resurser (meddelanden, målgrupper, åtgärder) finns<br/>3. Korrigera eller uppdatera brutna referenser<br/>4. Återskapa resekonfigurationen om det behövs <br/><br/>**Relaterad dokumentation**: [Reseskapande](journey-gs.md), [Anpassade åtgärder](../action/about-custom-action-configuration.md) |
| **CJMRT-000032-409** | Konflikt - resursen finns redan | Försök att skapa en resurs med duplicerat ID eller namn | &#x200B;1. Använd unika ID:n och namn för alla resurser <br/>2. Kontrollera om det finns befintliga resurser med samma identifierare <br/>3. Ta bort eller byt namn på objekt som är i konflikt <br/>4. Granska namnkonventioner <br/><br/>**Relaterad dokumentation**: [Reseversioner](journey-gs.md#journey-versions) |
| **CJMRT-170016-400** | Felaktig begäran vid konfiguration/förhandsgranskning av resan | Nödvändigt beroende eller trasig malllänk saknas för nyttolast | &#x200B;1. Verifiera att alla nödvändiga resurser är aktiva<br/>2. Kontrollera att mallar och innehållsblock har publicerats<br/>3. Kontrollera att alla beroenden är korrekt länkade<br/>4. Granska resultat av resetestläge <br/><br/>**Relaterad dokumentation**: [Testar resor](testing-the-journey.md), [Reseberoenden](journey-gs.md) |
| **CJMRT-080608-400** | Felaktig begäran i domän/kanal/delegering | Nödvändiga DNS-poster eller e-post-/SMS-konfiguration saknas | &#x200B;1. Slutför DNS-konfigurationen för e-postdomäner<br/>2. Verifiera att delegering av underdomän har slutförts<br/>3. Kör konfigurationsguiderna igen<br/>4. Tillåt tid för DNS-spridning (upp till 72 timmar)<br/><br/>**Relaterad dokumentation**: [Kanalytor](../configuration/channel-surfaces.md), [Delegering via underdomän](../configuration/delegate-subdomain.md) |
| **CJMRT-110100-500** | Internt fel vid nyttolast | Fel i backend-data/konfiguration eller konfiguration som inte stöds | &#x200B;1. Försök igen med åtgärden <br/>2. Förenkla konfigurationen om du använder avancerade funktioner<br/>3. Eskalera till Adobe Support med begärande-ID och exakt nyttolast <br/>4. Kontrollera om det finns kända fel i versionsinformationen <br/><br/>**Relaterad dokumentation**: [Felsökning på resan](troubleshooting.md) |

### CJMAS: Fel i meddelanderedigeringstjänsten {#cjmmas-errors}

Dessa fel inträffar när meddelanden, förinställningar och innehåll skapas, redigeras eller publiceras.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMAS-1149-400** | Felaktig begäran när meddelande, förinställning eller variant sparas | Obligatoriska fält saknas i meddelandet eller konfigurationen är felaktig | &#x200B;1. Fyll i alla obligatoriska fält (markerade med asterisk)<br/>2. Validera meddelande-/förinställd konfiguration<br/>3. Kontrollera fältvärdeformat och begränsningar<br/>4. Granska valideringsmeddelanden i användargränssnittet <br/><br/>**Relaterad dokumentation**: [E-postkanal](../email/get-started-email.md), [Kanalytor](../configuration/channel-surfaces.md) |
| **CJMAS-2073-422** | Enhet som inte kan bearbetas i redigering av meddelandeförinställning | Valideringsfel, fält som inte stöds eller felaktig syntax | &#x200B;1. Korrigera syntax-/fältfel enligt <br/>2. Jämför med en fungerande konfiguration<br/>3. Använd verifiering av meddelandeanvändargränssnitt innan du sparar<br/>4. Granska fältkrav i dokumentation <br/><br/>**Relaterad dokumentation**: [Meddelandeförinställningar](../configuration/channel-surfaces.md), [E-postinställningar](../email/email-settings.md) |
| **CJMAS-1300-500** | Internt fel vid meddelanderedigering | Serverkrasch på grund av infrastrukturproblem, stort innehåll eller driftstopp | &#x200B;1. Förenkla mall/innehåll (minska storlek/komplexitet)<br/>2. Försök igen med åtgärden <br/>3. Spara ditt arbete stegvis<br/>4. Om den är beständig eskalerar du till Adobe Support <br/><br/>**Relaterad dokumentation**: [Innehållsmallar](../content-management/content-templates.md) |
| **CJMAS-2001-200** | Status lyckades, men felbanderoll: länk för avanmälan saknas | Nödvändig länk för att avbryta prenumerationen saknas i e-postvarianten | &#x200B;1. Lägg till länk för avanmälan/avanmälan till alla e-postvarianter<br/>2. Kontrollera att det finns en länk i alla språkversioner<br/>3. Använd hjälpen för personalisering för att infoga länken för avanmälan <br/> 4. Testa alla varianter innan du publicerar <br/><br/>**Relaterad dokumentation**: [Hantering av avanmälan](../privacy/opt-out.md), [E-postdesign](../email/content-from-scratch.md) |
| **CJMAS-1603-403** | Ej tillåtet vid uppdatering/publicering av mall eller förinställning | Användaren saknar nödvändig behörighet/roll, eller åtgärden tillåts inte i det aktuella läget | &#x200B;1. Kontrollera att användaren har rätt behörigheter (Message Manager, Author, etc.)<br/>2. Kontrollera förinställning/mallstatus (utkast, publicerad, arkiverad)<br/>3. Begär åtkomst från administratören vid behov<br/>4. Granska produktprofiltilldelningar <br/><br/>**Relaterad dokumentation**: [Behörigheter](../administration/permissions.md), [Åtkomstkontroll](../administration/permissions-overview.md) |

### CJMCMP: Kampanjfel {#cjmcmp-errors}

Dessa fel inträffar när kampanjer skapas, konfigureras och aktiveras.

| Felkod | Beskrivning | Rotorsak | Upplösning |
|------------|-------------|-----------|-----------|
| **CJMCMP-2050-400** | Felaktig begäran om kampanjaktivering eller godkännande | Kampanjreferenser är ogiltiga/saknar princip eller segment | &#x200B;1. Granska alla kampanjnodskonfigurationer<br/>. . Verifiera att princip-/segmentlänkar är aktuella och giltiga<br/>3. Uppdatera med rätt konfiguration <br/> 4. Testa kampanjen igen före aktivering <br/><br/>**Relaterad dokumentation**: [Skapa kampanj](../campaigns/create-campaign.md), [Godkännande av kampanj](../test-approve/gs-approval.md) |

## Allmän felsökningsmetod {#troubleshooting-approach}

När du stöter på en felkod ska du följa detta systematiska tillvägagångssätt:

1. **Identifiera felet**: Observera den fullständiga felkoden, HTTP-statusen och eventuella tillhörande meddelande- eller fråge-ID:n.

2. **Hitta tjänsten**: Använd tjänstprefixet (CJMPTS, CJMRT, CJMMAS, CJMCMP) för att identifiera vilken komponent som påverkas.

3. **Kontrollera statuskoden**:
   * **400 (Ogiltig begäran)**: Granska indata och konfiguration
   * **403 (Ej tillåtet)**: Kontrollera behörigheter och åtkomsträttigheter
   * **409 (Konflikt)**: Sök efter dubbletter eller resurser som är i konflikt
   * **422 (Enhet som inte kan bearbetas)**: Verifiera data mot schemakrav
   * **500 (internt serverfel)**: Försök igen och eskalera eventuellt för att få stöd

4. **Granska de senaste ändringarna**: Överväg vad som har ändrats nyligen (reseuppdateringar, nya kampanjer, konfigurationsändringar osv.).

5. **Läs dokumentationen**: Använd länkarna i den här guiden för att få tillgång till detaljerad dokumentation om den berörda funktionen.

6. **Försök igen när det är lämpligt**: För 500-seriefel löser ett enkelt försök efter några minuter ofta övergående problem.

7. **Eskalera vid behov**: Om felet kvarstår efter följande lösningssteg kontaktar du Adobe Support med:
   * Fullständig felkod
   * ID för begäran (om tillgängligt)
   * Steg som ska återskapas
   * Relevant konfigurationsinformation

## Bästa tillvägagångssätt för att undvika vanliga fel {#best-practices}

### Aktivering före resan {#journey-best-practices}

* **Verifiera alla resurser**: Kontrollera att alla refererade målgrupper, datakällor och anpassade åtgärder är aktiva
* **Testa noggrant**: Använd testläge för att identifiera problem före publicering ([Läs mer](testing-the-journey.md))
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
* [Skyddsritningar och begränsningar](limitations.md)

## Support {#getting-support}

Om du stöter på bestående fel som inte kan åtgärdas med den här guiden:

1. **Samla in information**: Samla in felkoden, begärande-ID, tidsstämplar och steg för att återskapa
2. **Kontrollera systemstatus**: Besök [Adobe-status](https://status.adobe.com/){target="_blank"} för information om kända tjänstproblem
3. **Sökdokumentation**: [Adobe Experience League](https://experienceleague.adobe.com/docs/journey-optimizer.html?lang=sv-SE){target="_blank"} innehåller lösningar
4. **Engagemangsgrupp**: Skicka frågor i [Adobe Journey Optimizer Community](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer/ct-p/journey-optimizer){target="_blank"}
5. **Kontakta Adobe Support**: Skicka in en supportanmälan med all relevant information

>[!NOTE]
>
>Den här felkodsreferensen uppdateras kontinuerligt när nya koder identifieras och dokumenteras. Den senaste informationen finns i [Adobe Journey Optimizer Community-bloggarna](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/bg-p/journey-optimizer-blogs){target="_blank"} regelbundet.

**Relaterade ämnen**

* [Demystifiera Adobe Journey Optimizer-felkoder: Del 1](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/demystifying-adobe-journey-optimizer-error-codes-root-causes-and/ba-p/760884){target="_blank"}
* [Demystifiera Adobe Journey Optimizer-felkoder: Del 2](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/demystifying-adobe-journey-optimizer-error-codes-root-causes-and/bc-p/782661){target="_blank"}

