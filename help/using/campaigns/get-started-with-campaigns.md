---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med kampanjer
description: Läs mer om kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
keywords: kampanj, hur, starta, optimera
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: b038865ee71ae4acb463b32d5ea66488f42b5c54
workflow-type: tm+mt
source-wordcount: '1535'
ht-degree: 0%

---

# Kom igång med kampanjer {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="Kampanjschema"
>abstract="Som standard börjar kampanjer vid manuell aktivering och avslutas omedelbart efter att meddelandet har skickats en gång. Du kan ange ett specifikt datum och en speciell tid för meddelandet som ska skickas. Dessutom kan du ange ett slutdatum för återkommande åtgärdskampanjer. I åtgärdsutlösarna kan du även konfigurera meddelandets sändningsfrekvens så att den passar dina inställningar."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_start"
>title="Kampanjstart"
>abstract="Ange ett datum och en tidpunkt då meddelandet ska skickas."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_end"
>title="Kampanjslut"
>abstract="Ange när en återkommande kampanj ska sluta köras."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_triggers"
>title="Kampanjåtgärdsutlösare"
>abstract="Definiera en frekvens som kampanjens meddelande ska skickas med."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_throttling"
>title="Kurskontroll"
>abstract="Ange hastighetskontroll för kampanjen genom att ange önskade hastighetsbegränsningar. Den här funktionen är särskilt användbar för att förhindra överbelastning i system längre fram i kedjan, som landningssidor eller kundtjänstplattformar."

>[!CONTEXTUALHELP]
>id="ajo_homepage_card3"
>title="Skapa kampanjer"
>abstract="Använd **Adobe Journey Optimizer** för att leverera engångsinnehåll till en viss målgrupp via olika kanaler. När du använder resor utförs åtgärderna i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema."

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="Kampanjer"
>abstract="Skapa kampanjer för att leverera engångsinnehåll till en viss målgrupp i olika kanaler. Innan du skapar en kampanj bör du kontrollera att du har en kanalkonfiguration och en Adobe Experience Platform-målgrupp klar att använda."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="Kampanjtyp"
>abstract="Välj kampanjtyp. Tillgängliga kanaler varierar beroende på vald typ. <br>**Schemalagda kampanjer** (åtgärdskampanjer) - Perfekt för enkel engångsbatchkommunikation som du kan schemalägga att köras vid en viss tidpunkt.<br>**API-utlösta kampanjer** - Aktiveras via ett API-anrop, vilket aktiverar automatiserade händelsebaserade meddelanden direkt från externa system.<br>**Samordnade kampanjer** - Skapa en visuell arbetsyta med dra-och-släpp för att utforma och automatisera komplexa arbetsflöden för flerstegsmarknadsföring, från målgruppssegmentering till personaliserad meddelandeleverans över flera kanaler."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_orchestration"
>title="Kampanjer"
>abstract="Skapa ett segmenteringsflöde, utforma era flerkanalsmeddelanden och planera era kampanjer. Kanaler som stöds: E-post, SMS, push-meddelanden."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_scheduled_marketing"
>title="Kampanjer"
>abstract="Leverera enstaka eller återkommande utgående leveranser eller pågående inkommande åtgärder."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_scheduled_transactional"
>title="Kampanjer"
>abstract="Leverera enstaka eller återkommande utgående transaktionsaktiviteter."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_api_marketing"
>title="Kampanjer"
>abstract="Leverera personaliserad marknadskommunikation till riktade målgrupper. Kanaler som stöds: E-post, SMS, push-meddelanden."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_create_api_transactional"
>title="Kampanjer"
>abstract="Skicka transaktionsinformation till enskilda profiler eller profiler. Kanaler som stöds: E-post, SMS, push-meddelanden."

Adobe Journey Optimizer ger er möjlighet att leverera målinriktat engångsinnehåll till specifika målgrupper i flera kanaler. Med kampanjer kan ni genomföra samordnade marknadsföringsåtgärder samtidigt och nå er målgrupp med rätt budskap vid rätt tidpunkt.

Den här guiden ger en tydlig färdplan som hjälper er att förstå grunderna i kampanjer, välja rätt kampanjtyp för ert användningsfall och utforma kampanjer som ger slagkraftiga kundupplevelser.

## Vad är kampanjer?

**Kampanjer** är samordnade marknadsföringsåtgärder som levererar innehåll till en viss målgrupp i en eller flera kanaler. Till skillnad från resor där åtgärderna utförs sekventiellt utför kampanjer samtidigt - antingen direkt eller enligt ett angivet schema.

