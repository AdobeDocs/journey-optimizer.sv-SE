---
title: Samlingar
description: Lär dig arbeta med samlingar
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: 099d1439-34f7-47fe-9181-0e9ce2032a01
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '510'
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

Med samlingar kan du kategorisera och gruppera dina beslutsobjekt enligt dina önskemål. Dessa kategorier skapas genom att regler som utnyttjar attributen för beslutsposter skapas.

Anta att du har lagt till ett anpassat kategoriattribut i beslutsobjektens katalogschema. På så sätt kan du skapa en samling som innehåller alla beslutsobjekt med värdet Yoga i attributet Kategori.

Listan med samlingar finns på menyn **[!UICONTROL Catalogs]**.

Så här skapar du en samling:

1. Navigera till **[!UICONTROL Catalogs]** > **[!UICONTROL Collections]** och klicka på **[!UICONTROL Create collection]**.
1. Ange ett namn och en beskrivning för samlingen.
1. Lägg till en eller flera regler för att bestämma vilka objekt som ska inkluderas i samlingen. Så här gör du:

   1. Välj ett objektattribut att använda som villkor. Attributlistan innehåller alla standardattribut och anpassade attribut som definierats i katalogschemat. [Läs mer om objektets katalog](catalogs.md)
   1. Välj önskad operator och ange värdet som ska filtreras på. Ange varje erbjudandenamn explicit eller skapa och tilldela en&quot;luma-sommar&quot;-tagg till varje erbjudande.

      >[!NOTE]
      >
      >Operatorn **CONTAINS** stöder inte matchningar med delar eller jokertecken. Det fungerar som en **IN** -operator, vilket innebär att du måste ange en array med exakta värden för attributet.
      >
      >Anta till exempel att du har flera sommarerbjudanden som du vill ta med i en samling: *&quot;luma-sommar-yoga&quot;*, *&quot;luma-sommar-fitness&quot;* och *&quot;luma-sommar-running&quot;*. Om du vill ta med de här objekten måste du definiera en regel som&quot;Erbjudandenamn&quot; INNEHÅLLER&quot;luma-sommar-yoga&quot;,&quot;luma-sommar-fitness&quot;,&quot;luma-sommar-running&quot;. Den här regeln returnerar endast erbjudanden som exakt matchar ett av namnen i listan.
      >
      >Om du behöver partiell matchning (t.ex. alla erbjudanden som innehåller *&quot;luma-sommar&quot;*) stöds inte detta för närvarande. Du måste ange varje erbjudandenamn explicit eller tilldela en *&quot;luma-sommar&quot;* -tagg till varje erbjudande och använda den taggen i din regel.

   1. Upprepa dessa steg om du vill lägga till så många regler som behövs. När flera regler läggs till kan du välja mellan operatorerna **och** och **Eller** för att kombinera dem. Om du vill göra det klickar du på operatormärket för att växla mellan de två alternativen.
   1. Klicka på knappen **[!UICONTROL Preview collection]** för att visa de objekt som uppfyller de regler som du har definierat.

   ![](assets/collection-create.png)

1. När samlingsreglerna har definierats klickar du på **[!UICONTROL Create]**. Samlingen visas nu i listan.

>[!NOTE]
>
>Varje artikelsamling kan innehålla upp till 500 erbjudandeartiklar. [Läs mer om hur du bestämmer dig för skyddsprofiler och begränsningar](gs-experience-decisioning.md#guardrails)
