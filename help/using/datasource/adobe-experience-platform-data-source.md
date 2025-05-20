---
solution: Journey Optimizer
product: journey optimizer
title: Datakällan i Adobe Experience Platform
description: Lär dig konfigurera Adobe Experience Platform datakälla
feature: Journeys, Data Sources
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate, Experienced
keywords: inbyggd, källa, data, plattform, integrering
exl-id: 9083e355-15e3-4d1f-91ae-03095e08ad16
source-git-commit: f5ea4455fc0a8ed9e2819a260a8691fc1237844c
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 8%

---

# Datakällan i Adobe Experience Platform {#adobe-experience-platform-data-source}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_built_in"
>title="Datakällan i Adobe Experience Platform"
>abstract="Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är inbyggd och förkonfigurerad och kan inte tas bort. Den är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Ni kan använda profildata och Experience Events-data."

Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är inbyggd och förkonfigurerad och kan inte tas bort. Den här datakällan är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Ni kan använda profildata och Experience Events-data. Mer information om Adobe kundprofil i realtid finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}.

För att tillåta anslutningen till kundprofiltjänsten i realtid måste vi använda en nyckel för att identifiera en person och ett namnutrymme som kontextualiserar nyckeln. Därför kan du bara använda den här datakällan om dina resor börjar med en händelse som innehåller en nyckel och ett namnutrymme. [Läs mer](../building-journeys/journey.md).

Du kan redigera den förkonfigurerade fältgruppen med namnet &quot;ProfileFieldGroup&quot;, lägga till nya och ta bort de som inte används i utkast- eller direktresor. [Läs mer](../datasource/configure-data-sources.md#define-field-groups).

>[!NOTE]
>
>Du kan hämta de 1 000 senaste upplevelsehändelserna som skapades för mindre än ett år sedan.

De viktigaste stegen för att lägga till fältgrupper i den inbyggda datakällan beskrivs nedan:

1. Välj den inbyggda datakällan **Adobe Experience Platform** i listan över datakällor.

   Detta öppnar konfigurationsfönstret för datakällan till höger på skärmen.

   ![](assets/journey23.png)

1. Välj **[!UICONTROL Add a New Field Group]** om du vill definiera en [ny serie med fält som ska hämtas](../datasource/configure-data-sources.md#define-field-groups).

   ![](assets/journey24.png)

1. Välj ett schema i listrutan **[!UICONTROL Schema]**. I det här fältet visas **Profil** och **Experience Events**-scheman som är tillgängliga i Adobe Experience Platform. Scheman skapas i Adobe Experience Platform, men inte i Adobe Journey Optimizer.
1. Markera de fält som ska användas och spara ändringarna.


>[!TIP]
>
>Håll pekaren över namnet på en fältgrupp för att visa två ikoner till höger. Använd dessa för att **duplicera** eller **ta bort** fältgruppen. Observera att ikonen **[!UICONTROL Delete]** bara är tillgänglig om fältgruppen inte används i någon **Live**-, **Draft**- eller **Finished**-resa. Kontrollera om så är fallet i fältet **[!UICONTROL Used in]**.
