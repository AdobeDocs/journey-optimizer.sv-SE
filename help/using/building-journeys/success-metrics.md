---
solution: Journey Optimizer
product: journey optimizer
title: Publicera resan
description: Lär dig hur du rapporterar om dina resemått
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: publicera, resa, live, giltighet, kontrollera
exl-id: 95d0267e-fab4-4057-8ab5-6f7c9c866b0f
version: Journey Orchestration
source-git-commit: 7822e9662d03e6c6b2d5bc5ecb9ca85dc32f0942
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 1%

---

# Konfigurera och spåra dina resemått {#success-metrics}

Få tydlig insyn i hur effektiva era kundresor är med hjälp av kundstatistik. Med den här funktionen kan du spåra prestanda mot definierade KPI:er, identifiera insikter i vad som fungerar och identifiera områden som kan optimeras. Genom att mäta påverkan i realtid kan ni få kontinuerlig förbättring och fatta dataunderbyggda beslut som ökar kundengagemanget.

## Förhandskrav {#prerequisites}

Innan du använder dina resemått måste du lägga till en datamängd som innehåller fältgrupperna `Commerce Details`, `Web` och `Mobile` [&#x200B; &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE#field-group){target="_blank"} under Konfiguration > Rapportering i Adobe Experience Platform.

Dessa fältgrupper måste väljas bland de inbyggda alternativen, inte från anpassade grupper. Se avsnittet [Lägg till datauppsättningar](../reports/reporting-configuration.md#add-datasets).

## Tillgängliga mått {#metrics}

Listan med mätvärden varierar beroende på vilka [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE#field-group){target="_blank"} som ingår i datauppsättningen.

Om datauppsättningen inte har konfigurerats är bara följande mått tillgängliga: **[!UICONTROL Click]**, **[!UICONTROL Unique Click]**, **[!UICONTROL Clickthrough Rate]** och **[!UICONTROL Open Rate]**.

Observera att med en Customer Journey Analytics-licens kan ni skapa anpassade framgångsmått. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/participation-metric)


| Mätvärden | Relaterad fältgrupp |
|-|-|
| Klickningar | Ingen fältgrupp krävs |
| Unika klick | Ingen fältgrupp krävs |
| Klickfrekvens (CTR) | Ingen fältgrupp krävs |
| Klickbar öppningsfrekvens (CTOR) | Ingen fältgrupp krävs |
| Sidvyer | Webbfältgrupp |
| Applanseringar | Grupp för mobilfält |
| Första programstarten | Grupp för mobilfält |
| Appinstallationer | Grupp för mobilfält |
| Appuppgraderingar | Grupp för mobilfält |
| Inköp | Fältgruppen Commerce Details |
| Utcheckningar | Fältgruppen Commerce Details |
| Cart Adds | Fältgruppen Commerce Details |
| Cart Open | Fältgruppen Commerce Details |
| Vyer | Fältgruppen Commerce Details |
| Cart Removes | Fältgruppen Commerce Details |
| Produktvyer | Fältgruppen Commerce Details |
| Spara för senare | Fältgruppen Commerce Details |

## Tillskrivning {#attribution}

Varje mätresultat har en angiven attribuering som avgör vilka kontaktytor eller interaktioner som bidrog till ett visst resultat.

* **Metrisk attribuering med Journey Optimizer-licens**:

  Endast med Journey Optimizer-licens är det maximala tillgängliga uppslagsfönstret för valda mätvärden inställt på 7 dagar. För dessa mått anges attribueringsmodellen som standard till **Sista beröringen**, dvs. den senaste interaktionen före konverteringen.

  Du kan till exempel spåra om ett köp har gjorts efter att en kund interagerat med din resa under de senaste 7 dagarna.

* **Metrisk attribuering med Customer Journey Analytics-licens**:

  Med både Journey Optimizer- och Customer Journey Analytics-licenser kan ni skapa anpassade mätvärden med specifika attribueringsinställningar eller ändra de inbyggda mätningsattributen.

  Läs mer om [Attributmodeller](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/component-settings/attribution#attribution-models)

## Tilldela dina resemått {#assign}

>[!IMPORTANT]
>
>Endast ett resemått tillåts per resa.

Följ stegen nedan för att börja spåra dina resemått:

1. Klicka på **[!UICONTROL Journeys]** på **[!UICONTROL Create Journey]**-menyn.

1. Redigera kundens konfigurationsruta för att definiera namnet på resan och ange dess egenskaper. Lär dig hur du anger egenskaper för din resa på [den här sidan](../building-journeys/journey-properties.md).

1. Välj din **[!UICONTROL Journey metrics]** som ska användas för att mäta hur effektiv din resa är.

   Observera att mätvärdena gäller själva resan och är tillämpliga på alla delar av resan.

   ![Konfigurationspanelen för framgångsmått i resans egenskaper](assets/success_metric.png)

1. Klicka på **[!UICONTROL Save]**.

1. Utforma din resa med den nödvändiga **[!UICONTROL Activities]**.

1. Testa och publicera din resa.

1. Öppna din reserapport för att spåra resultatet av dina tilldelade framgångsmått.

   De värden du väljer visas i rapportens tabell över nyckeltal och kundstatistik.

   ![Prognosvärden för lyckade resultat visar tillgängliga händelser för målspårning](assets/success_metric_2.png)

