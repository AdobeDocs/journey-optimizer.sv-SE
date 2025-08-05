---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en måldimension
description: Lär dig mapp ett relationsschema till kundprofilen
exl-id: 2479c109-cd6f-407e-8a53-77e4477dc36f
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---


# Konfigurera en måldimension {#configuration}

Med **[!UICONTROL Orchestrated Campaigns]** kan du utforma och leverera riktad kommunikation på entitetsnivå med hjälp av Adobe Experience Platform relationsschemafunktioner.

Även om segmentering för **[!UICONTROL Orchestrated Campaigns]** i första hand utförs på relationsscheman, sker den faktiska meddelandeleveransen alltid på nivån **Profil**.

När du konfigurerar mål definierar du två huvudaspekter:

* **Målscheman**

  Du anger vilka relationsscheman som är berättigade för målinriktning. Som standard används schemat `Recipient`, men du kan konfigurera alternativ som `Visitors`, `Customers` osv.

  >[!IMPORTANT]
  >
  > Målschemat måste ha en :1-relation med `Profile`-schemat. Du kan till exempel inte använda `Purchases` som målschema eftersom det vanligtvis representerar en 1:N-relation.

* **Profillänkning**

  Systemet måste förstå hur målschemat mappar till `Profile`. Detta uppnås genom ett delat identitetsfält - ett som finns både i målschemat och `Profile`-schemat och som har konfigurerats som ett identitetsnamnområde.

## Skapa en måldimension {#targeting-dimension}

Börja med att konfigurera kampanjsamordning genom att mappa ett relationsschema till kundprofilen.

1. Från **[!UICONTROL Administration]** öppnar du menyn **[!UICONTROL Configurations]** och väljer **[!UICONTROL Campaign Target Dimension]**.

   ![](assets/target-dimension-1.png)

1. Klicka på **[!UICONTROL Create]** för att börja skapa **[!UICONTROL Targeting dimension]**.

1. Välj det [tidigare konfigurerade &#x200B; ](gs-schemas.md) i listrutan.

   Alla relationsscheman är synliga, men endast scheman med en direkt identitetsrelation till **profilen** kan väljas.

1. Välj den **[!UICONTROL Identity value]** som representerar den enhet som du vill ha som mål.

   I det här exemplet är kundprofilen länkad till flera prenumerationer, som vart och ett representeras av en unik `crmID` i `Recipient`-schemat. Genom att ange att **[!UICONTROL Target Dimension]** ska använda `Recipient`-schemat och dess `crmID`-identitet kan du skicka meddelanden på prenumerationsnivå i stället för till huvudkundprofilen, så att varje kontrakt eller rad får ett eget anpassat meddelande.

   [Läs mer i Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)

   ![](assets/target-dimension-2.png)

1. Klicka på **[!UICONTROL Save]** för att slutföra konfigurationen. Observera att när en **[!UICONTROL Target dimension]** väl har skapats kan den inte tas bort eller redigeras.

När du har konfigurerat **[!UICONTROL Target Dimension]** fortsätter du med att skapa och konfigurera **[!UICONTROL Channel Configuration]** och definierar motsvarande **[!UICONTROL Execution Details]**.

## Konfigurera kanalkonfigurationen {#channel-configuration}

När du har konfigurerat din **[!UICONTROL Target Dimension]** måste du konfigurera din e-post eller ditt SMS **[!UICONTROL Channel Configuration]** och definiera rätt **[!UICONTROL Execution Details]**. Detta gör att du kan definiera :

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
