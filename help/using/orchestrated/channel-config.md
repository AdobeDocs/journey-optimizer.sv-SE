---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera kanalkonfigurationen
description: Lär dig konfigurera kanalkonfigurationen
version: Campaign Orchestration
source-git-commit: 0b92d0e806c47b0d87ba53b7c7f1d56ee4453abb
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Konfigurera kanalkonfigurationen {#channel-configuration}

När du har konfigurerat [Target Dimension](target-dimension.md) måste du konfigurera **[!UICONTROL Channel Configuration]** och definiera rätt **[!UICONTROL Execution Details]**. Detta gör att du kan definiera :

* **Nivån för meddelandeleverans**: t.ex. ett meddelande per mottagare, t.ex. ett e-postmeddelande per person.

* **Körningsadressen**: det specifika kontaktfält som ska användas för att skicka, till exempel en e-postadress eller ett telefonnummer.

Så här konfigurerar du kanalkonfigurationen:

1. Börja med att skapa och konfigurera **[!UICONTROL Channel configuration]**.

   Du kan även uppdatera en befintlig **[!UICONTROL Channel configuration]**.

   ➡️ [Följ stegen som beskrivs på den här sidan](../email/surface-personalization.md)

1. Gå till fliken **[!UICONTROL Execution details]** från avsnittet **[!UICONTROL Channel configuration]** i **[!UICONTROL Orchestrated campaigns]**.

   ![](assets/target-dimension-3.png)

1. Klicka på **[!UICONTROL Enabled]** för att göra den kompatibel med orkestrerade kampanjer.

1. Välj leveranssätt:

   * **[!UICONTROL Target Dimension]**: skicka till den primära entiteten, t.ex. mottagare.

   * **[!UICONTROL Target + Secondary Dimension]**: skicka med både primära och sekundära entiteter, t.ex. mottagare + kontrakt.

1. Välj i listrutan din [tidigare skapade Target Dimension](#targeting-dimension).

   ![](assets/target-dimension-4.png)

1. Om du valde **[!UICONTROL Target + Secondary Dimension]** som leveransmetod, väljer du **[!UICONTROL Secondary Dimension]** för att definiera kontexten för meddelandeleverans.

1. Under avsnittet **[!UICONTROL Execution Address]** väljer du vilken **[!UICONTROL Source]** som ska användas för att hämta leveransadressen, till exempel e-postadressen eller telefonnumret:

   * **[!UICONTROL Profile]**: Välj det här alternativet om leveransadressen, t.ex. e-postadressen, lagras direkt i huvudkundprofilen.

     Användbart när du skickar meddelanden till huvudkunden, inte till en specifik associerad enhet.

   * **[!UICONTROL Target Dimension]**: Välj det här alternativet om leveransadressen lagras i den primära entiteten, t.ex. en mottagare.

     Användbart när varje mottagare har en egen leveransadress, till exempel en annan e-postadress eller ett annat telefonnummer.

   * **[!UICONTROL Secondary Dimension]**: När du använder **[!UICONTROL Target + Secondary Dimension]** som leveransmetod väljer du relevant **[!UICONTROL Secondary Dimension]** som du tidigare konfigurerat.

     Om den sekundära dimensionen till exempel representerar en bokning eller prenumeration kan körningsadressen, till exempel ett e-postmeddelande, hämtas från den nivån. Detta är användbart om profilerna använder olika kontaktuppgifter när de bokar eller prenumererar på en tjänst.

1. I fältet **[!UICONTROL Delivery address]** klickar du på ![redigeringsikonen](assets/do-not-localize/edit.svg) för att välja det specifika fält som ska användas för meddelandeleveransen.

   ![](assets/target-dimension-4.png)

1. När du har konfigurerat klickar du på **[!UICONTROL Submit]**.

Din kanal är nu klar att användas med **samordnade kampanjer**, och meddelanden levereras enligt den valda måldimensionen.
