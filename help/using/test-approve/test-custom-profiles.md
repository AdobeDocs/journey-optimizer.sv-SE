---
solution: Journey Optimizer
product: journey optimizer
title: Testa innehållet med exempelprofiler
description: Lär dig hur du förhandsgranskar e-postinnehåll och skickar korrektur med exempelprofiler.
feature: Overview, Get Started
topic: Content Management
role: User
level: Intermediate
badge: label="Beta"
hide: true
hidefromtoc: true
source-git-commit: 6b3518645b9cbfbe6f728011b0889c28fa754496
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Testa innehållet med exempelprofiler {#custom-profiles}

>[!CONTEXTUALHELP]
>id="ajo_simulate_sample_profiles"
>title="Simulera med exempelprofiler"
>abstract="På den här skärmen kan du förhandsgranska e-postinnehåll och skicka korrektur samtidigt som du personifierar exempelprofiler som du kan överföra från en CSV-fil eller lägga till manuellt direkt från den här skärmen."


<!--ATTENTE CONFIRMATION 

- nom (custom/sample)
- campaigns/journeys ou que campaigns

-->

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande endast tillgänglig som betaversion för vissa användare.

Med reseoptimering kan du förhandsgranska och testa e-postinnehåll med exempelprofiler som du kan överföra från en CSV-fil eller lägga till manuellt direkt när du simulerar innehållet. Med den här funktionen kan du välja exempelprofiler som ska användas för att förhandsgranska ditt innehåll och skicka korrektur. Alla profilattribut som används i ditt innehåll för personalisering identifieras automatiskt av systemet och kan användas för dina tester.

Klicka på knappen **[!UICONTROL Simulate content]** och välj **[!UICONTROL Simulate with CSV(Beta)]** för att få tillgång till den här upplevelsen.

![](assets/simulate-sample.png)


De viktigaste stegen för att testa ditt innehåll är följande:

1. Lägg till upp till 30 exempelprofiler, antingen genom att överföra en CSV-fil eller genom att lägga till dem en i taget manuellt. [Lär dig hur du lägger till exempelprofiler](#profiles)
1. Kontrollera förhandsgranskningen av ditt innehåll med de tillagda profilerna. [Lär dig förhandsgranska ditt innehåll](#preview)
1. Skicka upp till 10 korrektur till e-postadresserna och personifiera de önskade exempelprofilerna. [Lär dig skicka korrektur](#proofs)


## Skyddsritningar och begränsningar {#limitations}

Innan du börjar testa ditt innehåll med exempelprofiler bör du tänka på följande skyddsutkast och krav.

* Från och med nu är testning med exempelprofiler bara tillgängligt inom kampanjer och för e-postkanalen.
* Följande funktioner är inte tillgängliga i den aktuella versionen: Inkorgsåtergivning, skräppostrapporter, flerspråkigt innehåll och innehållsexperiment. Om du vill använda de här funktionerna väljer du knappen **[!UICONTROL Simulate content]** i ditt innehåll för att komma åt det tidigare användargränssnittet.
* Endast profilattribut stöds för närvarande. Om kontextuella attribut används i ditt innehåll för personalisering kan du inte testa ditt innehåll med dessa attribut.
* Endast följande datatyper stöds när du anger data för exempelprofilerna: tal (heltal och decimal), sträng, boolesk och datumtyp. Alla andra datatyper kommer att visa ett fel.

## Lägg till exempelprofiler {#profiles}

Du kan lägga till upp till 30 exempelprofiler för att testa ditt innehåll antingen med en CSV-fil eller manuellt:

* Om du vill överföra profiler från en CSV-fil klickar du på länken **[!UICONTROL Download template]** för att hämta en CSV-filmall. Mallarna innehåller en kolumn för varje profilattribut som används i ditt innehåll för personalisering.

  Fyll i CSV-filen och klicka sedan på **[!UICONTROL Upload sample profiles]** för att läsa in den för att testa innehållet.

* Om du vill lägga till en profil manuellt klickar du på knappen **[!UICONTROL Create sample profile]** och fyller i informationen för profilen. Ett fält visas för varje profilattribut som används i ditt innehåll för personalisering.

  ![](assets/simulate-custom-add.png)

När du har valt profiler visas en ruta för varje profil på skärmens vänstra sida. Du kan använda de här profilerna för att förhandsgranska ditt innehåll och skicka korrektur.

>[!NOTE]
>
>De nya exempelprofilerna fungerar bara som testverktyg för det aktuella innehållet. De lagras inte i Adobe Experience Platform utan i webbläsaren, vilket innebär att de inte visas när du loggar ut eller om du arbetar från en annan enhet.

## Förhandsgranska innehåll med exempelprofiler {#preview}

Om du vill förhandsgranska ditt innehåll med någon av profilerna markerar du den relevanta rutan för att uppdatera innehållsförhandsvisningen i det högra avsnittet med den information som har angetts för profilen.

Du kan ta bort en ruta när som helst med hjälp av ellipsknappen i det övre högra hörnet och välja **[!UICONTROL Remove]**. Om du vill redigera information för en profil klickar du på ellipsknappen och väljer **[!UICONTROL Edit]**.

![](assets/simulate-custom-boxes.png)

## Skicka korrektur {#proofs}

Med Journey Optimizer kan du skicka korrektur till e-postadresser samtidigt som du personifierar en eller flera exempelprofiler som du har lagt till på simuleringsskärmen. Stegen är följande:

1. Kontrollera att exempelprofiler har lagts till för att testa ditt innehåll och klicka på knappen **[!UICONTROL Send Proof]**.

1. I fältet **[!UICONTROL Recipients]** anger du den e-postadress som du vill skicka korrekturet till och klickar sedan på **[!UICONTROL Add]**. Upprepa åtgärden för att skicka korrekturet till ytterligare e-postadresser. Du kan lägga till upp till 10 korrekturmottagare.

1. I skärmens nedre del markerar du de exempelprofiler som du vill personifiera i korrekturet. Du kan välja flera profiler. I så fall kommer e-postmeddelandet att innehålla så många korrektur som de valda profilerna.

   Om du vill ha mer information om en profil väljer du länken **[!UICONTROL View profile details]**. På så sätt kan du visa information som har angetts på föregående skärm för de olika profilattributen.

   ![](assets/simulate-custom-proofs.png)

1. Klicka på knappen **[!UICONTROL Send Proof]** för att börja skicka korrekturet.

Du kan spåra sändningen när som helst genom att klicka på knappen **[!UICONTROL View proofs]** på skärmen för att simulera innehåll.

![](assets/simulate-custom-sent-proofs.png)
