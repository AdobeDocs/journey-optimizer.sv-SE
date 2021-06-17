---
title: Skapa ett meddelande
description: Lär dig hur du skapar ett meddelande
feature: Översikt
topic: Innehållshantering
role: User
level: Beginner
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 2%

---

# Skapa ett meddelande {#create-message}

Meddelanden är tillgängliga från genvägen **[!UICONTROL Messages]** till vänster. Alla meddelanden visas sorterade efter publiceringsdatum (för publicerade meddelanden) eller skapandedatum (för utkastmeddelanden).

>[!NOTE]
>
>Alla användare har tillgång till, kan skapa, redigera och publicera meddelanden. Läs mer om användarbehörigheter [i det här avsnittet](../using/administration/permissions.md).

![](assets/messages-list.png)

Använd växlingsknappen **[!UICONTROL Show recents]** för att lägga till direktlänkar till meddelanden som du har öppnat de senaste fem dagarna.

![](assets/show-recent-messages.png)

Använd filterikonen om du bara vill visa utkast, publicerade meddelanden eller meddelanden som publiceras. Du kan även söka på meddelandeetiketten enligt nedan:

![](assets/filter-messages.png)

## Skapa ett nytt meddelande

Följ stegen nedan för att skapa ett nytt meddelande:

1. Öppna meddelandelistan och klicka sedan på **[!UICONTROL Create Message]**.

1. Definiera meddelandeegenskaperna.

   ![](assets/create-message-properties.png)

   * Ange ett **[!UICONTROL Title]** (obligatoriskt) och ett **[!UICONTROL Description]**.

   * Välj **[!UICONTROL Preset]** som ska användas för meddelandet.

      Förinställningarna innehåller alla parametrar som krävs för att ett e-postmeddelande och/eller ett push-meddelande ska skickas enligt ert varumärke. [Läs mer om förinställningar](../using/configuration/message-presets.md).

   * Markera de kanaler som du vill använda för det meddelandet: E-post och/eller push-meddelanden. Du måste välja minst en kanal för att kunna skapa meddelandet.
   Observera att du när som helst kan komma åt och ändra meddelandets titel, beskrivning och förinställning med knappen **[!UICONTROL Properties]** i meddelandegränssnittet.

   ![](assets/message-properties.png)


1. Klicka på **[!UICONTROL Create]** för att bekräfta att meddelandet har skapats. Meddelandet läggs till i meddelandelistan i **[!UICONTROL Draft]**-statusen.

   En flik är tillgänglig för varje vald kanal. Använd dessa flikar för att konfigurera innehållet för varje kanal. Du kan ta bort en flik genom att markera den och klicka på knappen **[!UICONTROL Delete channel]** till höger.

   ![](assets/create-messages-content.png)

   Nu kan du skapa innehållet i meddelandet och anpassa inställningarna. Detaljerad information om konfigurationen av e-post och push-meddelanden finns i följande avsnitt:

   * [Skapa ett e-postmeddelande](create-email.md)
   * [Skapa push-meddelanden](create-push.md)

   >[!NOTE]
   >   
   >Du kan anpassa meddelanden med hjälp av profildata med uttrycksredigeraren. Mer information om anpassning finns i [det här avsnittet](personalization/personalize.md).


1. Styr återgivningen av meddelanden och kontrollera personaliseringsinställningarna med testprofiler med förhandsgranskningsavsnittet till vänster. Mer information om detta finns i [det här avsnittet](preview.md).

   ![](assets/messages-simple-preview.png)

1. Kontrollera varningar i den övre delen av redigeraren.  Vissa av dem är enkla varningar, men andra kan hindra dig från att publicera meddelandet. Läs mer i [det här avsnittet](alerts.md).

1. Du kan nu publicera ditt meddelande genom att klicka på knappen **[!UICONTROL Publish]** eller behålla det som ett utkast och publicera det senare. Mer information om hur du publicerar meddelanden finns i [det här avsnittet](publish-manage-message.md).

## Duplicera ett meddelande

Om du vill skapa ett meddelande från ett befintligt ska du använda knappen **[!UICONTROL Duplicate]** i meddelandegränssnittet. Alla inställningar och konfigurationer kopieras till det nya meddelandet

![](assets/message-duplicate.png)

Du kan byta namn på meddelandet innan du bekräftar duplicering.

![](assets/message-duplicate-confirm.png)

Ett bekräftelsemeddelande visas längst ned i fönstret när det nya meddelandet har skapats.

Du kan också duplicera ett meddelande från meddelandelistan med hjälp av den dedikerade ikonen.

![](assets/message-duplicate-from-list.png)

Samma bekräftelseprocess gäller.
