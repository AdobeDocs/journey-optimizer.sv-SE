---
solution: Journey Optimizer
product: journey optimizer
title: Datakällan i Adobe Experience Platform
description: Lär dig konfigurera Adobe Experience Platform datakälla
feature: Journeys, Data Sources
topic: Administration
role: Developer, Admin
level: Intermediate, Experienced
keywords: inbyggd, källa, data, plattform, integrering
exl-id: 9083e355-15e3-4d1f-91ae-03095e08ad16
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 9%

---

# Datakällan i Adobe Experience Platform {#adobe-experience-platform-data-source}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_built_in"
>title="Datakällan i Adobe Experience Platform"
>abstract="Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är inbyggd och förkonfigurerad och kan inte tas bort. Den är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna)."

Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är inbyggd och förkonfigurerad och kan inte tas bort. Den här datakällan är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Mer information om Adobe kundprofil i realtid finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}.

För att tillåta anslutningen till kundprofiltjänsten i realtid måste vi använda en nyckel för att identifiera en person och ett namnutrymme som kontextualiserar nyckeln. Därför kan du bara använda den här datakällan om dina resor börjar med en händelse som innehåller en nyckel och ett namnutrymme. [Läs mer](../building-journeys/journey.md).

Du kan redigera den förkonfigurerade fältgruppen med namnet &quot;ProfileFieldGroup&quot;, lägga till nya och ta bort de som inte används i utkast- eller direktresor. [Läs mer](../datasource/configure-data-sources.md#define-field-groups).


>[!CAUTION]
>
>Det finns inte stöd för att använda upplevelsehändelser i uttryck/villkor för resan. Om ditt användningsfall kräver att du använder upplevelsehändelser bör du överväga alternativa metoder. [Läs mer](../building-journeys/exp-event-lookup.md)


De viktigaste stegen för att lägga till fältgrupper i den inbyggda datakällan beskrivs nedan:

1. Välj den inbyggda **Adobe Experience Platform**-datakällan i listan över datakällor.

   Detta öppnar konfigurationsfönstret för datakällan till höger på skärmen.

   ![](assets/journey23.png)

1. Välj **[!UICONTROL Add a New Field Group]** om du vill definiera en [ny serie med fält som ska hämtas](../datasource/configure-data-sources.md#define-field-groups).

   ![](assets/journey24.png)

1. Välj ett schema i listrutan **[!UICONTROL Schema]**. Scheman skapas i Adobe Experience Platform, men inte i Adobe Journey Optimizer.
1. Markera de fält som ska användas och spara ändringarna.


>[!TIP]
>
>Håll pekaren över namnet på en fältgrupp för att visa två ikoner till höger. Använd dessa för att **duplicera** eller **ta bort** fältgruppen. Observera att ikonen **[!UICONTROL Delete]** bara är tillgänglig om fältgruppen inte används i någon **Live**-, **Draft**- eller **Finished**-resa. Kontrollera om så är fallet i fältet **[!UICONTROL Used in]**.
