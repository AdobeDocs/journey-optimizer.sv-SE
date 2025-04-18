---
solution: Journey Optimizer
product: journey optimizer
title: Publicera resan
description: Lär dig hur du rapporterar om vald resemätning
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: publicera, resa, live, giltighet, kontrollera
exl-id: 95d0267e-fab4-4057-8ab5-6f7c9c866b0f
source-git-commit: d28341dd39ec3ab838a5fbb3ae49539b8776c60b
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%

---

# Konfigurera och spåra dina resemått {#success-metrics}

Med kundstatistik kan ni effektivt mäta effekten av era aktiviteter genom att följa upp deras resultat mot fördefinierade mätvärden.
Genom att följa upp dessa mätvärden kan ni se hur bra kundresan går, identifiera områden som kan förbättras och fatta välgrundade beslut för att öka kundengagemanget.

## Förhandskrav {#prerequisites}

Innan du använder resemätverket måste du lägga till en datamängd som innehåller fältgrupperna `Commerce Details`, `Web` och `Mobile` [](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target="_blank"}.

## Tillgängliga mått {#metrics}

Listan med mätvärden varierar beroende på vilka [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target="_blank"} som ingår i datauppsättningen.

Om datauppsättningen inte har konfigurerats är bara följande mått tillgängliga: **[!UICONTROL Click]**, **[!UICONTROL Unique Click]**, **[!UICONTROL Clickthrough Rate]** och **[!UICONTROL Open Rate]**.

Observera att med en Customer Journey Analytics-licens kan ni skapa anpassade framgångsmått. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/participation-metric)


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

  Läs mer om [Attributmodeller](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/attribution#attribution-models)

## Tilldela dina Journey-mått {#assign}

Följ stegen nedan när du vill börja spåra dina resemått:

1. Klicka på **[!UICONTROL Create Journey]** på **[!UICONTROL Journeys]**-menyn.

1. Redigera kundens konfigurationsruta för att definiera namnet på resan och ange dess egenskaper. Lär dig hur du anger egenskaper för din resa på [den här sidan](../building-journeys/journey-properties.md).

1. Välj din **[!UICONTROL Journey metrics]** som ska användas för att mäta hur effektiv din resa är.

   Observera att mätvärdena gäller själva resan och är tillämpliga på alla delar av resan.

   ![](assets/success_metric.png)

1. Klicka på **[!UICONTROL Save]**.

1. Utforma din resa med den nödvändiga **[!UICONTROL Activities]**.

1. Testa och publicera din resa.

1. Öppna din reserapport för att spåra resultatet för dina tilldelade framgångsmått.

   Det valda måttet visas i rapportens tabell över nyckeltal och resestatistik.

   ![](assets/success_metric_2.png)
