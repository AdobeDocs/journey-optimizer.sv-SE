---
solution: Journey Optimizer
product: journey optimizer
title: Leveransguide för IP-värmare
description: Lär dig mer om grunderna för leveransförmåga och de bästa sätten att värma upp IP-adresser
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP, leveransförmåga, anseende, internetleverantör, engagemang
source-git-commit: 07896931a7c06e1b712f3b65e1dcf939b521ba83
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 2%

---

# Leveransguide för IP-värmare {#ip-warmup-deliverability-guide}

När du lanserar e-postkampanjer med nya IP-adresser eller domäner i Adobe Journey Optimizer är det viktigt att förstå leveransgrunderna för att skapa ett starkt avsändarrykte. Den här guiden beskriver viktiga koncept, förberedelser och metodtips som hjälper dig att gå över från noll till färdig inkorg.

➡️ [Titta på den här videon om du vill veta mer om grundläggande IP-värmersleverans](#video)

>[!NOTE]
>
>Stegvisa instruktioner om hur du implementerar IP-uppvärmningsplaner i Adobe Journey Optimizer finns i [Kom igång med IP-värmeringsplaner](ip-warmup-gs.md).

## Varför är IP och domänens anseende viktigt? {#reputation-matters}

Postlådeleverantörer (Gmail, Yahoo, Microsoft, Apple Mail med flera) utvärderar alla avsändare baserat på fyra huvudpelare:

* **Klagomål**: Markerade mottagarna dina meddelanden som skräppost?
* **Engagemang**: Öppnar, klickar eller svarar mottagarna på dina e-postmeddelanden?
* **Infrastruktur**: Är den sändande infrastrukturen autentiserad, stabil och tillförlitlig?
* **Innehåll**: Verkar ditt meddelandeinnehåll legitimt och värdefullt?

IP-värmen är främst avsedda för de tre första pelarna genom att gradvis visa för postlådeprovidrar att din nya infrastruktur är legitim och önskad innan du skalar till full sändningsvolym.

## Checklista före flygning {#pre-flight-checklist}

Innan du börjar värma upp dina IP-adresser måste du se till att alla grundläggande element finns på plats. Tabellen nedan visar de viktigaste uppgifterna som behöver utföras innan du påbörjar en IP-värmerappsplan.

| Uppgift | Varför det spelar någon roll | Så här uppnår du |
|------|----------------|-------------------|
| Reservera fasta IP-adresser och delegera underdomäner i AJO | Alla framtida anseende knyts till dessa infrastrukturelement | Navigera till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** > **[!UICONTROL Subdomains]**. [Läs mer](delegate-subdomain.md) |
| Konfigurera SPF och DKIM | Bekräftar att den avsändande servern är legitim och auktoriserad | Hanteras automatiskt av Adobe efter att underdomäner delegerats och kanalkonfigurationer skapats. [Läs mer](delegate-subdomain.md) |
| Ställ in DMARC-post | Aktiverar rapportering om e-postautentisering och principer för framtida tillämpning | Hanteras automatiskt av Adobe efter att underdomäner delegerats och kanalkonfigurationer skapats. [Läs mer](dmarc-record.md) |
| Konfigurera övervakning av dirigeringslista | Identifierar placeringsproblem i inkorgen tidigt i uppvärmningsprocessen | Lägg till dirigerade adresser när du skapar kanalkonfigurationen. [Läs mer](seed-lists.md) |
| Bygg fas 1 för målgrupper med högt engagemang | Ökar mätvärdena för tidigt engagemang med de mest aktiva mottagarna | Skapa en målgrupp med färre än 5 000 kontakter som har öppnat eller klickat de senaste 30 dagarna |

>[!CAUTION]
>
>Autentiseringsproblem (SPF, DKIM, DMARC) kan inte lösas via volymmappning. Kontrollera att dessa är korrekt konfigurerade innan du börjar skicka.

## Exempel på fyraveckorskalender {#warmup-calendar}

I den här exempelkalendern visas en progressiv volymbildruta baserat på procentandelen av din slutliga dagliga volym (UDV). Justera dessa siffror så att de passar era specifika sändningskrav och samarbeta med er leveranskonsult för att skapa en skräddarsydd plan.

| Dagar | % av UDV | Målgrupper | Innehållsrekommendationer |
|------|----------|-----------------|------------------------|
| 1-3 | 0,5 % | Dina mest engagerade mottagare | Använd ett kort, oformaterat textformat med en tydlig call-to-action-formatering som ligger över förskjutningen |
| 4-7 | 1 % | Engagerade användare och nya köpare | Lägg till en liten hjältebild, begränsa länkarna till 3 eller färre |
| 8-14 | 5 % | Bredare aktiv prenumerantlista | Presentera din standardmall för e-post, men undvik kostsamt reklammaterial |
| 15-21 | 25 % | Aktiva plus svagt inaktiva prenumeranter | Använd normalt marknadsföringsmaterial samtidigt som man noggrant övervakar antalet klagomål |
| 22-28 | 50-100 % | Fullständig lista (med hänsyn till undertryckningslistor) | Övergång till din stationära sändningsstation |

>[!NOTE]
>
>Adobe Journey Optimizer har en dedikerad funktion för [IP-värmningsplaner](ip-warmup-gs.md) som automatiserar volymhanteringen och förenklar värmningsprocessen utan att det krävs komplexa kundresekonfigurationer.

## Använda funktionen för AJO IP-uppvärmningsplaner {#ajo-warmup-feature}

Adobe Journey Optimizer har en smidig funktion för IP-uppvärmningsplaner som eliminerar behovet av manuell volymbegränsning genom komplexa kundresor. Den här funktionen garanterar en standardiserad metod för att bygga upp avsändarens anseende.

### Så fungerar det

1. **Skapa IP-värmare**: Bygg en eller flera kampanjer med alternativet **[!UICONTROL IP warmup plan activation]** aktiverat. [Läs mer](ip-warmup-campaign.md)

1. **Konfigurera din plan**: Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** > **[!UICONTROL IP warmup plans]** och överför den fasade mall för uppvärmning som har förberetts med din leveranskonsult. [Läs mer](ip-warmup-plan.md)

1. **Körningsfaser**: Välj en kampanj för varje fas och aktivera motsvarande körningar. Systemet exkluderar automatiskt profiler från tidigare körningar för att förhindra överkontaktlighet. [Läs mer](ip-warmup-execution.md)

1. **Övervaka och justera**: Använd den konsoliderade rapportkontrollpanelen för att spåra förloppet, övervaka körningsstatus och ändra planen om problem uppstår. [Läs mer](ip-warmup-execution.md#monitor-plan)

## Realtidsövervakning och nyckeltal {#monitoring}

Adobe Journey Optimizer har inbyggda rapporteringsfunktioner för att spåra prestanda för IP-värmare:

* **Live-rapporter**: Få åtkomst till realtidsmätning och visualisering av era kampanjer från fliken **[!UICONTROL Last 24hrs]**. [Läs mer](../reports/live-report.md)

* **Customer Journey Analytics-integrering**: Använd Customer Journey Analytics för att analysera data från Adobe Experience Platform och skapa anpassade visualiseringar om du vill ha mer information. [Läs mer](../reports/report-gs-cja.md)

### Måttmål

Övervaka dessa nyckeltal under hela värmen:

| Mått | Måltröskel | Åtgärd om överskriden |
|--------|-----------------|-------------------|
| Klagomålssats | ≤ 0,1 % | Granska segment och undertrycka kroniska klagare |
| Hård studsfrekvens | ≤ 2 % | Granska kvalitet och hygienrutiner för listor |
| Öppen kurs | ≥ 10 % | Verifiera att ni riktar in er på engagerade målgrupper |

>[!TIP]
>
>Använd funktionerna [kampanjliverapport](../reports/campaign-live-report.md#email-live) och [Customer Journey Analytics-rapport](../reports/campaign-global-report-cja-email.md) om du vill ha omfattande kampanjanalyser.

## Felsöka spelningsbok {#troubleshooting}

Använd den här beslutsmatrisen för att åtgärda vanliga problem under värmen:

| Symptom | Trolig orsak | Rekommenderad åtgärd |
|---------|--------------|-------------------|
| Tillfälliga Yahoo-fel (421 fel) | Volymen ökade för snabbt | Pausa sändning i 24 timmar och starta sedan om på föregående nivå |
| Öppen ränta under 2 % på startkonton | IP-blockeringslistning | Markera [Google Postmaster Tools](https://postmaster.google.com/) och [Microsoft SNDS](https://sendersupport.olc.protection.outlook.com/snds/); öppna en leveransbiljett om det behövs |
| Andelen klagomål överstiger 0,3 % | Målgrupp eller målgrupp som inte är särskilt inriktad | Granska segmentdefinitioner och exkludera kroniska klagare från din [undertryckningslista](manage-suppression-list.md) |

>[!IMPORTANT]
>
>Det är bättre att sänka värmen än att försöka reparera ett skadat avsändarrykte senare. Bevara alltid hälsosamma mätvärden framför aggressiv volymmappning.

## Bästa praxis efter varning {#post-warmup}

När du har slutfört din vårdsplan och mätvärden har stabiliserats:

* **Behåll enhetlighet**: Behåll dagliga volymökningar under 30 % vecka för vecka för att bevara ditt etablerade rykte

* **Övervaka kontinuerligt**: Schemalägg kvartalsvisa hälsokontroller för att identifiera och åtgärda problem proaktivt

* **Respektera engagemangssignaler**: Fortsätt att prioritera engagerade mottagare och implementera återengagemangskampanjer för inaktiva prenumeranter

* **Håll autentiseringen aktuell**: Kontrollera regelbundet att dina SPF-, DKIM- och DMARC-poster är korrekt konfigurerade

## Viktiga uppgifter {#key-takeaways}

* **IP-warmup är nödvändig**: Om du hoppar över warmup-processen kostar det mer tid och anseende än vad som krävs för att den ska fungera korrekt

* **Datadrivna beslut**: Följ upp klagomål, avhoppsfrekvens och engagemangsgrader dagligen och justera strategin innan internetleverantörer straffar dig

* **Autentisering först, volym två**: Lös alla problem med SPF, DKIM och DMARC innan du börjar montera volymen

* **Konsekvensproblem**: Postlådeprovidrar föredrar förutsägbara sändningsmönster och undviker plötsliga volymtoppar eller oregelbundna sändningsscheman

## Instruktionsvideo {#video}

Lär dig mer om grunderna för leveransförmåga, anseende och de bästa metoderna för IP-uppvärmning i Adobe Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/3463786/?captions=swe&learn=on)

<!--
>[!NOTE]
>
>For more guidance, explore the [Adobe Journey Optimizer Deliverability Guide blog post](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/adobe-journey-optimizer-deliverability-guide-from-zero/ba-p/761950).-->

## Relaterade ämnen {#related-topics}

* [Kom igång med planer för IP-värmare](ip-warmup-gs.md)
* [Skapa IP-värmningskampanjer](ip-warmup-campaign.md)
* [Skapa en IP-värmeringsplan](ip-warmup-plan.md)
* [Kör IP-värmerappen](ip-warmup-execution.md)
* [Konfigurera kanalkonfigurationer](channel-surfaces.md)
* [Delegera underdomäner](delegate-subdomain.md)
* [Hantera undertryckningslista](manage-suppression-list.md)
* [Guide till bästa praxis för slutprodukt](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=sv)

