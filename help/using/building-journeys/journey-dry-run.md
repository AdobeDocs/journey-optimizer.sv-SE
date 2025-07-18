---
solution: Journey Optimizer
product: journey optimizer
title: Körning av resetorr
description: Lär dig hur du publicerar en resa i körläge med torrt läge
feature: Journeys
role: User
level: Intermediate
badge: label="Begränsad tillgänglighet" type="Informative"
keywords: publicera, resa, live, giltighet, kontrollera
exl-id: 58bcc8b8-5828-4ceb-9d34-8add9802b19d
source-git-commit: 62525caa9b065538c090b98d38c15dbd960dafe7
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 0%

---

# Körning av resetorr {#journey-dry-run}

>[!CONTEXTUALHELP]
>id="ajo_journey_dry_run"
>title="Torr körning"
>abstract="Den här resan är i Torrkörning. Körning på resa Dry är ett särskilt publiceringsläge för resor i Adobe Journey Optimizer som gör det möjligt för resenärer att testa en resa med hjälp av verkliga produktionsdata utan att behöva kontakta riktiga kunder eller uppdatera profilinformation.  Den här funktionen hjälper resenärer att få förtroende för sin resedesign och målgruppsanpassning innan de publicerar den live."


>[!CONTEXTUALHELP]
>id="ajo_journey_dry_run_start"
>title="Publicera en resa i torrkörningsläge"
>abstract="Körning på resa Dry är ett särskilt publiceringsläge för resor i Adobe Journey Optimizer som gör det möjligt för resenärer att testa en resa med hjälp av verkliga produktionsdata. När du har utformat din resa kan du utföra en torr körning för att bekräfta att den fungerar och se till att stegen är korrekta. I det här publiceringsläget kan du röka en resa utan att skicka kommunikation till någon profil."

Körning på resa Dry är ett särskilt publiceringsläge för resor i Adobe Journey Optimizer som gör det möjligt för resenärer att testa en resa med hjälp av verkliga produktionsdata utan att behöva kontakta riktiga kunder eller uppdatera profilinformation.  Den här funktionen hjälper resenärer att få förtroende för sin resedesign och målgruppsanpassning innan de publicerar den live.


>[!AVAILABILITY]
>
>Den här funktionen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet) och kommer att lanseras globalt i en framtida version.


## Viktiga fördelar {#journey-dry-run-benefits}

Rundtur Dry-körningen ökar yrkesutövarnas förtroende och framgångar genom att möjliggöra säker, datadriven testning av kundresor med hjälp av verkliga produktionsdata, utan risk för att kontakta kunder eller ändra profilinformation. Den här funktionen gör det möjligt för resenärer att validera målgruppernas räckvidd och grenlogik innan de publicerar, vilket säkerställer att resorna överensstämmer med deras avsedda affärsmål.

Med Journey Dry-körningen får ni möjlighet att identifiera problem tidigt, optimera målinriktningsstrategier och förbättra resedesignen baserat på faktiska data - inte antaganden. Dry run är integrerat direkt i arbetsytan och ger intuitiv rapportering och insyn i viktiga resultatindikatorer så att teamen kan iterera säkert och effektivisera godkännandearbetsflödena. Detta förbättrar effektiviteten, minskar startriskerna och ger bättre resultat när det gäller kundengagemang.

I slutänden förbättrar den här funktionen time-to-value och minskar antalet misslyckade kundresor.

Journey Dry-körningen ger

1. **Säker testmiljö**: Profiler i torr körningsläge kontaktas inte, vilket säkerställer att det inte finns någon risk för att meddelanden skickas eller att livedata påverkas.
1. **Målgruppsinsikter**: Reseutövare kan förutsäga målgruppernas nåbarhet på olika kundnoder, inklusive avanmälan, undantag och andra villkor.
1. **Återkoppling i realtid**: Mätvärden visas direkt på arbetsytan i realtid, på liknande sätt som live-rapportering, vilket gör det möjligt för resenärerna att förfina sin resedesign.

