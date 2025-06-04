---
solution: Journey Optimizer
product: journey optimizer
title: Skapa samordnade kampanjer med Journey Optimizer
description: Lär dig hur du skapar en strukturerad kampanj med Adobe Journey Optimizer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 13da680d-fef8-4749-9190-8ca3d77b060a
source-git-commit: 7f535b87e415ae9191199b34476adb5c977b66e9
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---


# Skapa en orkestrerad kampanj {#create-first-campaign}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](send-messages.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med Query Modeler](orchestrated-query-modeler.md)<br/><br/>[Skapa din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](activities/and-join.md) - [Skapa målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kombinera](activities/combine.md) - [Ta bort dubbletter](activities/deduplication.md) - [Förbättra](activities/enrichment.md) - [Förena](activities/fork.md) - [Förena&lbrace;1 ](activities/reconciliation.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

>[!CONTEXTUALHELP]
>id="ajo_campaign_creation_workflow"
>title="Lista över samordnade kampanjer"
>abstract="Fliken **Flersteg** visar alla samordnade kampanjer. Klicka på namnet på en orkestrerad kampanj för att redigera den. Använd knappen **Skapa orkestrerad kampanj** för att lägga till en ny orkestrerad kampanj."

## Skapa kampanjen

Så här skapar du en orkestrerad kampanj:

1. Om du vill skapa en **orkestrerad kampanj** går du till menyn **Kampanjer** .

1. Klicka på knappen **[!UICONTROL Create orchestrated campaign]** i skärmens övre högra hörn.

1. I den samordnade kampanjen **Egenskaper** väljer du den mall som ska användas för att skapa den orkestrerade kampanjen (du kan också använda den inbyggda standardmallen). [Läs mer om samordnade kampanjmallar](#campaign-templates).

1. Ange en etikett för den orkestrerade kampanjen. Dessutom rekommenderar vi att du lägger till en beskrivning till din samordnade kampanj i det dedikerade fältet i **[!UICONTROL Additional options]**-avsnittet på skärmen.

1. Expandera avsnittet **[!UICONTROL Additional options]** om du vill konfigurera fler inställningar för den orkestrerade kampanjen.

1. Klicka på knappen **[!UICONTROL Create orchestrated campaign]** för att bekräfta att din samordnade kampanj har skapats.

Din samordnade kampanj har nu skapats och är tillgänglig i listan över arbetsflöden. Nu kan du komma åt den visuella arbetsytan och börja lägga till, konfigurera och organisera de uppgifter som ska utföras. [Lär dig att orkestrera samordnade kampanjaktiviteter](orchestrate-activities.md).

## Konfigurera kampanjinställningarna

Översikt över nya administratörsinställningar> scheman, körningsfält, sammanfogningsprincip. [Läs mer](configuration-steps.md)

## Arbeta med samordnade kampanjmallar {#campaign-templates}

>[!CONTEXTUALHELP]
>id="ajo_workflow_template_for_campaign"
>title="Samordnade kampanjmallar"
>abstract="Mallar för samordnade kampanjer innehåller förkonfigurerade inställningar och aktiviteter som kan återanvändas för att skapa nya samordnade kampanjer."

>[!CONTEXTUALHELP]
>id="ajo_workflow_template_creation_properties"
>title="Samordnade kampanjegenskaper"
>abstract="Mallar för samordnade kampanjer innehåller förkonfigurerade inställningar och aktiviteter som kan återanvändas för att skapa nya samordnade kampanjer. På den här skärmen anger du etiketten för den orchestrerade kampanjmallen och konfigurerar inställningarna för den, till exempel dess interna namn, mapp och körningsmappar, tidszon och övervakningsgrupp."

Mallar för samordnade kampanjer innehåller förkonfigurerade inställningar och aktiviteter som kan återanvändas för att skapa nya samordnade kampanjer. Du kan välja mallen för den orkestrerade kampanjen bland de orkestrerade kampanjegenskaperna när du skapar en orkestrerad kampanj. En tom mall anges som standard.

Du kan skapa en mall från en befintlig orkestrerad kampanj eller skapa en ny mall från grunden. Båda metoderna beskrivs nedan.

>[!BEGINTABS]

>[!TAB Skapa en mall från en befintlig orkestrerad kampanj]

Så här skapar du en samlad kampanjmall från en befintlig orkestrerad kampanj:

1. Öppna menyn **Campaign** och bläddra till den orkestrerade kampanjen för att spara den som en mall.
1. Klicka på de tre punkterna till höger om namnet på den orkestrerade kampanjen och välj **Kopiera som mall**.
1. Bekräfta att mallen har skapats i popup-fönstret.
1. Kontrollera, lägg till och konfigurera aktiviteterna efter behov på arbetsytan för den strukturerade kampanjmallen.
1. Bläddra till inställningarna från knappen **Inställningar** för att ändra namnet på den orkestrerade kampanjmallen och ange en beskrivning.
1. Markera mallens **mapp** och **körningsmapp**. Mappen är den plats där den orkestrerade kampanjmallen sparas. Körningsmappen är den mapp där samordnade kampanjer som skapats utifrån den här mallen sparas.
1. Spara ändringarna.

Mallen för den orkestrerade kampanjen är nu tillgänglig i malllistan. Du kan skapa en orkestrerad kampanj baserat på den här mallen. Den här samordnade kampanjen förkonfigureras med inställningarna och aktiviteterna som definieras i mallen.


>[!TAB Skapa en mall från grunden]


Så här skapar du en osammanhängande kampanjmall från grunden:

1. Öppna menyn **Campaign** och gå till fliken **Mallar**. Du kan se en lista med tillgängliga samordnade kampanjmallar.
1. Klicka på knappen **[!UICONTROL Create template]** i skärmens övre högra hörn.
1. Ange etiketten och öppna de ytterligare alternativen för att ange en beskrivning av den orkestrerade kampanjmallen.
1. Välj mapp och körningsmapp för mallen. Mappen är den plats där den orkestrerade kampanjmallen sparas. Körningsmappen är den mapp där samordnade kampanjer som skapats utifrån den här mallen sparas.
1. Klicka på knappen **Skapa** för att bekräfta inställningarna.
1. Lägg till och konfigurera aktiviteterna efter behov på arbetsytan för den strukturerade kampanjmallen.

   ![](assets/wf-template-activities.png){zoomable="yes"}

1. Spara ändringarna.

Mallen för den orkestrerade kampanjen är nu tillgänglig i malllistan. Du kan skapa en orkestrerad kampanj baserat på den här mallen. Den här samordnade kampanjen förkonfigureras med inställningarna och aktiviteterna som definieras i mallen.

>[!ENDTABS]
