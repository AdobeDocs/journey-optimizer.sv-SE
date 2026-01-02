---
solution: Journey Optimizer
product: journey optimizer
title: Få tillgång till och hantera kampanjer
description: Lär dig hur du får tillgång till och hanterar kampanjer i Journey Optimizer.
feature: Campaigns
topic: Content Management
role: User
mini-toc-levels: 1
level: Beginner
keywords: hantera kampanjer, status, schema, åtkomst, optimering
exl-id: 1b88c84e-9d92-4cc1-b9bf-27a2f1d29569
source-git-commit: d1fd0b60ae60c2642108a1eb308564c9d04f5f9e
workflow-type: tm+mt
source-wordcount: '1559'
ht-degree: 0%

---

# Få tillgång till och hantera kampanjer {#manage-campaigns}

>[!CONTEXTUALHELP]
>id="ajo_targeting_workflow_list"
>title="Samlad kampanjinventering"
>abstract="På den här skärmen kan du få tillgång till den fullständiga listan över samordnade kampanjer, kontrollera deras aktuella status, sista/nästa körningsdatum och skapa en ny Orchestrated-kampanj."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_campaign_action"
>title="Åtgärd"
>abstract="I det här avsnittet visas alla åtgärder som används i den samordnade kampanjen."

Lär dig hur du får tillgång till, ordnar och hanterar kampanjer i Adobe Journey Optimizer. Den här guiden täcker allt från att hitta kampanjer till att förstå status, utföra vanliga åtgärder och underhålla kampanjarbetsytan.

## Snabbstart: Vanliga uppgifter {#quick-tasks}

Gå direkt till det du behöver:

