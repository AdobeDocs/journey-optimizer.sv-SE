---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med källanslutningar i Journey Optimizer
description: Lär dig hur du importerar data från externa källor i Adobe Journey Optimizer
feature: Integrations, Data Ingestion
role: User
level: Beginner
exl-id: 359ea3c6-7746-469e-8a24-624f9726f2d8
source-git-commit: 52b58d18cdbbff79f4dcb7af2817b178a4a0b429
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 3%

---

# Kom igång med källkopplingar {#sources-gs}

## Vad är en källa? {#what-is-source}

En **källa** är en koppling som hämtar externa data till Adobe Journey Optimizer. Med hjälp av källor kan du importera kundinformation från system som du redan använder, till exempel CRM-plattformar, molnlagring eller databaser, och göra dessa data tillgängliga för att skapa personaliserade kundresor.

Se källor som broar mellan Journey Optimizer och era externa datasystem. De synkroniserar automatiskt data så att ni alltid har aktuell kundinformation som kan styra era marknadsföringskampanjer.

## Varför källorna är viktiga {#why-sources-matter}

Källor är avgörande för att skapa personaliserade, datadrivna kundupplevelser i Journey Optimizer. Här är varför:

* **Enhetlig kundvy** - Kombinera data från flera system för att se en komplett bild av varje kund
* **Realtidspersonalisering** - Använd aktuella data för att leverera relevanta meddelanden på dina resor i rätt tid
* **Automatisk datasynkronisering** - Håll kundinformationen aktuell utan manuell dataimport
* **Effektiva arbetsflöden** - Anslut en gång, sedan flödar data automatiskt in på dina resor

Du kan till exempel använda källor för att importera inköpshistorik från din e-handelsplattform och sedan skapa resor som skickar personaliserade produktrekommendationer baserat på vad kunderna har köpt.

## Vad du kan göra med källor {#sources-use-cases}

Exempel på användningsområden för Journey Optimizer:

* **Importera kunddata från CRM-system** - Synkronisera kontaktinformation, inställningar och interaktionshistorik från plattformar som Salesforce eller Microsoft Dynamics
* **Ansluta inköpsdata** - Anpassa erbjudanden genom att lägga in orderhistorik och produktinställningar från e-handelsplattformar
* **Integrera lojalitetsprogramdata** - Få åtkomst till punktsaldon och nivåinformation för att belöna dina mest engagerade kunder
* **Synkronisera beteendedata** - Importera webbplatsinteraktioner och appanvändningsmönster för att utlösa relevanta resor
* **Uppdatera profilattribut** - Håll kundprofiler aktuella med data från molnlagring eller databaser

## Vanliga källtyper {#source-types}

Journey Optimizer har stöd för olika typer av källor för att ansluta till era befintliga system:

**Adobe-program:**
* Adobe Analytics
* Adobe Audience Manager
* Adobe Campaign
* Adobe Commerce

**Molnlagring:**
* Amazon S3
* Azure Blob Storage
* Google Cloud-lagring
* SFTP

**Databaser:**
* Amazon Redshift
* Google BigQuery
* Microsoft SQL Server
* MySQL
* PostgreSQL

**CRM och automatiserad marknadsföring:**
* Microsoft Dynamics
* Salesforce
* Salesforce Marketing Cloud

➡️ Se hela listan i [Experience Platform-källkatalogen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=sv-SE#sources-catalog){target="_blank"}

## Innan du börjar {#prerequisites}

Innan du konfigurerar källor måste du se till att:

* **Lämpliga behörigheter** - Åtkomst för att hantera källor i Adobe Experience Platform
* **Source systemautentiseringsuppgifter** - Autentiseringsinformation för det externa system som du vill ansluta
* **Förstå dina data** - Ta reda på vilka datafält du behöver och hur de kopplas till Journey Optimizer-profiler

➡️ Läs mer om [åtkomstkontroll och behörigheter](../../administration/permissions.md)

## Så fungerar källor {#how-sources-work}

Adobe Journey Optimizer använder källramverket från Adobe Experience Platform. Här är det grundläggande arbetsflödet:

1. **Anslut** - Konfigurera autentisering för ditt externa datasystem
2. **Välj data** - Välj vilka data som ska importeras och hur ofta de ska synkroniseras
3. **Mappningsfält** - Definiera hur externa datafält motsvarar Journey Optimizer-profilattribut
4. **Schema** - Konfigurera automatiska datauppdateringsintervall
5. **Monitor** - Spåra dataflöde och åtgärda synkroniseringsproblem

När de är konfigurerade körs källorna automatiskt i bakgrunden, vilket håller kunddata aktuella och färdiga att användas på resorna.

## Läs mer {#learn-more}

![](assets/sources-home.png)

I den här videon får du veta mer om källanslutningar och hur du konfigurerar dem i Journey Optimizer:

>[!VIDEO](https://video.tv.adobe.com/v/335919?quality=12)

Mer information om hur du konfigurerar och hanterar källor finns i [dokumentationen för Adobe Experience Platform-källor](https://experienceleague.adobe.com/docs/experience-platform/sources/home.htmll?lang=sv){target="_blank"}.

## Nästa steg {#next-steps}

Nu när ni förstår vilka källor som är och varför de är viktiga:

* Utforska [källkatalogen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=sv-SE#sources-catalog){target="_blank"} för att hitta anslutningar för dina system
* Lär dig hur du [skapar en källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/overview.html){target="_blank"}
* Förstå [datamappning och -omvandling](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/overview.html){target="_blank"}
* Se hur du [använder importerade data på resor](../building-journeys/journey-gs.md)
