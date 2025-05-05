---
solution: Journey Optimizer
product: journey optimizer
title: Testa materialet med exempeldata (Beta)
description: Lär dig hur du förhandsgranskar innehåll och skickar e-postkorrektur med exempelindata från en CSV- eller JSON-fil eller lägger till manuellt.
feature: Email, Email Rendering, Personalization, Preview, Proofs
topic: Content Management
role: User
level: Intermediate
badge: label="Beta" type="Informative"
exl-id: 8462c75e-4f4b-4c4f-8734-19efbbc70c7a
source-git-commit: f41426bd41078b98a26c32ce259a848ab49d724c
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 0%

---

# Testa innehållet med exempelindata{#custom-profiles}

>[!CONTEXTUALHELP]
>id="ajo_simulate_sample_profiles"
>title="Simulera med exempelindata"
>abstract="På den här skärmen kan du testa olika varianter av ditt innehåll genom att ange värden för personaliseringsfält via en CSV- eller JSON-mall, eller genom att ange värdena manuellt."

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande tillgänglig för alla kunder som en betaversion.

Med reseoptimering kan du testa olika varianter av ditt innehåll genom att förhandsgranska det och skicka korrektur med exempelindata som överförts från en CSV- eller JSON-fil eller lagts till manuellt. Alla profilattribut som används i ditt innehåll för personalisering identifieras automatiskt av systemet och kan användas för dina tester för att skapa flera varianter. En variant refererar till en version av innehållet med olika värden för dess attribut.

>[!NOTE]
>
>För närvarande är simulering av innehållsvariationer bara tillgängligt för meddelandekanalerna E-post, SMS och Push.

Klicka på knappen **[!UICONTROL Simulate content]** och välj **[!UICONTROL Simulate content variations (Beta)]** för att få tillgång till den här upplevelsen.

![](assets/simulate-sample.png)

De viktigaste stegen för att testa ditt innehåll är följande:

1. Lägg till upp till 30 varianter med exempelindata, antingen genom att överföra en fil eller genom att lägga till data manuellt. [Lär dig hur du lägger till varianter](#profiles)
1. Kontrollera förhandsgranskningen av ditt innehåll med olika varianter. [Lär dig förhandsgranska ditt innehåll](#preview)
1. Skicka upp till 10 korrektur till e-postadresser med olika varianter för e-postinnehåll. [Lär dig skicka korrektur](#proofs)


## Skyddsritningar och begränsningar {#limitations}

Innan du börjar testa ditt innehåll med exempelindata bör du tänka på följande skyddsutkast och krav.

* Från och med nu är testning med exempelindata bara tillgängligt för e-post-, SMS- och push-meddelandekanalerna. Det går inte att komma åt upplevelsen via knappen&quot;Simulera innehåll&quot; i e-post-Designer.
* Följande funktioner är inte tillgängliga i den aktuella versionen: Inkorgsåtergivning, skräppostrapporter, flerspråkigt innehåll och innehållsexperiment. Om du vill använda de här funktionerna väljer du knappen **[!UICONTROL Simulate content]** i ditt innehåll för att komma åt det tidigare användargränssnittet.
* Endast profilattribut stöds för närvarande. Om kontextuella attribut används i ditt innehåll för personalisering kan du inte testa ditt innehåll med dessa attribut.
* Endast följande datatyper stöds när du anger data för dina varianter: tal (heltal och decimal), sträng, boolesk och datumtyp. Alla andra datatyper kommer att visa ett fel.

## Lägg till varianter {#profiles}

Du kan lägga till upp till 30 varianter för att testa innehållet, antingen med hjälp av en fil eller manuellt.

>[!NOTE]
>
>De tillagda varianterna fungerar bara som testningssyften för ditt aktuella innehåll. De lagras inte i Adobe Experience Platform utan i webbläsaren, vilket innebär att de inte visas när du loggar ut eller när du arbetar från en annan enhet.

### Lägga till variant med hjälp av en fil {#file}

Så här lägger du till en variant från en fil:

1. Klicka på länken **[!UICONTROL download sample]** för att hämta en filmall och välj sedan det filformat som du vill använda (CSV, JSON eller JSONLINES).
1. Klicka på **[!UICONTROL Download]** och lagra sedan mallen på önskad plats.
1. Öppna filen och fyll sedan i mallen efter dina behov. Mallen innehåller en kolumn för varje profilattribut som används i ditt innehåll för personalisering.

   +++Exempel på fil

   ```
   {
   "profile": {
       "attributes": {
       "person": {
           "name": {
               "lastName": "Doe",
               "firstName": "John"
               }
           }
       }
   }
   }
   ```

   +++

1. När filen är klar klickar du på **[!UICONTROL Upload Input data]** för att läsa in den och testa innehållet.
1. När filen har överförts läggs en ruta till i den vänstra rutan för varje rad från filen. Varje ruta innehåller alla profilattribut som används i ditt innehåll för personalisering. Du kan nu använda varianterna för att förhandsgranska ditt innehåll i den högra rutan och skicka korrektur.

   ![](assets/simulate-custom-variants.png)

### Lägg till varianter manuellt {#manual}

Så här lägger du till en variant manuellt:

1. Klicka på knappen **[!UICONTROL Create sample input]**.

   En ruta läggs till i den vänstra rutan med alla profilattribut som används i ditt innehåll för personalisering.

1. Fyll i exempelindata för varianten och klicka på **[!UICONTROL Save]**.

   ![](assets/simulate-custom-add.png)

1. När du har lagt till varianter kan du använda dem för att förhandsgranska ditt innehåll i den högra rutan och skicka korrektur.

## Förhandsgranska dina innehållsvarianter {#preview}

Om du vill förhandsgranska ditt innehåll med någon av varianterna markerar du den relevanta rutan för att uppdatera innehållsförhandsvisningen i det högra avsnittet med den information som har angetts för varianten.

I exemplet nedan har vi lagt till två varianter för e-postämnesraden:

| Val för variant 1 | Val för variant 2 |
|----------|-------------|
| ![](assets/simulate-custom-boxes.png) | ![](assets/simulate-custom-boxes2.png) |

Du kan när som helst ta bort en variant med hjälp av ellipsknappen i det övre högra hörnet och välja **[!UICONTROL Remove]**. Om du vill redigera information för en variant klickar du på ellipsknappen och väljer **[!UICONTROL Edit]**.

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
