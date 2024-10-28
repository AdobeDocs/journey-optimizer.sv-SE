---
solution: Journey Optimizer
product: journey optimizer
title: Publish hela resan
description: Lär dig rapportera om din resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: publicera, resa, live, giltighet, kontrollera
source-git-commit: 9b4ff0325d099252a5785aa13cfe0f1fe42acac6
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Live-rapport på arbetsytan {#report-journey}

>[!NOTE]
>
>Om du inte kan se data i din reserapport måste dina åtkomsträttigheter utökas till att omfatta behörigheten **[!UICONTROL View journeys report]**. [Läs mer](../administration/permissions.md)

När din resa har publicerats ger **Live Reporting** mätvärden från de senaste 24 timmarna, direkt på arbetsytan.

De visade händelserna inträffade under de senaste 24 timmarna, med ett minsta intervall på två minuter mellan händelsen och dess visning, vanligtvis inom fem minuter.

![](assets/journey_live_report.png)

Du har tillgång till följande för din direktresa:

* **[!UICONTROL Entered profiles]**: Totalt antal personer som avbrutit resan (inklusive fel).
* **[!UICONTROL Exited profiled]**: Totalt antal personer som har lämnat resan från den aktiviteten på grund av ett avslutningskriterium.
* **[!UICONTROL Profiles in error]**: Totalt antal personer som påträffade ett fel under sin resa.
* **[!UICONTROL Discarded profiles]**: Totalt antal personer som tagits bort från resan av någon av följande orsaker:

   * För **målgruppskvalificeringsaktiviteter** kan ett utkast tas bort om det förväntade verbet för målgruppskompetens inte matchar den resa som har tagits emot (t.ex. &quot;avslutad&quot; i stället för &quot;realiserad&quot;).
   * För **händelseutlösta** resor kan ett utkast göras om personen försökte att registrera om resan för tidigt eller när det inte var tillåtet att registrera om.
   * På **återkommande** resor räknas ett kasserat värde för varje upprepning om personen redan befinner sig på resan och återanmälningsprincipen inte är inställd på &quot;tvinga återinträde&quot;.
   * På **Läsa målgrupp**-aktiviteter inträffar ett ignoreringsförsök om ingen identitet har angetts för den exporterade personen eller om det mottagna ID-namnområdet inte matchar det förväntade för resan.

För varje aktivitet inom varje live-resa har du tillgång till:

* **[!UICONTROL Entered]**: Totalt antal personer som har gått in i den här aktiviteten.
* **[!UICONTROL Exited (met exit criteria)]**: Totalt antal personer som har lämnat resan från den aktiviteten på grund av ett avslutningskriterium.
* **[!UICONTROL Error]**: Totalt antal personer som hade ett fel i den aktiviteten.
