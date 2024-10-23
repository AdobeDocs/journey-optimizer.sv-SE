---
title: Resebegränsning och skiljeförfarande
description: Lär dig hur du skapar regler för bockning för dina resor och hur du godtyckliggör reseregistrering
role: User
level: Beginner
badge: label="Begränsad tillgänglighet"
hide: true
hidefromtoc: true
source-git-commit: fd644d4d4a92eb0e0770c1d04fe8e7cd90f3ebae
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 0%

---


# Resebegränsning och skiljeförfarande {#journey-capping}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med konflikthantering och -prioritering](gs-conflict-prioritization.md)
* [Upptäck potentiella konflikter i resor och kampanjer](conflicts.md)
* [Tilldela prioritetspoäng till resor och kampanjer](priority-scores.md)
* **[Resebegränsning och skiljeförfarande](journey-capping.md)**

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Konflikthanterings- och prioriteringsverktygen är för närvarande tillgängliga som begränsad tillgänglighet endast för utvalda användare.

Färttappning hjälper dig att begränsa antalet resor som en profil kan registreras på, vilket förhindrar att kommunikationen överbelastas. I Journey Optimizer kan du ange två typer av regler för begränsning:

* **Ankomstbegränsning** begränsar antalet reseposter under en viss period för en profil.
* **Samtidighetsbegränsning** begränsar hur många resor en profil kan registreras samtidigt.

Båda typerna av resefackning använder prioritetspoäng till godtyckliga poster.

## Skapa en regel för spärrning av resan {#create-rule}

Följ de här stegen för att skapa en regel för begränsning av kundresor:

1. Gå till menyn **[!UICONTROL Business rules (Beta)]** för att komma åt lagret för regeluppsättningar.

1. Välj den regeluppsättning där du vill lägga till begränsningsregeln eller skapa en ny regeluppsättning:

   * Om du vill använda en befintlig regeluppsättning markerar du den i listan. Det går bara att lägga till regler för resefackning i regeluppsättningar med domänen&quot;resa&quot;. Du kan kontrollera den här informationen i regeluppsättningslistorna i kolumnen **[!UICONTROL Domain]**.

     ![](assets/journey-capping-list.png)

   * Om du vill skapa begränsningsregeln i en ny regeluppsättning klickar du på **[!UICONTROL Create rule set]**, anger ett unikt namn för regeluppsättningen och väljer&quot;Resa&quot; i listrutan **[!UICONTROL Rule Set Domain]** och klickar sedan på **[!UICONTROL Save]**.

     ![](assets/journey-capping-rule-set.png)

1. Klicka på knappen **[!UICONTROL Add Rule]** på skärmen för regeluppsättningen och konfigurera regeln så att den passar dina behov:

   ![](assets/journey-capping-concurrency.png)

   * Ange ett unikt namn för regeln.

   * Ange regelns typ av begränsning i listrutan **[!UICONTROL Rule Type]**.

      * **[!UICONTROL Journey Entry Cap]**: Begränsar antalet poster i resan under en viss period för en profil.
      * **[!UICONTROL Journey Concurrency Cap]**: Begränsar hur många resor en profil kan registreras samtidigt.

   * Expandera avsnitten nedan för att lära dig hur du konfigurerar olika typer av fästning:

     +++Konfigurera en regel för bockning av resepost

      1. I fältet **[!UICONTROL Capping]** anger du det maximala antalet resor som en profil kan ange.
      1. I fältet **[!UICONTROL Duration]** definierar du tidsperioden som ska beaktas. Observera att längden baseras på UTC-tidszonen. Till exempel återställs daglig ändpunkt vid midnatt UTC.

     I det här exemplet vill vi begränsa profiler från att ange fler än fem resor per månad.

     ![](assets/journey-capping-entry-example.png)

     >[!NOTE]
     >
     >Systemet kommer att beakta prioriteringen av kommande schemalagda resor som har samma regel tillämpad på det.
     >
     >I det här exemplet, om marknadsföraren redan har gått in i fyra resor och det finns en annan schemalagd resa den här månaden med högre prioritet, kommer kunderna inte att kunna delta i den resa som har lägre prioritet.

+++

     +++Konfigurera en regel för samtidighetsbegränsning för resa

      1. I fältet **[!UICONTROL Capping]** anger du det maximala antalet resor som en profil kan registreras i samtidigt.

      1. Använd fältet **[!UICONTROL Prioritization look ahead]** för att dela upp reseposter baserat på prioritetspoäng under en vald period (t.ex. 1 dag, 7 dagar, 30 dagar). Detta gör det lättare att prioritera inträde på större kundresor om en profil är berättigad till flera kundresor.

     I det här exemplet vill vi hindra profiler från att komma in på resan om de redan är inskrivna i en annan resa som innehåller samma regeluppsättning. Om en annan resa inom de kommande 7 dagarna har ett högre prioritetspoäng kommer profilen inte att gå in på den här resan.

     ![](assets/journey-capping-concurrency-example.png){width="50%" zommable="yes"}

+++

1. När begränsningsregeln är klar att användas på resor aktiverar du den genom att klicka på ellipsknappen bredvid dess namn.

   ![](assets/journey-capping-activate-rule.png)

1. Aktivera hela regeluppsättningen genom att klicka på ellipsknappen bredvid knappen Lägg till regel i skärmens övre högra hörn.

   ![](assets/journey-capping-activate-rule-set.png)

## Tillämpa regler för begränsning av resor {#apply-capping}

Om du vill tillämpa en begränsningsregel på en resa får du åtkomst till resan och öppnar dess egenskaper. Välj den relevanta regeluppsättningen i listrutan **[!UICONTROL Capping rules]**.

När resan har aktiverats gäller de regler som definieras i regeluppsättningen.

![](../test-approve/assets/journey-capping-apply.png)

>[!IMPORTANT]
>
>Om en resa aktiveras omedelbart kan det ta upp till 15 minuter för systemet att börja inaktivera kunder. Du kan schemalägga din resa så att den börjar minst 15 minuter framåt för att förhindra den här möjligheten.
