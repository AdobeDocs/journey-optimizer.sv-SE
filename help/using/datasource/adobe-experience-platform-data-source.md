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
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 9%

---

# Datakällan i Adobe Experience Platform {#adobe-experience-platform-data-source}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_built_in"
>title="Datakällan i Adobe Experience Platform"
>abstract="Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är inbyggd och förkonfigurerad och kan inte tas bort. Den är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Ni kan använda profildata och Experience Events-data."

Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är inbyggd och förkonfigurerad och kan inte tas bort. Den här datakällan är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Ni kan använda profildata och Experience Events-data. Mer information om kundprofilen i realtid för Adobe finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}.


För att tillåta anslutningen till kundprofiltjänsten i realtid måste vi använda en nyckel för att identifiera en person och ett namnutrymme som kontextualiserar nyckeln. Därför kan du bara använda den här datakällan om dina resor börjar med en händelse som innehåller en nyckel och ett namnutrymme. [Läs mer](../building-journeys/journey.md).

Du kan redigera den förkonfigurerade fältgruppen med namnet &quot;ProfileFieldGroup&quot;, lägga till nya och ta bort de som inte används i utkast- eller direktresor. [Läs mer](../datasource/configure-data-sources.md#define-field-groups).


>[!NOTE]
>
>Du kan hämta de 1 000 senaste upplevelsehändelserna som skapades för mindre än ett år sedan.

Här är de viktigaste stegen för att lägga till fältgrupper i den inbyggda datakällan.

1. Välj den inbyggda Adobe Experience Platform-datakällan i listan över datakällor.

   Detta öppnar konfigurationsfönstret för datakällan till höger på skärmen.

   ![](assets/journey23.png)

1. Klicka **[!UICONTROL Add a New Field Group]** för att definiera en ny serie fält som ska hämtas. [Läs mer](../datasource/configure-data-sources.md#define-field-groups).

   ![](assets/journey24.png)

1. Välj ett schema från **[!UICONTROL Schema]** nedrullningsbar meny. I det här fältet visas profilscheman och Experience Events-scheman som är tillgängliga i Adobe Experience Platform. Schemat skapas inte i [!DNL Journey Optimizer]. Det genomförs i Adobe Experience Platform.
1. Markera de fält som du vill använda.
1. Klicka på **[!UICONTROL Save]**.

När du placerar markören på namnet på en fältgrupp visas två ikoner till höger. De gör att du kan ta bort och duplicera fältgruppen. Observera att **[!UICONTROL Delete]** ikonen är bara tillgänglig om fältgruppen inte används i någon live- eller utkastresa (information visas i **[!UICONTROL Used in]** fält).
