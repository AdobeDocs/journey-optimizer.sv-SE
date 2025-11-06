---
solution: Journey Optimizer
product: journey optimizer
title: Definiera den API-utlösta kampanjmålgruppen
description: Lär dig hur du definierar den API-triggade kampanjmålgruppen.
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
exl-id: 6dda5687-3742-4e88-be7c-c4969b183161
source-git-commit: 31fcdf7e0cb63df24b01be13b2a4a8822768e1b7
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---

# Definiera den API-utlösta kampanjmålgruppen {#api-audience}

Använd fliken **[!UICONTROL Audience]** för att definiera kampanjens målgrupp.

![](assets/campaign-audience.png)

## Välj målgruppen

**För marknadsförings-API-utlösta kampanjer** klickar du på knappen **[!UICONTROL Select audience]** för att visa listan över tillgängliga Adobe Experience Platform-målgrupper. [Läs mer om målgrupper](../audience/about-audiences.md).

>[!IMPORTANT]
>
>Användning av målgrupper och attribut från [målgruppskomposition](../audience/get-started-audience-orchestration.md) är för närvarande inte tillgängligt för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.

**För Transactional API-utlösta kampanjer** måste målprofilerna definieras i API-anropet. Ett enda API-anrop stöder upp till 20 unika mottagare. Varje mottagare måste ha ett unikt användar-ID. Dubblerade användar-ID tillåts inte. Läs mer i [API-dokumentationen för interaktiv meddelandekörning](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution/operation/postIMUnitaryMessageExecution){target="_blank"}

## Välj identitetstyp

I fältet **[!UICONTROL Identity type]** väljer du vilken typ av nyckel som ska användas för att identifiera personer från den valda målgruppen. Du kan antingen använda en befintlig identitetstyp eller skapa en ny med hjälp av Adobe Experience Platform identitetstjänst. Standardidentitetsnamnutrymmen visas på [den här sidan](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces#standard){target="_blank"}.

Endast en identitetstyp tillåts per kampanj. Individer som tillhör ett segment som inte har den valda identitetstypen bland sina olika identiteter kan inte omfattas av kampanjen. Läs mer om identitetstyper och namnutrymmen i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=sv){target="_blank"}.

## Aktivera skapande av profil vid kampanjkörning

I vissa fall kan du behöva skicka transaktionsmeddelanden till profiler som inte finns i systemet. Om en okänd användare till exempel försöker återställa lösenordet på webbplatsen. När det inte finns någon profil i databasen kan du i Journey Optimizer automatiskt skapa den när kampanjen körs för att tillåta att meddelandet skickas till den här profilen.

Aktivera alternativet **[!UICONTROL Create new profiles]** om du vill aktivera profilskapande när kampanjen körs. Om det här alternativet är inaktiverat kommer okända profiler att avvisas för alla utskickningar och API-anropet kommer att misslyckas.

![](assets/api-triggered-create-profile.png)

>[!IMPORTANT]
>
>Det här alternativet har tillhandahållits för **mycket små volymprofiler** i ett fall där stora volymer skickas, med en stor mängd profiler som redan finns på plattformen.
>
>Okända profiler skapas i datauppsättningen **AJO Interactive Messaging Profile** i tre standardnamnutrymmen (e-post, telefon och ECID) för varje utgående kanal (e-post, SMS och push). Om du använder ett anpassat namnutrymme skapas emellertid identiteten med samma anpassade namnutrymme.
>
>Det går inte att skapa profiler vid körning för [kampanjer med hög genomströmning](../campaigns/api-triggered-high-throughput.md) eftersom det här läget inte är beroende av Adobe-profiler. Systemet kontrollerar inte om profilerna finns eller inte.

## Aktivera webhooks {#webhook}

För kampanjer som triggas av Transactional API kan du aktivera webhooks för att få realtidsfeedback om meddelandets körningsstatus. Om du vill göra det växlar du alternativet **[!UICONTROL Enable webhooks]** för att skicka leveransstatushändelser till en konfigurerad webkrok.

![](assets/api-triggered-webhook.png)

Webkrokkonfigurationer hanteras centralt på menyn **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Feedback Webhook]** . Därifrån kan administratörer skapa och redigera webbkrokslutpunkter. [Lär dig hur du skapar webhooks för feedback](../configuration/feedback-webhooks.md)

## Nästa steg {#next}

När kampanjens konfiguration och innehåll är klart kan du schemalägga dess körning. [Läs mer](api-triggered-campaign-schedule.md)
