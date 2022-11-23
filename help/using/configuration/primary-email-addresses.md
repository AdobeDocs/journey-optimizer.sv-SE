---
solution: Journey Optimizer
product: journey optimizer
title: Ändra de primära e-postadresserna
description: Lär dig hur du avgör vilken e-postadress som ska användas från profiltjänsten.
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: fe2f6516-7790-4501-a3a1-3d7cb94d7874
source-git-commit: 0f69a47dccad20f3e978613b349a29f9daab94bd
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 4%

---

# Ändra primära adresser {#change-primary-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address"
>title="Ange vilken adress som ska användas"
>abstract="När det finns flera e-postadresser eller telefonnummer i databasen (personliga, professionella, osv.) kan du välja vilken som ska prioriteras för sändning."

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address_header"
>title="Ange vilken adress som ska användas"
>abstract="Redigera fälten som används för att bestämma profilens e-postadress eller telefonnummer som ska prioriteras för sändning."

När du anger en profil som mål kan det finnas flera e-postadresser eller telefonnummer i databasen (professionell e-postadress, personligt telefonnummer osv.).

Med [!DNL Journey Optimizer]kan du avgöra vilken e-postadress eller vilket telefonnummer som ska användas från profiltjänsten och prioritera när flera adresser är tillgängliga. Följ stegen nedan för att göra detta.

1. Gå till **[!UICONTROL Channels]** > **[!UICONTROL General]** > **[!UICONTROL Executions fields]**-menyn.

   ![](assets/primary-address-execution-fields.png)

1. De fält som för närvarande används som standard för att fastställa profilernas e-postadress och telefonnummer som visas på den här skärmen. Klicka **[!UICONTROL Edit]** för att ändra dem.

   ![](assets/primary-address.png)

1. Klicka på det aktuella fältet eller redigeringsikonen för att välja ett nytt fält.

   ![](assets/primary-address-edit.png)

1. Listan med tillgängliga XDM-fält av e-posttyp visas. Markera det fält som ska användas.

   ![](assets/primary-address-select-field.png)

1. Klicka **[!UICONTROL Save]** för att bekräfta ditt val.

Körningsfältet uppdateras och kommer nu att användas som primär adress.

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. -->
