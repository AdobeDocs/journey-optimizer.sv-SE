---
title: Konfiguration av direktreklam
description: Lär dig konfigurera direktreklamkanal i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keyword: direct, mail, configuration, direct-mail, provider
exl-id: ae5cc885-ade1-4683-b97e-eda1f2142041
source-git-commit: 173ae09e48a67e0e40aa59f0f714b014eb8b8064
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 0%

---

# Konfiguration av direktreklam {#direct-mail-configuration}

[!DNL Journey Optimizer] gör att du kan anpassa och generera de filer som direktreklamleverantörer behöver för att skicka e-post till dina kunder.

När [skapa ett direktpostmeddelande](../direct-mail/create-direct-mail.md)definierar du målgruppsdata, inklusive vald kontaktinformation (t.ex. postadress). En fil som innehåller dessa data genereras och exporteras sedan automatiskt till en server, där din direktmeddelandeleverantör kan hämta den och ta hand om själva sändningen.

Innan du kan generera filen måste du skapa:

1. A [konfiguration för filroutning](#file-routing-configuration) för att ange på vilken server filen ska exporteras.

1. A [direktreklamyta](#direct-mail-surface) som refererar till filroutningskonfigurationen.

>[!CAUTION]
>
>Om du inte har konfigurerat något alternativ för filroutning kan du inte skapa en direktreklamyta.

## Konfigurera filroutning {#file-routing-configuration}

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details"
>title="Definiera filroutningskonfigurationen"
>abstract="När du har skapat ett direktutskick skapas och exporteras filen som innehåller målgruppsdata till en server. Du måste ange serverinformationen så att din direktreklamleverantör kan komma åt och använda den filen för att leverera direktreklam."

<!--
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/direct-mail/create-direct-mail.html" text="Create a direct mail message"-->

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details_header"
>title="Definiera filroutningskonfigurationen"
>abstract="Du måste ange var filen ska exporteras för att din direktmeddelandeleverantör ska kunna använda den."

>[!CONTEXTUALHELP]
>id="ajo_dm_select_file_routing"
>title="Konfiguration av filroutning"
>abstract="Välj valfri konfiguration för filroutning, som anger var filen ska exporteras så att din direktmeddelandeleverantör kan använda den."

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_type"
>title="Välj servertyp för filen"
>abstract="Välj vilken typ av server du vill använda för att exportera dina direktmeddelandefiler. För närvarande stöds endast Amazon S3 och SFTP av Journey Optimizer."

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_aws_region"
>title="Välj AWS"
>abstract="Markera det geografiska område på AWS-servern där du vill exportera dina direktmeddelandefiler. Som allmän praxis är det att föredra att välja den närmaste regionen till den plats där direktreklamleverantören finns."

Om du vill leverera ett direktmejl [!DNL Journey Optimizer] genererar och exporterar filen som innehåller målgruppsdata till en server.

Du måste ange den serverinformationen så att din e-postleverantör kan komma åt och använda filen för att leverera e-post.

Följ stegen nedan för att konfigurera filflödet.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL File routing configuration]** > **[!UICONTROL File Routing]** menyn och klicka sedan på **[!UICONTROL Create routing configuration]**.

   ![](assets/file-routing-config-button.png){width="800" align="center"}

1. Ange ett namn för konfigurationen.

1. Välj **[!UICONTROL Server type]** som du vill använda för att exportera direktmeddelandefiler.

   ![](assets/file-routing-config-type.png){width="800" align="center"}

   >[!NOTE]
   >
   >Amazon S3 och SFTP<!--and Azure--> stöds i [!DNL Journey Optimizer].

1. Fyll i information och autentiseringsuppgifter för servern, t.ex. serveradress, åtkomstnyckel.

   ![](assets/file-routing-config-sftp-details.png)

1. Om du valde **[!UICONTROL Amazon S3]** väljer du **[!UICONTROL AWS region]** var serverinfrastrukturen ska placeras.

   ![](assets/file-routing-config-aws-region.png){width="800" align="center"}

   >[!NOTE]
   >
   >AWS-regioner är geografiska områden som AWS använder för sin molninfrastruktur. Som allmän praxis är det att föredra att välja den region som ligger närmast din direktreklamleverantörs plats.

1. Välj **[!UICONTROL Submit]**. Filroutningskonfigurationen skapas med **[!UICONTROL Active]** status. Den är nu klar att användas i en [direktreklamyta](#direct-mail-surface).

   >[!NOTE]
   >
   >Du kan också välja **[!UICONTROL Save as draft]** för att skapa filroutningskonfigurationen, men du kan inte markera den på en yta förrän den är **[!UICONTROL Active]**.

## Skapa en yta för direktreklam {#direct-mail-surface}

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_settings"
>title="Definiera inställningar för direktreklam"
>abstract="En yta för direktreklam innehåller formateringsinställningarna för filen som innehåller målgruppsdata och kommer att användas av e-postleverantören. Du måste också definiera var filen ska exporteras genom att välja filroutningskonfigurationen."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/direct-mail/direct-mail-configuration.html#file-routing-configuration" text="Konfigurera filroutning"

<!--
>[!CONTEXTUALHELP]
>id="ajo_dm_surface_sort"
>title="Define the sort order"
>abstract="If you select this option, the sort will be by profile ID, ascending or descending. If you unselect it, the sorting configuration defined when creating the direct mail message within a journey or a campaign."-->

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_split"
>title="Definiera tröskelvärdet för fildelning"
>abstract="Du måste ange maximalt antal poster för varje fil som innehåller målgruppsdata. Du kan välja valfritt tal mellan 1 och 200 000 poster. När det angivna tröskelvärdet har nåtts skapas en annan fil för de återstående posterna."

För direktreklam med [!DNL Journey Optimizer]måste du skapa en kanal för att definiera formateringsinställningarna för filen som ska användas av e-postleverantören.

En direktreklamyta måste även innehålla den filroutningskonfiguration som definierar den server där direktpostfilen ska exporteras.

1. Skapa en kanalyta. [Läs mer](../configuration/channel-surfaces.md)

1. Välj **[!UICONTROL Direct mail]** kanal.

   ![](assets/surface-direct-mail-channel.png){width="800" align="center"}

1. Definiera inställningarna för direktreklam i det dedikerade avsnittet i kanalytans konfiguration.

   ![](assets/surface-direct-mail-settings.png){width="800" align="center"}

   <!--![](assets/surface-direct-mail-settings-with-insertion.png)-->

1. Välj filformat: **[!UICONTROL CSV]** eller **[!UICONTROL Text delimited]**.

1. Om du väljer **[!UICONTROL Text delimited]** definierar du den kolumnavgränsare du vill använda: tabulering, semikolon eller vertikalstreck<!--or ampersand-->.

   ![](assets/surface-direct-mail-column-separator.png)

1. Välj **[!UICONTROL File routing configuration]** bland de som du har skapat. Detta anger var filen exporteras så att din direktmeddelandeleverantör kan använda den.

   >[!CAUTION]
   >
   >Om du inte har konfigurerat något alternativ för filroutning kan du inte skapa en direktreklamyta. [Läs mer](#file-routing-configuration)

   ![](assets/surface-direct-mail-file-routing.png){width="800" align="center"}

   <!--![](assets/surface-direct-mail-file-routing-with-insertion.png)-->

1. Skicka direktreklamytan.

Nu kan du [skapa ett direktmeddelandemeddelande](../direct-mail/create-direct-mail.md) i en kampanj. När kampanjen har startats exporteras filen som innehåller målgruppsdata automatiskt till den server som du har definierat. Leverantören av direktreklam kan då hämta filen och fortsätta med leveransen av direktreklam.

>[!NOTE]
>
>Duplicerade rader tas bort automatiskt.
>
>Om det maximala antalet poster (t.ex. rader) för varje fil som innehåller profildata är för högt skapas en annan fil automatiskt för de återstående posterna.

<!--
    In the **[!UICONTROL Insertion]** section, you can choose to automatically remove duplicate rows.

    Define the maximum number of records (i.e. rows) for each file containing profile data. After the specified threshold is reached, another file will be created for the remaining records.

    ![](assets/surface-direct-mail-split.png)

    For example, if there are 100,000 records in the file and the threshold limit is set to 60,000, the records will be split into two files. The first file will contain 60,000 rows, and the second file will contain the remaining 40,000 rows.

    >[!NOTE]
    >
    >NOTE You can set any number between 1 and 200,000 records, meaning each file must contain at least 1 row and no more than 200,000 rows.

-->