---
solution: Journey Optimizer
product: journey optimizer
title: Dynamiska medier
description: Använd dynamiska medier med Journey Optimizer
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4c1d39c4-3154-4bec-ac3c-c2ead7164d69
source-git-commit: f212a2178e83283d4755da5483d7c11ba4df183f
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---

# Infoga nedräkningstimer {#countdown}

Skapa trängsel och maximera konverteringarna med timer för Dynamic Media-nedräkning som uppdateras i realtid när mottagarna öppnar dina e-postmeddelanden. Den här funktionen är idealisk för Flash-försäljning, tidsbegränsade erbjudanden och tidskänsliga kampanjer.

Som marknadsförare för ett detaljhandelsmärke har du till exempel en 48-timmars Flash-försäljning. Genom att använda nedräkningstimern i dina e-postmeddelanden:

* Mottagare som öppnar omedelbart ser &quot;47 timmar återstår&quot;
* Mottagare som öppnar 24 timmar senare, se&quot;23 timmar återstår&quot;
* Mottagare som öppnar när försäljningen är slut ser &quot;Tiden är ute!&quot;

Mer information om hur du lägger till nedräkningstimer i mallen för dynamiska media i Adobe Experience Manager finns i [det här dokumentet](assets/do-not-localize/countdown.pdf).


1. I **[!DNL Adobe Experience Manager]** skapar du en dynamisk mediamall och lägger till en nedräkningstimerkomponent i den.

   ![](assets/timer-1.png)

1. I **[!DNL Journey Optimizer]** skapar du en ny kampanj eller öppnar en befintlig kampanj och öppnar sedan e-post-Designer.

1. Dra och släpp en **HTML** - eller **Asset** -komponent i ditt e-postinnehåll.

1. Håll pekaren över komponenten och klicka på **[!UICONTROL Show the source code]** (för HTML-komponenter) eller **[!UICONTROL Browse]** (för Asset-komponenter).

   ![](assets/timer-2.png)

1. Navigera till **[!UICONTROL Edit HTML]** på menyn **[!UICONTROL Assets]** och klicka på **[!UICONTROL Open asset selector]** för att bläddra och välja den publicerade dynamiska mediamallen.

   ![](assets/timer-3.png)

1. Aktivera pilleupplevelsen genom att växla Pills till On. Detta förbättrar läsbarheten genom att långa attributsökvägar döljs.

   ![](assets/timer-6.png)

1. Konfigurera de anpassningsbara URL-parametrarna som behövs för mallen på menyn **[!UICONTROL Custom attributes]**.

   Klicka på **[!UICONTROL Save]** när du är klar.

   ![](assets/timer-4.png)

1. Du kan också komma åt parametrarna för mallen Dynamic Media genom att markera resursen i e-post-Designer och sedan gå till **[!UICONTROL Settings]**-menyn.

   Konfigurera följande:

   * **Banderolltext**: Den text som visas med timern
   * **Sluttid**: Det datum och den tidpunkt då nedräkningen upphör att gälla. Ange bara tiden i GMT (Greenwich Mean Time). Systemet accepterar inte andra tidszoner.
   * **Reservtext**: Meddelandet visas när timern är slut

   ![](assets/timer-5.png)

1. Klicka på **[!UICONTROL Preview]** om du vill visa timern med nedräkningsuppdateringar i realtid och verifiera konfigurationen.

När mottagarna öppnar e-postmeddelandet ser de exakt hur lång tid som återstår för din Flash-försäljning. Om de öppnar e-postmeddelandet igen senare uppdateras nedräkningen automatiskt med den återstående tiden. Efter slutdatumet visas standardmeddelandet automatiskt.
