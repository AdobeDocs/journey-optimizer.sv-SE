---
solution: Journey Optimizer
product: journey optimizer
title: Om personaliseringsredigeraren
description: Lär dig arbeta med personaliseringsredigeraren.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, om, start
exl-id: 1ac2a376-a3a8-41ae-9b04-37886697f0fc
source-git-commit: fe22eef1e1d74101ba7c046fca28a5a95007dd81
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 2%

---

# Kom igång med personaliseringsredigeraren {#build-personalization-expressions}

>[!CONTEXTUALHELP]
>id="ajo_perso_editor"
>title="Om personaliseringsredigeraren"
>abstract="Med personaliseringsredigeraren kan du välja, ordna, anpassa och validera alla data för att skapa en anpassad personalisering för ditt innehåll."

>[!CONTEXTUALHELP]
>id="ajo_perso_editor_autocomplete"
>title="Automatiskt slutförd"
>abstract="Om du växlar till det här alternativet kan systemet automatiskt slutföra koden och ge förslag medan du skriver ditt uttryck. Det här alternativet är endast tillgängligt för HTML-format."

Anpassningsredigeraren är navet i personaliseringen i [!DNL Journey Optimizer]. Det finns i alla sammanhang där du behöver definiera personalisering som e-post, push och erbjudanden.

I personaliseringsredigeringsgränssnittet väljer, ordnar, anpassar och validerar du alla data för att skapa en anpassad personalisering för ditt innehåll.

![](assets/perso_ee1.png)

## Tillgängliga personaliseringskällor {#sources}

I den vänstra delen av skärmen visas en domänväljare där du kan välja källa för personalisering. Tillgängliga källor är:

* **[!UICONTROL Profile attributes]** : visar alla referenser som är kopplade till profilschemat som beskrivs i [dokumentationen för Adobe Experience Platform datamodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.
* **[!UICONTROL Audiences]**: visar alla målgrupper som skapats i Adobe Experience Platform Segmenteringstjänst. Mer information om segmentering finns [här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target="_blank"}.
* **[!UICONTROL Offer decisions]** : visar alla erbjudanden som är kopplade till en viss placering. Välj placering och infoga sedan erbjudandena i innehållet. En fullständig dokumentation om hur du hanterar erbjudanden finns i [det här avsnittet](../offers/get-started/starting-offer-decisioning.md).
* **[!UICONTROL Contextual attributes]** : När en kanalåtgärdsaktivitet (E-post, push, SMS) används i en resa eller kampanj är kontextattribut som relaterar till händelser och egenskaper tillgängliga för personalisering. Ett exempel på hur personalisering utnyttjar sammanhangsberoende attribut visas i [det här avsnittet](personalization-use-case.md).
* **[!UICONTROL Helper functions]** : visar alla hjälpfunktioner som är tillgängliga för att utföra dataåtgärder, som beräkningar, dataformatering eller konvertering, villkor och manipulera dem i personaliseringssammanhang. Läs mer i [det här avsnittet](functions/functions.md).

## Lägg till personaliseringsattribut {#add}

Klicka på plusknappen (+) för att lägga till ett attribut i ditt personaliseringsuttryck.

Med ellipsmenyn bredvid ikonen&quot;+&quot; kan du få mer information om varje variabel och lägga till de attribut som används oftast i favoriter. [Lär dig hur du lägger till attribut i favoriter](personalization-favorites.md)

>[!NOTE]
>
>Om ni riktar in er på en målgrupp med anrikningsattribut som genereras med ett arbetsflöde för komposition kan ni utnyttja dessa anrikningsattribut för att personalisera ert budskap. [Lär dig använda attribut för målgruppsberikning](../audience/about-audiences.md#enrichment)

Dessutom kan du definiera standardreservtext som visas om ett profilattribut av strängtyp är tomt. Det gör du genom att klicka på ellipsknappen bredvid attributet och välja **[!UICONTROL Insert with fallback text]**. Skriv den text som ska visas som standard om attributets värde är tomt för en profil och klicka sedan på **[!UICONTROL Add]**.

![](assets/attribute-details.png)

I följande exempel kan du välja de profiler som har sin födelsedag i dag och sedan slutföra anpassningen genom att infoga ett specifikt erbjudande som motsvarar den här dagen.

![](assets/perso_ee2.png)

När personaliseringsuttrycket är klart måste det valideras av personaliseringsredigeraren. Läs mer i [det här avsnittet](personalization-validation.md).
