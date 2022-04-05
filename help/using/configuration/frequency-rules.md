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
source-git-commit: 1d0e28583c500d5eddf9f88250f279d188c4784a
workflow-type: tm+mt
source-wordcount: '721'
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
   >För närvarande bara **[!UICONTROL Marketing]** finns tillgänglig.

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

När en regel för meddelandefrekvens skapas har den **[!UICONTROL Draft]** status och påverkar inte ännu något meddelande. Om du vill aktivera den klickar du på ellipsen bredvid regeln och väljer **[!UICONTROL Activate]**.

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

Följ stegen nedan för att tillämpa en frekvensregel på ett meddelande.

1. Skapa ett meddelande. [Läs mer](../messages/get-started-content.md#create-new-message)

1. Välj den kategori som du har definierat för [regel som du skapade](#create-new-rule).

   ![](assets/message-rules-msg-properties.png)

   >[!NOTE]
   >
   >För närvarande bara **[!UICONTROL Marketing]** finns för regler för meddelandefrekvens.

1. Välj den eller de kanaler du vill använda för meddelandet.

   ![](assets/message-rules-msg-channels.png)

1. Du kan klicka på **[!UICONTROL Frequency rule]** om du vill visa de frekvensregler som gäller för den valda kategorin och de valda kanalerna.

   ![](assets/message-rules-msg-link.png)

   En ny flik öppnas för att visa matchande regler för meddelandefrekvens.

1. [Design](../design/design-emails.md) och [publicera](../messages/publish-manage-message.md) ditt meddelande.

Alla frekvensregler som matchar den valda kategorin och kanalen/kanalerna tillämpas automatiskt på det här meddelandet.

<!--Clicking the link out button next to the category selector will jump you over to the rules inventory screen to see which rules will be applied to the message.-->

Du kan visa antalet profiler som har uteslutits från leverans i [Live- och globala vyer](../reports/message-monitoring.md)och i [e-postLive-rapport](../reports/email-live-report.md), där frekvensreglerna listas som en möjlig orsak för användare som inte får leverera.

## Exempel: kombinera flera regler {#frequency-rule-example}

Du kan kombinera flera regler för meddelandefrekvens, som beskrivs i exemplet nedan.

1. [Skapa en regel](#create-new-rule) anropad *Total marknadsföringstak*:

   * Markera alla kanaler (e-post, push).
   * Ange begränsning till 12.

   ![](assets/message-rules-ex-overall-cap.png)

1. Om du vill begränsa antalet marknadsföringsbaserade push-meddelanden som en användare skickas vidare skapar du en andra regel som kallas *Push Marketing Cap*:

   * Välj Push-kanal.
   * Ställ in capping på 4.

   ![](assets/message-rules-ex-push-cap.png)

1. Spara och [activate](#activate-rule) regeln.

1. Skapa ett meddelande. [Läs mer](../messages/get-started-content.md#create-new-message)

1. Välj **[!UICONTROL Marketing]** kategori.

   ![](assets/message-rules-ex-category-maktg.png)

1. Välj **[!UICONTROL Email]** och **[!UICONTROL Push Notification]** kanaler.

   ![](assets/message-rules-ex-channels.png)

1. Du kan klicka på **[!UICONTROL Frequency rule]** om du vill visa de frekvensregler som gäller för den valda kategorin och de valda kanalerna.

1. [Design](../design/design-emails.md) och [publicera](../messages/publish-manage-message.md) ditt meddelande.

I det här scenariot finns en enskild profil:
* kan ta emot upp till 12 marknadsföringsmeddelanden per månad,
* men utesluts från push-meddelanden om marknadsföring när de har fått 4 push-meddelanden.
