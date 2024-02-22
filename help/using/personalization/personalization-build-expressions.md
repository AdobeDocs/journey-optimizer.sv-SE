---
solution: Journey Optimizer
product: journey optimizer
title: Om uttrycksredigeraren
description: Lär dig arbeta med uttrycksredigeraren.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, om, start
exl-id: 1ac2a376-a3a8-41ae-9b04-37886697f0fc
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---

# Kom igång med uttrycksredigeraren {#build-personalization-expressions}

>[!CONTEXTUALHELP]
>id="ajo_perso_editor"
>title="Om uttrycksredigeraren"
>abstract="Med uttrycksredigeraren kan du välja, ordna, anpassa och validera alla data för att skapa en anpassad personalisering för ditt innehåll."

Uttrycksredigeraren är navet i personaliseringen i [!DNL Journey Optimizer]. Det finns i alla sammanhang där du behöver definiera personalisering som e-post, push och erbjudanden.

I gränssnittet för uttrycksredigeraren väljer, ordnar, anpassar och validerar du alla data för att skapa en anpassad personalisering för ditt innehåll.

![](assets/perso_ee1.png)

## Tillgängliga personaliseringskällor {#sources}

I den vänstra delen av skärmen visas en domänväljare där du kan välja källa för personalisering. Tillgängliga källor är:

* **[!UICONTROL Profile attributes]** : visar alla referenser som är associerade med profilschemat som beskrivs i [Dokumentation för Adobe Experience Platform Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.
* **[!UICONTROL Audiences]** : listar alla målgrupper som skapats i Adobe Experience Platform Segmentation Service. Mer information om segmentering finns [här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target="_blank"}.
* **[!UICONTROL Offer decisions]** : visar alla erbjudanden som är kopplade till en viss placering. Välj placering och infoga sedan erbjudandena i innehållet. En fullständig dokumentation om hur du hanterar erbjudanden finns på [det här avsnittet](../offers/get-started/starting-offer-decisioning.md).
* **[!UICONTROL Contextual attributes]** : När en kanalåtgärdsaktivitet (e-post, push, SMS) används i en resa eller kampanj är kontextattribut som relaterar till händelser och egenskaper tillgängliga för personalisering. Ett exempel på hur personalisering utnyttjar sammanhangsberoende attribut finns i [det här avsnittet](personalization-use-case.md).
* **[!UICONTROL Helper functions]** : innehåller alla hjälpfunktioner som är tillgängliga för att utföra dataåtgärder, t.ex. beräkningar, dataformatering eller konvertering, villkor och manipulera dem i personaliseringssammanhang. Läs mer i [det här avsnittet](functions/functions.md).

## Lägg till personaliseringsattribut {#add}

Klicka på plusknappen (+) för att lägga till ett attribut i ditt personaliseringsuttryck.

Med ellipsmenyn bredvid ikonen&quot;+&quot; kan du få mer information om varje variabel och lägga till de attribut som används oftast i favoriter. [Lär dig hur du lägger till attribut i favoriter](personalization-favorites.md)

>[!NOTE]
>
>Om ni riktar in er på en målgrupp med anrikningsattribut som genererats med ett arbetsflöde för komposition eller en anpassad överföring (CSV-fil) kan ni utnyttja dessa anrikningsattribut för att personalisera ert budskap. [Lär dig använda attribut för målgruppsberikning](../audience/about-audiences.md#enrichment)

Dessutom kan du definiera standardreservtext som visas om ett profilattribut av strängtyp är tomt. Det gör du genom att klicka på ellipsknappen bredvid attributet och välja **[!UICONTROL Insert with fallback text]**. Skriv den text som ska visas som standard om attributets värde är tomt för en profil och klicka sedan på **[!UICONTROL Add]**.

![](assets/attribute-details.png)

I följande exempel kan du välja de profiler som har sin födelsedag i dag och sedan slutföra anpassningen genom att infoga ett specifikt erbjudande som motsvarar den här dagen.

![](assets/perso_ee2.png)

När personaliseringsuttrycket är klart måste det valideras av uttrycksredigeraren. Läs mer i [det här avsnittet](personalization-validation.md).
