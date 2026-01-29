---
solution: Journey Optimizer
product: journey optimizer
title: Kontrollpanel för licensanvändning
description: Läs mer om Journey Optimizer License Use Dashboard
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 7e91face-c8f4-4e70-9123-9e36bae7e67e
source-git-commit: db1e4ee5b2b4bb3a3d7d9e86aded14ad3c613765
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# Kontrollpanel för licensanvändning {#license-usage}

[!DNL Adobe Journey Optimizer] [Användargränssnittet](../start/user-interface.md) innehåller en instrumentpanel som visar viktig information om din organisations licensanvändning, som den fångats in under en daglig ögonblicksbild.

Gå till **[!UICONTROL Administration]** > **[!UICONTROL License Usage]** om du vill komma åt den här instrumentpanelen. Fliken **[!UICONTROL Overview]** öppnas och kontrollpanelen visas.

![Kontrollpanel för licensanvändning - översikt](assets/license-usage-dashboard.png)

>[!NOTE]
>
>* Om du vill visa kontrollpanelen måste du ha behörigheten [Visa kontrollpanel för licensanvändning](https://experienceleague.adobe.com/docs/experience-platform/dashboards/permissions.html#available-permissions){target="_blank"}.
>
>* Vissa mått (t.ex. beräkningstimmar, e-post) visas inte för utvecklingssandlådor, vilket anges av `N/A` i kvotkolumnen. Endast värden som inte är null visas på kontrollpanelen: när mätvärdena är noll eller nära noll fylls de inte i.


För [!DNL Adobe Journey Optimizer] kan du kontrollera antalet **aktiveringsbara profiler** på kontrollpanelen.

## Vad är en engagerande profil? {#what-is-engageable-profile}

En **aktiveringsbar profil** är en informationspost som representerar en person som lagras i profiltjänsten och som har använts av resor eller kampanjer.

Viktiga egenskaper för engagerande profiler:

* **12-månaders rullande fönster**: Aktiverbara profiler räknas baserat på engagemang under de senaste 12 månaderna. Det här måttet visar hur många unika profiler du har försökt att interagera med med hjälp av Journey Optimizer funktioner för redigering, beslutsfattande, leverans, experimenterande eller orkestrering.

* **Unikt antal per sandlåda**: Om en profil anger flera resor eller kampanjer i en sandlåda räknas den bara en gång som en enda aktiveringsbar profil för den sandlådan.

* **Baserat på adresserbar publik**: Engagerbara profiler beräknas från din adresserbara publik. Antalet representerar den målgrupp som har varit engagerad de senaste 12 månaderna med hjälp av någon av Journey Optimizer funktioner, av din totala adresserbara publik.

* **Mätbeteende**: Antalet profiler som kan aktiveras:
   * Kan öka när nya profiler engageras via resor eller kampanjer
   * Kan inte minska om det inte finns något engagemang med vissa profiler i över 12 månader
   * Kan minska när pseudonyma profiler sammanfogas med kända profiler

>[!NOTE]
>
>Om du plötsligt får upp så många profiler som möjligt kan du få mer information om hur du förstår och löser problemet i avsnittet [Felsökning](#troubleshooting-engageable-profiles) nedan.

## Felsökning: Betydande ökning av antalet aktiveringsbara profiler {#troubleshooting-engageable-profiles}

Om du plötsligt ser en topp i antalet profiler som kan aktiveras (till exempel profiler som ökar från hundratusentals till miljontals inom en dag) ger det här avsnittet vägledning för att förstå och hantera problemet.

### Förstå ökningen

Mätvärdet för aktiveringsbara profiler visar antalet unika profiler som använts av resor eller kampanjer under de senaste 12 månaderna. En plötslig ökning kan bero på:

* Stora målgrupper som målgruppsanpassas av nya resor eller kampanjer
* Ändringar i datauppsättningar som är aktiverade för profiltjänsten
* Batchbearbetning av målgrupper som inte har varit engagerade nyligen

### Upplösningssteg

Följ de här stegen för att åtgärda problemet:

1. **Förstå logik för profilinventering:**

   * Engagerbara profiler beräknas utifrån unika profiler som använts av resor eller kampanjer under de senaste 12 månaderna.
   * Om en profil anger flera resor räknas den som en aktiveringsbar profil för den sandlådan.
   * Mätvärdet kan inte minska om det inte finns något engagemang med vissa profiler under mer än 12 månader eller om pseudonyma profiler sammanfogas med kända profiler.
   * Engagerbara profiler beräknas med kundens adresserbara publik.
   * Den målgrupp som har varit engagerad de senaste 12 månaderna med någon av Journey Optimizer-funktionerna, av den totala adresserbara målgruppen, avgör antalet engagerande profiler.

2. **Undersök resor, kampanjer och beslut som riktar sig till stora målgrupper:**

   * Granska nyligen utförda resor och kampanjer med ett stort antal profiler som mål med hjälp av [aktiveringsbara profilfrågor](../reports/query-examples.md#engageable-profiles-queries) eller [frågetjänsten](https://experienceleague.adobe.com/en/docs/experience-platform/query/home){target="_blank"}.
   * Identifiera specifika reseversioner som bidrog till att antalet profiler ökade.
   * Resor, kampanjer och beslut som rör nya profiler kommer sannolikt att leda till en ökning av antalet händelser i datauppsättningarna för resan, vilket bidrar till att antalet profiler som kan tas med i kampanjen ökar.

3. **Filtrera målgrupper på rese- och kampanjnivå:**

   * Använd filter på målgruppsnivå innan du påbörjar resor eller kampanjer för att förhindra onödiga ökningar i engagerande profiler.
   * Se till att endast relevanta målgrupper målgruppsanpassas under engagemang.

4. **Minska adresserbar målgruppsstorlek:**

   * Ta bort pseudonyma profiler om det behövs. Observera att åtgärden påverkar både Journey Optimizer och Real-Time Customer Data Platform.
   * Läs mer om [Pseudonym förfallotid för profildata](https://experienceleague.adobe.com/en/docs/experience-platform/profile/pseudonymous-profiles){target="_blank"} i kundprofilguiden för realtid.
   * **Obs!** Det går inte att konfigurera förfallodatum för pseudonyma profildata via plattformens gränssnitt eller API:er. Du måste kontakta supporten för att aktivera den här funktionen.

5. **Ändringar i övervakningsdatauppsättningen:**

   * Verifiera datauppsättningar som har aktiverats för profilering och se till att de inte innehåller för många ECID:n (Experience Cloud ID).
   * Om det behövs tar du bort datauppsättningar med höga ECID-värden och återskapar dem med reducerade poster.

6. **Utveckla en långsiktig minskningsstrategi:**

   * Antalet profiler som kan aktiveras minskar naturligt om vissa profiler inte används i mer än 12 månader.

**Se även:**

* [Engagerbara profiler - frågeexempel](../reports/query-examples.md#engageable-profiles-queries) - Exempelfrågor för att övervaka och analysera dina engagerande profiler
* [Adobe Experience Platform Query Service - översikt](https://experienceleague.adobe.com/en/docs/experience-platform/query/home){target="_blank"}

## Relaterad dokumentation {#related-documentation}

Läs mer i Adobe Experience Platform-dokumentationen:

* [Kontrollpanel för licensanvändning - översikt](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html){target="_blank"}
* [Utforska kontrollpanelen för licensanvändning](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html#exploring-the-license-usage-dashboard){target="_blank"}
* [Tillgängliga mått](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html#available-metrics){target="_blank"}
* [Pseudonymt utgångsdatum för profildata](https://experienceleague.adobe.com/docs/experience-platform/profile/pseudonymous-profiles.html){target="_blank"}
