---
title: Konfiguration av direktreklam
description: Lär dig konfigurera direktreklamkanal i Journey Optimizer
feature: Direct Mail, Surface
topic: Content Management
role: User
level: Experienced
keyword: direct, mail, configuration, direct-mail, provider
exl-id: ae5cc885-ade1-4683-b97e-eda1f2142041
source-git-commit: 65b7b8323e37a0143a3941af1b9c2fb8b595a376
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 1%

---

# Konfiguration av direktreklam {#direct-mail-configuration}

Med [!DNL Journey Optimizer] kan du anpassa och generera de filer som direktutskick kräver för att skicka e-post till dina kunder.

När [du skapar ett direktmeddelande](../direct-mail/create-direct-mail.md) definierar du målgruppsdata, inklusive den valda kontaktinformationen (t.ex. postadress). En fil som innehåller dessa data kommer sedan automatiskt att genereras och exporteras till en server, där din direktreklamleverantör kommer att kunna hämta den och ta hand om själva sändningen.

Innan du kan generera den här filen måste du skapa:

1. [En filroutningskonfiguration](#file-routing-configuration) för att ange den server där filen ska exporteras och kryptera filen om det behövs.

1. [En konfiguration](#direct-mail-configuration) för direktmeddelanden som refererar till konfigurationen för filroutning. Om du inte har konfigurerat något alternativ för fildirigering kommer du inte att kunna skapa en konfiguration för direktmeddelanden.


>[!CAUTION]
>
>* Om du vill skapa en konfiguration för filroutning måste du ha den inbyggda behörigheten **[!DNL Manage file routing]** . [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)
>
>* Filer med direktmeddelanden genereras endast vid exporten. Systemet lagrar inte äldre exporter i all oändlighet. Konfigurera ett alternativ för filroutning (SFTP eller molnlagring) för längre eller permanent säkerhetskopiering.

## Konfigurera filroutning {#file-routing-configuration}

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details"
>title="Definiera konfigurationen för filroutning"
>abstract="När du har skapat ett direktmeddelande genereras filen som innehåller målgruppsdata och exporteras till en server. Du måste ange serverinformationen så att din direktutskicksleverantör kan komma åt och använda filen för att leverera direktreklam."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/direct-mail/create-direct-mail" text="Skapa ett direktutskick"

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
>abstract="Välj vilken typ av server du vill använda för att exportera dina direktmeddelandefiler: Amazon S3, SFTP, Azure eller Data Landing Zone."

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_aws_region"
>title="Välj AWS"
>abstract="Markera det geografiska område på AWS-servern där du vill exportera dina direktmeddelandefiler. Som allmän praxis är det att föredra att välja den närmaste regionen till den plats där direktreklamleverantören finns."

>[!NOTE]
>
>För närvarande stöds Amazon S3, SFTP, Azure och Data Landing Zone i [!DNL Journey Optimizer].

Om du vill leverera ett direktmeddelande [!DNL Journey Optimizer] genererar och exporterar du filen som innehåller målgruppsdata till en server.

Du måste ange serverinformationen så att din direktutskicksleverantör kan komma åt och använda filen för att leverera e-post.

Följ stegen nedan för att konfigurera fildirigeringen.

1. Öppna menyn > **[!UICONTROL Administration]** **[!UICONTROL Channels]** > **[!UICONTROL Direct mail settings]** > **[!UICONTROL File routing]** och klicka sedan på **[!UICONTROL Create file routing config]**.

   ![](assets/file-routing-config-button.png){width="800" align="center"}

1. Ange ett namn för konfigurationen.

1. Välj vilken typ av server du vill använda för att exportera dina direktmeddelandefiler: Amazon S3, SFTP, Azure eller Data Landing Zone.

   ![](assets/file-routing-config-type.png){width="800" align="center"}

1. Fyll i de fält som är specifika för varje servertyp enligt beskrivningen på flikarna nedan.

>[!BEGINTABS]

>[!TAB Amazon S3]

Om du har valt **[!UICONTROL Amazon S3]** som , **[!UICONTROL Server type]** fyll i information och autentiseringsuppgifter för din server:

* **AWS-hinknamn**:För att veta var du hittar ditt AWS-hinknamn, se [den här sidan](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingBucket.html).

* **AWS-åtkomstnyckel**: Information om var du hittar ditt AWS-ID finns på [den här sidan](https://docs.aws.amazon.com/IAM/latest/UserGuide/security-creds.html#access-keys-and-secret-access-keys).

* **AWS hemlig nyckel**: Om du vill veta var du hittar din hemliga AWS-nyckel kan du läsa [den här sidan](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

* **AWS-region**: välj **[!UICONTROL AWS region]** där serverinfrastrukturen ska finnas. AWS-regioner är geografiska områden som AWS använder för sin molninfrastruktur. Som allmän praxis är det att föredra att välja den region som ligger närmast din direktreklamleverantörs plats.

![](assets/file-routing-config-aws-region.png){width="800" align="center"}

>[!TAB SFTP]

Om du valde **[!UICONTROL SFTP]** som **[!UICONTROL Server type]** fyller du i informationen och autentiseringsuppgifterna för servern:

* **Konto: Kontonamn** som används för att ansluta till SFTP-servern.

* **Serveradress**: URL till SFTP-servern.

* **Port**: Portnummer för FTP-anslutning.

* **Password**: Lösenord som används för att ansluta till SFTP-servern.

![](assets/file-routing-config-sftp-detail.png)

>[!NOTE]
>
>Om du vill ange en sökväg på servern för att spara filen uppdaterar du fältet för direktmeddelandekampanjen **[!UICONTROL Filename]** så att det innehåller den önskade sökvägen. [Läs mer](create-direct-mail.md#extraction-file)

>[!TAB Azure]

Om du har valt **[!UICONTROL Azure]** som , **[!UICONTROL Server type]** fyll i information och autentiseringsuppgifter för din server:

* **Azure-anslutningssträng**: Information om hur du hittar din **Azure-anslutningssträng** finns på [den här sidan](https://learn.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string#configure-a-connection-string-for-an-azure-storage-account).

  Azure-anslutningssträngen **** bör följa formatet nedan:

  `DefaultEndpointsProtocol=[http|https];AccountName=myAccountName;AccountKey=myAccountKey`

* **Containernamn**: Information om hur du hittar ditt **containernamn** finns på [den här sidan](https://learn.microsoft.com/en-us/azure/storage/blobs/blob-containers-portal).

  **Behållarnamnet** får bara innehålla behållarens namn utan snedstreck.

  >[!NOTE]
  >
  >Om du vill ange en sökväg i behållaren för att spara filen uppdaterar du fältet **[!UICONTROL Filename]** för direktreklamkampanjen så att den innehåller den önskade sökvägen. [Läs mer](create-direct-mail.md#extraction-file)

  ![](assets/file-routing-config-azure-detail.png)

>[!TAB Datalandningszon]

Om du valde **[!UICONTROL Data Landing Zone]** som **[!UICONTROL Server type]** behövs ingen specifik information.

![](assets/file-routing-config-dlz-detail.png)

Alla kunder i [!DNL Adobe Experience Platform] har etablerats med en Data Landing Zone-behållare per sandlåda. Läs mer om Data Landing Zone i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/cloud-storage/data-landing-zone){target="_blank"}.

>[!ENDTABS]

Om du vill kryptera filen kopierar och klistrar du in krypteringsnyckeln i fältet **[!UICONTROL PGP/GPG encryption key]**.

Välj **[!UICONTROL Submit]** när du har fyllt i informationen om din servertyp. Filroutningskonfigurationen skapas med statusen **[!UICONTROL Active]**. Den är nu klar att användas i en [direktadresskonfiguration](#direct-mail-surface).

Du kan också välja **[!UICONTROL Save as draft]** för att skapa filroutningskonfigurationen, men du kan inte välja den i en konfiguration förrän den är **[!UICONTROL Active]**.

## Skapa en konfiguration för direktreklam {#direct-mail-surface}

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_settings"
>title="Definiera inställningarna för direktreklam"
>abstract="En konfiguration för direktutskick innehåller inställningarna för formateringen av filen som innehåller målgruppsdata och som ska användas av e-postleverantören. Du måste också definiera var filen ska exporteras genom att välja filroutningskonfigurationen."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/direct-mail/direct-mail-configuration#file-routing-configuration" text="Konfigurera filroutning"

<!--
>[!CONTEXTUALHELP]
>id="ajo_dm_surface_sort"
>title="Define the sort order"
>abstract="If you select this option, the sort will be by profile ID, ascending or descending. If you unselect it, the sorting configuration defined when creating the direct mail message within a journey or a campaign."-->

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_split"
>title="Definiera tröskelvärdet för fildelning"
>abstract="Du måste ange maximalt antal poster för varje fil som innehåller målgruppsdata. Du kan välja valfritt tal mellan 1 och 200 000 poster. När det angivna tröskelvärdet har uppnåtts skapas en annan fil för de återstående posterna."

För att kunna leverera direktreklam med [!DNL Journey Optimizer]måste du skapa en kanalkonfiguration för att definiera inställningarna för formateringen av filen som ska användas av e-postleverantören.

En konfiguration för direktmeddelanden måste också innehålla konfigurationen för fildirigering som definierar den server som direktmeddelandefilen ska exporteras till.

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]**. Klicka på knappen **[!UICONTROL Create channel configuration]**. [Läs mer](../configuration/channel-surfaces.md)

   ![](assets/direct-mail-config-1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen och välj sedan den kanal som ska konfigureras.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela anpassade eller grundläggande dataanvändningsetiketter till konfigurationen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Välj kanalen **[!UICONTROL Direct mail]**.

   ![](assets/direct-mail-config-2.png)

1. Välj **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper till meddelanden som använder den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

1. Definiera inställningarna för direktreklam i det dedikerade avsnittet i kanalkonfigurationen.

   ![](assets/surface-direct-mail-settings.png){width="800" align="center"}

   <!--![](assets/surface-direct-mail-settings-with-insertion.png)-->

1. Välj filformat: **[!UICONTROL CSV]** eller **[!UICONTROL Text delimited]**.

1. Om du väljer **[!UICONTROL Text delimited]** definierar du den kolumnavgränsare du vill använda: tabulering, semikolon, pipe eller et-tecken.

   ![](assets/surface-direct-mail-column-separator.png)

1. Välj de **[!UICONTROL File routing configuration]** som du har skapat. Detta definierar vart filen ska exporteras så att din direktutskicksleverantör kan använda den.

   >[!CAUTION]
   >
   >Om du inte har konfigurerat något alternativ för fildirigering kommer du inte att kunna skapa en konfiguration för direktmeddelanden. [Läs mer](#file-routing-configuration)

   ![](assets/surface-direct-mail-file-routing.png){width="800" align="center"}

   <!--![](assets/surface-direct-mail-file-routing-with-insertion.png)-->

1. Skicka konfigurationen för direktmeddelanden.

Nu kan [du skapa ett direktmeddelande](../direct-mail/create-direct-mail.md) i en kampanj. När kampanjen har startats exporteras filen som innehåller målgruppsdata automatiskt till den server som du har definierat. Leverantören av direktmeddelanden kommer sedan att kunna hämta filen och fortsätta med direktmeddelandeleveransen.

>[!NOTE]
>
>Duplicerade rader där alla värden på raden är desamma tas automatiskt bort från filen.

<!--
    In the **[!UICONTROL Insertion]** section, you can choose to automatically remove duplicate rows.

    Define the maximum number of records (i.e. rows) for each file containing profile data. After the specified threshold is reached, another file will be created for the remaining records.

    ![](assets/surface-direct-mail-split.png)

    For example, if there are 100,000 records in the file and the threshold limit is set to 60,000, the records will be split into two files. The first file will contain 60,000 rows, and the second file will contain the remaining 40,000 rows.

    >[!NOTE]
    >
    >NOTE You can set any number between 1 and 200,000 records, meaning each file must contain at least 1 row and no more than 200,000 rows.

-->