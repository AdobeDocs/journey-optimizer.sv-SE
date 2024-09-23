---
solution: Journey Optimizer
product: journey optimizer
title: Testa innehållet med anpassade profiler
description: Lär dig hur du förhandsgranskar innehåll och skickar korrektur med anpassade profiler.
feature: Overview, Get Started
topic: Content Management
role: User
level: Intermediate
badge: label="Beta"
hide: true
hidefromtoc: true
source-git-commit: 6229f295b961b0535139b64928216e40c3759947
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---


# Testa innehållet med anpassade profiler {#custom-profiles}

>[!CONTEXTUALHELP]
>id="ajo_simulate_sample_profiles"
>title="Simulera med egna profiler"
>abstract="På den här skärmen kan du förhandsgranska ditt innehåll och skicka korrektur samtidigt som du personifierar anpassade profiler som du kan överföra från en CSV-fil eller lägga till manuellt direkt från den här skärmen."

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande endast tillgänglig som betaversion för vissa användare.
>
>Rendering av inkorgen och skräppostrapporter är inte tillgängliga i den aktuella upplevelsen. Om du vill använda de här funktionerna väljer du knappen **[!UICONTROL Simulate content]** i ditt innehåll för att komma åt det äldre användargränssnittet.

Med reseoptimering kan du förhandsgranska och testa ditt innehåll med anpassade profiler som du kan överföra från en CSV-fil eller lägga till manuellt direkt när du simulerar ditt innehåll.

Klicka på knappen **[!UICONTROL Simulate content]** och välj **[!UICONTROL Simulate with CSV(Beta)]** för att få tillgång till den här upplevelsen.

På den här skärmen kan du välja profiler som ska användas för att förhandsgranska ditt innehåll och skicka korrektur. Alla attribut som används i ditt innehåll för personalisering identifieras automatiskt av systemet och kan användas för dina tester.

De viktigaste stegen för att testa ditt innehåll är följande:

1. Lägg till anpassade profiler, antingen genom att överföra en CSV-fil eller genom att lägga till dem en i taget manuellt. [Lär dig hur du lägger till anpassade profiler](#profiles)
1. Kontrollera förhandsgranskningen av ditt innehåll med de tillagda profilerna. [Lär dig förhandsgranska ditt innehåll](#preview)
1. Skicka upp till 10 korrektur till e-postadresserna och personifiera de önskade anpassade profilerna. [Lär dig skicka korrektur](#proofs)


## Lägg till anpassade profiler {#profiles}

Du kan lägga till anpassade profiler för att testa ditt innehåll antingen med en CSV-fil eller manuellt:

* Om du vill överföra profiler från en CSV-fil klickar du på länken **[!UICONTROL Download template]** för att hämta en CSV-filmall. Mallarna innehåller en kolumn för varje personaliseringsattribut som används i ditt innehåll.

  Fyll i CSV-filen och klicka sedan på **[!UICONTROL Upload sample profiles]** för att läsa in den för att testa innehållet.

* Om du vill lägga till en profil manuellt klickar du på knappen **[!UICONTROL Create sample profile]** och fyller i informationen för profilen. Ett fält visas för varje personaliseringsattribut som används i ditt innehåll.

  ![](assets/simulate-custom-add.png)

När du har valt profiler visas en ruta för varje profil på skärmens vänstra sida. Du kan använda de här profilerna för att förhandsgranska ditt innehåll och skicka korrektur.

## Förhandsgranska innehåll med anpassade profiler {#preview}

Om du vill förhandsgranska ditt innehåll med någon av profilerna markerar du den relevanta rutan för att uppdatera innehållsförhandsvisningen i det högra avsnittet med den information som har angetts för profilen.

Du kan ta bort en ruta när som helst med hjälp av ellipsknappen i det övre högra hörnet och välja **[!UICONTROL Remove]**. Om du vill redigera information för en profil klickar du på ellipsknappen och väljer **[!UICONTROL Edit]**.

![](assets/simulate-custom-boxes.png)

## Skicka korrektur {#proofs}

Med Journey Optimizer kan du skicka korrektur till e-postadresser samtidigt som du personifierar en eller flera anpassade profiler som du har lagt till på simuleringsskärmen. Stegen är följande:

1. Kontrollera att anpassade profiler har lagts till för att testa ditt innehåll och klicka på knappen **[!UICONTROL Send Proof]**.

1. I fältet **[!UICONTROL Recipients]** anger du den e-postadress som du vill skicka korrekturet till och klickar sedan på **[!UICONTROL Add]**. Upprepa åtgärden för att skicka korrekturet till ytterligare e-postadresser. Du kan lägga till upp till 10 korrekturmottagare.

1. I skärmens nedre del väljer du de anpassade profiler som du vill personifiera i korrekturet. Du kan välja flera profiler. I så fall kommer e-postmeddelandet att innehålla så många korrektur som de valda profilerna.

   ![](assets/simulate-custom-proofs.png)

1. Klicka på knappen **[!UICONTROL Send Proof]** för att börja skicka korrekturet.

Du kan spåra sändningen när som helst genom att klicka på knappen **[!UICONTROL View proofs]** på skärmen för att simulera innehåll.

![](assets/simulate-custom-sent-proofs.png)
