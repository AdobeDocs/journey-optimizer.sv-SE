---
title: Konfiguration av direktreklam
description: Lär dig konfigurera direktreklamkanal i Journey Optimizer
feature: Direct Mail, Surface
topic: Content Management
role: User
level: Experienced
keyword: direct, mail, configuration, direct-mail, provider
exl-id: ae5cc885-ade1-4683-b97e-eda1f2142041
source-git-commit: b85210a46c928389db985f0f794618209773c071
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 1%

---

# Konfiguration av direktreklam {#direct-mail-configuration}

Med [!DNL Journey Optimizer] kan du anpassa och generera de filer som direktutskick kräver för att skicka e-post till dina kunder.

När du [skapar ett direktmeddelandemeddelande](../direct-mail/create-direct-mail.md) definierar du målgruppsdata, inklusive vald kontaktinformation (till exempel postadress). En fil som innehåller dessa data genereras och exporteras sedan automatiskt till en server, där din direktmeddelandeleverantör kan hämta den och ta hand om själva sändningen.

Innan du kan generera filen måste du skapa:

1. [En filroutningskonfiguration](#file-routing-configuration) som anger på vilken server filen ska exporteras och krypterar filen om det behövs.

1. [En direktadresskonfiguration](#direct-mail-configuration) som refererar till filroutningskonfigurationen. Om du inte har konfigurerat något alternativ för filroutning kommer du inte att kunna skapa en direktadresskonfiguration.


>[!CAUTION]
>
>* Om du vill skapa en filroutningskonfiguration måste du ha den inbyggda behörigheten **[!DNL Manage file routing]**. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)
>
>* Direktutskick genereras endast vid exporttillfället. Systemet lagrar inte i oändlighet äldre exporter. Konfigurera ett alternativ för filroutning (SFTP eller molnlagring) för längre eller permanent säkerhetskopiering.

## Konfigurera filroutning {#file-routing-configuration}

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details"
>title="Definiera filroutningskonfigurationen"
>abstract="När du har skapat ett direktutskick skapas och exporteras filen som innehåller målgruppsdata till en server. Du måste ange serverinformationen så att din direktreklamleverantör kan komma åt och använda den filen för att leverera direktreklam."
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

Om du vill leverera ett direktmeddelande genererar och exporterar [!DNL Journey Optimizer] filen som innehåller målgruppsdata till en server.

Du måste ange den serverinformationen så att din e-postleverantör kan komma åt och använda filen för att leverera e-post.

Följ stegen nedan för att konfigurera filflödet.

1. Gå till menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Direct mail settings]** > **[!UICONTROL File routing]** och klicka sedan på **[!UICONTROL Create file routing config]**.

   ![](assets/file-routing-config-button.png){width="800" align="center"}

1. Ange ett namn för konfigurationen.

1. Välj vilken typ av server du vill använda för att exportera dina direktmeddelandefiler: Amazon S3, SFTP, Azure eller Data Landing Zone.

   ![](assets/file-routing-config-type.png){width="800" align="center"}

1. Fyll i fälten som är specifika för varje servertyp enligt flikarna nedan.

>[!BEGINTABS]

>[!TAB Amazon S3]

Om du valde **[!UICONTROL Amazon S3]** som **[!UICONTROL Server type]** fyller du i informationen och autentiseringsuppgifterna för servern:

* **AWS-pytsen**:To vet var du hittar ditt AWS-bucket-namn, se [den här sidan](https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingBucket.html).