* **Skapa en ny kampanj** → [Välj kampanjtyp](get-started-with-campaigns.md#campaign-types)
   * [Skapa en åtgärdskampanj](create-campaign.md)
   * [Skapa API-utlösta kampanjer](api-triggered-campaigns.md)
   * [Skapa en orkestrerad kampanj](../orchestrated/gs-orchestrated-campaigns.md)
* **Hitta befintliga kampanjer** → [Sök och filtrera](#access)
* **Visa kampanjresultat** → [Kampanjrapporter](../reports/campaign-global-report-cja.md)
* **Schemalägg kampanjer** → [Använd kalendern](#calendar)
* **Hantera konflikter** → [Konflikthanteringsguide](../conflict-prioritization/gs-conflict-prioritization.md)

## Få tillgång till och bläddra bland kampanjer {#access}

Kampanjer är tillgängliga på menyn **[!UICONTROL Campaigns]**. Använd flikarna för att bläddra bland kampanjer efter typ: **Åtgärd** kampanjer, **API-utlösta** kampanjer och **samordnade** kampanjer. Läs mer om de [olika kampanjtyperna](get-started-with-campaigns.md#campaign-types). Vilka typer som är tillgängliga beror på ditt licensavtal och dina behörigheter.

>[!BEGINTABS]

>[!TAB Åtgärdskampanjer]

Välj fliken **[!UICONTROL Action]** för att få tillgång till listan över åtgärdskampanjer.

Som standard visas alla kampanjer med statusvärdena **[!UICONTROL Draft]**, **[!UICONTROL Scheduled]** och **[!UICONTROL Live]** i listan. Om du vill visa stoppade, slutförda och arkiverade kampanjer måste du rensa filtret.

![](assets/create-campaign-list.png)

>[!TAB API-utlösta kampanjer]

Välj fliken **[!UICONTROL API triggered]** för att få åtkomst till listan över API-utlösta kampanjer.

Som standard visas alla kampanjer med statusvärdena **[!UICONTROL Draft]**, **[!UICONTROL Scheduled]** och **[!UICONTROL Live]** i listan. Om du vill visa stoppade, slutförda och arkiverade kampanjer måste du rensa filtret.

![](assets/api-triggered-list.png)

>[!TAB Samordnade kampanjer]

Välj fliken **[!UICONTROL Orchestration]** om du vill få åtkomst till listan över Orchestrated-kampanjer.

![bild som visar lagret för orkestrerade kampanjer](assets/inventory.png){zoomable="yes"}

Varje orkestrerad kampanj i listan visar information som kampanjens aktuella [status](#statuses), den associerade kanalen och de associerade taggarna eller den senaste gången den ändrades. Du kan anpassa de kolumner som visas genom att klicka på knappen ![Konfigurera layout](assets/do-not-localize/inventory-configure-layout.svg) .

>[!ENDTABS]

### Söka efter och filtrera kampanjer {#search-filter}

Dessutom finns det ett sökfält och filter som gör det enklare att söka i listan. Du kan till exempel filtrera kampanjer så att de bara visas för en viss kanal eller tagg, eller för kampanjer som skapats under ett visst datumintervall.

## Kampanjåtgärder {#operations}

![Bilden som visar knappen Fler åtgärder](assets/do-not-localize/rule-builder-icon-more.svg) i kampanjinventeringen gör att du kan utföra olika åtgärder.

![bild som visar kampanjlagret](assets/inventory-actions.png)

### Tillgängliga åtgärder

**För alla kampanjtyper:**

* **[!UICONTROL View all time report]** / **[!UICONTROL View last 24 hours report]** - Få tillgång till rapporter för att mäta och visualisera effekten och resultatet av era kampanjer. [Läs mer om kampanjrapporter →](../reports/campaign-global-report-cja.md)
* **[!UICONTROL Edit tags]** - Redigera de taggar som är associerade med kampanjen. [Lär dig använda taggar →](../start/search-filter-categorize.md#add-tags)
* **[!UICONTROL Duplicate]** - Använd det här alternativet för att duplicera en kampanj, till exempel för att köra en Orchestrated-kampanj som har stoppats. [Läs mer om duplicering →](#duplicate-a-campaign)
* **[!UICONTROL Delete]** - Använd det här alternativet om du vill ta bort en kampanj. [Läs mer om att ta bort →](#delete-a-campaign)
* **[!UICONTROL Archive]** - Arkivera kampanjen. Alla arkiverade kampanjer tas bort enligt ett rullande schema 30 dagar efter det att de senast ändrades. Den här åtgärden är tillgänglig för alla kampanjer förutom **[!UICONTROL Draft]** kampanjer. [Läs mer om arkivering →](#archive-a-campaign)

**Endast för åtgärdskampanjer och API-utlösta kampanjer:**

* **[!UICONTROL Add to package]** - Lägg till kampanjen i ett paket för att exportera den till en annan sandlåda. [Lär dig hur du exporterar objekt →](../configuration/copy-objects-to-sandbox.md)
* **[!UICONTROL Open draft version]** - Om en ny version av kampanjen har skapats och ännu inte har aktiverats kan du komma åt dess utkastversion med den här åtgärden.

## Förstå kampanjstatus {#statuses}

Varje kampanj går igenom en livscykel som återspeglas av dess status i gränssnittet. Genom att förstå dessa statusar kan du veta vilka åtgärder som är tillgängliga och vad du ska göra härnäst.

| Status | Åtgärdskampanjer | API-utlösta kampanjer | Samordnade kampanjer | Vad det betyder | Nästa åtgärd |
|--------|:----------------:|:-----------------------:|:----------------------:|---------------|--------------|
| **[!UICONTROL Draft]** | ✅ | ✅ | ✅ | Redigeras, aktiveras inte | Fortsätt redigera eller [aktivera kampanj](review-activate-campaign.md) |
| **[!UICONTROL Scheduled]** | ✅ | ✅ | ✅ | Konfigurerad för ett specifikt startdatum | Vänta på start, [ändra vid behov](#modify) eller [visa i kalendern](#calendar) |
| **[!UICONTROL Live]** | ✅ | ✅ | ✅ | Aktiverat och körs | [Övervakningsprestanda](../reports/campaign-global-report-cja.md), [skapa ny version](#modify) vid behov |
| **[!UICONTROL In review]** | ✅ | ✅ | — | Skickat för godkännande | Vänta på [godkännande](../test-approve/gs-approval.md) eller ändra |
| **[!UICONTROL Stopped]** | ✅ | ✅ | ✅ | Manuellt stoppad, kan inte återaktiveras | [Duplicera för återanvändning](#duplicate-a-campaign) |
| **[!UICONTROL Completed]** | ✅ | ✅ | ✅ | Körningen är klar (autotilldelad 3 dagar efter aktivering eller vid slutdatumet för återkommande) | [Visa rapporter](../reports/campaign-global-report-cja.md), [arkiv](#archive-a-campaign) eller [dubblett](#duplicate-a-campaign) |
| **[!UICONTROL Failed]** | ✅ | ✅ | — | Körningen misslyckades | Kontrollera loggar, åtgärda problem, [duplicera för att försöka igen](#duplicate-a-campaign) |
| **[!UICONTROL Archived]** | ✅ | ✅ | ✅ | Arkiverad (tas bort automatiskt efter 30 dagar) | [Hämta med filter](#access) vid behov |
| **[!UICONTROL Closed]** | — | — | ✅ | Återkommande kampanj stängd, inga nya poster tillåts (fortsätter tills alla aktiviteter är slutförda) | Vänta på slutförande |
| **[!UICONTROL Publishing]** | — | — | ✅ | Publiceras | Vänta tills publiceringen är klar |

>[!NOTE]
>
>För åtgärdskampanjer och API-utlösta kampanjer anger ikonen&quot;Öppna utkast till version&quot; bredvid statusen **[!UICONTROL Live]** eller **[!UICONTROL Scheduled]** att en ny version har skapats och inte har aktiverats än.

### Felindikatorer

När ett fel inträffar inom en av era kampanjer visas en varningsikon bredvid kampanjens status. Klicka på den för att visa information om varningen. Dessa varningar kan inträffa i olika situationer, t.ex. när kampanjmeddelandet inte har publicerats eller om den valda konfigurationen är felaktig.

![](assets/campaign-alerts.png)

>[!NOTE]
>
>Assets/Bilder är tillgängliga i levererat material i upp till två år (730 dagar) sedan det publicerades första gången i ett fragment/textbundet meddelande. Återpublicering krävs efter denna förfalloperiod (när som helst efter 730 dagar) för att hålla dem tillgängliga i ytterligare två år. Om publiceringen görs inom 730 dagar efter den första publikationen kommer inte förfallodagen för mediefiler/bilder att förlängas till de kommande 730 dagarna.

## Kampanjkalender {#calendar}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_view"
>title="Kampanjlista och kalendervyer"
>abstract="Förutom kampanjlistan innehåller [!DNL Journey Optimizer] en kalendervy över dina kampanjer, som ger en tydlig visuell representation av deras scheman. Du kan när som helst växla mellan list- och kalendervyer med dessa knappar."

Förutom kampanjlistan innehåller [!DNL Journey Optimizer] en kalendervy över dina kampanjer, som ger en tydlig visuell representation av deras scheman.

### Så här fungerar kalendern

Hur kampanjer presenteras:

* Som standard visar kalenderrutnätet alla aktiva och schemalagda kampanjer för den valda veckan. Ytterligare filteralternativ kan visa slutförda, stoppade och avslutade aktiveringar eller aktiveringar av en viss typ eller kanal.
* Utkastkampanjer visas inte.
* Kampanjer som sträcker sig över flera dagar visas högst upp i kalenderrutnätet.
* Om ingen starttid anges används den närmaste manuella aktiveringstiden för att placera den i kalendern.
* Kampanjer visas som 1-timmars tidsintervall, men detta återspeglar inte den faktiska tiden för sändning eller slutförande.

### Navigera i kalendern

1. Klicka på ikonen ![kalender](assets/do-not-localize/Smock_Calendar_18_N.svg) för att komma åt din kampanjkalender.

1. Använd pilknapparna eller datumväljaren ovanför kalendern för att flytta mellan veckor.

   I kalendern visas alla kampanjer som är schemalagda för den aktuella veckan.

   ![kalendervy som visar aktiva kampanjer](assets/campaigns-timeline.png)

1. Klicka på ![kugghjulsikonen](assets/do-not-localize/Smock_Gears_18_N.png) för att växla visningen av objekt som sträcker sig över flera dagar eller veckor.

   ![kalendervy som visar aktiva kampanjer](assets/campaign-long-term.png)

1. Klicka på ikonen ![Lägg till kalender](assets/do-not-localize/Smock_CalendarAdd_18_N.svg) för att hantera och lägga till upp till tre externa kalendrar.

   ![kalendervy som visar externa kalendrar](assets/campaign-external-calendar.png)

1. Dra och släpp dina CSV-filer med händelsenamn, startdatum och slutdatum.

   Överförda händelser visas för alla användare i din organisation och visas i både Resekalendrar och Campaign-kalendrar.

   +++CSV-formatet ska vara följande:

   | Kolumn1 | Kolumn2 | Column3 |
   |-|-|-|
   | Händelsenamn | Startdatum i formatet mm/dd/åå | Slutdatum i formatet mm/dd/åå |

   +++

1. Om det behövs kan du dölja, visa eller ta bort tillagda externa kalendrar.

   ![kalendervy som visar externa kalendrar](assets/campaign-manage-calendar.png)

1. Om du vill ha mer information om en kampanj klickar du på det synliga blocket för att öppna detaljer om den. En informationsruta öppnas med olika information om kampanjen, t.ex. typ, åtkomst till rapporter eller taggar som har tilldelats.

   ![kampanjlista med informationsrutan öppnad](assets/campaign-rail.png)

## Ändra och stoppa återkommande åtgärdskampanjer {#modify}

### Ändra en åtgärdskampanj {#modify-an-action-campaign}

Följ de här stegen för att ändra och skapa en ny version av en kampanj för återkommande åtgärder:

1. Öppna åtgärdskampanjen och klicka sedan på knappen **[!UICONTROL Modify campaign]**.

1. En ny version av kampanjen skapas. Du kan kontrollera live-versionen genom att klicka på **[!UICONTROL Open live version]**.

   ![](assets/create-campaign-draft.png)

   I kampanjlistan visas aktiverade kampanjer med en pågående utkastversion med en specifik ikon i kolumnen **[!UICONTROL Status]**. Klicka på den här ikonen för att öppna utkastet till kampanjversionen.

   ![](assets/create-campaign-edit-list.png)

1. När ändringarna är klara kan du aktivera den nya versionen av kampanjen (se [Granska och aktivera en kampanj](review-activate-campaign.md)).

   >[!IMPORTANT]
   >
   >När du aktiverar utkastet ersätts kampanjens liveversion.

**Relaterade ämnen:**
* [Kampanjegenskaper](campaign-properties.md)
* [Kampanjåtgärder](campaign-action.md)
* [Kampanjinnehåll](campaign-content.md)
* [Kampanjmålgrupp](campaign-audience.md)
* [Kampanjschema](campaign-schedule.md)

### Stoppa en Action-kampanj {#stop}

Om du vill stoppa en återkommande kampanj öppnar du den och klickar sedan på knappen **[!UICONTROL Stop campaign]**.

![](assets/create-campaign-stop.png)

>[!IMPORTANT]
>
>Att stoppa en kampanj kommer inte att stoppa en pågående sändning, men det kommer att stoppa en schemalagd sändning eller nästa förekomst om sändning redan pågår.

## Arkivera en kampanj {#archive-a-campaign}

Med tiden växer listan över kampanjer och blir så småningom svårare att hitta färdiga och stoppade kampanjer.

För att förhindra detta kan ni arkivera slutförda och stoppade kampanjer som ni inte längre behöver. Om du vill göra det klickar du på ellipsknappen och väljer **[!UICONTROL Archive]**.

![](assets/create-campaign-archive.png)

Arkiverade kampanjer kan sedan hämtas med det dedikerade filtret i listan.

## Ta bort en kampanj {#delete-a-campaign}

Om du vill ta bort en kampanj använder du ellipsen ![som visar knappen Fler åtgärder](assets/do-not-localize/rule-builder-icon-more.svg) och väljer **[!UICONTROL Delete]**.

![](assets/delete-a-campaign.png){width="70%" align="left"}

>[!IMPORTANT]
>
>Det här alternativet är endast tillgängligt för **[!UICONTROL Draft]** kampanjer.

## Duplicera en kampanj {#duplicate-a-campaign}

Om du vill duplicera en kampanj, till exempel om den har stoppats, använder du ellipsen ![som visar knappen Fler åtgärder](assets/do-not-localize/rule-builder-icon-more.svg) och väljer **[!UICONTROL Duplicate]**.

Ange namnet på kampanjen och bekräfta.

Kampanjen skapas och läggs till i kampanjlistan.

## Ytterligare resurser

* **Komma igång** - [Kom igång med kampanjer](get-started-with-campaigns.md) | [Skapa din första Action-kampanj](create-campaign.md) | [Guide för API-utlösta kampanjer](api-triggered-campaigns.md) | [Guide för samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md)

* **Kampanjkonfiguration** - [Kampanjegenskaper](campaign-properties.md) | [Kampanjåtgärder och -kanaler](campaign-action.md) | [Design av kampanjinnehåll](campaign-content.md) | [Kampanjmålgrupp](campaign-audience.md) | [Kampanjplanering](campaign-schedule.md)

* **Avancerade funktioner** - [Arbetsflöden för godkännande](../test-approve/gs-approval.md) | [Konflikthantering och -prioritering](../conflict-prioritization/gs-conflict-prioritization.md) | [Frekvensbegränsning per kanal ](../conflict-prioritization/channel-capping.md) | [Prioritetspoäng](../conflict-prioritization/priority-scores.md) | [Exportera kampanjer till andra sandlådor](../configuration/copy-objects-to-sandbox.md)

* **Övervakning och optimering** - [Kampanjrapporter (CJA)](../reports/campaign-global-report-cja.md) | [Konfigurera aviseringar](../reports/alerts.md)

* **Organisation** - [Arbeta med taggar](../start/search-filter-categorize.md) | [Hantera behörigheter](../administration/ootb-product-profiles.md)
