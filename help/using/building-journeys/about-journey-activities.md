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
source-git-commit: 503bedc30c35305537c62f9452f4a2dc07424523
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 8%

---

# Kom igång med reseaktiviteter {#about-journey-activities}

Kombinera de olika händelserna, samordningen och åtgärderna för att skapa flerstegsscenarier för olika kanaler.

## Evenemangsaktiviteter {#event-activities}

Personaliserade resor utlöses av händelser, t.ex. ett onlineköp. När en profil går in på en resa förflyttas de som en individ, och inga två personer följer med på samma hastighet eller längs samma väg. När du påbörjar en resa med en händelse aktiveras resan när händelsen tas emot. Varje person på resan följer sedan, individuellt, de steg som definieras på din resa.

Händelser som konfigurerats av den tekniska användaren (se [den här sidan](../event/about-events.md)) visas alla i den första kategorin på paletten, till vänster på skärmen. Följande aktiviteter är tillgängliga:

* [Allmänna händelser](../building-journeys/general-events.md)
* [Reaktion](../building-journeys/reaction-events.md)
* [Målgruppskvalifikation](../building-journeys/audience-qualification-events.md)

![](assets/journey43.png)

Starta din resa genom att dra och släppa en händelseaktivitet. Du kan också dubbelklicka på den.

![](assets/journey44.png)

## Orchestration-verksamhet {#orchestration-activities}

Orchestration-aktiviteter är olika villkor som hjälper till att bestämma nästa steg i resan. Det kan vara om personen har ett öppet supportärende eller inte, väderprognosen på sin nuvarande plats, om de slutförde ett köp eller inte, eller uppnådde 10 000 förmånspoäng.

På paletten till vänster på skärmen finns följande orkestreringsfunktioner:

* [Villkor](../building-journeys/condition-activity.md)
* [Vänta](../building-journeys/wait-activity.md)
* [Läs målgrupp](../building-journeys/read-audience.md)

![](assets/journey49.png)

## Verksamheter {#action-activities}

Åtgärder är vad du vill ska hända som ett resultat av någon typ av utlösare, som att skicka ett meddelande. Det är den del av resan som kundupplevelsen innebär.

På paletten, till vänster på skärmen, under **[!UICONTROL Events]** och **[!UICONTROL Orchestration]**, hittar du kategorin **[!UICONTROL Actions]**. Följande åtgärdsaktiviteter är tillgängliga:

* [Inbyggda kanalåtgärder](../building-journeys/journeys-message.md)
* [Anpassade åtgärder](../building-journeys/using-custom-actions.md)
* [Hoppa](../building-journeys/jump.md)

![](assets/journey58.png)

Dessa aktiviteter representerar olika tillgängliga kommunikationskanaler. Du kan kombinera dem för att skapa ett flerkanalsscenario.

<!--If you have configured custom actions, they also appear here. [Learn more](../building-journeys/using-custom-actions.md)-->

Du kan också ange specifika åtgärder för att skicka meddelanden till dig:

* Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en särskild anpassad åtgärd. [Läs mer](../action/action.md)

* Om du arbetar med Campaign och Journey Optimizer, se följande avsnitt:

   * [[!DNL Journey Optimizer] och Campaign v7/v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] och Campaign Standard](../action/acs-action.md)

## Bästa praxis {#best-practices}

### Lägga till en etikett

De flesta aktiviteter gör att du kan definiera en **[!UICONTROL Label]**. Detta lägger till ett suffix till namnet som visas under din aktivitet på arbetsytan. Detta är användbart om du använder samma aktivitet flera gånger under resan och vill identifiera dem enklare. Felsökningen blir också enklare om fel uppstår, vilket gör det lättare att läsa rapporterna. Du kan också lägga till en valfri **[!UICONTROL Description]**.

![](assets/journey-action-label.png)

>[!NOTE]
>
>För vissa aktiviteter visas även deras ID i rutan. Detta ID kan användas vid rapportering som en mer stabil nyckel än etiketten, som kan ändras.

### Hantera avancerade parametrar {#advanced-parameters}

De flesta aktiviteter visar ett antal avancerade och/eller tekniska parametrar som du inte kan ändra.

![](assets/journey-advanced-parameters.png)

För bättre läsbarhet kan du dölja de här parametrarna med knappen **[!UICONTROL Hide read-only fields]**.

![](assets/journey-hide-read-only-fields.png)

I vissa specifika sammanhang kan du åsidosätta parametrarnas värden för specifik användning. Om du vill framtvinga ett värde klickar du på ikonen **[!UICONTROL Enable parameter override]** till höger om fältet. [Läs mer](../configuration/primary-email-addresses.md#journey-parameters)

![](assets/journey-enable-parameter-override.png)

### Lägg till en alternativ sökväg

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få den att fortsätta är att markera rutan **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths).

![](assets/journey42.png)
