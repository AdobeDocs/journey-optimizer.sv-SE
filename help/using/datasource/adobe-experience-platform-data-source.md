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
source-git-commit: e45ec5f0e1bbcc73892f9cde5923627886f44ef6
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 8%

---

# Datakällan i Adobe Experience Platform {#adobe-experience-platform-data-source}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_built_in"
>title="Datakällan i Adobe Experience Platform"
>abstract="Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är inbyggd och förkonfigurerad och kan inte tas bort. Den är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Ni kan använda profildata och Experience Events-data."

Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är inbyggd och förkonfigurerad och kan inte tas bort. Den här datakällan är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Ni kan använda profildata och Experience Events-data. Mer information om kundprofilen i realtid för Adobe finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}.

För att tillåta anslutningen till kundprofiltjänsten i realtid måste vi använda en nyckel för att identifiera en person och ett namnutrymme som kontextualiserar nyckeln. Därför kan du bara använda den här datakällan om dina resor börjar med en händelse som innehåller en nyckel och ett namnutrymme. [Läs mer](../building-journeys/journey.md).

Du kan redigera den förkonfigurerade fältgruppen med namnet &quot;ProfileFieldGroup&quot;, lägga till nya och ta bort de som inte används i utkast- eller direktresor. [Läs mer](../datasource/configure-data-sources.md#define-field-groups).

>[!NOTE]
>
>Du kan hämta de 1 000 senaste upplevelsehändelserna som skapades för mindre än ett år sedan.

Här är de viktigaste stegen för att lägga till fältgrupper i den inbyggda datakällan.

1. Välj den inbyggda Adobe Experience Platform-datakällan i listan över datakällor.

   Detta öppnar konfigurationsfönstret för datakällan till höger på skärmen.

   ![](assets/journey23.png)

1. Klicka på **[!UICONTROL Add a New Field Group]** för att definiera en ny serie med fält som ska hämtas. [Läs mer](../datasource/configure-data-sources.md#define-field-groups).

   ![](assets/journey24.png)

1. Välj ett schema i listrutan **[!UICONTROL Schema]**. I det här fältet visas profilscheman och Experience Events-scheman som är tillgängliga i Adobe Experience Platform. Schemat skapas inte i [!DNL Journey Optimizer]. Det genomförs i Adobe Experience Platform.
1. Markera de fält som du vill använda.
1. Klicka på **[!UICONTROL Save]**.

När du placerar markören på namnet på en fältgrupp visas två ikoner till höger. De gör att du kan ta bort och duplicera fältgruppen. Observera att ikonen **[!UICONTROL Delete]** bara är tillgänglig om fältgruppen inte används i någon direktresa eller utkastresa (information visas i fältet **[!UICONTROL Used in]**).
