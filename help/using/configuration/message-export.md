---
solution: Journey Optimizer
product: journey optimizer
title: Meddelandeexport i Journey Optimizer
description: Lär dig hur du exporterar meddelanden
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: export, meddelanden, HIPAA, e-post, SMS, konfiguration
exl-id: 7b50c933-9738-4b1b-acae-08f0a8d41dab
source-git-commit: ab0f100d53cb987919eb134442bf05e64c30719a
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 1%

---

# Exportera meddelandeinnehåll {#message-export}

>[!CONTEXTUALHELP]
>id="ajo_admin_msg_export"
>title="Behåll och exportera skickat innehåll"
>abstract="Om du väljer det här alternativet kan du skriva innehållet i skickade e-postmeddelanden eller SMS-meddelanden med den här konfigurationen till en [!DNL Experience Platform]-datauppsättning. Posterna sparas i 7 kalenderdagar efter intag, under vilka du kan exportera dem till ditt eget lagringsutrymme."

>[!AVAILABILITY]
>
>Den här funktionen är bara tillgänglig för e-post- och SMS-kanalen, för organisationer som har köpt tillägget för meddelandeexport. Kontakta din Adobe-representant om du vill veta mer.

Med **Meddelandeexport** kan du överföra skickat e-post- och SMS-meddelandeinnehåll från [!DNL Journey Optimizer] till ditt eget lagringsutrymme via [!DNL Adobe Experience Platform] mål, vilket gör att du kan leverera data från [!DNL Experience Platform] till externa slutpunkter. [Läs mer](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home){target="_blank"}

Med den här funktionen skrivs innehållet i e-post- och SMS-meddelanden som skickas via [!DNL Journey Optimizer] och som har markerats för export till [!DNL Experience Platform] **AJO Message Export DataSet**. [Läs mer om datauppsättningar](../data/get-started-datasets.md)

Posterna sparas sedan i datauppsättningen i sju kalenderdagar från intag, under vilka du kan exportera dem till valfritt externt system.

## Guardrails

* Den här funktionen stöder bara kanalerna **Email** och **SMS**.
* Poster i datauppsättningen för export av AJO-meddelanden behålls **i sju kalenderdagar från att användaren har fått det**.
* Backfill stöds inte för meddelanden som skickas innan meddelandeexport aktiverades enligt beskrivningen nedan.

## Aktivera meddelandeexport {#enable-message-export}

Startprocessen för funktionen för meddelandeexport består av två steg:

1. [Konfigurera exportdataflödet](#set-up-export-dataflow) i [!DNL Experience Platform];
1. [Aktivera meddelandeexport](#config-message-export) vid kanalkonfigurationen i [!DNL Journey Optimizer].

>[!WARNING]
>
>Endast nya poster visas när du har aktiverat export och skickat meddelanden. Det går inte att säkerhetskopiera innehåll innan exportprocessen konfigureras och alternativet Exportera meddelande aktiveras.

### Ställ in exportdataflöde {#set-up-export-dataflow}

Innan du kan exportera dina data måste du konfigurera exportprocessen genom att definiera [!DNL Experience Platform]-målet och datauppsättningen som ska användas. Följ stegen nedan.

>[!NOTE]
>
>Den här inställningen måste konfigureras för varje sandlåda.

1. Välj en [måltyp](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/destination-types){target="_blank"} för Experience Platform. En lista över tillgängliga målplattformar som kan ta emot data finns tillgänglig på [den här sidan](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/overview){target="_blank"}.

1. I [!DNL Experience Platform] konfigurerar du målet genom att definiera autentiseringsuppgifter, bucket/container, sökvägsprefix och säkerhetsalternativ. [Lär dig hur](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets){target="_blank"}

1. Skapa ett datauppsättningsexportflöde med följande data:

   * Source-datauppsättning: välj **AJO Message Export DataSet**.
   * Filformat: välj JSON eller Parquet (välj ett som baseras på de underordnade verktygen).
   * Schema: kontrollera att det körs inom 7-dagars kvarhållningsfönstret.

### Aktivera meddelandeexport i kanalkonfigurationen {#config-message-export}

Om du vill använda meddelandeexport på dina kampanjer och resor måste du aktivera det dedikerade alternativet på kanalkonfigurationsnivån. Följ stegen nedan.

1. I [!DNL Journey Optimizer] redigerar eller skapar du önskad e-post- eller SMS [kanalkonfiguration](channel-surfaces.md#create-channel-surface).

1. Välj alternativet **[!UICONTROL Enable Message Export]**.

   ![](assets/config-message-export.png)

1. Spara ändringarna och skicka kanalkonfigurationen.

När du har skickat meddelanden via kampanjer eller resor med den här kanalkonfigurationen, skrivs e-post och SMS-meddelanden till **AJO Message Export Dataset**. Du kan sedan [komma åt posterna](#access-exported-data) i datauppsättningen och exportera dem till det valda lagringsmålet baserat på exportdataflödet som du har definierat.

>[!NOTE]
>
>Om du inaktiverar växeln **[!UICONTROL Enable Message Export]** stoppas nya poster för den här kanalkonfigurationen från att hämtas till datauppsättningen. Befintliga poster behålls tills kvarhållandet upphör.

## Få åtkomst till exporterade meddelandedata {#access-exported-data}

När meddelanden har skickats med en kanalkonfiguration där meddelandeexport är aktiverad kan du få åtkomst till och granska exporterade data i **AJO Message Export DataSet**.

Så här visar du exporterade meddelandedata:

1. I [!DNL Journey Optimizer] går du till **[!UICONTROL Data management]** > **[!UICONTROL Datasets]** i den vänstra navigeringen. [Läs mer om datauppsättningar](../data/get-started-datasets.md)

1. Kontrollera att du visar systemgenererade datauppsättningar.

1. Välj **AJO Message Export Dataset** i listan.

   ![](assets/datasets-list.png)

1. Klicka på **[!UICONTROL Preview dataset]** på sidan med information om datauppsättningar för att visa de senaste posterna.

   ![](assets/ajo-message-export-dataset.png)

Datauppsättningen innehåller omfattande information för varje meddelande som skickas via kanalkonfigurationen med meddelandeexport aktiverad, inklusive ämnesrad, meddelandebrödtext, mottagarens e-postadress eller telefonnummer, avsändaradress eller telefonnummer, datum och tid som skickas, personaliseringsdata med mera.

Alla poster i datauppsättningen behålls i **sju kalenderdagar från intag**. Under den här kvarhållningsperioden kan du komma åt data för efterlevnadsrevisioner, juridiska frågor eller exportera dem till ditt eget lagringssystem via den konfigurerade Experience Platform-destinationen.

