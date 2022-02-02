---
title: Om uttrycksredigeraren
description: Lär dig hur du arbetar med uttrycksredigeraren.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
source-git-commit: 50e12a28ed9f94133a9810a460172d34ad3a4593
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Om uttrycksredigeraren {#build-personalization-expressions}

Uttrycksredigeraren är navet i personaliseringen i [!DNL Journey Optimizer]. Det finns i alla sammanhang där du behöver definiera personalisering som e-post, push och erbjudanden.

I gränssnittet för uttrycksredigeraren väljer, ordnar, anpassar och validerar du alla data för att skapa en anpassad personalisering för ditt innehåll.

![](assets/perso_ee1.png)

I den vänstra delen av skärmen visas en domänväljare där du kan välja källa för personalisering.

![](assets/perso_ee3.png)

Tillgängliga källor är:

* **[!UICONTROL Profile attributes]** : visar alla referenser som är associerade med profilschemat som beskrivs i [Dokumentation för Adobe Experience Platform Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target=&quot;_blank&quot;}.
* **[!UICONTROL Segment memberships]** : listar alla segment som har skapats i Adobe Experience Platform Segmenteringstjänst. Mer information om segmentering finns [här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target=&quot;_blank&quot;}.
* **[!UICONTROL Offer decisions]** : visar alla erbjudanden som är kopplade till en viss placering. Välj placering och infoga sedan erbjudandena i innehållet. En fullständig dokumentation om hur du hanterar erbjudanden finns på [det här avsnittet](../deliver-personalized-offers.md).
* **[!UICONTROL Contextual attributes]** : när **Meddelande** som används i en resa är sammanhangsberoende resefält tillgängliga via den här menyn. Läs mer i [det här avsnittet](personalization-use-case.md).
* **[!UICONTROL Helper functions]** : visar alla hjälpfunktioner som är tillgängliga för att utföra dataåtgärder, t.ex. beräkningar, dataformatering eller konverteringar, villkor och manipulera dem i personaliseringssammanhang. Läs mer i [det här avsnittet](functions/functions.md).

Vid markering läggs referensen till i redigeraren.

>[!NOTE]
>
>Informationsikonen bredvid ikonen + öppnar ett verktygstips med mer information om varje variabel.
>
>Du kan lägga till de attribut som används mest i favoriter. Läs mer i [det här avsnittet](personalization-favorites.md).

I följande exempel kan du välja de profiler som har sin födelsedag i dag och sedan slutföra anpassningen genom att infoga ett specifikt erbjudande som motsvarar den här dagen.

![](assets/perso_ee2.png)

När personaliseringsuttrycket är klart måste det valideras av uttrycksredigeraren. Läs mer i [det här avsnittet](personalization-validation.md).