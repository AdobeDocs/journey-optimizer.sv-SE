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
source-git-commit: 79c3c47eb6978f377bf4dc49f787e9a509aa3f61
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---


# Återförsök {#retries}

När ett e-postmeddelande misslyckas på grund av ett tillfälligt **Mjukt studs** eller **Ignorerat**-fel, utförs flera försök. Varje fel ökar en felräknare. När den här räknaren når gränsvärdet läggs adressen till i listan över spärrade adresser.

>[!NOTE]
>
>Läs mer om feltyperna i avsnittet [Leveransfel](../suppression-list.md#delivery-failures).

I standardkonfigurationen anges tröskelvärdet till tre fel:

* Vid det tredje felet som påträffades vid samma leverans ignoreras adressen.

* Om det finns olika leveranser och två fel inträffar med minst 24 timmars mellanrum, ökas felräknaren vid varje fel och adressen visas inte vid det tredje försöket.

Om en leverans lyckas efter ett nytt försök initieras adressräknaren på nytt.

Du kan ändra gränsvärdet med knappen **[!UICONTROL Edit]** på menyn **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL General]**.

![](../assets/retries-edition.png)

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