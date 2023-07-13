---
solution: Journey Optimizer
product: journey optimizer
title: Larm
description: Lär dig hur du hanterar aviseringar
feature: Alerts
topic: Administration
role: Admin
level: Intermediate
exl-id: 0855ca5b-c7af-41c4-ad51-bed820ae5ecf
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Kom igång med aviseringar {#alerts}

Journey Optimizer utnyttjar Adobe Experience Platform varningsfunktioner. På så sätt kan du få åtkomst till systemvarningar via användargränssnittet. Du kan visa tillgängliga aviseringar och prenumerera på dem.

När en viss uppsättning villkor för dina åtgärder har nåtts (t.ex. ett eventuellt problem när systemet överskrider ett tröskelvärde), skickas varningsmeddelanden till alla användare i organisationen som har prenumererat på dem. Dessa meddelanden kan upprepas under ett fördefinierat tidsintervall tills varningen har lösts.

Läs mer om varningar i Adobe Experience Platform [dokumentation](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html).
Mer information om hur du prenumererar på aviseringar och konfigurerar dem finns i detta [page](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html).

>[!AVAILABILITY]
>
>Vissa designändringar pågår för aviseringen&quot;Läs publikutlösaren misslyckades&quot;. Den här aviseringen har pausats och har tillfälligt tagits bort från användargränssnittet. När dessa ändringar har släppts visas varningen igen och du kan prenumerera på den.
>

I den vänstra menyn, under **Administration**, klicka **Varningar**.

<!--A pre-configured alert for Journey Optimizer is available. This alert will warn you if a read segment node has not processed any profile during the defined time frame.

![](assets/alerts1.png)-->

Om ett oväntat beteende inträffar skickas ett varningsmeddelande till de som prenumererar på varningen via e-post i det övre högra hörnet av gränssnittet.

<!--![](assets/alerts2.png)-->


När [visa varningsregler i Adobe Experience Platform UI](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html)kan du prenumerera på varje regel separat. När du prenumererar på aviseringar via [I/O-händelsemeddelanden](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html)Men varningsreglerna är ordnade i olika prenumerationspaket.

<!--The I/O event subscription name corresponding to the Read segment alert is: "Journey read segment Delays, Failures and Errors".

>[!WARNING]
>
>These alerts apply only to live journeys. Alerts will not be triggered for journeys in test mode.-->
