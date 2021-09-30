---
title: Snabbstart
description: Journey Optimizer snabbstart
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 71ab7369-fd84-46eb-95d2-941bd887d565
source-git-commit: 9c1edc8d79c58fcf4f2048b9fe81cd31ea621777
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 4%

---

# Snabbstart {#cjm-quick-start}

## Viktiga steg att starta {#cjm-key-steps}

Med [!DNL Adobe Journey Optimizer] kan du importera befintligt meddelandeinnehåll eller utforma ett nytt innehåll, anpassa meddelanden med kundprofildata, skapa händelser för att utlösa meddelanden, definiera segment och förfina målgrupper, skicka flerkanalsmeddelanden, skapa och lägga till erbjudanden och få tillgång till en komplett uppsättning rapporterings- och övervakningsverktyg för att mäta effekten av era meddelanden och kundresor.

Beroende på din organisation kan du definiera flera typer av användare och ge dem åtkomst till vissa funktioner beroende på deras behörigheter.

## Förbered och konfigurera miljön

Innan du börjar använda [!DNL Adobe Journey Optimizer] måste du utföra flera steg för att förbereda miljön.

Som systemadministratör måste du **förstå produktprofiler och tilldela behörigheter** för sandlådeadministration och kanalkonfiguration. Du måste också konfigurera sandlådor och hantera dem för de tillgängliga produktprofilerna.
Du kan sedan tilldela teammedlemmar till produktprofiler och **konfigurera kanalkonfiguration** för meddelanden.

Läs mer på följande sidor:

* **Ange** användarbehörigheter och ge åtkomst till dina teammedlemmar. [Läs mer](../using/administration/permissions.md)

* **Distribuera[!DNL Adobe Experience Manager Assets Essentials]** för att hantera resurser och bilder i dina meddelanden: -användare som behöver åtkomst till  [!DNL Assets Essentials] måste vara en del av  **Assets Essentials** konsumentanvändare/och  **Assets Essentials** användarproduktprofiler. [Läs mer i Assets Essentials-dokumentationen](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html){target=&quot;_blank&quot;}

* **Konfigurera** kanalerna och definiera inställningarna för e-post och push-meddelanden. [Läs mer](../using/configuration/get-started-configuration.md)

* **Definiera dina** förinställningar och konfigurera brandingsparametrarna. [Läs mer](../using/configuration/message-presets.md)

* **Hantera** sandlådor för att partitionera instansen i separata virtuella miljöer. [Läs mer](../using/administration/sandboxes.md)


## Förbered era data och konfigurera era resor

Som dataadministratör måste du **identifiera data och skapa schema och datauppsättning** för att kunna hämta data till Adobe Experience Platform.

Steg för att skapa ett identitetsnamnutrymme och en datauppsättning aktiverad för profiler, skapa segment och testprofiler beskrivs i avsnitten nedan:

* Lär dig hur du förhandsgranskar och skapar en **datauppsättning** i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html){target=&quot;_blank&quot;}

* Lär dig hur du skapar ett **identitetsnamnutrymme** i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces){target=&quot;_blank&quot;}

* Lär dig hur du skapar **testprofiler** i [den här sidan](../using/building-journeys/creating-test-profiles.md)

* Läs mer om **dataöverföring** i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html){target=&quot;_blank&quot;}

* Lär dig hur du **definierar målgrupper**, skapar segment, hanterar samtycke och sekretess i [den här sidan](../using/segment/about-segments.md)

För att kunna skicka meddelanden under resor måste du dessutom konfigurera **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]**. Läs mer i [det här avsnittet](../using/configuration/about-data-sources-events-actions.md)

## Skapa meddelanden, erbjudanden och resor

Som resande lärare kan du läsa följande avsnitt för att konfigurera din första resa, lägga till erbjudanden och resurser och skicka meddelanden:

* **Skapa meddelanden**: få tillgång till meddelanden, utforma eller läsa in e-post och push-innehåll, lägga till personalisering och förhandsgranskningsmeddelanden. [Läs mer](create-message.md)

* **Överför resurser**: använda Adobe Experience Manager Assets Essentials för att hantera resurser och bilder. [Läs mer](assets-essentials.md)

* **Lägg till erbjudanden**: Använd Journey Optimizer Decision Management för att lägga in skräddarsydda erbjudanden i era meddelanden. [Läs mer](../using/offers/get-started/starting-offer-decisioning.md)

* **Skapa resor**: skicka meddelanden, utnyttja sammanhangsbaserade data, förfina målgrupper, utforma och köra flerstegsbaserade fallstudier. [Läs mer](building-journeys/journey.md)

* **Övervaka meddelanden och resor**: kontrollera meddelandekörning, kontrollera meddelande- och reserapporter, uppföljningsstatistik. [Läs mer](message-monitoring.md)
