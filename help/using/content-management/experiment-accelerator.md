---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Experimentation Accelerator
description: Förbättra er förmåga att utföra experiment effektivt och generera insikter
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: innehåll, experimentera, multipelt, målgrupp, behandling
hide: true
hidefromtoc: true
source-git-commit: eb5c9c949b89406cfe62f136bd6a52ab2692b6e4
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Kom igång med Journey Optimizer Experimentation Accelerator {#content-experiment}

>[!BEGINSHADEBOX]

* **[Kom igång med Journey Optimizer Experimentation Accelerator](experiment-accelerator.md)**
* [Dataanvändning i AI med Journey Optimizer Experimentation Accelerator](experiment-accelerator-security.md)
* [Journey Optimizer Experimentation Accelerator bästa praxis](experiment-accelerator-best-practices.md)
* [Övervaka experiment](experiment-accelerator-monitor.md)
* [Experimentationsmått](experiment-accelerator-metrics.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>**Journey Optimizer Experimentation Accelerator** kräver att kunderna har en licens för antingen Adobe Target eller Adobe Journey Optimizer.

**Journey Optimizer Experimentation Accelerator** är ett kraftfullt verktyg som har utformats för att effektivisera och förbättra experimenteringsprocessen. Genom att integrera med Adobe Target och Adobe Journey Optimizer utgör programmet en central plattform för att hantera, analysera och optimera experiment. Med hjälp av AI-baserade insikter och adaptiv testning kan ni med Journey Optimizer Experimentation Accelerator fatta datadrivna beslut, förbättra marknadsföringsstrategier och få mätbara resultat.

Några viktiga fördelar:

* **Snabbare experimenterande**: Kör adaptiva, alltid-på-tester med modeller som justeras över tid.

* **Enhetlig plattform**: Hantera alla experiment från Adobe Target och Journey Optimizer på ett och samma ställe.

* **AI-styrda insikter**: Hitta viktiga resultat, prestandadrivrutiner och nya möjligheter automatiskt.

* **Smartare målgruppsanpassning**: Använd beteendes- och innehållsdata för att prioritera effektiva experiment.

* **KPI-övervakning**: Spåra mätvärden som lyft och förtroende mellan experiment.

* **Smidig Collaboration**: Dela enkelt resultat och hantera teamroller med aviseringar i realtid.

## Använd Journey Optimizer Experimentation Accelerator

När du har [skapat och konfigurerat ditt experiment](content-experiment.md) och skickat dina kampanjer eller resor till dina profiler, kan du få tillgång till **[!UICONTROL Journey Optimizer Experimentation Accelerator]** och fördjupa dig i hur ditt experiment fungerar.

Du kan komma åt **[!UICONTROL Journey Optimizer Experimentation Accelerator]** antingen från den vänstra menyn i listrutan [!UICONTROL Experimentation] eller via Apps-väljaren. Observera att användare som bara har en Target-licens bara kan komma åt den via Apps-väljaren.

Vilka experiment som är tillgängliga beror på din konfiguration:

* **För Adobe Journey Optimizer-användare**: Experiment som har konfigurerats i den aktiverade organisationens sandlåda inkluderas automatiskt.

* **För Adobe Target-användare med Journey Optimizer**: Alla A/B-aktiviteter i Target visas i **[!UICONTROL Journey Optimizer Experimentation Accelerator]** i produktionssandlådan för Journey Optimizer.

* **För användare som endast har Adobe Target**: Alla A/B-aktiviteter i målorganisationen inkluderas i produktionssandlådan för Journey Optimizer.

Om du vill använda **[!UICONTROL Journey Optimizer Experimentation Accelerator]** måste du ha tillgång till sandlådan och följande relaterade behörighet:

* **[!UICONTROL View Experiments]**
* **[!UICONTROL Manage Experiment Metada]**

+++ Lär dig hur du tilldelar Experimentatrelaterade behörigheter

1. Gå till fliken **[!DNL Permissions]** i **[!UICONTROL Roles]**-produkten och välj önskad **[!UICONTROL Role]**.

1. Klicka på **[!UICONTROL Edit]** om du vill ändra behörigheterna.

1. Lägg till resursen **[!UICONTROL Experiment accelerator]** och välj sedan **[!UICONTROL View Experiments]** och/eller **[!UICONTROL Manage Experiment Metada]** i listrutan.

   ![](assets/permissions-experiment.png)

1. Klicka på **[!UICONTROL Save]** om du vill använda ändringarna.

Alla användare som redan har tilldelats den här rollen får sina behörigheter automatiskt uppdaterade.

Så här tilldelar du rollen till nya användare:

1. Navigera till fliken **[!UICONTROL Users]** i rollkontrollpanelen och klicka på **[!UICONTROL Add User]**.

1. Ange användarens namn, e-postadress eller välj i listan och klicka sedan på **[!UICONTROL Save]**.

   Om användaren inte har skapats tidigare, se [den här dokumentationen](https://experienceleague.adobe.com/sv/docs/experience-platform/access-control/abac/permissions-ui/users).

Användaren får ett e-postmeddelande med instruktioner om hur du kommer åt instansen.

+++

<!--table style="table-layout:fixed"><tr style="border: 0;">
<td><img alt="Overview" href="experiment-accelerator-overview.md" src="assets/do-not-localize/experiments-2.jpeg">
<div align="center"><p><strong><a href="experiment-accelerator-overview.md">Overview</a></strong></p></div></td>
<td><img alt="Experiments" href="experiment-accelerator-monitor.md" src="assets/do-not-localize/experiment-overview.jpeg">
<div align="center"><p><strong><a href="experiment-accelerator-monitor.md">Experiments</a></strong></p></div></td>
<td><img alt="Metrics" href="experiment-accelerator-metrics.md" src="assets/do-not-localize/experiment-metrics.png">
<div align="center"><p><strong><a href="experiment-accelerator-metrics.md">Metrics</a></strong></p></div></td>
</tr></table-->
