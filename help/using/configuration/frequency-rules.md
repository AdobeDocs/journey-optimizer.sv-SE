---
title: Frekvensregler
description: Lär dig hur du definierar frekvensregler
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 49248fb6-5a91-45b2-9de8-2f078d59c0fc
source-git-commit: 40c42303b8013c1d9f4dd214ab1acbec2942e094
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Regler för meddelandefrekvens {#frequency-rules}

[!DNL Journey Optimizer] Med kan du styra hur ofta användare ska få ett meddelande eller delta i en resa genom att ställa in flerkanalsregler som automatiskt utesluter överbegärda profiler från meddelanden och åtgärder.

Ni vill till exempel inte att ert varumärke ska skicka mer än tre marknadsföringsmeddelanden per månad till sina kunder.

För att göra detta kan du använda en frekvensregel som begränsar antalet meddelanden som skickas baserat på en eller flera kanaler under en månadskalenderperiod.

>[!NOTE]
>
>Reglerna för meddelandefrekvens skiljer sig från reglerna för avanmälningshantering, som gör det möjligt för användare att avbryta prenumerationen från att ta emot meddelanden från ett varumärke. [Läs mer](../messages/consent.md#opt-out-management)

## Åtkomstregler {#access-rules}

Regler är tillgängliga från **[!UICONTROL Administration]** > **[!UICONTROL Rules]** -menyn. Alla regler visas sorterade efter ändringsdatum.

![](assets/message-rules-access.png)

<!--To access, create, edit or delete message frequency rules, you must have the message configuration permission. [Learn more](../administration/high-low-permissions.md#administration-permissions)-->

Använd filterikonen för att filtrera efter kategori, status och/eller kanal. Du kan också söka på meddelandeetiketten.

![](assets/message-rules-filter.png)

## Skapa en regel {#create-new-rule}

Följ stegen nedan för att skapa en ny regel.

1. Öppna **[!UICONTROL Message frequency rules]** lista och klicka sedan på **[!UICONTROL Create rule]**.

   ![](assets/message-rules-create.png)

1. Definiera regelnamnet.

   ![](assets/message-rules-details.png)

1. Välj meddelanderegelkategori.

   >[!NOTE]
   >
   >För närvarande bara **[!UICONTROL Marketing]** finns.

1. Ange begränsningen för regeln, vilket innebär det maximala antalet meddelanden som kan skickas till en enskild användarprofil varje månad.

   ![](assets/message-rules-capping.png)

   >[!NOTE]
   >
   >Frekvensgränsen baseras på en månatlig kalenderperiod. Den återställs i början av varje månad.

1. Markera kanalen som du vill använda för den här regeln: **[!UICONTROL Email]** eller **[!UICONTROL Push notification]**.

   ![](assets/message-rules-channels.png)

   >[!NOTE]
   >
   >Du måste markera minst en kanal för att kunna skapa regeln.

1. Markera flera kanaler om du vill tillämpa begränsning för alla markerade kanaler som ett totalt antal.

   Ange till exempel 15 som capping och markera både e-post- och push-kanalerna. Om en profil redan har fått 10 marknadsföringsmeddelanden och 5 push-meddelanden om marknadsföring, kommer den här profilen att uteslutas vid nästa leverans av marknadsföringsmeddelanden eller push-meddelanden.

1. Klicka **[!UICONTROL Save as draft]** för att bekräfta att regeln har skapats. Ditt meddelande läggs till i regellistan med **[!UICONTROL Draft]** status.

   ![](assets/message-rules-created.png)

## Aktivera en regel {#activate-rule}

Om du vill aktivera en regel för meddelandefrekvens klickar du på ellipsen bredvid regeln och väljer **[!UICONTROL Activate]**.

![](assets/message-rules-activate.png)

Om du aktiverar en regel påverkas alla meddelanden som gäller för nästa körning. Lär dig hur [tillämpa en frekvensregel på ett meddelande](#apply-frequency-rule).

>[!NOTE]
>
>Du behöver inte ändra eller publicera om meddelanden eller resor för att en regel ska börja gälla.

Om du vill inaktivera en regel för meddelandefrekvens klickar du på ellipsen bredvid regeln och väljer **[!UICONTROL Deactivate]**.

![](assets/message-rules-deactivate.png)

Regelens status ändras till **[!UICONTROL Inactive]** och regeln gäller inte för framtida meddelandekörningar. Meddelanden som körs just nu påverkas inte.

>[!NOTE]
>
>När du inaktiverar en regel påverkas eller återställs inte antalet enskilda profiler.

## Tillämpa en frekvensregel på ett meddelande {#apply-frequency-rule}

Om du vill tillämpa en frekvensregel på ett meddelande behöver du bara välja kategorin som du definierade för den här regeln när [skapar meddelandet](../messages/get-started-content.md#create-new-message).

![](assets/message-rules-properties.png)

Genom att välja **[!UICONTROL Marketing]** -kategori kommer alla matchande regler för meddelandefrekvens automatiskt att tillämpas på det här meddelandet.

<!--Clicking the link out button next to the category selector will jump you over to the rules inventory screen to see which rules will be applied to the message.-->

Du kan visa antalet profiler som har uteslutits från leverans i [Live- och globala vyer](../reports/message-monitoring.md)och i [e-postLive-rapport](../reports/email-live-report.md), där frekvensreglerna listas som en möjlig orsak för användare som inte får leverera.

## Exempel

Du kan kombinera flera regler för meddelandefrekvens, som beskrivs i exemplet nedan.

1. Skapa en anropad regel *Total marknadsföringstak*:

   * Markera alla kanaler (e-post, push).
   * Ange begränsning till 12.

1. Om du vill begränsa antalet marknadsföringsbaserade push-meddelanden som en användare skickas vidare skapar du en andra regel som kallas *Begränsa marknadsföringspush*:

   * Välj Push-kanal.
   * Ställ in capping på 4.

I det här scenariot kan en enskild profil ta emot upp till 12 marknadsföringsmeddelanden per månad, men de kommer inte att kunna skicka push-meddelanden efter att de har tagit emot 4 push-meddelanden.
