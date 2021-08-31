---
title: Återförsök
description: Lär dig hur nya försök utförs innan du skickar en adress till listan över inaktiveringar
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
source-git-commit: b18f8c468157988be9cca44795b46f6fb4a0208e
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# Återförsök {#retries}

När ett e-postmeddelande misslyckas på grund av ett tillfälligt **fel av typen Mjuk studs** utförs flera försök. Varje fel ökar en felräknare. När den här räknaren når gränsvärdet läggs adressen till i listan över spärrade adresser.

>[!NOTE]
>
>Läs mer om feltyperna i avsnittet [Leveransfel](../suppression-list.md#delivery-failures).

I standardkonfigurationen är tröskelvärdet 5 fel.

* Adressen undertrycks vid det femte påträffade felet inom [tidsperioden](#retry-duration) för samma leverans.

* Om det finns olika leveranser och två fel inträffar med minst 24 timmars mellanrum, ökas felräknaren vid varje fel och adressen visas inte vid det femte försöket.

Om en leverans lyckas efter ett nytt försök initieras adressräknaren på nytt.

Om standardvärdet 5 inte passar dina behov kan du ändra feltröskeln enligt stegen nedan.

1. Gå till **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL Suppression list]**.

1. Markera knappen **[!UICONTROL Edit suppression rules]**.

   ![](../assets/suppression-list-edit-retries.png)

1. Redigera det tillåtna antalet på varandra följande mjuka studsar efter dina behov.

   ![](../assets/suppression-list-edit-soft-bounces.png)

   Du måste ange ett heltalsvärde mellan 1 och 20, vilket innebär att det minsta antalet försök är 1 och det högsta antalet är 20.

   >[!CAUTION]
   >
   >Värden över 10 kan orsaka problem med leveransens anseende, liksom IP-begränsning eller blockeringslistning från Internet-leverantörer. [Läs mer om leverans](../deliverability.md)

<!--![](../assets/retries-edition.png)-->

<!--The minimum delay between retries and the maximum number of retries to be performed are based on how well an IP is performing, both historically and currently, at a given domain.-->

## Tidsperiod för återförsök {#retry-duration}

**Tidsperioden för nytt försök** är den tidsram i vilken ett e-postmeddelande om leveransen som påträffade ett tillfälligt fel eller ett mjukt avhopp kommer att provas igen.

Som standard kommer nya försök att utföras i **3,5 dagar** (eller **84 timmar**) från den tidpunkt då meddelandet lades till i e-postkön.

För att vara säker på att försök inte utförs igen när de inte längre behövs kan du ändra den här inställningen efter dina behov när du skapar eller redigerar en [meddelandeförinställning](message-presets.md) som gäller för e-postkanalen.

Du kan t.ex. ange återförsöksperioden till 24 timmar för ett transaktionsmejl som relaterar till lösenordsåterställning och som innehåller en länk som bara är giltig för en dag. På samma sätt kan du vid midnatt-försäljning definiera en återförsöksperiod på 6 timmar.

>[!NOTE]
>
>Återförsöksperioden får inte vara längre än 84 timmar. Den minsta återförsöksperioden är 6 timmar för marknadsföringsmeddelanden och 10 minuter för transaktionsmeddelanden.

Lär dig hur du justerar parametrarna för e-poståterförsök när du skapar en meddelandeförinställning i [det här avsnittet](message-presets.md#create-message-preset).

<!--After 3.5 days, any message in the retry queue will be removed from the queue and sent back as a bounce.-->

<!--Once a message has been in the retry queue for a maximum of 3.5 days and has failed to deliver, it will time out and its status will be updated to Failed??-->