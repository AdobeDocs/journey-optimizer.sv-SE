---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med datauppsättningar
description: Lär dig hur du använder Adobe Experience Platform datauppsättningar i Adobe Journey Optimizer
feature: Data Model, Datasets, Data Management
role: Developer, Admin
level: Experienced
keywords: plattform, datasjön, skapa, sjö, datamängder, profil
exl-id: dcdd3c81-0f00-4259-a8a5-9062a4c40b6f
source-git-commit: a6f2cc11f57c5cd766cd31e941649fb5003ae30b
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Kom igång med datauppsättningar {#datasets-gs}

Alla data som importeras till Adobe Experience Platform lagras i Data Lake som datauppsättningar. En datauppsättning är en lagrings- och hanteringskonstruktion för en datamängd, vanligtvis en tabell, som innehåller ett schema (kolumner) och fält (rader).

## Skyddsritningar och begränsningar

* Från och med 1 november 2024 har direktuppspelningssegmentering inte längre stöd för skicka och öppna händelser från [!DNL Journey Optimizer] spårnings- och feedbackdatauppsättningar. Använd affärsregler i stället för att implementera frekvensbegränsning eller trötthetshantering. Mer information finns i [det här avsnittet](../conflict-prioritization/rule-sets.md), inklusive en fallförklaring för det dagliga taktavlägget [här](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/elevate-customer-experience-with-daily-frequency-capping-in-ajo/ba-p/761510){target="_blank"}.

* Från och med februari 2025 introduceras ett TTL-skyddsutkast till Journey Optimizer systemgenererade datauppsättningar. [Läs mer](datasets-ttl.md)

## Åtkomst till datauppsättningar {#access}

Med arbetsytan **Datauppsättningar** i [!DNL Adobe Journey Optimizer] kan du utforska data och skapa datauppsättningar. Om du vill öppna kontrollpanelen för datauppsättningar väljer du **Datauppsättningar** i den vänstra navigeringen.

![](assets/datasets-home.png)

Välj fliken **Bläddra** om du vill visa listan över alla tillgängliga datauppsättningar för din organisation. Information visas för varje datamängd som anges, inklusive namn, schema som datauppsättningen följer och status för den senaste importen. Som standard visas bara de datauppsättningar som du har kapslat in i. Om du vill se de systemgenererade datauppsättningarna aktiverar du alternativet **Visa systemdatauppsättningar** från filtret.

![](assets/ajo-system-datasets.png)


Markera namnet på en datauppsättning för att komma åt aktivitetsskärmen för datauppsättningen och se information om den datauppsättning du valde. Fliken Aktivitet innehåller ett diagram som visar hur många meddelanden som har förbrukats samt en lista över lyckade och misslyckade batchar.

Om du vill förhandsgranska en datauppsättning väljer du **Förhandsgranska datauppsättning** i skärmens övre högra hörn för att förhandsgranska den senaste slutförda gruppen i den här datauppsättningen. När en datauppsättning är tom inaktiveras förhandsgranskningslänken.

![](assets/dataset-preview.png)

## [!DNL Journey Optimizer] systemdatauppsättningar {#system-datasets}

I det här avsnittet visas systemdatauppsättningar som används av [!DNL Journey Optimizer]. Om du vill visa en fullständig lista över fält och attribut för varje schema kan du läsa [Journey Optimizer schemaordlista](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=sv-SE){target="_blank"}.

>[!CAUTION]
>
> Systemdatauppsättningarna **får inte ändras**. Alla ändringar återställs automatiskt vid varje produktuppdatering.

* Rapportering

   * _Rapportering - händelsedatauppsättning för meddelandefeedback_: Meddelandeleveransloggar. Information om alla mejl från Journey Optimizer för rapportering och målgruppsframställning. Feedback från e-postleverantörer om studsar registreras också i den här datauppsättningen.
   * _Rapportering - händelsedatauppsättning för e-postspårning_: Interaktionsloggar för e-postkanal som används för rapportering och målgruppsskapande. Information som lagras om åtgärder som slutanvändaren utför via e-post (öppningar, klick etc.).
   * _Rapportering - händelsedatauppsättningen Push Tracking Experience_: Interaktionsloggar för push-kanal som används för att skapa rapporter och målgrupper. Information som lagras om åtgärder som slutanvändaren utför i push-meddelanden.
   * _Rapportering - Resestegshändelse_: Hämtar alla händelser för körningssteg som har genererats från Journey Optimizer och som ska användas av tjänster som rapportering. Viktigt för att skapa rapporter i Customer Journey Analytics för YY-analys. Kopplad till en resemetadata.
   * _Rapportering - Resor_: Inlämningsinformation för metadatadatadatauppsättningar för varje steg i en resa.
   * _Rapportering - BCC_: Datauppsättning för feedbackhändelse som lagrar leveransloggar för BCC-e-post. Ska användas för rapportering.

* Godkännande

  _Samtyckestjänstdatauppsättning_: lagrar sambandsinformation för en profil.

* Intelligenta tjänster

  _Poäng för optimering vid sändning/engagemang_: Resultat för AI vid körning på resa.


## Skapa datauppsättningar{#create-datasets}

Att lägga till data i [!DNL Adobe Experience Platform] är grunden för att skapa en profil. Du kan sedan utnyttja profiler i [!DNL Adobe Journey Optimizer]. Börja med att definiera scheman, använd ETL-verktyg för att förbereda och standardisera data och skapa sedan datauppsättningar baserade på dina scheman.

Du kan skapa en datauppsättning från ett schema eller en CSV-fil. Detaljerad information om hur du skapar datauppsättningar finns i [!DNL Adobe Experience Platform]-dokumentationen:

* [Skapa en datauppsättning med ett befintligt schema](https://experienceleague.adobe.com/sv/docs/experience-platform/catalog/datasets/user-guide#schema){target="_blank"}
* [Mappa en CSV-fil till ett befintligt XDM-schema](https://experienceleague.adobe.com/sv/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema){target="_blank"}

I den här videon får du lära dig hur du skapar en datauppsättning, mappar den till ett schema, lägger till data i den och bekräftar att data har importerats.

>[!VIDEO](https://video.tv.adobe.com/v/334293?quality=12)

## Dataförvaltning

I en datauppsättning bläddrar du till fliken **Datastyrning** för att kontrollera etiketter på data- och fältnivå. Datastyrning kategoriserar data efter vilken typ av policyer som gäller.

En av kärnfunktionerna i [!DNL Adobe Experience Platform] är att samla data från flera företagssystem så att marknadsförarna bättre kan identifiera, förstå och engagera kunder. Dessa data kan vara föremål för användarbegränsningar som fastställts av din organisation eller av juridiska bestämmelser. Det är därför viktigt att se till att dataåtgärderna är kompatibla med dataanvändningspolicyer.

Med [!DNL Adobe Experience Platform Data Governance] kan du hantera kunddata och säkerställa efterlevnad av regler, begränsningar och policyer som gäller för dataanvändning. Det spelar en nyckelroll inom Experience Platform på olika nivåer, bland annat i fråga om katalogisering, datalinje, dataanvändningsetiketter, dataanvändningspolicyer och kontroll av användningen av data för marknadsföringsåtgärder.

Läs mer om etiketter för datastyrning och dataanvändning i [dokumentationen för datastyrning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/user-guide.html?lang=sv-SE){target="_blank"}

## Exempel och användningsområden {#samples}

* [Självstudiekurs - Importera data till Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html?lang=sv-SE){target="_blank"}
* [Användningsfall från början till slut](../audience/creating-test-profiles.md) - Skapa ett schema, en datauppsättning och inmatningsdata för att lägga till testprofiler i [!DNL Adobe Journey Optimizer]
* [Frågeexempel](../data/datasets-query-examples.md) - [!DNL Adobe Journey Optimizer] datauppsättningar och relaterade användningsexempel.

>[!MORELIKETHIS]
>
>* [Dokumentation för datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=sv-SE){target="_blank"}
>* [Dokumentation om dataöverföring](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=sv-SE){target="_blank"}.
>* [Bästa praxis för berättigande av datahanteringslicens](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/license/data-management-best-practices#data-management-best-practices){target="_blank"}
