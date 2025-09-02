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
source-git-commit: c39a71da901b888ff440a1488658b577ff72cc32
workflow-type: tm+mt
source-wordcount: '500'
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

![](assets/primary-address-execution-fields.png)

De aktuella värdena används för alla leveranser på sandlådenivå. Du kan uppdatera fälten om det behövs.

I de flesta fall ändrar du ett körningsfält globalt och definierar ett värde som ska användas för alla e-post- eller SMS-meddelanden. <!--[Learn how](#admin-settings)-->

<!--In some specific use cases only, you can override the value set globally and define a different value at the journey level. [Learn more](#journey-parameters)-->

## Uppdatera administrationsinställningarna {#admin-settings}

Om du vill ändra körningsfälten globalt på sandlådenivå följer du stegen nedan.

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Executions fields]**.

1. Klicka på **[!UICONTROL Edit]** om du vill ändra standardvärdena.

   ![](assets/primary-address.png)

1. Klicka på det aktuella fältet eller redigeringsikonen för att välja ett nytt fält.

   ![](assets/primary-address-edit.png)

1. Listan med tillgängliga XDM-fält av e-posttyp visas. Markera det fält som ska användas.

   ![](assets/primary-address-select-field.png)

1. Klicka på **[!UICONTROL Save]** för att bekräfta ditt val.

Körningsfältet uppdateras och kommer nu att användas som primär adress.

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. -->

## Åsidosätt standardkörningsfältet {#override-default-execution-address}

>[!CONTEXTUALHELP]
>id="ajo_journey_execution_address"
>title="Definiera ett anpassat värde"
>abstract="I vissa specifika fall kan du åsidosätta standardadressen för körningen. Använd ikonen **Aktivera åsidosättning av parameter** till höger om fältet för att definiera en anpassad primär adress."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/configuration/primary-email-addresses#journey-parameters" text="Om körningsadressen"

För specifika användningsfall kan du åsidosätta körningsfältet som ställts in globalt och definiera ett annat värde på e-postkonfigurationsnivån eller på resenivån.

Att åsidosätta det här värdet kan vara användbart för att:

* Testa ett mejl. Du kan lägga till en egen e-postadress: när du har publicerat resan skickas e-postmeddelandet till dig.
* Skicka ett e-postmeddelande till prenumeranterna av en lista. Läs mer i [det här användningsexemplet](../building-journeys/message-to-subscribers-uc.md).

### I e-postkonfigurationen

Du kan ändra standardfältinställningen för körning i de [allmänna inställningarna](#admin-settings) när du definierar en e-postkanalskonfiguration. [Läs mer](../email/email-settings.md#execution-address)

När en körningsadress definieras i e-postkonfigurationen används den som primär adress och åsidosätter den allmänna inställningen på sandlådenivå.

### I resans parametrar {#journey-parameters}

När du lägger till en **[!UICONTROL Email]**- eller **[!UICONTROL SMS]**-åtgärd till en [-resa](../email/create-email.md#create-email-journey-campaign) visas den primära e-postadressen under de avancerade parametrarna för resan.

I vissa specifika sammanhang kan du åsidosätta det här värdet med hjälp av ikonen **[!UICONTROL Enable parameter override]** till höger om fältet.

![](assets/journey-enable-parameter-override.png)

>[!CAUTION]
>
>Åsidosättning av e-postadresser ska endast användas för särskilda användningsfall. Oftast behöver du inte ändra e-postadressen eftersom det värde som definieras som primär adress i **[!UICONTROL Execution fields]** är den som ska användas.