* **AWS-åtkomstnyckel**: Information om var du hittar ditt AWS-ID finns på [den här sidan](https://docs.aws.amazon.com/IAM/latest/UserGuide/security-creds.html#access-keys-and-secret-access-keys).

* **AWS hemlig nyckel**: Om du vill veta var du hittar din hemliga AWS-nyckel kan du läsa [den här sidan](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

* **AWS-region**: välj **[!UICONTROL AWS region]** där serverinfrastrukturen ska finnas. AWS-regioner är geografiska områden som AWS använder för sin molninfrastruktur. Som allmän praxis är det att föredra att välja den region som ligger närmast din direktreklamleverantörs plats.

![](assets/file-routing-config-aws-region.png){width="800" align="center"}

>[!TAB SFTP]

Om du valde **[!UICONTROL SFTP]** som **[!UICONTROL Server type]** fyller du i informationen och autentiseringsuppgifterna för servern:

* **[!UICONTROL Authentication type]**: Välj den typ av autentisering som används för att ansluta till servern (lösenord eller SSH-nyckel).

* **[!UICONTROL Account]**: Kontonamnet som används för att ansluta till SFTP-servern.

* **[!UICONTROL Server address]**: &#x200B; URL för SFTP-servern.

* **[!UICONTROL Port]**: Portnummer för SFTP-anslutning.

* **[!UICONTROL Password]** / **[!UICONTROL SSH Key]**: &#x200B; lösenord eller SSH-nyckel som används för att ansluta till SFTP-servern.

![](assets/file-routing-config-sftp-detail.png)

>[!TIP]
>
>När SSH-nyckelautentisering används måste nyckeln vara en **Base64-kodad OpenSSH** -privat nyckel. Om det är en PPK-formatfil använder du PuTTY-verktyget för att konvertera den till OpenSSH-format. Detaljerade instruktioner finns i [det här avsnittet](#ssh-key-generation).

>[!NOTE]
>
>Om du vill ange en sökväg på servern för att spara filen uppdaterar du fältet **[!UICONTROL Filename]** för direktreklamkampanjen så att det innehåller den önskade sökvägen. [Läs mer](create-direct-mail.md#extraction-file)

>[!TAB Azure]

Om du valde **[!UICONTROL Azure]** som **[!UICONTROL Server type]** fyller du i informationen och autentiseringsuppgifterna för servern:

* **Azure-anslutningssträng**: Om du vill hitta din **Azure-anslutningssträng** läser du [den här sidan](https://learn.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string#configure-a-connection-string-for-an-azure-storage-account).

  **Azure-anslutningssträngen** ska följa formatet nedan:

  `DefaultEndpointsProtocol=[http|https];AccountName=myAccountName;AccountKey=myAccountKey`

* **Behållarnamn**: Om du vill hitta **Behållarnamn** kan du läsa [den här sidan](https://learn.microsoft.com/en-us/azure/storage/blobs/blob-containers-portal).

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

### Generera SSH-nyckel för SFTP-autentisering {#ssh-key-generation}

Om du använder SFTP med SSH-nyckelautentisering måste du ha en Base64-kodad privat nyckel för OpenSSH. Om nyckeln inte är korrekt formaterad kan du få anslutningsfel när du konfigurerar filroutningen.

+++Skapa en Base64-kodad privat nyckel för OpenSSH

1. Generera nyckelparet i PuTTYgen. RSA med 2 048 bitar eller mer rekommenderas.
1. Välj **Konverteringar** > **Exportera OpenSSH-nyckel** på menyn.
1. Välj att spara den privata nyckeln **utan lösenfrasskydd** när du uppmanas till detta.
1. Välj **Alla filer (*) i dialogrutan Spara.*)** som filtyp för att säkerställa att nyckeln sparas som oformaterad text och inte som en .ppk-fil.
1. Öppna den sparade filen med en textredigerare och verifiera filens format:
   * Filen måste börja med `-----BEGIN RSA PRIVATE KEY-----` (fem streck före och efter).
   * Det ska inte finnas någon formulering som anger kryptering.
   * Filen måste sluta med `-----END RSA PRIVATE KEY-----` (fem streck före och efter).
1. Kopiera **hela filinnehållet** (inklusive `-----BEGIN/END RSA PRIVATE KEY-----`-markörerna) och koda det till Base64 med ett verktyg som [Base64-kodning och Decode](https://www.base64encode.org/).

   >[!NOTE]
   >
   >I Base64-kodningsutdata tar du bort eventuell MIME-formatering. Den kodade nyckeln måste vara en enda kontinuerlig sträng.

1. Nu kan du klistra in Base64-kodad SSH-nyckel i det dedikerade fältet i Journey Optimizer.

>[!CAUTION]
>
>Efter Base64-kodning innehåller nyckeln inte längre `-----BEGIN/END RSA PRIVATE KEY-----`-markörerna och får inte innehålla några radbrytningar. Motsvarande offentliga nyckel måste läggas till i SFTP-serverns auktoriserade nyckelfil.

Mer information om hur du ansluter ditt SFTP-konto till Experience Platform finns i [den här dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/cloud-storage/sftp).

+++

## Skapa en konfiguration för direktreklam {#direct-mail-surface}

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_settings"
>title="Definiera inställningar för direktreklam"
>abstract="En konfiguration för direktreklam innehåller formateringsinställningarna för filen som innehåller målgruppsdata och kommer att användas av e-postleverantören. Du måste också definiera var filen ska exporteras genom att välja filroutningskonfigurationen."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/direct-mail/direct-mail-configuration#file-routing-configuration" text="Konfigurera filroutning"

<!--
>[!CONTEXTUALHELP]
>id="ajo_dm_surface_sort"
>title="Define the sort order"
>abstract="If you select this option, the sort will be by profile ID, ascending or descending. If you unselect it, the sorting configuration defined when creating the direct mail message within a journey or a campaign."-->

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_split"
>title="Definiera tröskelvärdet för fildelning"
>abstract="Du måste ange maximalt antal poster för varje fil som innehåller målgruppsdata. Du kan välja valfritt tal mellan 1 och 200 000 poster. När det angivna tröskelvärdet har nåtts skapas en annan fil för de återstående posterna."

För att kunna leverera direktreklam med [!DNL Journey Optimizer] måste du skapa en kanalkonfiguration som definierar inställningarna för formateringen av filen som ska användas av e-postleverantören.

En konfiguration för direktreklam måste även innehålla den filroutningskonfiguration som definierar den server där direktpostfilen ska exporteras.

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

1. Välj **[!UICONTROL File routing configuration]** bland de som du har skapat. Detta anger var filen exporteras så att din direktmeddelandeleverantör kan använda den.

   >[!CAUTION]
   >
   >Om du inte har konfigurerat något alternativ för filroutning kommer du inte att kunna skapa en direktadresskonfiguration. [Läs mer](#file-routing-configuration)

   ![](assets/surface-direct-mail-file-routing.png){width="800" align="center"}

   <!--![](assets/surface-direct-mail-file-routing-with-insertion.png)-->

1. Skicka konfigurationen för direktreklam.

Du kan nu [skapa ett direktmeddelandemeddelande](../direct-mail/create-direct-mail.md) inuti en kampanj. När kampanjen har startats exporteras filen som innehåller målgruppsdata automatiskt till den server som du har definierat. Leverantören av direktreklam kan då hämta filen och fortsätta med leveransen av direktreklam.

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