---
solution: Journey Optimizer
product: journey optimizer
title: Testa innehållet med exempelindata
description: Lär dig förhandsgranska e-postinnehåll och skicka korrektur med exempelindata.
feature: Overview, Get Started
topic: Content Management
role: User
level: Intermediate
badge: label="Beta"
hide: true
hidefromtoc: true
source-git-commit: 100c9ca994199a3b90650ebfbabbf0b7ac8726c2
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 0%

---


# Testa innehållet med exempelindata {#custom-profiles}

>[!CONTEXTUALHELP]
>id="ajo_simulate_sample_profiles"
>title="Simulera med exempelindata"
>abstract="På den här skärmen kan du testa olika varianter av ditt e-postinnehåll genom att ange värden för anpassningsfält via en CSV-mall (hämta CSV) eller genom att ange värdena manuellt."

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande endast tillgänglig som betaversion för vissa användare.

Med reseoptimering kan du testa olika varianter av ditt e-postinnehåll genom att förhandsgranska det och skicka korrektur med exempelindata som överförts från en CSV-fil eller lagts till manuellt. Alla profilattribut som används i ditt innehåll för personalisering identifieras automatiskt av systemet och kan användas för dina tester för att skapa flera varianter.

Klicka på knappen **[!UICONTROL Simulate content]** och välj **[!UICONTROL Simulate with CSV(Beta)]** för att få tillgång till den här upplevelsen.

![](assets/simulate-sample.png)

De viktigaste stegen för att testa ditt innehåll är följande:

1. Lägg till upp till 30 varianter med exempelindata, antingen genom att överföra en CSV-fil eller genom att lägga till data manuellt. [Lär dig hur du lägger till varianter](#profiles)
1. Kontrollera förhandsgranskningen av ditt innehåll med olika varianter. [Lär dig förhandsgranska ditt innehåll](#preview)
1. Skicka upp till 10 korrektur till e-postadresser med olika varianter. [Lär dig skicka korrektur](#proofs)


## Skyddsritningar och begränsningar {#limitations}

Innan du börjar testa ditt innehåll med exempelindata bör du tänka på följande skyddsutkast och krav.

* Från och med nu är testning med exempelindata bara tillgängligt för e-postkanalen. Det går inte att komma åt upplevelsen via knappen&quot;Simulera innehåll&quot; i e-post-Designer.
* Följande funktioner är inte tillgängliga i den aktuella versionen: Inkorgsåtergivning, skräppostrapporter, flerspråkigt innehåll och innehållsexperiment. Om du vill använda de här funktionerna väljer du knappen **[!UICONTROL Simulate content]** i ditt innehåll för att komma åt det tidigare användargränssnittet.
* Endast profilattribut stöds för närvarande. Om kontextuella attribut används i ditt innehåll för personalisering kan du inte testa ditt innehåll med dessa attribut.
* Endast följande datatyper stöds när du anger data för dina varianter: tal (heltal och decimal), sträng, boolesk och datumtyp. Alla andra datatyper kommer att visa ett fel.

## Lägg till varianter {#profiles}

Du kan lägga till upp till 30 varianter för att testa ditt innehåll, antingen med hjälp av en CSV-fil eller manuellt:

* Om du vill överföra exempelindata från en CSV-fil klickar du på länken **[!UICONTROL download CSV]** för att hämta en CSV-filmall. Mallarna innehåller en kolumn för varje profilattribut som används i ditt innehåll för personalisering.

  Fyll i CSV-filen och klicka sedan på **[!UICONTROL Upload Input data]** för att läsa in den för att testa innehållet.

* Om du vill lägga till en variant manuellt klickar du på knappen **[!UICONTROL Create sample input]** och fyller i exempelindata för varianten. Ett fält visas för varje profilattribut som används i ditt innehåll för personalisering.

  ![](assets/simulate-custom-add.png)

När du har valt profiler visas en ruta för varje variant på skärmens vänstra sida. Du kan använda de här profilerna för att förhandsgranska ditt innehåll och skicka korrektur.

>[!NOTE]
>
>De tillagda varianterna fungerar bara som testningssyften för ditt aktuella innehåll. De lagras inte i Adobe Experience Platform utan i webbläsaren, vilket innebär att de inte visas när du loggar ut eller om du arbetar från en annan enhet.

## Förhandsgranska dina innehållsvarianter {#preview}

Om du vill förhandsgranska ditt innehåll med någon av varianterna markerar du den relevanta rutan för att uppdatera innehållsförhandsvisningen i det högra avsnittet med den information som har angetts för varianten.

Du kan när som helst ta bort en variant med hjälp av ellipsknappen i det övre högra hörnet och välja **[!UICONTROL Remove]**. Om du vill redigera information för en variant klickar du på ellipsknappen och väljer **[!UICONTROL Edit]**.

![](assets/simulate-custom-boxes.png)

## Skicka korrektur {#proofs}

Med Journey Optimizer kan du skicka korrektur till e-postadresser samtidigt som du personifierar en eller flera varianter som du har lagt till på simuleringsskärmen. Stegen är följande:

1. Kontrollera att varianter har lagts till för att testa ditt innehåll och klicka på knappen **[!UICONTROL Send Proof]**.

1. I fältet **[!UICONTROL Recipients]** anger du den e-postadress som du vill skicka korrekturet till och klickar sedan på **[!UICONTROL Add]**. Upprepa åtgärden för att skicka korrekturet till ytterligare e-postadresser. Du kan lägga till upp till 10 korrekturmottagare.

1. I skärmens nedre del väljer du den variant som du vill använda i korrekturet. Du kan välja flera varianter. I så fall kommer e-postmeddelandet att innehålla så många korrektur som de valda varianterna.

   Om du vill ha mer information om en variant väljer du länken **[!UICONTROL View profile details]**. På så sätt kan du visa information som har angetts i föregående fönster för de olika varianterna.

   ![](assets/simulate-custom-proofs.png)

1. Klicka på knappen **[!UICONTROL Send Proof]** för att börja skicka korrekturet.

1. Om du vill spåra korrekturet klickar du på knappen **[!UICONTROL View proofs]** på skärmen för att simulera innehåll.

![](assets/simulate-custom-sent-proofs.png)
