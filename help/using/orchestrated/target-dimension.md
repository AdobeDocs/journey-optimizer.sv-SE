---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en måldimension
description: Lär dig mapp ett relationsschema till kundprofilen
exl-id: 2479c109-cd6f-407e-8a53-77e4477dc36f
version: Campaign Orchestration
source-git-commit: ac80d1cec351a3029c8b2bf862275ffe7fd5c86d
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---


# Konfigurera en måldimension {#configuration}

Med **[!UICONTROL Orchestrated Campaigns]** kan du utforma och leverera riktad kommunikation på entitetsnivå med hjälp av Adobe Experience Platform relationsschemafunktioner. Experience Platform använder scheman för att beskriva datastrukturen på ett konsekvent och återanvändbart sätt. När data hämtas till Experience Platform är de strukturerade enligt ett XDM-schema.

Även om segmentering för **[!UICONTROL Orchestrated Campaigns]** i första hand utförs på relationsscheman, sker den faktiska meddelandeleveransen alltid på nivån **Profil**.

När du konfigurerar mål definierar du två huvudaspekter:

* **Målscheman**

  Du anger vilka relationsscheman som är berättigade för målinriktning. Som standard används schemat `Recipient`, men du kan konfigurera alternativ som `Visitors`, `Customers` osv.

  >[!IMPORTANT]
  >
  > Målschemat måste ha en :1-relation med `Profile`-schemat. Du kan till exempel inte använda `Purchases` som målschema eftersom det vanligtvis representerar en 1:N-relation.

* **Profillänkning**

  Systemet måste förstå hur målschemat mappar till `Profile`-schemat. Detta uppnås genom ett delat identitetsfält - ett som finns både i målschemat och `Profile`-schemat och som har konfigurerats som ett identitetsnamnområde.

➡️ [Läs mer om relationsscheman i Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational#how-relational-schemas-differ-from-standard-xdm-schemas)

## Skapa en måldimension {#targeting-dimension}

Börja med att konfigurera kampanjsamordning genom att mappa ett relationsschema till kundprofilen.

1. Från **[!UICONTROL Administration]** öppnar du menyn **[!UICONTROL Configurations]** och väljer **[!UICONTROL Campaign Target Dimension]**.

   ![](assets/target-dimension-1.png)

1. Klicka på **[!UICONTROL Create]** för att börja skapa **[!UICONTROL Targeting dimension]**.

1. Välj det [tidigare konfigurerade &#x200B; &#x200B;](gs-schemas.md) i listrutan.

   Alla relationsscheman är synliga, men endast scheman med en direkt identitetsrelation till **profilen** kan väljas.

1. Välj den **[!UICONTROL Identity value]** som representerar den enhet som du vill ha som mål.

   I det här exemplet är kundprofilen länkad till flera prenumerationer, som vart och ett representeras av en unik `crmID` i `Recipient`-schemat. Genom att ange att **[!UICONTROL Target Dimension]** ska använda `Recipient`-schemat och dess `crmID`-identitet kan du skicka meddelanden på prenumerationsnivå i stället för till huvudkundprofilen, så att varje kontrakt eller rad får ett eget anpassat meddelande.

   [Läs mer i Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)

   ![](assets/target-dimension-2.png)

1. Klicka på **[!UICONTROL Save]** för att slutföra konfigurationen. Observera att när en **[!UICONTROL Target dimension]** väl har skapats kan den inte tas bort eller redigeras.

När du har konfigurerat **[!UICONTROL Target Dimension]** fortsätter du med att skapa och konfigurera **[!UICONTROL Channel Configuration]** och definierar motsvarande **[!UICONTROL Execution Details]**.