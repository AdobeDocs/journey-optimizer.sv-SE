---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med reseaktiviteter
description: Kom igång med reseaktiviteter
feature: Journeys, Activities, Overview
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: resa, aktiviteter, komma igång, händelser, åtgärd
exl-id: 239b3d72-3be0-4a82-84e6-f219e33ddca4
version: Journey Orchestration
source-git-commit: 97fa287d94efb7fb95817fc15268e736517cb629
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 11%

---

# Kom igång med reseaktiviteter {#about-journey-activities}

Kombinera händelser, samordning och åtgärder för att skapa flerstegsscenarier för flera kanaler.

## Händelseaktiviteter {#event-activities}

Personaliserade resor börjar med exempelvis online-köp. När en profil går in på en resa, förflyttas den på egen hand. Varje profil kan ha olika sökväg och takt. När du börjar med en händelse utlöses resan när händelsen kommer fram. Varje profil följer sedan de steg som definieras under din resa.

Händelser som konfigurerats av den tekniska användaren (se [den här sidan](../event/about-events.md)) visas i palettens första kategori. Den här kategorin finns till vänster på skärmen. Följande händelseaktiviteter är tillgängliga:

* [Allmänna händelser](../building-journeys/general-events.md)
* [Reaktion](../building-journeys/reaction-events.md)
* [Målgruppskvalifikation](../building-journeys/audience-qualification-events.md)

![Paletten Händelseaktiviteter i resedesignern](assets/journey43.png)

Dra och släpp en händelseaktivitet för att starta din resa. Du kan också dubbelklicka på den.

![Dra och släpp händelseaktivitet i resedesignern](assets/journey44.png)

## Orchestration-verksamhet {#orchestration-activities}

Orchestration-aktiviteter är villkor som hjälper till att bestämma nästa steg i resan. Dessa villkor kan vara huruvida personen har ett öppet supportärende eller slutfört ett köp. De kan även omfatta lokala väderprognoser eller huruvida personen nått 10 000 kundpoäng.

På paletten till vänster på skärmen finns följande orkestreringsfunktioner:

* [Optimera](optimize.md)
* [Läs målgrupp](read-audience.md)
* [Vänta](wait-activity.md)
* [Innehållsbeslut](content-decision.md)
* [Datauppsättningssökning](dataset-lookup.md)

![Paletten Orchestration-aktiviteter i resedesignern](assets/journey-orchestration-activities.png)

## Åtgärdsaktiviteter {#action-activities}

Åtgärder är vad du vill ska hända som ett resultat av någon typ av utlösare, som att skicka ett meddelande. Det är den del av resan som kundupplevelsen innebär.

På paletten till vänster på skärmen, under **[!UICONTROL Events]** och **[!UICONTROL Orchestration]**, hittar du kategorin **[!UICONTROL Actions]**. Följande åtgärdsaktiviteter är tillgängliga:

* [Inbyggda kanalåtgärder](../building-journeys/journey-action.md) som är tillgängliga från aktiviteten **Åtgärd**
* [Anpassade åtgärder](../building-journeys/using-custom-actions.md)
* [Hoppa](../building-journeys/jump.md)

![Åtgärdsaktivitetspaletten i resedesignern](assets/journey58.png)

Dessa aktiviteter representerar olika tillgängliga kommunikationskanaler. Du kan kombinera dem för att skapa ett flerkanalsscenario.

Du kan också ange specifika åtgärder för att skicka meddelanden:

* Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en specifik anpassad åtgärd. [Läs mer](../action/action.md)

* Om du arbetar med [!DNL Adobe Campaign] och [!DNL Adobe Journey Optimizer] kan du läsa följande avsnitt:

   * [[!DNL Adobe Journey Optimizer] och [!DNL Adobe Campaign] v7/v8](../action/acc-action.md)
   * [[!DNL Adobe Journey Optimizer] och [!DNL Adobe Campaign] Standard](../action/acs-action.md)
   * [[!DNL Adobe Journey Optimizer] och [!DNL Adobe Marketo Engage]](../action/marketo-engage.md)

## Bästa praxis {#best-practices}

Använd dessa rekommendationer för att hålla resorna läsbara, enhetliga och enkla att felsöka.

### Lägga till en etikett

De flesta aktiviteter gör att du kan definiera en **[!UICONTROL Label]**. Detta lägger till ett suffix till namnet som visas under din aktivitet på arbetsytan. Detta är användbart om du använder samma aktivitet flera gånger under resan och vill identifiera dem enklare. Det underlättar även felsökning vid fel och gör rapporter enklare att läsa. Du kan också lägga till en valfri **[!UICONTROL Description]**.

![Etikett- och beskrivningsfält i egenskaperna för reseaktiviteten](assets/journey-action-label.png)

>[!NOTE]
>
>För vissa aktiviteter visas även deras ID i rutan. Detta ID kan användas vid rapportering som en mer stabil nyckel än etiketten, som kan ändras.

### Hantera avancerade parametrar {#advanced-parameters}

De flesta aktiviteter visar ett antal avancerade och/eller tekniska parametrar som du inte kan ändra.

![Avancerade parameterfält i egenskaperna för reseaktivitet](assets/journey-advanced-parameters.png)

För bättre läsbarhet kan du dölja de här parametrarna med knappen **[!UICONTROL Hide read-only fields]** överst i den högra rutan.

![Dölj ikonen för skrivskyddade fält i egenskaperna för reseaktivitet](assets/journey-hide-read-only-fields.png)

I vissa specifika sammanhang kan du åsidosätta parametrarnas värden för specifik användning. Om du vill framtvinga ett värde klickar du på ikonen **[!UICONTROL Enable parameter override]** till höger om fältet. [Läs mer](../configuration/primary-email-addresses.md#override-execution-address-journey)

![Aktivera alternativ för åsidosättning av parameter i egenskaperna för e-postaktivitet](assets/journey-enable-parameter-override.png)

>[!NOTE]
>
>Om de avancerade parametrarna är dolda klickar du på knappen **[!UICONTROL Show read-only fields]**
>
>![Visa ikonen för skrivskyddade fält i egenskaperna för reseaktivitet](assets/journey-show-read-only-fields.png){width=60%}

### Lägg till en alternativ sökväg

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få den att fortsätta är att markera rutan **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths)

![Lägg till ett alternativ sökväg i egenskaperna för villkorsaktivitet](assets/journey42.png)

## Felsökning {#troubleshooting}

Kontrollera att alla aktiviteter är konfigurerade korrekt innan du testar och publicerar din resa. Du kan inte utföra tester eller publikationer om fel fortfarande upptäcks av systemet.

Lär dig hur du felsöker fel i aktiviteter och under resan [på den här sidan](troubleshooting.md).

Se även [Övervakning och felsökning](../../rp_landing_pages/troubleshoot-journey-landing-page.md)
