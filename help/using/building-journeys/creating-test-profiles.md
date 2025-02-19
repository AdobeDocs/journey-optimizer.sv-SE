---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en testprofil
description: Lär dig hur du skapar en testprofil
feature: Test Profiles, Profiles
topic: Content Management
role: User, Data Engineer
level: Intermediate
keywords: testprofiler, testning, test, resa
exl-id: bd5e053a-69eb-463b-add3-8b9168c8e280
source-git-commit: 7df2d6a68ce20dbd9d07be3d6cfba9eba5ec0242
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 1%

---

# Skapa testprofiler {#create-test-profiles}

Testprofiler krävs när [testläget](../building-journeys/testing-the-journey.md) används i en resa och när du [förhandsgranskar och testar ditt innehåll](../content-management/preview-test.md).

>[!NOTE]
>
>I [!DNL Journey optimizer] kan du också testa olika varianter av ditt innehåll genom att förhandsgranska det och skicka korrektur med exempelindata som har överförts från en CSV-/JSON-fil, eller lagts till manuellt. [Lär dig hur du testar innehåll med exempelindata](../test-approve/simulate-sample-input.md)

Det finns flera sätt att skapa testprofiler. På den här sidan hittar du information om:

* Omvandla en [befintlig profil](#turning-profile-into-test) till en testprofil

* Skapa testprofiler genom att överföra en [csv-fil](#create-test-profiles-csv) eller använda [API-anrop](#create-test-profiles-api).

  Förutom dessa två metoder levereras Adobe Journey Optimizer med ett specifikt [användningsfall](#use-case-1) i produkten för att underlätta skapandet av testprofiler.

Du kan också överföra en json-fil i en befintlig datauppsättning. Mer information finns i [dokumentationen för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset){target="_blank"}.

Observera att det liknar att skapa en testprofil att skapa vanliga profiler i Adobe Experience Platform. Mer information finns i [dokumentationen för kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}.

➡️ [Lär dig skapa testprofiler i den här videon](#video)

## Förhandskrav {#test-profile-prerequisites}

För att kunna skapa profiler måste du först skapa ett schema och en datauppsättning i Adobe [!DNL Journey Optimizer].

Så här skapar du ett **schema**:

1. Klicka på **[!UICONTROL Schemas]** i menyavsnittet DATAHANTERING.
   ![](assets/test-profiles-0.png)
1. Klicka på **[!UICONTROL Create schema]** i det övre högra hörnet, välj en schematyp, till exempel **Individual Profile**, och klicka på **Next**.
   ![](assets/test-profiles-1.png)
1. Ange ett namn för schemat och klicka på **Slutför**.
   ![](assets/test-profiles-1-bis.png)
1. Klicka på **Lägg till$$ till vänster i avsnittet **Fältgrupper** och välj rätt fältgrupper. Se till att du lägger till fältgruppen **Profiltestinformation**.
   ![](assets/test-profiles-1-ter.png)
När du är klar klickar du på **[!UICONTROL Add field groups]**: listan med fältgrupper visas på schemaöversiktsskärmen.
   ![](assets/test-profiles-2.png)

   >[!NOTE]
   >
   >Klicka på schemats namn för att uppdatera dess egenskaper.

1. I listan med fält klickar du på det fält som du vill definiera som primär identitet.
   ![](assets/test-profiles-3.png)
1. I den högra rutan **[!UICONTROL Field properties]** kontrollerar du alternativen **[!UICONTROL Identity]** och **[!UICONTROL Primary Identity]** och väljer ett namnutrymme. Om du vill att den primära identiteten ska vara en e-postadress väljer du namnutrymmet **[!UICONTROL Email]**. Klicka på **[!UICONTROL Apply]**.
   ![](assets/test-profiles-4bis.png)
1. Markera schemat och aktivera alternativet **[!UICONTROL Profile]** i rutan **[!UICONTROL Schema properties]**.
   ![](assets/test-profiles-5.png)
1. Klicka på **Spara**.

>[!NOTE]
>
>Mer information om schemaskapande finns i [XDM-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites){target="_blank"}.

Sedan måste du **skapa datauppsättningen** som profilerna ska importeras i. Följ de här stegen:

1. Bläddra till **[!UICONTROL Datasets]** och klicka sedan på **[!UICONTROL Create dataset]**.
   ![](assets/test-profiles-6.png)
1. Välj **[!UICONTROL Create dataset from schema]**.
   ![](assets/test-profiles-7.png)
1. Markera det tidigare skapade schemat och klicka sedan på **[!UICONTROL Next]**.
   ![](assets/test-profiles-8.png)
1. Välj ett namn och klicka sedan på **[!UICONTROL Finish]**.
   ![](assets/test-profiles-9.png)
1. Aktivera alternativet **[!UICONTROL Profile]**.
   ![](assets/test-profiles-10.png)

>[!NOTE]
>
> Mer information om hur du skapar datauppsättningar finns i [dokumentationen för katalogtjänsten](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started){target="_blank"}.

## Exempel på användning i produkten{#use-case-1}

På Adobe Journey Optimizer hemsida kan du använda testprofilerna i programmet. Det här användningsexemplet underlättar skapandet av testprofiler som används för att testa resor före publicering.

![](assets/use-cases-home.png)

Klicka på knappen **[!UICONTROL Begin]** för att starta användningsfallet.

Följande information krävs:

1. **Identitetsnamnrymd**: [Identitetsnamnrymden](../audience/get-started-identity.md) som används för att unikt identifiera testprofilerna. Om e-post till exempel används för att identifiera testprofilerna bör identitetsnamnområdet **E-post** markeras. Om den unika identifieraren är telefonnumret bör identitetsnamnområdet **Telefon** väljas.

2. **CSV-fil**: En kommaavgränsad fil som innehåller listan med testprofiler som ska skapas. Användningsfallet förväntar sig ett fördefinierat format för CSV-filen som innehåller listan med testprofiler som ska skapas. Varje rad i filen ska innehålla följande fält i rätt ordning:

   1. **Person-ID**: Unik identifierare för testprofilen. Värdena för det här fältet bör återspegla det valda identitetsnamnutrymmet. (Om till exempel **Telefon** väljs för identitetsnamnområdet bör värdena i det här fältet vara telefonnummer. Om **E-post** är markerat bör värdena i det här fältet vara e-postmeddelanden)
   1. **E-postadress**: Testa profilens e-postadress. (Fältet **Person-ID** och fältet **E-postadress** kan innehålla samma värden om **E-post** har valts som identitetsnamnrymd)
   1. **Förnamn**: Testprofilens förnamn.
   1. **Efternamn**: Testprofilens efternamn.
   1. **Ort**: Testprofilens ort i bostaden
   1. **Land**: Testa profilland för bosättning
   1. **Kön**: Testa profilkön. Tillgängliga värden är **man**, **hona** och **non_specified**

När du har valt identitetsnamnrymden och angett CSV-filen baserat på formatet ovan, klickar du på knappen **[!UICONTROL Run]** överst till höger. Användningsexemplet kan ta några minuter att slutföra. När användningsärendet har slutförts och testprofilerna har skapats skickas ett meddelande till användaren.

>[!NOTE]
>
>Testprofiler kan åsidosätta befintliga profiler. Innan du kör användningsfallet måste du kontrollera att CSV-filen bara innehåller testprofiler och att den körs mot rätt sandlåda.

## Förvandla en profil till en testprofil{#turning-profile-into-test}

Du kan omvandla en befintlig profil till en testprofil: du kan uppdatera profilattribut på samma sätt som när du skapar en profil.

Ett enkelt sätt att göra detta är att använda en **[!UICONTROL Update Profile]**-åtgärdsaktivitet på en resa och ändra det booleska fältet **testProfile** från false till true.

Din resa består av en **[!UICONTROL Read Audience]**- och en **[!UICONTROL Update Profile]**-aktivitet. Först måste ni skapa en målgrupp med de profiler ni vill omvandla till testprofiler.

>[!NOTE]
>
> Eftersom du kommer att uppdatera fältet **testProfile** måste de valda profilerna innehålla det här fältet. Det relaterade schemat måste ha fältgruppen **Profiltestinformation**. Se [det här avsnittet](../audience/creating-test-profiles.md#test-profiles-prerequisites).

1. Bläddra till **Publiker** och sedan till **Skapa målgrupp** i det övre högra hörnet.
   ![](assets/test-profiles-22.png)
1. Definiera ett namn för målgruppen och bygg målgruppen: välj de fält och värden som ska användas för de profiler du vill ha.
   ![](assets/test-profiles-23.png)
1. Klicka på **Spara** och kontrollera att målgruppen har angett rätt profiler.
   ![](assets/test-profiles-24.png)

   >[!NOTE]
   >
   > Målgruppsberäkning kan ta lite tid. Läs mer om målgrupper i [det här avsnittet](../audience/about-audiences.md).

1. Skapa nu en ny resa och börja med en **[!UICONTROL Read Audience]**-koordinationsaktivitet.
1. Välj den målgrupp som skapats tidigare och det namnutrymme som profilerna använder.
   ![](assets/test-profiles-25.png)
1. Lägg till en **[!UICONTROL Update Profile]**-åtgärdsaktivitet.
1. Markera schemat, fältet **testProfiles**, datamängden och ange värdet till **True**. Om du vill utföra det här i fältet **[!UICONTROL VALUE]** klickar du på ikonen **Ritstift** till höger, väljer **[!UICONTROL Advanced mode]** och anger **true**.
   ![](assets/test-profiles-26.png)
1. Klicka på **[!UICONTROL Publish]**.
1. Kontrollera att profilerna har uppdaterats korrekt i avsnittet **[!UICONTROL Audiences]**.
   ![](assets/test-profiles-28.png)

   >[!NOTE]
   >
   > Mer information om aktiviteten **[!UICONTROL Update Profile]** finns i [det här avsnittet](../building-journeys/update-profiles.md).

## Skapa en testprofil med en CSV-fil{#create-test-profiles-csv}

I Adobe Experience Platform kan du skapa profiler genom att överföra en CSV-fil som innehåller de olika profilfälten till datauppsättningen. Det här är den enklaste metoden.

1. Skapa en enkel csv-fil med ett kalkylprogram.
1. Lägg till en kolumn för varje fält som behövs. Se till att du lägger till det primära identitetsfältet (&quot;personID&quot; i exemplet ovan) och att fältet&quot;testProfile&quot; har värdet&quot;true&quot;.
   ![](assets/test-profiles-11.png)
1. Lägg till en rad per profil och fyll i värdena för varje fält.
   ![](assets/test-profiles-12.png)
1. Spara kalkylbladet som en CSV-fil. Se till att kommatecken används som avgränsare.
1. Bläddra till Adobe Experience Platform **arbetsflöden**.
   ![](assets/test-profiles-14.png)
1. Välj **Mappa CSV till XDM-schema** och klicka sedan på **Starta**.
   ![](assets/test-profiles-16.png)
1. Markera den datauppsättning som du vill importera profilerna till. Klicka på **Nästa**.
   ![](assets/test-profiles-17.png)
1. Klicka på **Välj filer** och markera din CSV-fil. När filen har överförts klickar du på **Nästa**.
   ![](assets/test-profiles-18.png)
1. Mappa CSV-källfälten till schemafälten och klicka sedan på **Slutför**.
   ![](assets/test-profiles-19.png)
1. Dataimporten börjar. Statusen ändras från **Bearbetning** till **Slutfört**. Klicka på **Förhandsgranska datauppsättning** längst upp till höger.
   ![](assets/test-profiles-20.png)
1. Kontrollera att testprofilerna har lagts till korrekt.
   ![](assets/test-profiles-21.png)

Testprofilerna läggs till och kan nu användas när du testar en resa. Se [det här avsnittet](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
> Mer information om csv-import finns i [dokumentationen för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials){target="_blank"}.

## Skapa testprofiler med API-anrop{#create-test-profiles-api}

Du kan också skapa testprofiler via API-anrop. Läs mer i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}.

Du måste använda ett profilschema som innehåller fältgruppen &quot;Profiltestinformation&quot;. Flaggan testProfile ingår i den här fältgruppen.
När du skapar en profil måste du skicka värdet: testProfile = true.

Observera att du även kan uppdatera en befintlig profil för att ändra dess testProfile-flagga till &quot;true&quot;.

Här är ett exempel på ett API-anrop för att skapa en testprofil:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

## Instruktionsvideo {#video}

Lär dig skapa testprofiler.

>[!VIDEO](https://video.tv.adobe.com/v/334236?quality=12)
