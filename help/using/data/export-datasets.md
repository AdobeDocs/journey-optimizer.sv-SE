---
solution: Journey Optimizer
product: journey optimizer
title: Exportera datauppsättningar till molnlagringsplatser
description: Lär dig hur du exporterar datauppsättningar med Adobe Experience Platform molnlagringsmål.
role: User
level: Beginner
badge: label="Beta" type="Informative"
keywords: plattform, datasjön, skapa, sjö, datamängder, profil
exl-id: 66b5c691-ddc4-4e9b-9386-2ce6c307451c
source-git-commit: c823d1a02ca9d24fc13eaeaba2b688249e61f767
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---

# Exportera datauppsättningar till molnlagringsplatser {#export-datasets}

>[!AVAILABILITY]
>
>Exportfunktionen för datauppsättningar är för närvarande i betaversion och tillgänglig för alla Adobe Journey Optimizer-användare. Kontakta din Adobe-representant om du vill få åtkomst till mål om du inte redan har åtkomst.

Med Journey Optimizer kan du upprätta en direktanslutning till molnlagringsplatser för att exportera innehållet i dina datauppsättningar.

Genom att exportera dina data regelbundet kan du se till att du har en fullständig och aktuell registrering av dina kundinteraktioner, använda informationen i rapporterings- eller analyssyfte och upprätthålla efterlevnad av juridiska krav.

## Tillgängliga molnlagringsdestinationer {#destinations}

Du kan exportera datauppsättningar till sex molnlagringsmål som är tillgängliga från **[!UICONTROL Destinations]** -menyn på **[!UICONTROL Catalog]** -fliken.

![](assets/dataset-export-setup.png)

>[!AVAILABILITY]
>
>Dessa destinationer är alla tillgängliga i betaversionen och kan komma att ändras.

Mer information om respektive mål finns i Adobe Experience Platform-dokumentationen:

* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html)
* [Azure Data Lake Gen 2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html)
* [Datallandningszon](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html)
* [Google Cloud-lagring](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html)

## Förutsättningar {#prerequisites}

Kontrollera följande krav innan du börjar exportera datauppsättningarna:

* Om du vill exportera datauppsättningar behöver du **Hantera mål**, **Visa mål**, **Aktivera destinationer** och **Hantera och aktivera datauppsättningsmål** [behörigheter för åtkomstkontroll](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#permissions). Läs [åtkomstkontroll - översikt](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/overview.html) eller kontakta produktadministratören för att få de behörigheter som krävs.

* Den här funktionen stöder endast export av första generationens data, dvs. rådata enligt definitionen i [Real-time Customer Data Platform produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/real-time-customer-data-platform-b2c-edition-prime-and-ultimate-packages.html). Kontrollera att datauppsättningen som du vill exportera inte innehåller andra generationens data.

## De viktigaste stegen för att exportera datauppsättningar {#main-steps}

De viktigaste stegen för att exportera en datauppsättning till en molnlagringsplats är följande:

![](assets/dataset-export-process.png)

Detaljerad information om varje steg finns i Adobe Experience Platform dokumentation: [Exportera datauppsättningar till molnlagringsmål](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en).

1. **Konfigurera molnlagringsmålet**. Om du inte redan har gjort det ansluter du till ett molnlagringsmål från målkatalogen. [Lär dig hur du skapar en ny målanslutning](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en#setup)

   <!--![](assets/dataset-export-setup.png)-->

1. **Välj molnlagringsmål** där du vill exportera datauppsättningarna. Klicka på knappen **[!UICONTROL Export datasets]** på det önskade kortet och välj den anslutning som ska användas.

   <!--![](assets/dataset-export-destination.png)-->

   >[!NOTE]
   >
   >Om du använder Adobe Journey Optimizer tillsammans med kundprofiler i realtid, kommer målkorten att visa en aktiveringsknapp, som gör att du kan både exportera datauppsättningar och aktivera segment för den här destinationen, beroende på vilka behörigheter du har aktiverat.

1. **Välj datauppsättning(ar)** som du vill exportera till det valda målet.

   <!--![](assets/dataset-export-dataset-selection.png)-->

1. **Schemalägg exporten** av din datauppsättning. Ange när exporten ska börja och med vilken frekvens den ska ske.

   <!--![](assets/dataset-export-schedule.png)-->

1. **Granska och bekräfta exporten** genom att kontrollera sammanfattningen som visas i slutet av konfigurationen.

   <!--![](assets/dataset-export-review.png)-->

När exporten är klar, lagras innehållet i datauppsättningen på din molnlagringsplats enligt det schema du har konfigurerat. [Lär dig hur du verifierar lyckad datauppsättningsexport](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html#verify)
