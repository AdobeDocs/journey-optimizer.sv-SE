---
title: Skapa IP-pooler
description: Lär dig hur du hanterar IP-pooler
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 606334c3-e3e6-41c1-a10e-63508a3ed747
source-git-commit: e81e21f714a3c5450defa1129e1e2b9969dc1de7
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 0%

---

# Skapa IP-pooler {#create-ip-pools}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_pool_header"
>title="Konfigurera en IP-pool"
>abstract="Du kan skapa IP-pooler för att gruppera IP-adresserna för dina underdomäner för att förbättra e-postleveransen."

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_pool"
>title="Konfigurera en IP-pool"
>abstract="Du kan skapa IP-pooler för att gruppera IP-adresserna för dina underdomäner för att förbättra e-postleveransen."

## Om IP-pooler {#about-ip-pools}

Med [!DNL Journey Optimizer]kan du skapa IP-pooler för att gruppera IP-adresserna för dina underdomäner.

Vi rekommenderar starkt att du skapar IP-pooler för e-postleverans. På så sätt kan du förhindra att en underdomän får ett anseende som påverkar dina andra underdomäner.

Ett exempel är att ha en IP-pool för dina marknadsföringsmeddelanden och en annan för dina transaktionsmeddelanden. På så sätt påverkas inte transaktionsmeddelanden som skickas till samma kund om ett av dina marknadsföringsmeddelanden fungerar dåligt och deklareras som skräppost av en kund, som fortfarande får transaktionsmeddelanden (inköpsbekräftelser, meddelanden om lösenordsåterställning osv.).

## Skapa en IP-pool {#create-ip-pool}

Så här skapar du en IP-pool:

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL IP pools]** menyn och klicka sedan på **[!UICONTROL Create IP Pool]**.

   ![](assets/ip-pool-create.png)

1. Ange ett namn och en beskrivning (valfritt) för IP-poolen.

   >[!NOTE]
   >
   >Namnet måste börja med en bokstav (A-Z) och endast innehålla alfanumeriska tecken eller specialtecken ( _, ., - ).

1. Välj de IP-adresser som ska ingå i poolen i listrutan och klicka sedan på **[!UICONTROL Submit]**.

   ![](assets/ip-pool-config.png)

   >[!NOTE]
   >
   >Alla IP-adresser som har etablerats med din instans är tillgängliga i listan.

IP-poolen skapas nu och visas i listan. Du kan markera den för att komma åt dess egenskaper och visa den associerade kanalytan (t.ex. meddelandeförinställning). Mer information om hur du associerar en kanalyta med en IP-pool finns i [det här avsnittet](channel-surfaces.md).

![](assets/ip-pool-created.png)

## Redigera en IP-pool {#edit-ip-pool}

Så här redigerar du en IP-pool:

1. Öppna IP-poolnamnet genom att klicka på det i listan.

   ![](assets/ip-pool-list.png)

1. Redigera egenskaperna efter behov. Du kan ändra beskrivningen och lägga till eller ta bort IP-adresser.

   >[!NOTE]
   >
   >IP-poolnamnet kan inte redigeras. Om du vill ändra den måste du ta bort IP-poolen och skapa en annan med valfritt namn.

   ![](assets/ip-pool-edit.png)

   >[!CAUTION]
   >
   >Fortsätt med extra omsorg när du funderar på att ta bort en IP-adress, eftersom detta medför ytterligare belastning på de andra IP-adresserna och kan få allvarliga konsekvenser för leveransen. Om du är osäker kan du kontakta en expert på slutprodukter.

1. Spara ändringarna.

Uppdateringen träder i kraft omedelbart eller asynkront, beroende på vilken IP-pool som är associerad med en [kanalyta](channel-surfaces.md) eller inte:

* Om IP-poolen är **not** som är associerad med valfri kanalyta, uppdateras omedelbart (**[!UICONTROL Success]** status).
* Om IP-poolen **är** som är kopplad till en kanalyta kan uppdateringen ta upp till 3 timmar (**[!UICONTROL Processing]** status).

>[!NOTE]
>
>När [skapa en kanalyta](channel-surfaces.md#create-channel-surface), om du väljer en IP-pool som ingår i utgåvan (**[!UICONTROL Processing]** status) och aldrig har associerats med den underdomän som har valts för den ytan, kan du inte fortsätta med att skapa en yta. [Läs mer](channel-surfaces.md#subdomains-and-ip-pools)

Om du vill kontrollera IP-poolens uppdateringsstatus klickar du på **[!UICONTROL More actions]** och markera **[!UICONTROL Recent updates]**.

![](assets/ip-pool-recent-update.png)

>[!NOTE]
>
>När en IP-pool har uppdaterats kan du behöva vänta:
>* några minuter innan det konsumeras av enhetsmeddelanden,
>* till nästa batch för att IP-poolen ska börja gälla i batchmeddelanden.


Du kan också använda **[!UICONTROL Delete]** för att ta bort en IP-pool. Observera att du inte kan ta bort en IP-pool som har kopplats till en kanalyta.

