---
title: Om uttrycksredigeraren
description: Lär dig hur du arbetar med uttrycksredigeraren.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 1ac2a376-a3a8-41ae-9b04-37886697f0fc
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 1%

---

# Om uttrycksredigeraren {#build-personalization-expressions}

>[!CONTEXTUALHELP]
>id="ajo_perso_editor"
>title="Om uttrycksredigeraren"
>abstract="Med uttrycksredigeraren kan du välja, ordna, anpassa och validera alla data för att skapa en anpassad personalisering för ditt innehåll."

Uttrycksredigeraren är navet i personaliseringen i [!DNL Journey Optimizer]. Det finns i alla sammanhang där du behöver definiera personalisering som e-post, push och erbjudanden.

I gränssnittet för uttrycksredigeraren väljer, ordnar, anpassar och validerar du alla data för att skapa en anpassad personalisering för ditt innehåll.

![](assets/perso_ee1.png)

I den vänstra delen av skärmen visas en domänväljare där du kan välja källa för personalisering.

![](assets/perso_ee3.png)

Tillgängliga källor är:

* **[!UICONTROL Profile attributes]** : visar alla referenser som är associerade med profilschemat som beskrivs i [Dokumentation för Adobe Experience Platform Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target=&quot;_blank&quot;}.
* **[!UICONTROL Segment memberships]** : listar alla segment som har skapats i Adobe Experience Platform Segmenteringstjänst. Mer information om segmentering finns [här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target=&quot;_blank&quot;}.
* **[!UICONTROL Offer decisions]** : visar alla erbjudanden som är kopplade till en viss placering. Välj placering och infoga sedan erbjudandena i innehållet. En fullständig dokumentation om hur du hanterar erbjudanden finns på [det här avsnittet](../messages/deliver-personalized-offers.md).
* **[!UICONTROL Contextual attributes]** : när **Meddelande** som används i en resa är sammanhangsberoende resefält tillgängliga via den här menyn. Läs mer i [det här avsnittet](personalization-use-case.md).
* **[!UICONTROL Helper functions]** : visar alla hjälpfunktioner som är tillgängliga för att utföra dataåtgärder, t.ex. beräkningar, dataformatering eller konverteringar, villkor och manipulera dem i personaliseringssammanhang. Läs mer i [det här avsnittet](functions/functions.md).

Klicka på plusknappen (+) för att lägga till ett attribut i redigeraren.

>[!NOTE]
>
>Med ellipsmenyn bredvid ikonen&quot;+&quot; kan du få mer information om varje variabel och lägga till de mest frekventa attribut som används i [favoriter](personalization-favorites.md).

![](assets/attribute-details.png)

I följande exempel kan du välja de profiler som har sin födelsedag i dag och sedan slutföra anpassningen genom att infoga ett specifikt erbjudande som motsvarar den här dagen.

![](assets/perso_ee2.png)

När personaliseringsuttrycket är klart måste det valideras av uttrycksredigeraren. Läs mer i [det här avsnittet](personalization-validation.md).
