---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med flerspråkigt innehåll
description: Läs mer om flerspråkigt innehåll i Journey Optimizer
feature: Multilingual Content
topic: Content Management
role: User
level: Beginner
keywords: komma igång, börja, innehåll, experimentera
hide: true
hidefromtoc: true
exl-id: 6244d717-fbd6-468e-9164-60451d0d62f0
source-git-commit: 03c714833930511fa734662b637d2416728073c2
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 1%

---

# Skapa flerspråkigt innehåll {#multilingual}

Med den flerspråkiga funktionen kan ni enkelt skapa innehåll på flera språk i en och samma kampanj. Med den här funktionen kan ni växla mellan olika språk när ni redigerar kampanjer, effektivisera hela redigeringsprocessen och förbättra möjligheterna att effektivt hantera flerspråkigt innehåll.

## Skapa nationella inställningar {#create-locale}

När du konfigurerar språkinställningarna enligt beskrivningen i [Skapa språkinställningar](#language-settings) om det inte finns någon specifik språkinställning för ditt flerspråkiga innehåll kan du skapa så många nya språkinställningar som behövs med **[!UICONTROL Translation]** -menyn.

1. Från **[!UICONTROL Administration]** meny, åtkomst **[!UICONTROL Channel]**.

   På översättningsmenyn får du tillgång till listan över aktiverade språkområden.

1. Klicka på **[!UICONTROL Add locale]** på fliken **[!UICONTROL Locale dictionary]**.

   ![](assets/locale_1.png)

1. Välj din språkinställningskod på menyn **[!UICONTROL Language]** lista och associerade **[!UICONTROL Region]**.

1. Klicka **[!UICONTROL Save]** för att skapa din språkinställning.

   ![](assets/locale_2.png)

## Skapa språkinställningar {#language-settings}

I det här avsnittet kan du ange ditt primära språk och tillhörande språk för hantering av ditt flerspråkiga innehåll. Du kan också välja det attribut som du vill använda för att söka efter information om profilspråket

1. Från **[!UICONTROL Administration]** meny, åtkomst **[!UICONTROL Channel]**.

1. I **[!UICONTROL Language settings]** meny, klicka **[!UICONTROL Create language settings]**.

   ![](assets/multilingual-settings-1.png)

1. Ange ditt namn **[!UICONTROL Language settings]**.

1. Välj **[!UICONTROL Locales]** som är kopplade till dessa inställningar. Du kan lägga till högst 50 språkområden.

   Om en **[!UICONTROL Locale]** saknas kan du skapa den manuellt i förväg från **[!UICONTROL Translation]** eller av API. Se [Skapa en ny språkinställning](#create-locale).

   ![](assets/multilingual-settings-2.png)

1. Från **[!UICONTROL Sending preference]** väljer du det attribut du vill söka efter för att hitta information om profilspråk.

   ![](assets/multilingual-settings-3.png)

1. Klicka **[!UICONTROL Edit]** bredvid **[!UICONTROL Locale]** för att ytterligare personalisera den och lägga till **[!UICONTROL Profile preferences]**.

   ![](assets/multilingual-settings-4.png)

1. Välj andra **[!UICONTROL Locales]** från listrutan Profilinställningar och klicka på **[!UICONTROL Add profiles]**.

1. Gå till den avancerade menyn i **[!UICONTROL Locale]** för att definiera **[!UICONTROL Primary locale]**, dvs. standardspråket om profilattributet inte anges.

   Du kan även ta bort språkområdet från den här avancerade menyn.

   ![](assets/multilingual-settings-5.png)

1. Klicka **[!UICONTROL Submit]** för att skapa **[!UICONTROL Language settings]**.

<!--
1. Access the **[!UICONTROL Channel surfaces]** menu and create a new channel surface or select an existing one.

1. In the **[!UICONTROL Header parameters]** section, select the **[!UICONTROL Enable multilingual]** option.

1. Select your **[!UICONTROL Locales dictionary]** and add as many as needed.
-->

## Skapa en flerspråkig kampanj {#create-multilingual-campaign}

1. Börja med att skapa och konfigurera kampanjen efter era behov. [Läs mer](../campaigns/create-campaign.md)

1. Navigera till **[!UICONTROL Actions]** och väljer **[!UICONTROL Edit content]**.

   ![](assets/multilingual-campaign-1.png)

1. Skapa eller importera ditt ursprungliga innehåll och anpassa det efter behov.

1. När det primära innehållet har skapats klickar du på **[!UICONTROL Save]** och gå tillbaka till kampanjkonfigurationsskärmen.

   ![](assets/multilingual-campaign-2.png)

1. Klicka **[!UICONTROL Add languages]** och markera dina tidigare skapade **[!UICONTROL Language settings]**. [Läs mer](#create-language-settings)

   ![](assets/multilingual-campaign-3.png)

1. Få åtkomst till de avancerade inställningarna i **[!UICONTROL Locales]** meny och välj **[!UICONTROL Copy primary to all locales]**.

   ![](assets/multilingual-campaign-4.png)

1. Nu när det primära innehållet dupliceras i hela det markerade  **[!UICONTROL Locales]**, komma åt de olika språkinställningarna och klicka **[!UICONTROL Edit email body]** att översätta innehållet.

   ![](assets/multilingual-campaign-5.png)

1. Du kan välja att inaktivera eller aktivera språkområden med **[!UICONTROL More action]** menyn för det valda språkområdet.

   ![](assets/multilingual-campaign-6.png)

1. Om du vill inaktivera flerspråkig konfiguration klickar du på **[!UICONTROL Add languages]** och välj det språk du vill behålla som lokalt språk.

   ![](assets/multilingual-campaign-7.png)

1. Klicka **[!UICONTROL Review to activate]** för att visa en sammanfattning av kampanjen.

   Sammanfattningen gör att du kan ändra kampanjen om det behövs och kontrollera om någon parameter är felaktig eller saknas.

1. Bläddra igenom det flerspråkiga innehållet för att se återgivningen på varje språk.

   ![](assets/multilingual-campaign-8.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]**.

Din kampanj är nu aktiverad. Meddelandet som konfigurerats i kampanjen skickas omedelbart, eller på det angivna datumet. Observera att så fort Campaign är klar kan den inte ändras. Om du vill återanvända innehåll kan du duplicera din kampanj.

När ni har skickat dem kan ni mäta effekten av era kampanjer i kampanjrapporterna.

## Flerspråkig kampanjrapport {#multilingual-campaign-report}

Globala rapporter, tillgängliga från **Alltid** visar du händelser som inträffade för minst två timmar sedan och täcker händelser under en viss tidsperiod. Kampanjens globala rapport kan nås direkt från er Campaign via **[!UICONTROL View report]** -knappen.

Mer information om tillgängliga data i Campaign-rapporten finns i [den här sidan](../reports/campaign-global-report.md).

+++Läs mer om de olika mätvärden och widgetar som finns för ditt flerspråkiga innehåll.

![](assets/report_multilingual.png)

The **[!UICONTROL Email sending statistics by languages]** information om hur framgångsrik leveransen är beroende på din **[!UICONTROL Locales]**:

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

The **[!UICONTROL Email tracking statistics by languages]** widgeten innehåller tillgängliga data för mottagaraktivitet för leveransen beroende på din **[!UICONTROL Locales]**:

* **[!UICONTROL Unsubscribes]**: Antal klick på länken för att avbryta prenumerationen.

* **[!UICONTROL Opens]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som användaren klickat på ett innehåll.
+++


<!--
# Create a multilingual journey {#create-multilingual-journey}

1. Create your journey with a Delivery and personalize your content as needed.
1. From your delivery action, click Edit content.
1. Click Add languages.

# Translation project/ Create translation project:

1. From the Translation projects menu, click Create project.
1. Type-in a Name and Description.
1. Select the Source locale.
1. Click Add language to access the menu and define the languages for your translation project.
1. Select from the list your Target locale(s) and choose which Translation provider you want to use.
1. Click Add language when you finished linking your Target locale with the correct Translation provider.
1. Click Save.
1. From the Advanced menu of your Translation project, you can choose to Edit, deactive or delete it.
-->
