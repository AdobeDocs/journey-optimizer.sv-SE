---
title: Anpassa innehåll i Journey Optimizer
description: Kom igång med personalisering
feature: Personalization
topic: Personalization
role: Data Engineer
level: Beginner
exl-id: f448780b-91bc-455e-bf10-9a9aee0a0b24
source-git-commit: 244f05998098bf1770d5f33c955f09688f58ffe7
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---

# Kom igång med personalisering{#add-personalization}

Upptäck [!DNL Adobe Journey Optimizer] personaliseringsfunktioner för att anpassa era meddelanden till varje specifik mottagare genom att utnyttja de data och den information ni har om dem. Det kan vara deras förnamn, intressen, var de bor, vad de har köpt och mycket annat.

➡️ [Lär dig hur du anpassar ett meddelande i dessa videofilmer](#video-perso)

[!DNL Journey Optimizer] använder **inline** enkel personaliseringssyntax baserad på Handlebars, som gör att du kan skapa uttryck med innehåll inneslutet av dubbla klammerparenteser **{{}}**. Du kan lägga till flera uttryck i samma innehåll eller fält utan begränsningar. Läs mer i [Anpassningssyntax](personalization-syntax.md).

Personaliseringen baseras på profildata som hanteras av **Individuell XDM-profil** schema definierat i Adobe Experience Platform. Läs mer i [Dokumentation för Adobe Experience Platform Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target=&quot;_blank&quot;}.

>[!CAUTION]
>The **Individuell XDM-profil** schema är det enda schema som du kan använda för att anpassa innehåll i [!DNL Journey Optimizer].

**Exempel:**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`

* `Hello {{profile.person.name.fullName}}`

När du bearbetar meddelandet (e-post och push) ersätter Journey Optimizer uttrycket med data som finns i databasen för Experience Cloud Platform:  `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` blir &quot;Hello John Doe&quot;.


## Anpassningssammanhang{#personalization-areas}

Innehåll och visning av meddelanden som levereras av [!DNL Journey Optimizer] kan personaliseras på flera olika sätt.

I alla fält med redigeringsikonen kan du öppna redigeringsprogrammet för anpassning (även kallat uttrycksredigeraren) och definiera personalisering.

![](assets/perso_icon.png)

### Anpassa e-postmeddelanden

När du skapar ett e-postmeddelande kan du lägga till personalisering i **[!UICONTROL Subject line]** meddelandets fält.

![](assets/perso_subject.png)

I e-postdesignern kan du anpassa innehållet:

* I **message**: klicka i ett textblock och klicka på **Anpassa** ikonen i det sammanhangsberoende verktygsfältet och välj **Infoga personalisering** fält. Mer information om gränssnittet för e-postdesignern finns i [section](../design-emails.md).

   ![](assets/perso_insert.png)

* För **link**: markera text eller bild i ett textblock och klicka på **Infoga länk** ikonen i det sammanhangsberoende verktygsfältet. I fönstret kan du lägga till ett anpassningsblock genom att klicka på **Lägg till personalisering** ikon.

   ![](assets/perso_link.png)

I båda fallen får du tillgång till personaliseringsredigeraren.

![](assets/perso_ee.png)

### Anpassa push-meddelanden

Du kan också anpassa dina **Push-meddelanden** i följande fält:

* **Titel**
* **Brödtext**
* **Eget ljud**
* **Badges**
* **Anpassade data**

![](assets/perso_push.png)

Läs mer om konfigurationen för push-meddelanden i [det här avsnittet](../push-gs.md).

### Anpassa era erbjudanden {#personalize-offers}

Du kan även komma åt personaliseringsredigeraren när du lägger till textinnehåll till offerternas representationer.

Läs mer om hur du hanterar innehåll med beslutsstöd i [det här avsnittet](../offers/offer-library/creating-personalized-offers.md#custom-text).

## Använda uttrycksredigeraren {#use-expression-editor}

Uttrycksredigeraren är navet i personaliseringen i [!DNL Journey Optimizer].

Det finns i alla sammanhang där du behöver definiera personalisering som e-post, push och erbjudanden.

I gränssnittet för uttrycksredigeraren väljer, ordnar, anpassar och validerar du alla data för att skapa en anpassad personalisering för ditt innehåll.

![](assets/perso_ee1.png)

I den vänstra delen av skärmen visas en domänväljare där du kan välja källa för personalisering.

![](assets/perso_ee3.png)

Tillgängliga källor är:

* **[!UICONTROL Profile attributes]** : visar alla referenser som är associerade med profilschemat som beskrivs i [Dokumentation för Adobe Experience Platform Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html){target=&quot;_blank&quot;}.
* **[!UICONTROL Segment memberships]** : listar alla segment som har skapats i Adobe Experience Platform Segmenteringstjänst. Mer information om segmentering finns [här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target=&quot;_blank&quot;}.
* **[!UICONTROL Offer decisions]** : visar alla erbjudanden som är kopplade till en viss placering. Välj placering och infoga sedan erbjudandena i innehållet. En fullständig dokumentation om hur du hanterar erbjudanden finns på [det här avsnittet](../deliver-personalized-offers.md).
* **[!UICONTROL Contextual attributes]** : när **Meddelande** som används i en resa är sammanhangsberoende resefält tillgängliga via den här menyn. Läs mer i [det här avsnittet](personalization-use-case.md).
* **[!UICONTROL Helper functions]** : visar alla hjälpfunktioner som är tillgängliga för att utföra dataåtgärder, t.ex. beräkningar, dataformatering eller konverteringar, villkor och manipulera dem i personaliseringssammanhang. Läs mer i [det här avsnittet](functions/functions.md).

Vid markering läggs referensen till i redigeraren.

>[!NOTE]
>
>Informationsikonen bredvid ikonen + öppnar ett verktygstips med mer information om varje variabel.

I följande exempel kan du välja de profiler som har sin födelsedag i dag och sedan slutföra anpassningen genom att infoga ett specifikt erbjudande som motsvarar den här dagen.

![](assets/perso_ee2.png)

### Lägg till i favoriter{#fav}

Genom att lägga till olika attribut på Favoriter-menyn får du snabb åtkomst till de objekt du använder mest. Om du vill lägga till ett attribut i dina favoriter klickar du på ellipsmenyn och väljer **[!UICONTROL Add to favorites]**.

![](assets/favorite-option.png)

Om du vill få tillgång till objekt som du är nöjd med använder du **[!UICONTROL Favorites]** menyalternativ i listrutan.

![](assets/favorite-menu.png)

I den här listan kan du snabbt lägga till personaliseringsobjektet i det aktuella uttrycket.

![](assets/favorite-list.png)

Om du inte längre vill se ett objekt i favoritlistan kan du ta bort det från Favoriter.

![](assets/favorite-remove.png)

## Instruktionsvideor{#video-perso}

Lär dig hur du använder sammanhangsbaserad händelseinformation från en resa för att personalisera ett meddelande.

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

Lär dig hur du använder sammanhangsbaserad händelseinformation från en resa för att personalisera ett meddelande.

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)
