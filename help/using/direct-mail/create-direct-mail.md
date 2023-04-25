---
title: Skapa ett direktutskick
description: Lär dig hur du skapar ett direktutskick i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: direktreklam, meddelande, kampanj
hide: true
hidefromtoc: true
exl-id: 6b438268-d983-4ab8-9276-c4b7de74e6bd
badge: label="Beta" type="Informative"
source-git-commit: a6a892ec20dfeb6879bef2f4c2eb4a0f8f54885f
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 3%

---

# Skapa ett direktutskick {#create-direct}

>[!CONTEXTUALHELP]
>id="ajo_direct_mail"
>title="Skapa direktreklam"
>abstract="Skapa direktreklam i schemalagda kampanjer och utforma de extraheringsfiler som direktreklamleverantörer behöver för att skicka e-post till era kunder."

>[!BEGINSHADEBOX]

Vad du hittar i den här dokumentationen:

* **[Skapa direktreklam](create-direct-mail.md)**
* [Konfigurera direktreklam](direct-mail-configuration.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Direktreklam finns för närvarande som en privat betaversion och kan uppdateras ofta utan föregående meddelande.

Direktreklam är en offlinekanal som gör att du kan anpassa och generera extraheringsfiler som krävs av direktreklamleverantörer för att skicka e-post till dina kunder.

När du skapar ett direktutskick genererar Journey Optimizer en fil som innehåller alla målprofiler och valda data (postadress, till exempel profilattribut). Din e-postleverantör kan då hämta filen och ta hand om själva sändningen.

Direktutskick kan bara skapas i samband med schemalagda kampanjer. De är inte tillgängliga för användning i API-utlösta kampanjer eller under resor.

>[!IMPORTANT]
>
>Kontrollera att du har konfigurerat innan du skickar ett direktmeddelande:
>
>1. A [konfiguration för filroutning](../direct-mail/direct-mail-configuration.md#file-routing-configuration) som anger den server där extraheringsfilen ska överföras och lagras,
>1. A [meddelandeyta för direktreklam](../direct-mail/direct-mail-configuration.md#direct-mail-surface) som kommer att referera till filroutningskonfigurationen.


## Skapa ett direktmejl {#create}

Så här skapar och skickar du ett direktutskick:

1. Skapa en ny schemalagd kampanj, välj **[!UICONTROL Direct mail]** som du vill och välja vilken kanalyta som ska användas. [Lär dig hur du skapar en direktreklamyta](../direct-mail/direct-mail-configuration.md#direct-mail-surface)

   ![](assets/direct-mail-campaign.png)

1. Klicka **[!UICONTROL Create]** Definiera sedan grundläggande information om kampanjen (namn, beskrivning). [Lär dig konfigurera en kampanj](../campaigns/create-campaign.md)

   ![](assets/direct-mail-edit.png)

1. Klicka på **[!UICONTROL Edit content]** för att konfigurera extraheringsfilen som ska skickas till din direktmeddelandeleverantör.

1. Definiera namnet på extraheringsfilen i **[!UICONTROL Filename]** fält.

   Ibland kan du behöva lägga till information i början eller slutet av extraheringsfilen.  Om du vill göra det använder du **[!UICONTROL Notes]** anger du sedan om du vill ta med anteckningen som sidhuvud eller sidfot.

   <!--Click on the button to the right of the Output file field and enter the desired label. You can use personalization fields, content blocks and dynamic text (see Defining content). For example, you can complete the label with the delivery ID or the extraction date.-->

   ![](assets/direct-mail-properties.png)

1. Använd det vänstra området för att definiera den information som ska visas som kolumner i extraheringsfilen:

   1. Klicka på **[!UICONTROL Add]** om du vill lägga till en ny kolumn och sedan markera den i listan.

   1. I **[!UICONTROL Formatting]** anger du en etikett för kolumnen och definierar sedan de profilattribut som ska visas med [Uttrycksredigeraren](../personalization/personalization-build-expressions.md).

      ![](assets/direct-mail-content.png)

   1. Om du vill sortera extraheringsfilen med den markerade kolumnen växlar du **[!UICONTROL Sort by]** på. The **[!UICONTROL Sort By]** visas sedan bredvid kolumnens etikett i filstrukturen.

1. Upprepa dessa steg för att lägga till så många kolumner som behövs för att skapa extraheringsfilen. Observera att du kan lägga till upp till 50 kolumner.

   Du kan när som helst ta bort en kolumn genom att markera den och klicka på **[!UICONTROL Remove]** från **[!UICONTROL Formatting]** -avsnitt.

   ![](assets/direct-mail-complete.png)

1. Slutför konfigurationen av kampanjen när du har definierat innehållet för direktreklam.

   När kampanjen startar genereras extraheringsfilen automatiskt och exporteras till den server som anges i [konfiguration för filroutning](../direct-mail/direct-mail-configuration.md).
