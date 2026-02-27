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
source-git-commit: 1b0b2b5aa8c5b4ea0a101583ee1132574996bd98
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# Infoga nedräkningstimer {#countdown}

Skapa trängsel och maximera konverteringarna med timer för Dynamic Media-nedräkning som uppdateras i realtid när mottagarna öppnar dina e-postmeddelanden. Den här funktionen är idealisk för Flash-försäljning, tidsbegränsade erbjudanden och tidskänsliga kampanjer.

Som marknadsförare för ett detaljhandelsmärke har du till exempel en 48-timmars Flash-försäljning. Genom att använda nedräkningstimern i dina e-postmeddelanden:

* Mottagare som öppnar omedelbart ser &quot;47 timmar återstår&quot;
* Mottagare som öppnar 24 timmar senare, se&quot;23 timmar återstår&quot;
* Mottagare som öppnar efter att försäljningen avslutats ser&quot;Försäljningen är avslutad&quot;

Mer information om hur du skapar dynamiska media i Adobe Experience Manager finns i [det här dokumentet](assets/do-not-localize/Dynamic%20Media%20Templates.pdf).


1. I **[!DNL Adobe Experience Manager]** skapar du en dynamisk mediamall och lägger till en nedräkningstimerkomponent i den.

   ![](assets/timer-1.png)

1. I **[!DNL Journey Optimizer]** skapar du en ny kampanj eller öppnar en befintlig kampanj och öppnar sedan e-post-Designer.

1. Dra och släpp en **[!UICONTROL HTML component]** i ditt e-postinnehåll.

1. Välj **[!UICONTROL Show the source code]** om du vill redigera HTML direkt.

   ![](assets/timer-2.png)

1. Navigera till **[!UICONTROL Edit HTML]** på menyn **[!UICONTROL Assets]** och klicka på **[!UICONTROL Open asset selector]** för att bläddra och välja den publicerade dynamiska mediamallen.

   ![](assets/timer-3.png)

1. Konfigurera de anpassningsbara URL-parametrarna som behövs för mallen på menyn **[!UICONTROL Custom attributes]**.

   Klicka på **[!UICONTROL Save]** när du är klar.

   ![](assets/timer-4.png)

1. Markera resursen i e-post-Designer och gå sedan till menyn **[!UICONTROL Styles]**.

   Konfigurera följande inställningar:
   * **Banderolltext**: Den text som visas med timern
   * **Sluttid**: Det datum och den tidpunkt då nedräkningen upphör att gälla. Ange bara tiden i GMT (Greenwich Mean Time). Systemet accepterar inte andra tidszoner.
   * **Reservtext**: Meddelandet visas när timern är slut

   ![](assets/timer-5.png)

1. Klicka på **[!UICONTROL Preview]** om du vill visa timern med nedräkningsuppdateringar i realtid och verifiera konfigurationen.

När mottagarna öppnar e-postmeddelandet ser de exakt hur lång tid som återstår för din Flash-försäljning. Om de öppnar e-postmeddelandet igen senare uppdateras nedräkningen automatiskt med den återstående tiden. Efter slutdatumet visas standardmeddelandet automatiskt.