Under torra körningar utförs resan med följande särdrag:

* **Kanalåtgärd**-noder som e-post, SMS eller push-meddelanden körs inte
* **Anpassade åtgärder** inaktiveras under körning och deras svar anges till null
* **Väntenoderna** ignoreras under körning av torr nod.
  <!--You can override the wait block timeouts, then if you have wait blocks duration longer than allowed dry run journey duration, then that branch will not execute completely.-->
* **Datakällor**, inklusive externa datakällor, körs som standard

>[!CAUTION]
>
>* Behörigheter att starta Torr körning är begränsade till användare med hög behörighet på **[!DNL Publish journeys]**. Behörigheter att stoppa Torr körning är begränsade till användare med hög behörighet på **[!DNL Manage journeys]**. Läs mer om hur du hanterar [!DNL Journey Optimizer] användares åtkomsträttigheter i [det här avsnittet](../administration/permissions-overview.md).
>
>* Innan du börjar använda funktionen för torr körning ska du [läsa igenom GuarDRAils and Limitations](#journey-dry-run-limitations).


## Starta en torr körning {#journey-dry-run-start}

Du kan använda körningsfunktionen Torr i alla utkast-resor utan fel.

Så här aktiverar du Torr körning:

1. Öppna den resa du vill testa.
1. Markera knappen **Torr körning**.

   ![Starta färdens torra körning](assets/dry-run-button.png)

1. Bekräfta publikationen.

   Ett statusmeddelande, **Aktivera Torr körning**, visas medan övergången pågår.

1. När den har aktiverats går resan in i läget **Torr körning**.

## Övervaka en torr körning {#journey-dry-monitor}

När Dry Mode-publikationen har startats kan du visualisera körningen av resan och hur profiler utvecklas genom resegrenar och noder.

Mätvärden visas direkt på arbetsytan. Läs mer om live-rapportering och statistik för resan i [Live-rapporten på arbetsytan](report-journey.md).

![Övervaka körningen i torr riktning](assets/dry-run-metrics.png)


Du kan även komma åt **Senaste 24-timmarsrapporterna** och **heltidsrapporterna** för torr körning. Klicka på knappen **Visa rapport** i det övre högra hörnet av arbetsytan för att få åtkomst till dessa rapporter.

![Få åtkomst till rapporterna för körning i torr körning](assets/dry-run-report.png)

>[!CAUTION]
>
> Rapporteringsdata är bara tillgängliga när Torr körning är **aktiv**.  När den har stoppats är rapportdata inte längre tillgängliga. Använd knappen **Exportera** ovanför rapporterna om du vill hämta dem vid behov.


## Stoppa en torr körning {#journey-dry-run-stop}

Torra körningsresor **måste** stoppas manuellt.

Klicka på knappen **Stäng** för att avsluta testet och klicka sedan på **Tillbaka till utkast** för att bekräfta.

<!-- After 14 days, Dry run journeys automatically transition to the **Draft** status.-->

## Skyddsritningar och begränsningar {#journey-dry-run-limitations}

* Körningsläget Torr är inte tillgängligt för resor som innehåller reaktionshändelser
* Profiler i torr körningsläge räknas mot profiler som kan användas
* Resor i torr körning räknas som en del av kvoten för direktfärd
* Torra resor påverkar inte affärsreglerna
* Om en tidigare version av en resa är **Live** när en ny version skapas tillåts inte aktivering av körningen av Dry för den nya versionen.
* Körning av körning av resedagring genererar stepEvents. Dessa stepEvents har en särskild flagga och ett körnings-ID för torr:
   * `_experience.journeyOrchestration.stepEvents.inDryRun` returnerar `true` om Torr-körningen är aktiverad, i annat fall `false`
   * `_experience.journeyOrchestration.stepEvents.dryRunID` returnerar ID:t för en instans med torr körning

* Vid analys av mått för reserapportering med hjälp av tjänsten Adobe Experience Platform Query, måste händelser som genererats av Dry Run uteslutas. Om du vill göra det anger du flaggan `inDryRun` till `false`.