---
title: Anpassningssammanhang i Journey Optimizer
description: Lär dig i vilka sammanhang du kan lägga till personalisering
source-git-commit: 741fe2b614e3ded57c4a7ecd9b7333bdd99ab359
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 2%

---

# Personaliseringskontext och -verktyg {#personalization-areas}

![](../assets/do-not-localize/badge.png)

Innehållet i och visningen av meddelanden från Journey Optimizer kan personaliseras på flera olika sätt.

Alla fält som är kopplade till redigeringsikonen kan öppna redigeringsprogrammet för anpassning och ta emot anpassat innehåll.

![](assets/perso_icon.png)

## Anpassa e-postmeddelanden

När du skapar ett e-postmeddelande kan du lägga till anpassning i fältet **Ämne** för e-post i meddelandet.

![](assets/perso_subject.png)

I e-postdesignern kan du anpassa innehållet:

* I **meddelandet**: Klicka i ett textblock, klicka på ikonen **Anpassa** i det sammanhangsberoende verktygsfältet och välj **Infoga personalisering** fält. Mer information om gränssnittet för e-postdesignern finns i det här [avsnittet](../design-emails.md).

   ![](assets/perso_insert.png)

* För en **länk**: Om du vill markera text eller bild i ett textblock klickar du på ikonen **Infoga länk** i det sammanhangsberoende verktygsfältet. I fönstret kan du lägga till ett anpassningsblock genom att klicka på ikonen **Lägg till personalisering**.

   ![](assets/perso_link.png)

## Anpassa push-meddelanden

Du kan också anpassa dina **push-meddelanden** i följande fält:

* **Titel**
* **Brödtext**
* **Eget ljud**
* **Badges**
* **Anpassade data**

![](assets/perso_push.png)

Läs mer om konfigurationen av push-meddelanden i [det här avsnittet](../create-push.md).

## Använda uttrycksredigeraren

Uttrycksredigeraren är navet i personaliseringen i Journey Optimizer.

Det finns i alla sammanhang där du behöver definiera personalisering som e-post, push och erbjudanden.

I gränssnittet för uttrycksredigeraren väljer, ordnar, anpassar och validerar du alla data för att skapa en anpassad personalisering för ditt innehåll.

![](assets/perso_ee1.png)

I den vänstra delen av skärmen visas en domänväljare där du kan välja källa för personalisering.

* **Profil** : visar alla referenser som är associerade med profilschemat som beskrivs i dokumentationen [ för ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv)Adobe Experience Platform datamodell (XDM).
* **Segmentmedlemskap** : listar alla segment som har skapats i Adobe Experience Platform Segmenteringstjänst. Mer information om segmentering finns [här](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en)
* **Erbjudanden** : visar alla erbjudanden som är kopplade till en viss placering. Välj placering och infoga sedan erbjudandena i innehållet. En fullständig dokumentation om hur du hanterar erbjudanden finns i [det här avsnittet](../deliver-personalized-offers.md)
* **Kontext** : När  **** Meddelandeaktiviteten används i en resa är sammanhangsberoende resefält tillgängliga på den här menyn. Se [det här avsnittet](personalization-use-case.md)
* **Hjälpfunktioner** : visar alla hjälpfunktioner som är tillgängliga för att utföra dataåtgärder, t.ex. beräkningar, dataformatering eller konverteringar, villkor och manipulera dem i personaliseringssammanhang. [Läs mer](functions/functions.md)



Vid markering läggs referensen till i redigeraren.

>[!NOTE]
>
>Informationsikonen bredvid ikonen + öppnar ett verktygstips med mer information om varje variabel.

I följande exempel kan du välja de profiler som har sin födelsedag i dag och sedan slutföra anpassningen genom att infoga ett specifikt erbjudande som motsvarar den här dagen.

![](assets/perso_ee2.png)




