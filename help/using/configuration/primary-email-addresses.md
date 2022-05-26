---
title: 'Ändra de primära e-postadresserna '
description: Lär dig hur du avgör vilken e-postadress som ska användas från profiltjänsten.
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: fe2f6516-7790-4501-a3a1-3d7cb94d7874
source-git-commit: 59cba4086cd198a8be597a9971105569d5db2eee
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 6%

---

# Ändra primära adresser {#change-primary-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address"
>title="Ange vilken adress som ska användas"
>abstract="När det finns flera tillgängliga adresser i databasen (personliga, professionella, osv.) kan du välja vilken adress som ska prioriteras för sändning."

När du anger en profil som mål kan det finnas flera e-postadresser i databasen (personlig, professionell e-postadress osv.).

Med [!DNL Journey Optimizer]kan du avgöra vilken e-postadress som ska användas från profiltjänsten och prioritera när flera adresser är tillgängliga. Följ stegen nedan för att göra detta.

1. Gå till **[!UICONTROL Channels]** > **[!UICONTROL General]** > **[!UICONTROL Executions fields]**-menyn.

   ![](assets/primary-address-execution-fields.png)

1. Det fält som för närvarande används som standard för att bestämma profilens e-postadresser som visas på den här skärmen. Klicka **[!UICONTROL Edit]** för att ändra det.

   ![](assets/primary-address.png)

1. Klicka på det aktuella fältet eller redigeringsikonen för att markera ett nytt fält.

   ![](assets/primary-address-edit.png)

1. Listan med tillgängliga XDM-fält av e-posttyp visas. Markera det fält som ska användas.

   ![](assets/primary-address-field.png)

1. Klicka **[!UICONTROL Save]** för att bekräfta ditt val.

   ![](assets/primary-address-save.png)

   Körningsfältet uppdateras och kommer nu att användas som primär adress.

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. -->
