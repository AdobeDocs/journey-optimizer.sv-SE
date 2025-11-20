---
solution: Journey Optimizer
product: journey optimizer
title: Publicera resan
description: Lär dig rapportera om din resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: publicera, resa, live, giltighet, kontrollera
exl-id: 186b061d-0941-48be-8917-bbdfff6dae90
version: Journey Orchestration
source-git-commit: 6961a07e2874f9beb76a9beaebb29997d114d8e7
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 1%

---

# Live-rapport på arbetsytan {#report-journey}

När din resa har publicerats och [Dry run mode](journey-dry-run.md) har aktiverats ger **Live Reporting** mätvärden från de senaste 24 timmarna, direkt på arbetsytan.


>[!AVAILABILITY]
>
>Om du inte kan se data i din reserapport måste dina åtkomsträttigheter utökas till att omfatta behörigheten **[!UICONTROL View journeys report]**. [Läs mer](../administration/permissions.md)


De visade händelserna inträffade under de senaste 24 timmarna, med ett minsta intervall på två minuter mellan händelsen och dess visning, vanligtvis inom fem minuter.

![Kontrollpanel för liverapport i resan som visar prestandamått i realtid](assets/journey_live_report.png)

För dina resor i Live eller [Torr körning](journey-dry-run.md) kan du kontrollera:

* **[!UICONTROL Entered profiles]**: Totalt antal personer som har passerat resan.
* **[!UICONTROL Exited profiles]**: Totalt antal personer som avbrutit resan (inklusive fel).
* **[!UICONTROL Profiles in error]**: Totalt antal personer som påträffade ett fel under sin resa.
* **[!UICONTROL Discarded profiles]**: Totalt antal personer som tagits bort från resan av någon av följande orsaker:

   * För **målgruppskvalificeringsaktiviteter** kan ett utkast tas bort om det förväntade verbet för målgruppskompetens inte matchar den resa som har tagits emot (t.ex. &quot;avslutad&quot; i stället för &quot;realiserad&quot;).
   * För **händelseutlösta** resor kan ett utkast göras om personen försökte att registrera om resan för tidigt eller när det inte var tillåtet att registrera om.
   * På **återkommande** resor räknas ett kasserat värde för varje upprepning om personen redan befinner sig på resan och återanmälningsprincipen inte är inställd på &quot;tvinga återinträde&quot;.
   * På **Läsa målgrupp**-aktiviteter inträffar ett ignoreringsförsök om ingen identitet har angetts för den exporterade personen eller om det mottagna ID-namnområdet inte matchar det förväntade för resan.

För varje aktivitet inom varje resa i Live eller [Torr körningsläge](journey-dry-run.md) har du tillgång till:

* **[!UICONTROL Entered]**: Totalt antal personer som har gått in i den här aktiviteten. För **Åtgärd**-aktiviteter, eftersom de inte körs i körningsläget Torr, indikerar det här måttet att profiler passerar igenom.
* **[!UICONTROL Exited (met exit criteria)]**: Totalt antal personer som har lämnat resan från den aktiviteten på grund av ett avslutningskriterium (inklusive fel).
* **[!UICONTROL Exited (forced exit)]**: Totalt antal personer som avbrutit resan medan den pausades på grund av en konfiguration för reseadministratörer. Det här måttet är alltid lika med noll för resor i körläge med torr körning.
* **[!UICONTROL Error]**: Totalt antal personer som hade ett fel i den aktiviteten.

## Felsöka saknade rapporteringsdata {#troubleshooting-missing-data}

Om du inte ser förväntade data i dina reserapporter bör du tänka på följande:

* **Resensnamnsynkronisering**: Verifiera att resenamnet i Adobe Journey Optimizer matchar det namn som lagrats i rapporteringsdatauppsättningen. Om namnen inte matchar kan det förhindra att rapportdata visas korrekt.

* **Tidsåtgång för datauppdatering**: När du har uppdaterat ett resenamn eller en konfiguration kan du vänta tillräckligt länge för att data ska uppdateras. Rapporteringsdata visas vanligtvis inom några minuter, men kan i vissa fall ta längre tid.

* **Åtkomstbehörigheter**: Kontrollera att du har de behörigheter som krävs för att visa reserapporter. Om du inte ser några data bör du kontrollera med administratören att behörigheten **[!UICONTROL View journeys report]** är aktiverad. [Läs mer om behörigheter](../administration/permissions.md)

* **Resursstatus**: Rapporteringsdata är bara tillgängliga för publicerade resor eller resor som körs i [Torrkörningsläge](journey-dry-run.md). Utkastresor genererar inga rapportdata.

Kontakta Adobe-administratören eller Adobe support om problemet kvarstår efter att du har verifierat dessa objekt.

>[!MORELIKETHIS]
>
>* [Kom igång med rapportering](../reports/gs-reports.md)
>* [Publicera din resa](publish-journey.md)
>* [Renstorkning](journey-dry-run.md)
>* [Konfigurera och spåra dina resemått](success-metrics.md)
>* [Anpassade reserapporter](../reports/sharing-overview.md)
