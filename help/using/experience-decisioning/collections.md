---
title: Samlingar
description: Lär dig arbeta med samlingar
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
source-git-commit: 69a2ef17b6f5ccd40c08858f7b434029964d544d
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 3%

---

# Samlingar {#collections}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsobjekt
   * [Konfigurera objektkatalogen](catalogs.md)
   * [Skapa beslutsobjekt](items.md)
   * **[Hantera artikelsamlingar](collections.md)**
* Konfigurera val av objekt
   * [Skapa beslutsregler](rules.md)
   * [Skapa rangordningsmetoder](ranking.md)
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