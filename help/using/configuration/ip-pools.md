---
title: Skapa IP-pooler
description: '"Lär dig hantera IP-pooler"'
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Applikationsinställningar
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 1%

---


# Skapa IP-pooler

## Om IP-pooler

Med Journey Optimizer kan du skapa IP-pooler för att gruppera IP-adresserna för dina underdomäner.

Vi rekommenderar starkt att du skapar IP-pooler för e-postleverans. På så sätt kan du förhindra att en underdomän får ett anseende som påverkar dina andra underdomäner.

Ett exempel är att ha en IP-pool för dina marknadsföringsmeddelanden och en annan för dina transaktionsmeddelanden. På så sätt påverkas inte transaktionsmeddelanden som skickas till samma kund om ett av dina marknadsföringsmeddelanden fungerar dåligt och deklareras som skräppost av en kund, som fortfarande får transaktionsmeddelanden (inköpsbekräftelser, meddelanden om återställning av lösenord osv.).

## Skapa en IP-pool

Så här skapar du en IP-pool:

1. Gå till menyn **[!UICONTROL Channels]** / **[!UICONTROL IP pools]** och klicka sedan på **[!UICONTROL Create IP Pool]**.

   ![](../assets/ip-pool-create.png)

1. Ange ett namn och en beskrivning (valfritt) för IP-poolen.

   >[!NOTE]
   >
   >Underdomänens namn måste börja med en bokstav (A-Z) och endast innehålla alfanumeriska tecken eller specialtecken ( _, ., - ).

1. Välj de IP-adresser som ska ingå i poolen i listrutan och klicka sedan på **[!UICONTROL Submit]**.

   ![](../assets/ip-pool-config.png)

   >[!NOTE]
   >
   >Alla IP-adresser som har etablerats med din instans är tillgängliga i listan.

IP-poolen skapas nu och visas i listan. Du kan markera den för att komma åt dess egenskaper och visa den tillhörande meddelandeförinställningen. Mer information om hur du associerar en meddelandeförinställning med en IP-pool finns i [det här avsnittet](message-presets.md)).

![](../assets/ip-pool-created.png)

Om du vill redigera en IP-pool öppnar du den och redigerar sedan egenskaperna för den.

>[!NOTE]
>
>Om en meddelandeförinställning har kopplats till IP-poolen måste du först ta bort den innan du redigerar IP-poolen. När ändringarna är klara kan du koppla meddelandeförinställningen igen.
