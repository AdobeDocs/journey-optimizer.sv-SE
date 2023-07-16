---
title: Skapa samlingar
description: Lär dig organisera erbjudanden med samlingar
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 0c8808e3-9148-4a33-9fd5-9218e02c2dfd
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Skapa samlingar {#create-collections}

>[!CONTEXTUALHELP]
>id="ajo_decisioning_decision_collection"
>title="Om erbjudandesamlingar"
>abstract="Med erbjudandesamlingar kan ni ordna era erbjudanden genom att gruppera om dem i olika kategorier."

Med samlingar kan du ordna dina erbjudanden genom att gruppera om dem i olika kategorier. Du kan till exempel skapa en&quot;sport&quot;-samling som bara innehåller sportrelaterade erbjudanden.

➡️ [Upptäck den här funktionen i en video](#video)

Listan med erbjudandesamlingar finns i **[!UICONTROL Offers]** -menyn.

![](../assets/collections_list.png)

Du kan skapa två typer av samlingar:

* **Dynamiska samlingar** är samlingar av erbjudanden som baseras på samlingskvalificerare (som tidigare kallades &quot;taggar&quot;). Dessa samlingar uppdateras automatiskt. Om till exempel ett nytt erbjudande skapas med den valda samlingskvalificeraren läggs det automatiskt till i samlingen.

* **Statiska samlingar** är samlingar som skapats genom att du manuellt väljer enskilda erbjudanden som ska ingå i samlingen. Samlingen kan bara uppdateras genom att fler erbjudanden läggs till manuellt.

Så här skapar du en samling:

1. Gå till **[!UICONTROL Collections]** tabbtangenten och sedan klicka **[!UICONTROL Create collection]**.

1. Ange namn och typ av samling som ska skapas.

   ![](../assets/collection_create.png)

1. Om du vill skapa en dynamisk samling använder du den vänstra rutan för att välja den som ska lägga till erbjudandena i samlingen. Klicka sedan på **[!UICONTROL Save]**. Alla erbjudanden med den valda samlingskvalificeraren sparas i samlingen.

   Mer information om att skapa samlingskvalificerare finns i [Skapa samlingskvalificerare](../offer-library/creating-tags.md).

   ![](../assets/dynamic_collection.png)

1. Om du vill skapa en statisk samling använder du den vänstra rutan för att filtrera listan med erbjudanden (status, samlingskvalificerare, datum, kanal, innehållstyp) och väljer sedan de erbjudanden som ska läggas till i samlingen.

   ![](../assets/static_collection.png)

   >[!NOTE]
   >
   >Statiska samlingar uppdateras inte automatiskt. Om du vill lägga till erbjudanden i en statisk samling måste du redigera den och lägga till dem manuellt.

1. Om du vill tilldela anpassade eller grundläggande användningsrubriker till en statisk samling väljer du **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../../administration/object-based-access.md)

   >[!NOTE]
   >
   >Det går inte att använda OLAC för dynamiska samlingar. Den måste hanteras på erbjudandenivå. Därför är det möjligt att du inte ser några erbjudanden i en dynamisk samling om du inte har tillgång till något av dessa erbjudanden.

1. När samlingen har skapats visas den i listan. Du kan markera den om du vill redigera eller ta bort den.

   ![](../assets/collection_created.png)

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329376?quality=12)


