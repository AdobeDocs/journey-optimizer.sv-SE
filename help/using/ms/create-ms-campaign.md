---
solution: Journey Optimizer
product: journey optimizer
title: Skapa flerstegskampanjer med Journey Optimizer
description: Lär dig skapa en kampanj i flera steg med Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: 13da680d-fef8-4749-9190-8ca3d77b060a
source-git-commit: 271c4739a5537a99da981913606bc9eb099b5139
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 1%

---

# Skapa en orkestrerad kampanj {#create-first-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_creation_workflow"
>title="Lista över flerstegskampanjer"
>abstract="Fliken **Flersteg** visar alla flerstegskampanjer. Klicka på namnet på en kampanj i flera steg för att redigera den. Använd knappen **Skapa flerstegskampanj** för att lägga till en ny flerstegskampanj."

## Förhandskrav

### Behörigheter

### Inställningar

Översikt över nya administratörsinställningar> scheman, körningsfält, sammanfogningsprincip. [Läs mer](ms-schemas.md)


## Skapandesteg

Så här skapar du en kampanj i flera steg:

1. Bläddra till menyn **Kampanjer** om du vill skapa en **kampanj i flera steg**.

1. Klicka på knappen **[!UICONTROL Create multi-step campaign]** i skärmens övre högra hörn.

1. I dialogrutan **Egenskaper** för flerstegskampanjer väljer du den mall som ska användas för att skapa flerstegskampanjen (du kan också använda den inbyggda standardmallen). [Läs mer om kampanjmallar i flera steg](#campaign-templates).

1. Ange en etikett för flerstegskampanjen. Dessutom rekommenderar vi att du lägger till en beskrivning till din flerstegskampanj i det dedikerade fältet i **[!UICONTROL Additional options]**-avsnittet på skärmen.

1. Expandera avsnittet **[!UICONTROL Additional options]** om du vill konfigurera fler inställningar för flerstegskampanjen.

1. Klicka på knappen **[!UICONTROL Create multi-step campaign]** för att bekräfta att du har skapat en kampanj i flera steg.

Din flerstegskampanj har nu skapats och är tillgänglig i listan över arbetsflöden. Nu kan du komma åt den visuella arbetsytan och börja lägga till, konfigurera och organisera de uppgifter som ska utföras. [Lär dig att samordna kampanjaktiviteter i flera steg](orchestrate-activities.md).

## Arbeta med mallar för kampanjer i flera steg {#campaign-templates}

>[!CONTEXTUALHELP]
>id="ajo_workflow_template_for_campaign"
>title="Mallar för flerstegskampanjer"
>abstract="Mallar för flerstegskampanjer innehåller förkonfigurerade inställningar och aktiviteter som kan återanvändas för att skapa nya flerstegskampanjer."

>[!CONTEXTUALHELP]
>id="ajo_workflow_template_creation_properties"
>title="Egenskaper för kampanjer i flera steg"
>abstract="Mallar för flerstegskampanjer innehåller förkonfigurerade inställningar och aktiviteter som kan återanvändas för att skapa nya flerstegskampanjer. På den här skärmen anger du etiketten för flerstegskampanjmallen och konfigurerar inställningarna för den, till exempel dess interna namn, mapp och körningsmappar, tidszon och övervakningsgrupp."

Mallar för flerstegskampanjer innehåller förkonfigurerade inställningar och aktiviteter som kan återanvändas för att skapa nya flerstegskampanjer. Du kan välja en mall för din flerstegskampanj bland egenskaperna för flerstegskampanjer när du skapar en flerstegskampanj. En tom mall anges som standard.

Du kan skapa en mall från en befintlig kampanj i flera steg eller skapa en ny mall från början. Båda metoderna beskrivs nedan.

>[!BEGINTABS]

>[!TAB Skapa en mall från en befintlig flerstegskampanj]

Så här skapar du en kampanjmall i flera steg från en befintlig kampanj i flera steg:

1. Öppna menyn **Campaign** och bläddra till den flerstegskampanj som du vill spara som en mall.
1. Klicka på de tre punkterna till höger om namnet på flerstegskampanjen och välj **Kopiera som mall**.
1. Bekräfta att mallen har skapats i popup-fönstret.
1. Kontrollera, lägg till och konfigurera aktiviteter efter behov på arbetsytan för flerstegskampanjer.
1. Bläddra till inställningarna från knappen **Inställningar** för att ändra namnet på mallen för flerstegskampanj och ange en beskrivning.
1. Markera mallens **mapp** och **körningsmapp**. Mappen är den plats där kampanjmallen för flera steg sparas. Körningsmappen är den mapp där flerstegskampanjer som skapats utifrån den här mallen sparas.
1. Spara ändringarna.

Mallen för flerstegskampanjer är nu tillgänglig i malllistan. Du kan skapa en kampanj i flera steg baserat på den här mallen. Den här flerstegskampanjen kommer att förkonfigureras med inställningarna och aktiviteterna som definieras i mallen.


>[!TAB Skapa en mall från grunden]


Så här skapar du en kampanjmall i flera steg från grunden:

1. Öppna menyn **Campaign** och gå till fliken **Mallar**. Du kan se en lista över tillgängliga mallar för kampanjer i flera steg.
1. Klicka på knappen **[!UICONTROL Create template]** i skärmens övre högra hörn.
1. Ange etiketten och öppna de ytterligare alternativen för att ange en beskrivning av din kampanjmall i flera steg.
1. Välj mapp och körningsmapp för mallen. Mappen är den plats där kampanjmallen för flera steg sparas. Körningsmappen är den mapp där flerstegskampanjer som skapats utifrån den här mallen sparas.
1. Klicka på knappen **Skapa** för att bekräfta inställningarna.
1. Lägg till och konfigurera aktiviteterna efter behov på arbetsytan för flerstegskampanjer.

   ![](assets/wf-template-activities.png){zoomable="yes"}

1. Spara ändringarna.

Mallen för flerstegskampanjer är nu tillgänglig i malllistan. Du kan skapa en kampanj i flera steg baserat på den här mallen. Den här flerstegskampanjen kommer att förkonfigureras med inställningarna och aktiviteterna som definieras i mallen.

>[!ENDTABS]