Använd [!DNL Journey Optimizer] för att:

* Leverera **engångs- eller återkommande innehåll** till målgruppssegment
* Utför **samordnade flerkanalskommunikationer** via e-post, push, SMS, i appen, webben med mera
* Utlös **automatiska svar** via API-anrop för händelsestyrda meddelanden i realtid
* Utforma **komplexa arbetsflöden för marknadsföring** med visuella orkestreringsverktyg

![](assets/gs-campaigns.png)

➡️ **Vill du börja bygga?** [Skapa din första kampanj](create-campaign.md) på några minuter.

## Välj kampanjtyp {#campaign-types}

**Innan du börjar bygga** är det viktigt att du förstår vilken typ av kampanj som passar ditt användningsexempel. Adobe Journey Optimizer har stöd för tre olika kampanjtyper, var och en för olika scenarier och aktiveringsmekanismer:

![](assets/campaign-modal.png)

>[!BEGINTABS]

>[!TAB Åtgärdskampanjer (schemalagda)]

![ikon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg) **När du ska använda:** Enkel, schemalagd batchkommunikation

**Åtgärdskampanjer** (kallas även schemalagda kampanjer) är idealiska för enkel, engångs- eller återkommande batchkommunikation som körs vid en viss tidpunkt.

**Två kategorier:**

* **Marknadsföring** - Kampanjerbjudanden, engagemangskampanjer, meddelanden, juridiska meddelanden eller policyuppdateringar. Kräver att mottagarna är invalda.
* **Transaktionell** - Avbrott, nödsituationer, annulleringar. Kräver inte deltagande.

**Perfekt för:**

* Månatliga nyhetsbrev till kundsegment
* Tidskänsliga reklamutskick
* Säsongskampanjer
* Kommunikation om produktlansering
* Meddelanden om tjänstavbrott

➡️ [Lär dig mer om åtgärdskampanjer](create-campaign.md)

>[!TAB API-utlösta kampanjer]

![ikon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg) **När ska du använda:** Händelsestyrda meddelanden i realtid med externa system

**API-utlösta kampanjer** aktiveras via API-anrop, vilket aktiverar automatiserade meddelanden direkt från externa system. Dessa kampanjer stöder personalisering med både profilattribut och kontextdata i realtid från API-nyttolasten.

**Två kategorier:**

* **Marknadsföring** - Personlig marknadskommunikation till målgrupper
* **Transactional** - Meddelanden efter enskilda åtgärder (lösenordsåterställningar, kundvagn osv.)

**Perfekt för:**

* Bekräftelser för återställning av lösenord
* Återvinning av kundvagn
* Beställningsbekräftelser och leveransuppdateringar
* Meddelanden om kontoaktivitet
* Personaliserade rekommendationer i realtid

➡️ [Läs om API-utlösta kampanjer](api-triggered-campaigns.md)

>[!TAB Samordnade kampanjer]

![ikon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg) **När ska du använda:** Komplexa arbetsflöden för flerstegsmarknadsföring

**Samordnade kampanjer** ger en visuell arbetsyta med dra-och-släpp-funktioner för att utforma och automatisera sofistikerade arbetsflöden för marknadsföring. Från målgruppssegmentering till skräddarsydd meddelandeleverans i alla kanaler - allt sker i en intuitiv miljö som utformats för snabbhet och kontroll.

**Perfekt för:**

* Flerstegsprogram för kundengagemang
* Komplexa strategier för segmentering och målinriktning
* Samordna kampanjer i flera kanaler
* Varumärkesinitierad marknadsföring i stor skala
* Avancerad automatisering av arbetsflöden med flera beslutspunkter

➡️ [Läs om samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md)

>[!ENDTABS]

>[!NOTE]
>
>Vet du inte vilken typ du ska välja? Börja med **Åtgärdskampanjer** för schemalagd batchkommunikation eller **API-utlösta kampanjer** för meddelanden i realtid - dessa omfattar de vanligaste användningsfallen.

## Arbetsflöde för kampanjskapande {#workflow}

Framgångsrika kampanjer följer en tydlig och upprepningsbar process. Här är ditt stegvisa arbetsflöde:

**1. Planera** → **2. Konfigurera** → **3. Design** → **4. Granska** → **5. Aktivera** → **6. Monitor**

### &#x200B;1. **Planera din kampanj** {#plan}

Förtydliga era mål innan du börjar:

