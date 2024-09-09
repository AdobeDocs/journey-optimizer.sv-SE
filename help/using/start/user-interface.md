---
solution: Journey Optimizer
product: journey optimizer
title: Användargränssnitt
description: Läs mer om Journey Optimizer användargränssnitt
feature: Overview, Get Started
topic: Content Management
role: User
level: Intermediate
exl-id: 681532f8-1149-465e-92c8-2b5366abc3aa
source-git-commit: 9c6e4647b1c3f0b39ebfaa1711c5c87d0c7168e5
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 4%

---

# Användargränssnitt {#cjm-user-interface}

Om du vill komma åt [!DNL Adobe Journey Optimizer] ansluter du till [Adobe Experience Cloud](https://experience.adobe.com) med din Adobe ID och väljer [!DNL Journey Optimizer].

De viktigaste begreppen när du bläddrar i användargränssnittet är vanliga i Adobe Experience Platform. Mer information finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-ui/ui-guide.html#adobe-experience-platform-ui-guide){target="_blank"}.

Vilka komponenter och funktioner som är tillgängliga i användargränssnittet beror på dina [behörigheter](../administration/permissions.md) och ditt [licenspaket](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}. Fråga din Adobe Customer Success Manager för alla frågor.

>[!NOTE]
>
>Den här dokumentationen uppdateras ofta för att återspegla de senaste ändringarna i produktanvändargränssnittet. Vissa skärmbilder kan dock skilja sig något från användargränssnittet.

## Vänster navigering {#left-nav}

Bläddra bland länkarna till vänster för att komma åt [!DNL Journey Optimizer]-funktioner.

![](assets/ajo-home.png)

>[!NOTE]
>
>Tillgängliga funktioner kan variera beroende på dina behörigheter och licensavtal.

Nedan finns en fullständig lista över tjänster och funktioner som är tillgängliga i den vänstra navigeringen samt länkar till tillhörande hjälpsidor.

### Startsida {#left-nav-home}

Startsidan för [!DNL Journey Optimizer] innehåller nyckellänkar och resurser som ska startas.

Listan **[!UICONTROL Recents]** innehåller genvägar till nyligen skapade händelser och resor. Den här listan visar datum och status för när de skapades och ändrades.

Bläddra bland användningsexempel i produkten för att börja skapa resurser och meddelanden. [Läs mer](#in-product-use-cases).

Använd länkarna längst ned på startsidan för att lära dig hur du börjar med [!DNL Journey Optimizer]. [Läs mer](#find-help-and-support).

### [!UICONTROL JOURNEY MANAGEMENT] {#left-nav-journey}

Bygg kampanjer och resor från det här avsnittet.

* **[!UICONTROL Campaigns]** - Skapa, konfigurera och orkestrera kampanjer för att leverera engångsinnehåll till en viss målgrupp via olika kanaler. [Läs mer](../campaigns/get-started-with-campaigns.md)

* **[!UICONTROL Journeys]** - Skapa, konfigurera och samordna dina kundresor: kombinera händelser, samordning och åtgärdsaktiviteter för att skapa flerstegsscenarier för flera kanaler. [Läs mer](../building-journeys/journey-gs.md#jo-build)

* **[!UICONTROL Landing pages]** - Skapa, utforma, testa och publicera landningssidor: skicka länkar till onlineformulär där användarna kan välja att inte ta emot meddelanden eller prenumerera på vissa tjänster. [Läs mer](../landing-pages/get-started-lp.md)


### [!UICONTROL DECISION MANAGEMENT] {#left-nav-offers}

Skapa erbjudanden och komponenter från det här avsnittet.

* **[!UICONTROL Offers]** - Använd dina senaste källor och datauppsättningar från den här menyn. Använd det här avsnittet för att skapa erbjudanden. [Läs mer](../offers/offer-library/creating-personalized-offers.md)

* **[!UICONTROL Components]** - Skapa placeringar, regler och taggar. [Läs mer](../offers/offer-library/key-steps.md)

### [!UICONTROL CONTENT MANAGEMENT] {#left-nav-content}

Skapa och hantera innehåll från det här avsnittet.

* **[!UICONTROL Assets]** - [!DNL Adobe Experience Manager Assets] är en central databas med resurser som du kan använda för att fylla i dina meddelanden. [Läs mer](../content-management/assets.md)

* **[!UICONTROL Content templates]** - Skapa fristående mallar för att enkelt återanvända anpassat innehåll i Journey Optimizer kampanjer och resor för en snabbare och bättre designprocess. [Läs mer](../content-management/content-templates.md)

* **[!UICONTROL Fragments]** - Skapa och hantera fragment för att underlätta e-postdesignprocessen: skapa anpassade innehållsblock som kan användas för att snabbt sammanställa e-postinnehåll. [Läs mer](../content-management/fragments.md)

### [!UICONTROL DATA MANAGEMENT] {#left-nav-data}

Hantera data från det här avsnittet.

* **[!UICONTROL Schemas]** - Använd Adobe Experience Platform för att skapa och hantera XDM-scheman (Experience Data Model) på en interaktiv visuell arbetsyta som kallas Schemaredigeraren. [Läs mer](../data/get-started-schemas.md)

* **[!UICONTROL Datasets]** - Alla data som importeras till Adobe Experience Platform lagras i Data Lake som datauppsättningar. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader). [Läs mer](../data/get-started-datasets.md)

* **[!UICONTROL Queries]** - Använd Adobe Experience Platform Query Service för att skriva och köra frågor, visa frågor som har körts tidigare och få åtkomst till frågor som har sparats av användare i din organisation. [Läs mer](../data/get-started-queries.md)

* **[!UICONTROL Monitoring]** - Använd den här menyn för att övervaka din datainmatning i Adobe Experience Platform användargränssnitt. Läs mer i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/quality/monitor-data-ingestion.html){target="_blank"}

### [!UICONTROL CONNECTIONS] {#left-nav-connections}

Hantera dataanslutningar med andra appar och moln i det här avsnittet.

* **[!UICONTROL Sources]** - Använd den här menyn om du vill importera data från en mängd olika källor, till exempel Adobe-program, molnbaserade lagringsplatser, databaser med mera. Du kan strukturera, etikettera och förbättra inkommande data. [Läs mer](get-started-sources.md)

* **[!UICONTROL Destinations]** - Använd den här menyn för att skapa en liveanslutning med molnlagringsplatser för att exportera innehållet i dina datauppsättningar. [Läs mer](../data/export-datasets.md)

### [!UICONTROL CUSTOMER] {#left-nav-customers}

Hantera era målgrupper och profildata från det här avsnittet.

* **[!UICONTROL Audiences]** - Skapa och hantera målgrupper i Experience Platform och använd dem på dina resor. [Läs mer](../audience/about-audiences.md)

* **[!UICONTROL Subscription lists]** - I [!DNL Journey Optimizer] samlas kunder som har anmält sig till en prenumerationstjänst in i en prenumerationslista. [Läs mer](../landing-pages/subscription-list.md)

* **[!UICONTROL Profiles]** - Kundprofilen i realtid skapar en helhetsbild av alla dina enskilda kunder och kombinerar data från flera kanaler, inklusive online-, offline-, CRM- och tredjepartsdata. [Läs mer](../audience/get-started-profiles.md)

* **[!UICONTROL Identities]** - Adobe Experience Platform Identity Service hanterar identifieringen av dina kunder i realtid av olika enheter, kanaler och nära nog alla kanaler i det som kallas identitetsdiagram inom Adobe Experience Platform. [Läs mer](../audience/get-started-identity.md)

### [!UICONTROL PRIVACY] {#left-nav-privacy}

Styr din sekretesshantering och dina förfrågningar från det här avsnittet.

* **[!UICONTROL Policies]** - Med Adobe Experience Platform kan du etikettera dina fält och skapa marknadsföringsåtgärder för varje kanal. Sedan definierar ni en styrningspolicy som är kopplad till en etikett och en marknadsföringsåtgärd. [Läs mer](../action/action-privacy.md)

* **[!UICONTROL Requests]** - Sekretessbegäranden hanteras i Adobe Experience Platform Privacy Service. Det innehåller ett RESTful-API och ett användargränssnitt som hjälper dig att hantera kunddataförfrågningar. [Läs mer](../privacy/requests.md)

* **[!UICONTROL Audit]** - Bläddra till det här avsnittet för att kontrollera aktivitetsloggar. [Läs mer](../privacy/audit-logs.md)

* **[!UICONTROL Data hygiene]** - I det här avsnittet kan du konfigurera och schemalägga dataåtgärder för hygienen så att du kan vara säker på att dina register underhålls på rätt sätt. [Läs mer](../privacy/data-hygiene.md)

### [!UICONTROL ADMINISTRATION] {#left-nav-admin}

* **[!UICONTROL Configurations]** - Använd den här menyn för att konfigurera [händelser](../event/about-events.md), [datakällor](../datasource/about-data-sources.md) och [åtgärder](../action/action.md) att använda på dina resor.

  Du kan även komma åt avsnittet **Rapportering** för att konfigurera rapportering för kampanjexperiment. [Läs mer](../content-management/reporting-configuration.md)

* **[!UICONTROL Business rules]** - Använd det här avsnittet om du vill skapa affärsregler för flera kanaler för att styra hur ofta användare tar emot ett meddelande eller deltar i en resa. [Läs mer](../configuration/frequency-rules.md)

* **[!UICONTROL Alerts]** - Med användargränssnittet kan du visa en historik över mottagna aviseringar baserat på mätvärden som visas av Adobe Experience Platform observability Insights. I gränssnittet kan du även visa, aktivera och inaktivera tillgängliga varningsregler. [Läs mer](../reports/alerts.md)

* **[!UICONTROL Sandboxes]** - Adobe Experience Platform tillhandahåller sandlådor som partitionerar en enda instans till separata virtuella miljöer för att utveckla och utveckla program för digitala upplevelser. Bläddra i det här avsnittet för att hantera dina sandlådor. [Läs mer](../administration/sandboxes.md)

* **[!UICONTROL Channels]** - Använd det här avsnittet för att konfigurera dina kanaler, inklusive underdomäner, konfigurationer och leveransinställningar. [Läs mer](../configuration/get-started-configuration.md)

* **[!UICONTROL Tags]** - Med enhetliga taggar kan du enkelt klassificera dina resor och kampanjer för att förbättra sökningen från listorna. [Läs mer](../start/search-filter-categorize.md#work-with-unified-tags)

## Användningsexempel inifrån produkten {#in-product-uc}

Från startsidan för [!DNL Adobe Journey Optimizer] tillhandahåller produktanvändningsexempel snabba indata för att skapa testprofiler eller dina första kundresor.

![](assets/use-cases-home.png)

Exempel:

* **Skapa testprofiler** om du vill skapa testprofiler med vår CSV-mall för att testa personaliserade meddelanden och resor. Lär dig hur du implementerar det här användningsfallet [på den här sidan](../audience/creating-test-profiles.md#use-case-1).
* **Skicka ett födelsedagsmeddelande till kunder** för att automatiskt skicka ett e-postmeddelande och önska dina kunder en viss födelsedag. (kommer snart)
* **Skicka e-post till nya kunder** för att enkelt skicka upp till två e-postmeddelanden till dina nyregistrerade kunder. (kommer snart)
* **Skicka push-meddelanden till importerad lista över kunder** för att snabbt skicka ett push-meddelande till en lista över kunder som importerats från en CSV-fil. (kommer snart)

Klicka på länken **[!UICONTROL View details]** om du vill veta mer om de olika användningsexemplen.

Klicka på knappen **[!UICONTROL Begin]** om du vill köra ett användningsfall.

Du kommer åt körda användningsfall från knappen **[!UICONTROL View library]**.

## Hitta hjälp och support {#find-help}

Få åtkomst till Adobe Journey Optimizer hjälpsidor från startsidans nedre del.

Använd ikonen **Hjälp** för att få åtkomst till hjälpsidor, kontakta support och dela feedback. Du kan söka efter hjälpartiklar och videoklipp i sökfältet.

![](assets/ajo-help.png)

På varje sida använder du sammanhangsberoende hjälpknappar för att lära dig mer om en funktion och bläddra till dokumentationen för **[!DNL Adobe Experience League]**.

![](assets/do-not-localize/Context-help.gif)

## Språkinställningar {#language-pref}

Användargränssnittet finns på följande språk:

* Engelska
* Franska
* Tyska
* Italienska
* Spanska
* Portugisiska (Brasilien)
* Japanska
* Koreanska
* Traditionell kinesiska
* Förenklad kinesiska

Standardspråket för gränssnittet avgörs av det språk du föredrar i användarprofilen.

Så här byter du språk:

* Klicka på **Inställningar** i din avatar högst upp till höger.
  ![](assets/preferences.png)
* Klicka sedan på det språk som visas under din e-postadress
* Välj önskat språk och klicka på **Spara**. Du kan välja ett andra språk om komponenten som du använder inte är lokaliserad på ditt första språk.
  ![](assets/select-language.png)

<!--CONTEXTUAL HELP TO DISPATCH IN DOCS ONCE FEATURE LIVE-->

<!--PRIORITIZATION & CONFLICT MANAGEMENT-->

>[!CONTEXTUALHELP]
>id="ajo_journey_priority"
>title="Prioritet"
>abstract="Tilldela en prioritetspoäng till resan, från 0 till 100. Ett högre tal anger en högre prioritet. När två resor använder samma yta väljer Journey Optimizer den resa som har högst prioritet. Om resorna har samma poäng väljs den resa som senast ändrades."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_priority"
>title="Prioritet"
>abstract="Tilldela kampanjens prioritetspoäng, från 0 till 100. Ett högre tal anger en högre prioritet. När två kampanjer använder samma yta väljer Journey Optimizer den kampanj som har högst prioritet. Om kampanjerna har samma poäng väljs den senaste kampanjen."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_conflict"
>title="Visningsprogrammet i konflikt i kampanjer"
>abstract="Visningsprogrammet i konflikt i kampanjer"

>[!CONTEXTUALHELP]
>id="ajo_journey_conflict"
>title="Konfliktvisningsprogrammet under resor"
>abstract="Konfliktvisningsprogrammet under resor"

>[!CONTEXTUALHELP]
>id="ajo_rule_set_object_type"
>title="Objekttyp"
>abstract="Objekttyp"

>[!CONTEXTUALHELP]
>id="ajo_journey_rule_set"
>title="Använd regeluppsättning för resor"
>abstract="TBD"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_rule_set"
>title="Använd regeluppsättning för kampanjer"
>abstract="TBD"

>[!CONTEXTUALHELP]
>id="ajo_rule_set_prioritization"
>title="Faktor i prioritering"
>abstract="TBD"

<!--CONTENT LOCKING-->

>[!CONTEXTUALHELP]
>id="ajo_locking_governance"
>title="Styrning"
>abstract="Styrning"

>[!CONTEXTUALHELP]
>id="ajo_locking_mode"
>title="Läge"
>abstract="Läge"

>[!CONTEXTUALHELP]
>id="ajo_locking_content_addition"
>title="Aktivera tillägg av innehåll"
>abstract="Aktivera tillägg av innehåll"

>[!CONTEXTUALHELP]
>id="ajo_locking_structure"
>title="Låsning av innehåll i struktur"
>abstract="Låsning av innehåll i struktur"

>[!CONTEXTUALHELP]
>id="ajo_locking_component"
>title="Använd specifik låsning i komponenten"
>abstract="Använd specifik låsning i komponenten"

>[!CONTEXTUALHELP]
>id="ajo_email_editable_areas"
>title="Markera redigerbara områden"
>abstract="Markera redigerbara områden"

>[!CONTEXTUALHELP]
>id="ajo_email_locking_activated"
>title="Styrning har aktiverats"
>abstract="Lås innehåll aktiveras och kan förhindra att du gör ändringar."

>[!CONTEXTUALHELP]
>id="ajo_email_locking_read_only"
>title="Skrivskyddad"
>abstract="Det här innehållet är skrivskyddat och kan inte ändras."

<!--GOVERNANCE POLICIES-->

>[!CONTEXTUALHELP]
>id="ajo_data_governance_policy_violation"
>title="Överträdelse av databehandlingspolicy"
>abstract="Överträdelse av databehandlingspolicy"

<!--APPROVAL POLICIES-->

>[!CONTEXTUALHELP]
>id="ajo_permissions_approval_policy"
>title="Godkännandeprincip"
>abstract="Godkännandeprincip"

>[!CONTEXTUALHELP]
>id="ajo_approval_policy_request_approval"
>title="Begär godkännande"
>abstract="Begär godkännande (två separata ID:n?)"

>[!CONTEXTUALHELP]
>id="ajo_approval_policy_request_change"
>title="Begär ändring"
>abstract="Begär ändring (två separata ID:n?)"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_edit_disabled"
>title="Redigera inaktiverat"
>abstract="Redigera inaktiverat (kampanjer)"

>[!CONTEXTUALHELP]
>id="ajo_journey_edit_disabled"
>title="Redigera inaktiverat"
>abstract="Redigera inaktiverat (resor)"

>[!CONTEXTUALHELP]
>id="ajo_approval_policy_approval_status"
>title="Godkännandestatus"
>abstract="Godkännandestatus (två separata ID:n?)"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_approve"
>title="Godkänn"
>abstract="Godkänn (kampanjer)"

>[!CONTEXTUALHELP]
>id="ajo_journey_approve"
>title="Godkänn"
>abstract="Godkänn (resor)"
