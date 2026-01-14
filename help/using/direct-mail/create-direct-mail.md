---
title: Skapa ett direktutskick
description: Lär dig hur du skapar ett direktutskick i Journey Optimizer
feature: Direct Mail
topic: Content Management
role: User
level: Beginner
keywords: direktreklam, meddelande, kampanj
exl-id: 6b438268-d983-4ab8-9276-c4b7de74e6bd
source-git-commit: ef109382448b013398b83714b0f5e85f428ffadd
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 2%

---

# Skapa ett direktutskick {#create-direct}

>[!CONTEXTUALHELP]
>id="ajo_direct_mail"
>title="Skapa direktreklam"
>abstract="Skapa direktreklam i schemalagda kampanjer och utforma de extraheringsfiler som direktreklamleverantörer behöver för att skicka e-post till era kunder."

Skapa en schemalagd kampanj och konfigurera extraheringsfilen om du vill skapa direktutskick. Den här filen krävs av direktreklamleverantörer för att skicka e-post till dina kunder.

>[!IMPORTANT]
>
>Kontrollera att du har konfigurerat innan du skapar ett direktmeddelandemeddelande:
>
>1. En [filroutningskonfiguration](../direct-mail/direct-mail-configuration.md#file-routing-configuration) som anger på vilken server extraheringsfilen ska överföras och lagras,
>1. En [konfiguration för direktmeddelandetjänst](../direct-mail/direct-mail-configuration.md#direct-mail-surface) som refererar till filroutningskonfigurationen.

## Skapa en kampanj för direktreklam{#create-dm-campaign}

Om du vill skapa en direktreklamkampanj skapar du en schemalagd kampanj, väljer målgrupp och konfigurerar inställningar för direktreklam inklusive meddelandekonfigurationen. Följ de här stegen:

1. Öppna menyn **[!UICONTROL Campaigns]** och klicka sedan på **[!UICONTROL Create campaign]**.

1. Välj den typ av kampanj som du vill köra

   * **Schemalagd - marknadsföring**: Kör kampanjen direkt eller på ett angivet datum. Schemalagda kampanjer syftar till att skicka marknadsföringsmeddelanden. De konfigureras och körs från användargränssnittet.

   * **API-utlöst - Markering/transaktion**: Kör kampanjen med ett API-anrop. API-utlösta kampanjer syftar till att skicka antingen marknadsförings- eller transaktionsmeddelanden, dvs. meddelanden som skickas ut efter en åtgärd som utförs av en individ: lösenordsåterställning, kundvagn osv.

1. I avsnittet **[!UICONTROL Properties]** redigerar du kampanjens **[!UICONTROL Title]** och **[!UICONTROL Description]**.

1. Om du vill definiera målgruppen klickar du på knappen **[!UICONTROL Select audience]** och väljer bland de tillgängliga Adobe Experience Platform-målgrupperna. [Läs mer](../audience/about-audiences.md).

   >[!IMPORTANT]
   >
   >För närvarande är valet av målgrupp begränsat till 3 miljoner profiler. Denna begränsning kan hävas på begäran av Adobe.

1. I fältet **[!UICONTROL Identity namespace]** väljer du lämpligt namnutrymme för att identifiera personer inom den valda målgruppen. [Läs mer](../event/about-creating.md#select-the-namespace).

1. Välj **[!UICONTROL Actions]** i avsnittet **[!UICONTROL Direct mail]**.

1. Välj eller skapa en **[!UICONTROL Direct mail configuration]** som ska användas. [Lär dig hur du skapar en konfiguration för direktreklam](direct-mail-configuration.md#direct-mail-surface).

   ![](assets/direct-mail-campaign.png){width="800" align="center"}

   >[!AVAILABILITY]
   >
   >Direct Mail har stöd för funktionen **Holdout** men för närvarande saknar stöd för **Bearbetningar**. [Lär dig arbeta med experiment](../content-management/get-started-experiment.md)

1. Kampanjer kan schemaläggas för ett specifikt datum eller ställas in så att de återkommer med regelbundna intervall. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** för din kampanj i [det här avsnittet](../campaigns/campaign-schedule.md).

Nu kan du börja konfigurera extraheringsfilen som ska skickas till din direktmeddelandeleverantör.

## Konfigurera extraheringsfilen {#extraction-file}

>[!CONTEXTUALHELP]
>id="ajo_direct_mail_data_fields"
>title="Fält"
>abstract="Lägg till och konfigurera kolumnerna och den information som ska visas i extraheringsfilen som krävs av direktutskick för att skicka e-post till dina kunder. Du kan lägga till upp till 50 kolumner."

>[!CONTEXTUALHELP]
>id="ajo_direct_mail_formatting"
>title="Filformatering för extrahering"
>abstract="För varje fält anger du en etikett och den information som ska visas med personaliseringsredigeraren. <br/><br/> Med alternativet <b>Sortera efter</b> kan du använda det valda fältet för att sortera extraheringsfilens kolumner."

Extraheringsfilen krävs av direktreklamleverantörer för att skicka e-post till dina kunder. Så här definierar du extraheringsfilens konfiguration:

1. Klicka på knappen **[!UICONTROL Edit content]** på konfigurationsskärmen för kampanjen för att konfigurera innehållet i extraheringsfilen.

1. Justera extraheringsfilens egenskaper:

   1. Ange ett namn för extraheringsfilen i fältet **[!UICONTROL Filename]**.

      >[!NOTE]
      >
      >Som standard skrivs filen till rotkatalogen på servern. Fältet **[!UICONTROL Filename]** accepterar även formatet /your/path/here/Filename.csv, där den angivna sökvägen är målkatalog på den valda servern. <!--TBC if for SFTP and Azure only, or for all servers including S3-->

   1. Du kan också aktivera alternativet **[!UICONTROL Append timestamp to export filename]** om du vill lägga till en automatisk tidsstämpel till det angivna filnamnet.

   1. Ibland kan du behöva lägga till information i början eller slutet av extraheringsfilen.  Om du vill göra det använder du fältet **[!UICONTROL Notes]** och anger sedan om du vill ta med anteckningen som sidhuvud eller sidfot.

      ![](assets/direct-mail-properties.png){width="800" align="center"}

1. Konfigurera kolumnerna och den information som ska visas i extraheringsfilen:

   1. Klicka på knappen **[!UICONTROL Add]** för att skapa en ny kolumn.

   1. Fönstret **[!UICONTROL Formatting]** visas till höger, så att du kan ställa in den markerade kolumnen. Ange en **[!UICONTROL Label]** för kolumnen.

   1. I fältet **[!UICONTROL Data]** väljer du de profilattribut som ska visas med [anpassningsredigeraren](../personalization/personalization-build-expressions.md).

   1. Om du vill sortera extraheringsfilen med en kolumn markerar du kolumnen och växlar till alternativet **[!UICONTROL Sort by]**. Ikonen **[!UICONTROL Sort By]** visas bredvid kolumnens etikett i avsnittet **[!UICONTROL Data Fields]**.

      ![](assets/direct-mail-content.png){width="800" align="center"}

   1. Upprepa dessa steg om du vill lägga till så många kolumner som behövs för extraheringsfilen. Observera att du kan lägga till upp till 50 kolumner.

      Om du vill ändra en kolumns position drar och släpper du den till önskad plats i avsnittet **[!UICONTROL Data field]**. Om du vill ta bort en kolumn markerar du den och klickar på knappen **[!UICONTROL Remove]** i rutan **[!UICONTROL Formatting]**.

Nu kan du testa ditt direktutskick och skicka det till din publik. [Lär dig hur du testar och skickar direktmeddelanden](test-send-direct-mail.md)

