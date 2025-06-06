---
solution: Journey Optimizer
product: journey optimizer
title: Körning av resetorr
description: Lär dig hur du publicerar en resa i körläge med torrt läge
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Begränsad tillgänglighet" type="Informative"
keywords: publicera, resa, live, giltighet, kontrollera
exl-id: 58bcc8b8-5828-4ceb-9d34-8add9802b19d
source-git-commit: 9ac387f073d8f0384e20cb2d8fe327efe4b8ecde
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 0%

---

# Körning av resetorr {#journey-dry-run}

>[!CONTEXTUALHELP]
>id="ajo_journey_dry_run"
>title="Torka din resa"
>abstract="När du har utformat din resa kan du utföra en torr körning för att bekräfta att den fungerar och se till att stegen är korrekta. I det här publiceringsläget kan du röka en resa utan att skicka kommunikation till någon profil."

Körning på resa Dry är ett särskilt publiceringsläge för resor i Adobe Journey Optimizer som gör att marknadsförare kan testa en resa med hjälp av verkliga produktionsdata utan att behöva kontakta riktiga kunder eller uppdatera profilinformation.  Den här funktionen hjälper marknadsförarna att få förtroende för sin kundresa och målgruppsanpassning innan de publicerar den live.


>[!AVAILABILITY]
>
>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.


## Viktiga fördelar {#journey-dry-run-benefits}

Rundtur Dry-körningen ökar yrkesutövarnas förtroende och framgångar genom att möjliggöra säker, datadriven testning av kundresor med hjälp av verkliga produktionsdata, utan risk för att kontakta kunder eller ändra profilinformation. Den här funktionen ger marknadsförarna möjlighet att validera målgruppernas räckvidd och branschlogik innan de publicerar, vilket säkerställer att resorna är i linje med de avsedda affärsmålen.

Med Journey Dry-körningen får ni möjlighet att identifiera problem tidigt, optimera målinriktningsstrategier och förbättra resedesignen baserat på faktiska data - inte antaganden. Dry run är integrerat direkt i arbetsytan och ger intuitiv rapportering och insyn i viktiga resultatindikatorer så att teamen kan iterera säkert och effektivisera godkännandearbetsflödena. Detta förbättrar effektiviteten, minskar startriskerna och ger bättre resultat när det gäller kundengagemang.

I slutänden förbättrar den här funktionen time-to-value, minskar antalet misslyckade kundresor och stärker Adobe position som den betrodda plattformen för att samordna personaliserade, slagkraftiga kundresor.

Journey Dry-körningen ger

1. **Säker testmiljö**: Profiler i torr körningsläge kontaktas inte, vilket säkerställer att det inte finns någon risk för att meddelanden skickas eller att livedata påverkas.
1. **Målgruppsinsikter**: Marknadsförarna kan förutsäga målgruppernas nåbarhet på olika kundnoder, inklusive avanmälan, undantag och andra villkor.
1. **Återkoppling i realtid**: Mätvärden visas direkt på arbetsytan i realtid, på liknande sätt som direktrapportering, vilket gör att marknadsförarna kan förfina sin resedesign.

## Starta en torr körning {#journey-dry-run-start}

Du kan använda körningsfunktionen Torr i alla utkast-resor utan fel.

Så här aktiverar du Torr körning:

1. Öppna den resa du vill testa.
1. Klicka på knappen **Torr körning**.

   ![Starta färdens torra körning](assets/dry-run-button.png)

1. Bekräfta publikationen

   Ett statusmeddelande, **Aktivera Torr körning**, visas medan övergången pågår.

1. När resan har aktiverats går den vidare till körningsläget Torr.

Under torra körningar utförs resan med följande särdrag:

* **Kanalåtgärd**-noder med e-post-, SMS- eller push-meddelanden körs inte.
* **Anpassade åtgärder** inaktiveras under körning av Dry och deras svar anges till null.
* **Väntenoderna** ignoreras under körning av torr nod.
  <!--You can override the wait block timeouts, then if you have wait blocks duration longer than allowed dry run journey duration, then that branch will not execute completely.-->
* **Externa datakällor** körs som standard.

>[!NOTE]
>
> * Profiler i körningsläget Torr räknas mot profiler som kan användas.
> * Torra resor påverkar inte affärsreglerna. En profil i en körningsresa med Torr körning kommer till exempel inte att uteslutas från andra resor på grund av regler som `1 journey per day`.

## Övervaka en torr körning {#journey-dry-monitor}

När Dry Mode-publikationen har startats kan du visualisera körningen av resan och hur profiler utvecklas genom resegrenar och noder.

Mätvärden visas direkt på arbetsytan.

![Övervaka körningen i torr riktning](assets/dry-run-metrics.png)

För varje aktivitet kan du kontrollera:

* **[!UICONTROL Entered]**: Totalt antal personer som har gått in i den här aktiviteten.
* **[!UICONTROL Exited (met exit criteria)]**: Totalt antal personer som har lämnat resan från den aktiviteten på grund av ett avslutningskriterium.
* **[!UICONTROL Exited (forced exit)]**: Totalt antal personer som slutade när resan pausades.
* **[!UICONTROL Error]**: Totalt antal personer som hade ett fel i den aktiviteten.


På kundresan kan du kontrollera:

* Totalt antal **angivna profiler**
* Totalt antal **avslutade profiler**
* Totalt antal **profiler i fel**
* Det totala antalet **ignorerade profiler** under resan

Du kan även komma åt **Senaste 24-timmarsrapporterna** och **heltidsrapporterna** för torr körning. Klicka på knappen **Visa rapport** i det övre högra hörnet av arbetsytan för att få åtkomst till dessa rapporter.

![Få åtkomst till rapporterna för körning i torr körning](assets/dry-run-report.png)

>[!CAUTION]
>
> Rapporteringsdata är bara tillgängliga när Torr körning är **aktiv**.  När den har stoppats är rapportdata inte längre tillgängliga. Använd knappen **Exportera** ovanför rapporterna om du vill hämta dem vid behov.


## Stoppa en torr körning {#journey-dry-run-stop}

Torra körningar måste stoppas manuellt. Klicka på knappen **Stäng** för att avsluta testet och bekräfta.

Efter 14 dagar övergår Dry Run-resor automatiskt till utkaststatus.
