---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med datauppsättningar
description: Lär dig hur du använder Adobe Experience Platform-datauppsättningar i Adobe Journey Optimizer
role: User
level: Beginner
keywords: plattform, datasjön, skapa, sjö, datamängder, profil
exl-id: dcdd3c81-0f00-4259-a8a5-9062a4c40b6f
source-git-commit: 59499dec7d15dd4565c7910d7b454d82243ff011
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 1%

---

# Kom igång med datauppsättningar {#datasets-gs}

Alla data som importeras till Adobe Experience Platform lagras i Data Lake som datauppsättningar. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader).

## Åtkomst till datauppsättningar{#access-datasets}

The **Datauppsättningar** arbetsyta i [!DNL Adobe Journey Optimizer] Med användargränssnittet kan du utforska data och skapa datauppsättningar.

Välj **Datauppsättningar** i den vänstra navigeringen för att öppna kontrollpanelen för datauppsättningar.

![](assets/datasets-home.png)

Lägga till data i [!DNL Adobe Experience Platform] är grunden till en profil. Sedan kan du använda profiler i [!DNL Adobe Journey Optimizer]. Börja med att definiera scheman, använd ETL-verktyg för att förbereda och standardisera data och skapa sedan datauppsättningar baserade på dina scheman.

Välj **Bläddra** om du vill visa en lista över alla tillgängliga datauppsättningar för din organisation. Information visas för varje datamängd som anges, inklusive namn, schema som datauppsättningen följer och status för den senaste importen.

Som standard visas bara de datauppsättningar som du har kapslat in i. Om du vill se de systemgenererade datauppsättningarna aktiverar du **Visa systemdatauppsättningar** växla från filtret.

![](assets/ajo-system-datasets.png)

Markera namnet på en datauppsättning för att komma åt aktivitetsskärmen för datauppsättningen och se information om den datauppsättning du valde. Fliken Aktivitet innehåller ett diagram som visar hur många meddelanden som har förbrukats samt en lista över lyckade och misslyckade batchar.

Här är de olika datamängderna som är tillgängliga:

**Rapportering**

* _Rapportering - händelsedatauppsättning för meddelandefeedback_: Meddelandeleveransloggar. Information om alla meddelandeleveranser från Journey Optimizer för rapportering och skapande av segment. Feedback från e-postleverantörer om studsar registreras också i den här datauppsättningen.
* _Rapportering - händelsedatauppsättning för e-postspårning_: Interaktionsloggar för e-postkanal som används för att skapa rapporter och segment. Information som lagras om åtgärder som slutanvändaren utför via e-post (öppningar, klick etc.).
* _Rapportering - händelsedatauppsättning för push-spårning_: Interaktionsloggar för push-kanal som används för att skapa rapporter och segment. Information som lagras om åtgärder som slutanvändaren utför i push-meddelanden.
* _Rapportering - resesegmentshändelse_: Hämtar alla händelser av typen&quot;Journey Step Experience&quot; som genererats från Journey Optimizer och som ska användas av tjänster som Reporting. Viktigt för att skapa rapporter i Customer Journey Analytics för YY-analys. Kopplad till en resemetadata.
* _Rapportering - Resor_: Införlivningsinformation för metadatadatauppsättningar för varje steg i en resa.
* _Rapportering - hemlig kopia_: Feedback Event Dataset som lagrar leveransloggar för BCC-e-postmeddelanden. Ska användas för rapportering.

**Godkännande**

* _Samtycketjänstens datauppsättning_: lagrar information om samtycke för en profil.

**Intelligenta tjänster**

* _Poäng för optimering av sändningstid/engagemangsmoment_: Poängvärden för Journey AI.

Om du vill visa en fullständig lista över fält och attribut för varje schema läser du i [Journey Optimizer schemaordlista](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html){target="_blank"}.

## Förhandsgranska datauppsättningar{#preview-datasets}

Välj **Förhandsgranska datauppsättning** i skärmens övre högra hörn för att förhandsgranska den senaste lyckade gruppen i den här datauppsättningen. När en datauppsättning är tom inaktiveras förhandsgranskningslänken.

![](assets/dataset-preview.png)

## Skapa datauppsättningar{#create-datasets}

Om du vill skapa en ny datauppsättning börjar du med att välja **Skapa datauppsättning** i kontrollpanelen för datauppsättningar.

Du kan:

* Skapa datauppsättning från schema. [Läs mer i den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#schema){target="_blank"}
* Skapa datauppsättning från CSV-fil. [Läs mer i den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html){target="_blank"}

I den här videon får du lära dig hur du skapar en datauppsättning, mappar den till ett schema, lägger till data i den och bekräftar att data har importerats.

>[!VIDEO](https://video.tv.adobe.com/v/334293?quality=12)

## Datastyrning

I en datauppsättning bläddrar du till **Datastyrning** för att kontrollera etiketter på data- och fältnivå. Datastyrning kategoriserar data efter vilken typ av policyer som gäller.

En av kärnfunktionerna i [!DNL Adobe Experience Platform] är att sammanföra data från olika affärssystem för att göra det lättare för marknadsförarna att identifiera, förstå och engagera kunderna. Dessa data kan vara föremål för användarbegränsningar som fastställts av din organisation eller av juridiska bestämmelser. Det är därför viktigt att se till att dataåtgärderna är kompatibla med dataanvändningspolicyer.

[!DNL Adobe Experience Platform Data Governance] gör att ni kan hantera kunddata och säkerställa att ni följer regler, begränsningar och policyer som gäller för dataanvändning. Det spelar en nyckelroll på olika nivåer inom Experience Platform, bland annat för katalogisering, datalinje, märkning av dataanvändning, dataanvändningspolicyer och kontroll av användningen av data för marknadsföringsåtgärder.

Läs mer om datastyrning och etiketter för dataanvändning i [Dokumentation för datastyrning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/user-guide.html){target="_blank"}

## Exempel och användningsområden{#uc-datasets}

Lär dig hur du skapar ett schema, en datauppsättning och importerar data för att lägga till testprofiler i Adobe Journey Optimizer i [detta kompletta exempel](../segment/creating-test-profiles.md)

Läs mer om att skapa datauppsättningar i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html){target="_blank"}.

Lär dig hur du använder användargränssnittet för datauppsättningar i [Översiktlig dokumentation för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html){target="_blank"}.

Det finns en lista med användningsfall med frågeexempel [här](../data/datasets-query-examples.md).

**Se även**

* [Översikt över direktuppspelning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=sv){target="_blank"}
* [Importera data till Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html){target="_blank"}
