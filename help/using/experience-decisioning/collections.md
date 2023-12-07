---
title: Samlingar
description: Lär dig arbeta med samlingar
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 099d1439-34f7-47fe-9181-0e9ce2032a01
source-git-commit: c13cd73229b2fab80722663afae9fe24b660c0f9
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%

---

# Samlingar {#collections}

>[!CONTEXTUALHELP]
>id="ajo_exd_item_collections"
>title="Skapa samlingar"
>abstract="Med samlingar kan du kategorisera och gruppera dina beslutsobjekt enligt dina önskemål. Dessa kategorier skapas genom att regler som utnyttjar attributen för beslutsposter skapas."

>[!CONTEXTUALHELP]
>id="ajo_exd_item_collection_rules"
>title="Definiera regler för din samling"
>abstract="Lägg till en eller flera regler för att bestämma vilka objekt som ska inkluderas i samlingen. Välj ett objektattribut att använda som villkor. Markera önskad operator och ange värdet som ska filtreras. Lägg till så många regler som behövs."

>[!CONTEXTUALHELP]
>id="ajo_exd_strategy_collection"
>title="Välj en samling"
>abstract="Välj den samling som innehåller de erbjudanden som ska övervägas. Det här steget är obligatoriskt när du skapar en urvalsstrategi. Med samlingar kan du kategorisera och gruppera dina beslutsobjekt enligt dina önskemål. Du kan till exempel skapa en samling som innehåller alla beslutsobjekt med värdet Yoga i det anpassade attributet Kategori."

>[!BEGINSHADEBOX &quot;Det du hittar i den här handboken&quot;]

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsposter: [Konfigurera objektkatalogen](catalogs.md) - [Skapa beslutsobjekt](items.md) - **[Hantera artikelsamlingar](collections.md)**
* Konfigurera objektmarkering: [Skapa beslutsregler](rules.md) - [Skapa rangordningsmetoder](ranking.md)
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

Med samlingar kan du kategorisera och gruppera dina beslutsobjekt enligt dina önskemål. Dessa kategorier skapas genom att regler som utnyttjar attributen för beslutsposter skapas.

Anta att du har lagt till ett anpassat kategoriattribut i beslutsobjektens katalogschema. På så sätt kan du skapa en samling som innehåller alla beslutsobjekt med värdet Yoga i attributet Kategori.

Listan med samlingar finns på **[!UICONTROL Items]** -menyn.

Så här skapar du en samling:

1. Navigera till **[!UICONTROL Items]** > **[!UICONTROL Collections]** och klicka **[!UICONTROL Create collection]**.
1. Ange ett namn och en beskrivning för samlingen.
1. Lägg till en eller flera regler för att bestämma vilka objekt som ska inkluderas i samlingen. Så här gör du:

   1. Välj ett objektattribut att använda som villkor. Attributlistan innehåller alla standardattribut och anpassade attribut som definierats i katalogschemat. [Läs mer om objektets katalog](catalogs.md)
   1. Markera önskad operator och ange värdet som ska filtreras.
   1. Upprepa dessa steg om du vill lägga till så många regler som behövs. När flera regler har lagts till kan du välja mellan **Och** och **eller** -operatorer för att kombinera dem. Om du vill göra det klickar du på operatormärket för att växla mellan de två alternativen.

   ![](assets/collection-create.png)

1. När samlingsreglerna har definierats klickar du på **[!UICONTROL Create]**. Samlingen visas nu i listan.
