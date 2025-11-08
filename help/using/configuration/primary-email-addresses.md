---
solution: Journey Optimizer
product: journey optimizer
title: Ändra körningsadresserna
description: Lär dig hur du avgör vilken e-postadress som ska användas från profiltjänsten.
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
keywords: primär, körning, e-post, mål, profil, optimering
exl-id: fe2f6516-7790-4501-a3a1-3d7cb94d7874
source-git-commit: b8d56578aae90383092978446cb3614a4a033f80
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---

# Ändra körningsadresserna {#change-primary-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address"
>title="Definiera vilken adress som ska användas"
>abstract="När det finns flera e-postadresser eller telefonnummer i databasen (personliga, professionella, osv.) kan du välja vilken som ska prioriteras för sändning."

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address_header"
>title="Definiera vilken adress som ska användas"
>abstract="Redigera fälten som används för att bestämma profilens e-postadress eller telefonnummer som ska prioriteras för sändning."

När du anger en profil som mål kan det finnas flera e-postadresser eller telefonnummer i databasen (professionell e-postadress, personligt telefonnummer osv.).

I så fall använder [!DNL Journey Optimizer] **[!UICONTROL Execution fields]** för att avgöra vilken e-postadress eller vilket telefonnummer som ska användas från profiltjänsten i prioritetsordning.

Om du vill kontrollera de fält som används som standard går du till menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Executions fields]** .

![](assets/primary-address-execution-fields.png){width=90%}

>[!NOTE]
>
>Körningsfält är tillgängliga för kanalerna Email, SMS och WhatsApp.

De aktuella värdena används för alla leveranser på sandlådenivå. Du kan uppdatera fälten om det behövs.

I de flesta fall ändrar du ett körningsfält globalt och definierar ett värde som ska användas för alla e-post-, SMS- eller WhatsApp-meddelanden.

## Uppdatera administrationsinställningarna {#admin-settings}

Om du vill ändra körningsfälten globalt på sandlådenivå följer du stegen nedan.

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Executions fields]**.

1. Klicka på **[!UICONTROL Edit]** om du vill ändra standardvärdena.

   ![](assets/primary-address-edit.png){width=70%}

1. Klicka på det aktuella fältet eller redigeringsikonen för att välja ett nytt fält.

   ![](assets/primary-address-edit-field.png){width=70%}

1. Listan med tillgängliga XDM-fält av e-posttyp visas. Markera det fält som ska användas.

   ![](assets/primary-address-select-field.png){width=90%}

1. Klicka på **[!UICONTROL Save]** för att bekräfta ditt val.

Körningsfältet uppdateras och kommer nu att användas som primär adress.

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. -->

## Åsidosätt standardfältet för körning i transportparametrarna {#override-execution-address-journey}

>[!CONTEXTUALHELP]
>id="ajo_journey_execution_address"
>title="Definiera ett anpassat värde"
>abstract="I vissa specifika fall kan du åsidosätta standardadressen för körningen. Använd ikonen **Aktivera åsidosättning av parameter** till höger om fältet för att definiera en anpassad primär adress."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/configuration/primary-email-addresses#journey-parameters" text="Om körningsadressen"

För specifika användningsfall kan du åsidosätta körningsfältet som ställts in globalt och definiera ett annat värde på resenivån.

Att åsidosätta det här värdet kan vara användbart för att:

* Testa leveransen. Du kan lägga till en egen e-postadress eller ett eget telefonnummer: när du har publicerat resan skickas e-postmeddelandet, SMS-meddelandet eller whatsApp-meddelandet till dig.
* Skicka ett meddelande till prenumeranterna på en lista. Läs mer i [det här användningsexemplet](../building-journeys/message-to-subscribers-uc.md).

När du lägger till en **[!UICONTROL Email]**-, **[!UICONTROL SMS]**- eller **[!UICONTROL WhatsApp]**-åtgärd för en [-resa](../email/create-email.md#create-email) visas den primära e-postadressen eller telefonnumret under de avancerade parametrarna för resan.

Åsidosätt det här värdet med ikonen **[!UICONTROL Enable parameter override]** till höger om fältet.

![](assets/journey-enable-parameter-override.png){width=85%}

>[!CAUTION]
>
>Åsidosättning av e-postadress eller telefonnummer bör endast användas för särskilda ändamål. För det mesta behöver du inte ändra det eftersom det värde som definieras som primär adress i **[!UICONTROL Execution fields]** på sandlådenivå är det som ska användas.

## Åsidosätt standardfältet för körning i kanalkonfigurationen {#override-execution-address-channel-config}

>[!CONTEXTUALHELP]
>id="ajo_email_config_execution_address"
>title="Åsidosätt den standardadress som ska användas"
>abstract="När det finns flera e-postadresser eller telefonnummer i databasen (personliga, professionella, osv.) kan du välja vilken som ska prioriteras för sändning. Den primära adressen definieras på sandlådenivå, men här kan du åsidosätta standardinställningen för den här specifika kanalkonfigurationen."

Du kan ändra standardkörningsadressen för en viss e-post, SMS eller whatsApp [kanalkonfiguration](channel-surfaces.md).

Det gör du genom att gå till avsnittet **[!UICONTROL Execution dimension]** och redigera det dedikerade fältet under **[!UICONTROL Execution Address]**.

>[!NOTE]
>
>För [WhatsApp-kanalen](../whatsapp/whatsapp-configuration.md#whatsapp-configuration) finns **[!UICONTROL WhatsApp Execution Field]** under avsnittet **[!UICONTROL WhatsApp Settings]**.

![](assets/sms-config-execution-address.png){width=85%}

Välj sedan ett objekt i listan med tillgängliga XDM-fält för e-posttyp.

![](assets/sms-config-execution-field.png)

Körningsfältet uppdateras och används sedan som primär adress för kampanjer eller resor med den här kanalkonfigurationen. Den åsidosätter den [allmänna inställningen](#admin-settings) som definierats på sandlådenivå.

<!--[Learn more on the execution address in the email configuration ](../email/email-settings.md#execution-address)-->
