---
title: Kom igång med datauppsättningar
description: Lär dig hur du använder Adobe Experience Platform-datauppsättningar i Adobe Journey Optimizer
role: User
level: Beginner
exl-id: dcdd3c81-0f00-4259-a8a5-9062a4c40b6f
source-git-commit: 9ebcfd6c41c17fe3be0423822209443fc55244a7
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 2%

---

# Kom igång med datauppsättningar {#datasets-gs}

Alla data som importeras till Adobe Experience Platform lagras i Data Lake som datauppsättningar. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader).

## Åtkomst till datauppsättningar{#access-datasets}

The **Datauppsättningar** arbetsyta i [!DNL Adobe Journey Optimizer] Med användargränssnittet kan du utforska data och skapa datauppsättningar.

Välj **Datauppsättningar** i den vänstra navigeringen för att öppna kontrollpanelen för datauppsättningar.

![](assets/datasets-home.png)

Att lägga till data i Adobe Experience Platform är grunden för att skapa en profil. Sedan kan du använda profiler i [!DNL Adobe Journey Optimizer]. Börja med att definiera scheman, använd ETL-verktyg för att förbereda och standardisera data och skapa sedan datauppsättningar baserade på dina scheman.

Välj **Bläddra** om du vill visa en lista över alla tillgängliga datauppsättningar för din organisation. Information visas för varje datamängd som anges, inklusive namn, schema som datauppsättningen följer och status för den senaste importen.

Som standard visas bara de datauppsättningar som du har kapslat in i. Om du vill se de systemgenererade datauppsättningarna aktiverar du **Visa systemdatauppsättningar** växla från filtret.

![](assets/ajo-system-datasets.png)

Markera namnet på en datauppsättning för att komma åt aktivitetsskärmen för datauppsättningen och se information om den datauppsättning du valde. Fliken Aktivitet innehåller ett diagram som visar hur många meddelanden som har förbrukats samt en lista över lyckade och misslyckade batchar.

## Skapa datauppsättningar{#create-datasets}

Om du vill skapa en ny datauppsättning börjar du med att välja **Skapa datauppsättning** i kontrollpanelen för datauppsättningar.

Du kan:

* Skapa datauppsättning från schema. [Läs mer i den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en#schema){target=&quot;_blank&quot;}
* Skapa datauppsättning från CSV-fil. [Läs mer i den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html){target=&quot;_blank&quot;}


I den här videon får du lära dig hur du skapar en datauppsättning, mappar den till ett schema, lägger till data i den och bekräftar att data har importerats.

>[!VIDEO](https://video.tv.adobe.com/v/334293?quality=12)


Lär dig hur du skapar ett schema, en datauppsättning och importerar data för att lägga till testprofiler i Adobe Journey Optimizer i [detta kompletta exempel](../segment/creating-test-profiles.md)

Läs mer om att skapa datauppsättningar i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html){target=&quot;_blank&quot;}.

Lär dig hur du använder användargränssnittet för datauppsättningar i [Översiktlig dokumentation för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html){target=&quot;_blank&quot;}.


**Se även**

* [Skapa ett schema, en datauppsättning och inmatningsdata för att lägga till testprofiler i Journey Optimizer](../segment/creating-test-profiles.md)
* [Översikt över direktuppspelning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=sv){target=&quot;_blank&quot;}
* [Importera data till Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html){target=&quot;_blank&quot;}
