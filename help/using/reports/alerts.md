---
solution: Journey Optimizer
product: journey optimizer
title: Larm
description: Lär dig hur du hanterar aviseringar
feature: Alerts
topic: Administration
role: Admin
level: Intermediate
source-git-commit: e7431d1b69e460471b01439c9bd2577fd69944ed
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Kom igång med aviseringar {#alerts}

Journey Optimizer utnyttjar Adobe Experience Platform varningsfunktioner. På så sätt kan du få åtkomst till systemvarningar via användargränssnittet. Du kan visa tillgängliga aviseringar och prenumerera på dem. När en viss uppsättning villkor för dina åtgärder har nåtts (t.ex. ett eventuellt problem när systemet överskrider ett tröskelvärde), skickas varningsmeddelanden till alla användare i organisationen som har prenumererat på dem. Dessa meddelanden kan upprepas under ett fördefinierat tidsintervall tills varningen har lösts.

Läs mer om varningar i Adobe Experience Platform [dokumentation](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html).
Mer information om hur du prenumererar på aviseringar och konfigurerar dem finns i detta [page](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html).

I den vänstra menyn, under **Administration**, klicka **Varningar**. Det finns en förkonfigurerad avisering för Journey Optimizer. Den här varningen varnar dig om en nod i ett lässegment inte har bearbetat någon profil under den definierade tidsramen.

![](assets/alerts1.png)

Om ett sådant oväntat beteende inträffar, skickas ett varningsmeddelande till de som prenumererar på varningen via e-post i det övre högra hörnet av gränssnittet.

![](assets/alerts2.png)

När [visa varningsregler i plattformsgränssnittet](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html)kan du prenumerera på varje regel separat. När du prenumererar på aviseringar via [I/O-händelsemeddelanden](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html)Men varningsreglerna är ordnade i olika prenumerationspaket. Prenumerationsnamnet för I/O-händelsen som motsvarar varningen för Läs segment är: &quot;Besök lässegmentet Fördröjningar, Fel och fel&quot;.

>[!WARNING]
>
>Dessa registreringar gäller endast för direktresor. Varningar utlöses inte för resor i testläge.