---
title: Anpassa innehåll i Journey Optimizer
description: Kom igång med personalisering
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Beginner
source-git-commit: adb915a2013d1d1bf17ed5efb7ac4eb9c655c501
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 2%

---

# Kom igång med personalisering{#add-personalization}

Upptäck [!DNL Adobe Journey Optimizer]-personaliseringsfunktioner för att anpassa dina meddelanden till varje specifik mottagare genom att utnyttja de data och den information du har om honom/henne. Det kan vara hans förnamn, intressen, var han bor, vad han köpte och mycket annat.

[!DNL :arrow_forward:] [Lär dig hur du anpassar ett meddelande i dessa videofilmer](#video-perso)

[!DNL Journey Optimizer] använder en  **** inlineenkel personaliseringssyntax baserad på Handlebars, som gör att du kan skapa uttryck med innehåll omslutet av dubbla klammerparenteser **{{}}**. Du kan lägga till flera uttryck i samma innehåll eller fält utan begränsningar. Läs mer i [Personaliseringssyntax](personalization-syntax.md).

Anpassningen baseras på profildata som hanteras av schemat **XDM Individual Profile** som definieras i Adobe Experience Platform. Mer information finns i [dokumentationen för Adobe Experience Platform datamodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv).

>[!CAUTION]
>Schemat **XDM Individual Profile** är det enda schema som du kan använda för att anpassa innehåll i [!DNL Journey Optimizer].

**Exempel:**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`

* `Hello {{profile.person.name.fullName}}`

När du bearbetar meddelandet (e-post och push) ersätter Journey Optimizer uttrycket med data som finns i databasen för Experience Cloud Platform:  `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` blir&quot;Hello John Doe&quot;.


## Anpassningssammanhang{#personalization-areas}

Innehållet i och visningen av meddelanden som levereras av [!DNL Journey Optimizer] kan anpassas på flera olika sätt.

I alla fält med redigeringsikonen kan du öppna redigeringsprogrammet för anpassning (även kallat uttrycksredigeraren) och definiera personalisering.

![](assets/perso_icon.png)

### Anpassa e-postmeddelanden

När du skapar ett e-postmeddelande kan du lägga till anpassning i fältet **Ämne** för e-post i meddelandet.

![](assets/perso_subject.png)

I e-postdesignern kan du anpassa innehållet:

* I **meddelandet**: Klicka i ett textblock, klicka på ikonen **Anpassa** i det sammanhangsberoende verktygsfältet och välj **Infoga personalisering** fält. Mer information om gränssnittet för e-postdesignern finns i det här [avsnittet](../design-emails.md).

   ![](assets/perso_insert.png)

* För en **länk**: Om du vill markera text eller bild i ett textblock klickar du på ikonen **Infoga länk** i det sammanhangsberoende verktygsfältet. I fönstret kan du lägga till ett anpassningsblock genom att klicka på ikonen **Lägg till personalisering**.

   ![](assets/perso_link.png)

I båda fallen får du tillgång till personaliseringsredigeraren.

![](assets/perso_ee.png)


### Anpassa push-meddelanden

Du kan också anpassa dina **push-meddelanden** i följande fält:

* **Titel**
* **Brödtext**
* **Eget ljud**
* **Badges**
* **Anpassade data**

![](assets/perso_push.png)

Läs mer om konfigurationen av push-meddelanden i [det här avsnittet](../push-gs.md).

## Använda uttrycksredigeraren

Uttrycksredigeraren är navet i personaliseringen i [!DNL Journey Optimizer].

Det finns i alla sammanhang där du behöver definiera personalisering som e-post, push och erbjudanden.

I gränssnittet för uttrycksredigeraren väljer, ordnar, anpassar och validerar du alla data för att skapa en anpassad personalisering för ditt innehåll.

![](assets/perso_ee1.png)

I den vänstra delen av skärmen visas en domänväljare där du kan välja källa för personalisering. Tillgängliga källor är:

* **Profil** : visar alla referenser som är associerade med profilschemat som beskrivs i dokumentationen [ för ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)Adobe Experience Platform datamodell (XDM).
* **Segmentmedlemskap** : listar alla segment som har skapats i Adobe Experience Platform Segmenteringstjänst. Mer information om segmentering finns [här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).
* **Erbjudanden** : visar alla erbjudanden som är kopplade till en viss placering. Välj placering och infoga sedan erbjudandena i innehållet. En fullständig dokumentation om hur du hanterar erbjudanden finns i [det här avsnittet](../deliver-personalized-offers.md).
* **Kontext** : När  **** Meddelandeaktiviteten används i en resa är sammanhangsberoende resefält tillgängliga på den här menyn. Läs mer i [det här avsnittet](personalization-use-case.md).
* **Hjälpfunktioner** : visar alla hjälpfunktioner som är tillgängliga för att utföra dataåtgärder, t.ex. beräkningar, dataformatering eller konverteringar, villkor och manipulera dem i personaliseringssammanhang. Läs mer i [det här avsnittet](functions/functions.md).

Vid markering läggs referensen till i redigeraren.

>[!NOTE]
>
>Informationsikonen bredvid ikonen + öppnar ett verktygstips med mer information om varje variabel.

I följande exempel kan du välja de profiler som har sin födelsedag i dag och sedan slutföra anpassningen genom att infoga ett specifikt erbjudande som motsvarar den här dagen.

![](assets/perso_ee2.png)

## Instruktionsvideor{#video-perso}

Lär dig hur du använder sammanhangsbaserad händelseinformation från en resa för att personalisera ett meddelande.

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

Lär dig hur du använder sammanhangsbaserad händelseinformation från en resa för att personalisera ett meddelande.

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)