* **Vad är målet?** (t.ex. enhetskonverteringar, öka engagemanget, meddela kunderna)
* **Vem är målgruppen?** (specifikt segment från Adobe Experience Platform)
* **Vilken kampanjtyp passar?** (Se [kampanjtyper](#campaign-types) ovan)
* **Vilka kanaler ska du använda?** (e-post, push, SMS, in-app, webb, osv.)
* **När ska det köras?** (omedelbar, schemalagd eller API-utlöst)

### &#x200B;2. **Konfigurera kampanjegenskaper** {#configure}

Lägg grunden till er kampanj:

1. **Namnge och beskriv** din kampanj för enkel identifiering
2. **Välj kampanjtyp** (åtgärd, API-utlöst eller Orchestrated)
3. **Välj målgrupp** från Adobe Experience Platform
4. **Ange prioritet** om konflikthantering används
5. **Konfigurera schema** (för åtgärdskampanjer) eller API-information (för API-utlösta)

**Typspecifika stödlinjer:**
* [Egenskaper för åtgärdskampanj →](campaign-properties.md)
* [Egenskaper för API-utlösta kampanjer →](api-triggered-campaign-properties.md)
* [Samordnade kampanjinställningar →](../orchestrated/create-orchestrated-campaign.md)

### &#x200B;3. **Designa ditt innehåll** {#design}

Skapa övertygande budskap för er målgrupp:

* Använd **e-post-Designer** för e-postupplevelser
* Konfigurera **push-meddelanden** med bilder och djupa länkar
* Utforma **SMS/MMS-meddelanden** med personalisering
* Skapa **upplevelser i appen** och **webb**
* Lägg till **personalisering** med profilattribut och sammanhangsbaserade data

**Typspecifika stödlinjer:**
* [Åtgärdskampanjens innehåll →](campaign-content.md)
* [API-utlöst kampanjinnehåll →](api-triggered-campaign-content.md)
* [Samordnat kampanjinnehåll →](../orchestrated/create-orchestrated-campaign.md)

### &#x200B;4. **Granska och testa** {#review}

Granska alltid kampanjen före aktiveringen:

* **Förhandsgranska innehåll** med testprofiler
* **Kontrollera målinriktning** för att säkerställa rätt målgrupp
* **Verifiera schema** och aktiveringsinställningar
* **Begär godkännande** om arbetsflödet för godkännande används
* **Testa leveransen** med startvärdeslistor

**Typspecifika stödlinjer:**
* [Granska åtgärdskampanjer →](review-activate-campaign.md)
* [Granska kampanjer som triggas av API →](review-activate-api-triggered-campaign.md)
* [Granska samordnade kampanjer →](../orchestrated/create-orchestrated-campaign.md)

### &#x200B;5. **Aktivera kampanjen** {#activate}

Aktivera kampanjen när granskningen är klar:

* **Manuell aktivering** - Aktivera omedelbart eller vid schemalagd tidpunkt
* **API-aktivering** - Använd aktiveringsslutpunkten för API-utlösta kampanjer
* **Godkännandeprocess** - Om det behövs väntar du på godkännande från berörda parter
* Obs! Aktiva kampanjer kan inte redigeras (du måste duplicera dem för att kunna göra ändringar)

**Typspecifika stödlinjer:**
* [Aktivera åtgärdskampanjer →](review-activate-campaign.md)
* [Aktivera API-utlösta kampanjer →](review-activate-api-triggered-campaign.md)
* [Aktivera samordnade kampanjer →](../orchestrated/create-orchestrated-campaign.md)

### &#x200B;6. **Övervaka och analysera** {#monitor}

Spåra kampanjens resultat:

* Visa kampanjrapporter och analyser
* Övervaka leveransfrekvenser och engagemangsmått
* Spåra fel och studsar
* Analysera konvertering och avkastning
* Använd insikter för optimering

**Typspecifika stödlinjer:**
* [Kampanjrapporter →](../reports/campaign-global-report-cja.md)
* [API-utlöst kampanjövervakning →](api-triggered-campaigns.md#monitor)
* [Samlad kampanjanalys →](../orchestrated/create-orchestrated-campaign.md)

➡️ **Vill du börja?** Välj kampanjtyp:
* [Skapa en åtgärdskampanj →](create-campaign.md)
* [Skapa API-utlöst kampanj →](api-triggered-campaigns.md)
* [Skapa en orkestrerad kampanj →](../orchestrated/gs-orchestrated-campaigns.md)

## Förhandskrav {#prerequisites}

Innan du arbetar med kampanjer bör du kontrollera att du har följande på plats:

### Nödvändig konfiguration

* **Publiker** - Publiker måste vara tillgängliga i Adobe Experience Platform innan kampanjer kan skapas. [Kom igång med målgrupper →](../audience/about-audiences.md)

* **Kanalkonfigurationer** - Kanalkonfigurationer (förinställningar) måste skapas och vara tillgängliga för de kanaler som du vill använda. [Konfigurera kanalkonfigurationer →](../configuration/channel-surfaces.md)

* **Behörigheter** - Du behöver lämpliga behörigheter baserat på kampanjtypen. Kontakta administratören om du inte har åtkomst till kampanjfunktioner. [Läs om inbyggda roller →](../administration/ootb-product-profiles.md)

| Kampanjtyp | Behörigheter |
|----------------------------|----------------------------------------------------------------------------|
| **Åtgärdskampanjer** | Kampanjadministratör<br>Kampanjgodkännare<br>Kampanjhanterare<br>Kampanjvisningsprogram |
| **API-utlösta kampanjer** | Kampanjadministratör<br>Kampanjgodkännare<br>Kampanjhanterare<br>Kampanjvisningsprogram |
| **Samordnade kampanjer** | Orchestrated Campaign Administrator<br>Orchestrated Campaign Approver<br>Orchestrated Campaign Manager<br>Orchestrated Campaign Viewer |

+++Tilldela kampanjbehörigheter

1. Navigera till fliken **[!UICONTROL Roles]** i produkten [!DNL Permissions] och välj en av de inbyggda kampanjrelaterade **[!UICONTROL Roles]**.

1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

1. Ange användarens namn eller e-postadress eller välj användaren i listan och klicka på **[!UICONTROL Save]**.

   Om användaren inte har skapats tidigare, se [dokumentationen för Lägg till användare](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users){target="_blank"}.

Användaren bör sedan få ett e-postmeddelande som omdirigeras till din instans.

+++

## Kampanjfunktioner {#capabilities}

Utforska följande kraftfulla funktioner när ni blir mer bekväma med kampanjer:

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg)

**Schemaläggning och timing**

Schemalägg kampanjer för specifika datum/tidpunkter, ange återkommande leveranser och optimera sändningstiderna för maximal effekt.

[Läs mer om schemaläggning](campaign-schedule.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**Klassificeringskontroll**

Begränsa meddelandegenomströmningen för att förhindra överbelastning i system längre fram i kedjan, som landningssidor eller kundtjänstplattformar.

[Begränsningar för kontrollfrekvens](create-campaign.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**Målgruppsanpassning**

Rikta in er på specifika Adobe Experience Platform-målgrupper med precision och hantera målgruppskvalifikationer dynamiskt.

[Välj kampanjmålgrupp](campaign-audience.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**Arbetsflöden för godkännande**

Implementera gransknings- och godkännandeprocesser innan kampanjer publiceras, för att säkerställa kvalitet och efterlevnad.

[Granska och aktivera](review-activate-campaign.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/clock.svg)

**Tysta timmar**

Följ kundernas önskemål genom att undvika meddelandeleverans under angivna tidsperioder.

[Konfigurera tysta timmar](quiet-hours.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**Tidsoptimering vid sändning**

Använd AI för att fastställa den bästa tidpunkten för att skicka meddelanden för maximal interaktion med varje individ.

[Optimera sändningstiden](campaigns-message-optimization.md)
:::

::::

## Kom igång med kampanjtyper {#get-started-types}

Nu när du förstår kampanjer i [!DNL Journey Optimizer] väljer du kampanjtyp för att komma igång:

<table style="table-layout:fixed"><tr style="border: 0; text-align: center;">
<td><a href="create-campaign.md"><img width="70%" alt="åtgärdskampanjer" src="assets/do-not-localize/gs-action-campaign.png"></a><br/><a href="create-campaign.md">Åtgärdskampanjer</a></td>
<td><a href="api-triggered-campaigns.md"><img width="70%" alt="sms" src="assets/do-not-localize/gs-api-triggered-campaign.png"></a><br/><a href="api-triggered-campaigns.md">API-utlösta kampanjer</a></td>
<td><a href="../orchestrated/gs-orchestrated-campaigns.md"><img width="70%" alt="push" src="assets/do-not-localize/gs-orchestrated-campaign.png"></a><a href="../orchestrated/gs-orchestrated-campaigns.md">Samordnade kampanjer</a></td>
</tr></table>
