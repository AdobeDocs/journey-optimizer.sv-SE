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
source-git-commit: 6386a5ee5a0d1f221beab67f43636c599531736a
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Kom igång med aviseringar {#alerts}

Journey Optimizer utnyttjar Adobe Experience Platform varningsfunktioner. På så sätt kan du få åtkomst till systemvarningar via användargränssnittet. Du kan visa tillgängliga aviseringar och prenumerera på dem.

När en viss uppsättning villkor för dina åtgärder har nåtts (t.ex. ett eventuellt problem när systemet överskrider ett tröskelvärde), skickas varningsmeddelanden till alla användare i organisationen som har prenumererat på dem.

<!--These messages can repeat over a pre-defined time interval until the alert has been resolved.-->

Läs mer om varningar i Adobe Experience Platform [dokumentation](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html).

Mer information om hur du prenumererar på aviseringar och konfigurerar dem finns i detta [page](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html).

>[!AVAILABILITY]
>
>Vissa designändringar pågår för aviseringen &#39;Läs målutlösaren misslyckades&#39;. Den här aviseringen har pausats och har tillfälligt tagits bort från användargränssnittet. När dessa ändringar har släppts visas varningen igen och du kan prenumerera på den.

I den vänstra menyn, under **Administration**, klicka **Varningar**. Det finns en förkonfigurerad avisering för Journey Optimizer. Den här varningen varnar dig om en anpassad åtgärd misslyckas. Vi anser att det finns ett fel där det har förekommit mer än 1 procent av felen i en specifik anpassad åtgärd under de senaste fem minuterna. Detta utvärderas var 30:e sekund.

![](assets/alerts-custom-action.png)


<!--A pre-configured alert for Journey Optimizer is available. This alert will warn you if a read segment node has not processed any profile during the defined time frame.

![](assets/alerts1.png)-->

Om ett oväntat beteende inträffar skickas ett varningsmeddelande till de som prenumererar på varningen via e-post eller direkt inom Journey Optimizer, i det övre högra hörnet av gränssnittet, baserat på användarinställningarna.

När en varning har lösts får du ett meddelande om att den har lösts. Det här kan inträffa av två orsaker för den anpassade åtgärdsaviseringen:
* Under de senaste fem minuterna har det inte förekommit något fel för den anpassade åtgärden (eller fel under tröskelvärdet 1 %).
* Ingen profil har nått den anpassade åtgärden.

När [visa varningsregler i Adobe Experience Platform UI](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html)kan du prenumerera på varje regel separat. När du prenumererar på aviseringar via [I/O-händelsemeddelanden](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html)Men varningsreglerna är ordnade i olika prenumerationspaket. Prenumerationsnamnet för en I/O-händelse som motsvarar aviseringen om anpassad åtgärd är: &quot;Fel vid anpassad åtgärd på resan&quot;.

<!--The I/O event subscription name corresponding to the Read segment alert is: "Journey read segment Delays, Failures and Errors".-->

>[!WARNING]
>
>Dessa registreringar gäller endast för direktresor. Varningar utlöses inte för resor i testläge.

