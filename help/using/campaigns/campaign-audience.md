---
solution: Journey Optimizer
product: journey optimizer
title: Definiera målgruppen för Action-kampanjen
description: Lär dig definiera målgruppen för Action-kampanjen.
feature: Campaigns
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
keywords: skapa, optimera, kampanj, yta, meddelanden
exl-id: 5635ef04-c69d-4397-9762-7a6f1265d453
source-git-commit: 93698c93f3750b4d7feff18509f8144a7c79f156
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 3%

---

# Definiera målgruppen för Action-kampanjen {#action-campaign-audience}

Använd fliken **[!UICONTROL Audience]** för att definiera kampanjens målgrupp.

![](assets/campaign-audience.png)

1. **Välj målgruppen**

   För marknadsföringskampanjer klickar du på knappen **[!UICONTROL Select audience]** för att visa listan över tillgängliga Adobe Experience Platform-målgrupper. [Läs mer om målgrupper](../audience/about-audiences.md).

   >[!IMPORTANT]
   >
   >Användning av målgrupper och attribut från [målgruppskomposition](../audience/get-started-audience-orchestration.md) är för närvarande inte tillgängligt för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.

1. **Välj identitetstyp**

   I fältet **[!UICONTROL Identity type]** väljer du vilken typ av nyckel som ska användas för att identifiera personer från den valda målgruppen. Du kan antingen använda en befintlig identitetstyp eller skapa en ny med hjälp av Adobe Experience Platform identitetstjänst. Standardidentitetsnamnutrymmen visas på [den här sidan](https://experienceleague.adobe.com/sv/docs/experience-platform/identity/features/namespaces#standard){target="_blank"}.

   Endast en identitetstyp tillåts per kampanj. Individer som tillhör ett segment som inte har den valda identitetstypen bland sina olika identiteter kan inte omfattas av kampanjen. Läs mer om identitetstyper och namnutrymmen i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=sv){target="_blank"}.

## Nästa steg {#next}

När målgruppen för er Action-kampanj är klar kan ni planera kampanjen. [Läs mer](campaign-schedule.md)
