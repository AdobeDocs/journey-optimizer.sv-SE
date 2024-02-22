---
solution: Journey Optimizer
product: journey optimizer
title: Försök igen
description: Lär dig hur nya försök utförs innan du skickar en adress till listan över inaktiveringar
feature: Deliverability, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: återförsök, studsa, mjuk, optimering, fel
exl-id: 05564a99-da50-4837-8dfb-bb1d3e0f1097
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---

# Försök igen {#retries}

När ett e-postmeddelande misslyckas på grund av ett tillfälligt **Mjuk studsa** fel för en viss adress, flera försök utförs. Varje fel ökar en felräknare. När den här räknaren når gränsvärdet läggs e-postadressen till i listan över spärrade adresser.

>[!NOTE]
>
>Läs mer om olika typer av fel i [Leveransfel](../reports/suppression-list.md#delivery-failures) -avsnitt.

I standardkonfigurationen är tröskelvärdet 5 fel.

* För samma leverans påträffades fel den femte i [återförsökstid](#retry-duration), är adressen undertryckt.

* Om det finns olika leveranser och två fel inträffar med minst 24 timmars mellanrum, ökas felräknaren vid varje fel och adressen visas inte vid det femte försöket. Fel ackumuleras för varje adress.

Om en leverans lyckas efter ett nytt försök initieras adressräknaren på nytt.

Exempel:

* Du skickar ett e-postmeddelande på måndag med en återförsöksperiod på 24 timmar. Den emma.jones@mail.com adressen levereras inte. Ett nytt försök att skicka e-postmeddelandet görs upp till tre gånger och försök att nå den 24 timmar långa återförsöksperioden avbryts.

* Du skickar ett e-postmeddelande till på onsdag. emma.jones@mail.com, som redan har ett antal tre fel, har också angetts som mål och levereras inte - två gånger. Ytterligare två fel räknas.

Under förutsättning att inga andra leveransförsök gjorts och att de båda meddelandena lyckades, läggs emma.jones@mail.com till i listan över inaktiveringar med tanke på den kumulativa effekten av 3 + 2-fel.

## Försök igen med tröskelversionen {#edit-retry-threshold}

>[!CONTEXTUALHELP]
>id="ajo_admin_suppression_list_bounces"
>title="Uppdatera tröskelvärdet för återförsök"
>abstract="Om standardvärdet inte passar dina behov kan du ändra det tillåtna antalet på varandra följande mjuka studsar. När räknaren för nya försök når feltröskeln för en viss e-postadress läggs den här adressen till i listan över spärrade adresser."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/deliverability/suppression-list.html" text="Förstå listan över undantag"

Om standardvärdet 5 inte passar dina behov kan du ändra feltröskeln enligt stegen nedan.

1. Gå till **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL Suppression list]**.

1. Markera knappen **[!UICONTROL Edit suppression rules]**.

   ![](assets/suppression-list-edit-retries.png)

1. Redigera det tillåtna antalet på varandra följande mjuka studsar efter dina behov.

   ![](assets/suppression-list-edit-soft-bounces.png)

   Du måste ange ett heltalsvärde mellan 1 och 20, vilket innebär att det minsta antalet försök är 1 och det högsta antalet är 20.

   >[!CAUTION]
   >
   >Värden över 10 kan orsaka problem med leveransens anseende, liksom IP-begränsning eller blockeringslistning från Internet-leverantörer. [Läs mer om leverans](../reports/deliverability.md)

## Tidsperiod för återförsök {#retry-duration}

The **återförsökstid** är den tidsram inom vilken ett e-postmeddelande om leveransen som påträffade ett tillfälligt fel eller en mjuk avhoppning kommer att skickas igen.

Som standard utförs återförsök för **3,5 dagar** (eller **84 timmar**) när meddelandet lades till i e-postkön.

För att vara säker på att försök inte utförs igen när de inte längre behövs kan du ändra den här inställningen efter behov när du skapar eller redigerar en [kanalyta](channel-surfaces.md) (t.ex. meddelandeförinställning) som gäller för e-postkanalen.

Du kan t.ex. ange återförsöksperioden till 24 timmar för ett transaktionsmejl som relaterar till lösenordsåterställning och som innehåller en länk som bara är giltig för en dag. På samma sätt kan du vid en midnatt-försäljning definiera en återförsöksperiod på 6 timmar.

>[!NOTE]
>
>Återförsöksperioden får inte vara längre än 84 timmar. Den minsta återförsöksperioden är 6 timmar för marknadsföringsmeddelanden och 10 minuter för transaktionsmeddelanden.

Lär dig hur du justerar parametrarna för återförsök i e-postmeddelanden när du skapar en kanalyta i [det här avsnittet](../email/email-settings.md#email-retry).

