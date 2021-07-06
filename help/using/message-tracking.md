---
title: Spåra meddelanden
description: Lär dig hur du lägger till länkar och spårar skickade meddelanden
feature: Övervakning
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: f5a6a9b6c786b39b492a177de0b19a54b81729f7
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 1%

---

# Lägga till länkar och spåra meddelanden {#tracking}

Använd [!DNL Journey Optimizer] för att lägga till länkar till ditt innehåll och spåra skickade meddelanden för att övervaka mottagarnas beteende.

## Aktivera spårning {#enable-tracking}

Du kan aktivera spårning på meddelandenivå genom att kontrollera alternativen **[!UICONTROL Open Tracking for email]** och/eller **[!UICONTROL Click Tracking for email]** när [du skapar meddelandet](create-message.md).

![](assets/message-tracking.png)

>[!NOTE]
>
>Båda alternativen är aktiverade som standard.

På så sätt kan du spåra mottagarnas beteende via:
* **[!UICONTROL Open Tracking for email]**: Meddelanden som har öppnats.
* **[!UICONTROL Click Tracking for email]**: Klicka på länkar i ett e-postmeddelande.

## Infoga länkar {#insert-links}

När du utformar ett meddelande kan du lägga till länkar till innehållet.

>[!NOTE]
>
>När [spårning är aktiverat](#enable-tracking) spåras alla länkar som ingår i meddelandeinnehållet.

Följ stegen nedan om du vill infoga länkar i ditt e-postinnehåll:

1. Markera ett element och klicka på **[!UICONTROL Insert link]** i det sammanhangsberoende verktygsfältet.

   ![](assets/message-tracking-insert-link.png)

1. Välj den typ av länk som du vill skapa:

   * **[!UICONTROL External link]**: Infoga en länk till en extern URL.

   * **[!UICONTROL Unsubscription link]**: Infoga en länk för att avbeställa beställning av meddelanden från ert varumärke. Läs mer om hantering av avanmälan i [det här avsnittet](consent.md#opt-out-management).

   * **[!UICONTROL Mirror page]**: Infoga en länk för att visa e-postinnehållet i en webbläsare. Läs mer i [det här avsnittet](#mirror-page).

   ![](assets/message-tracking-links.png)

1. Du kan anpassa länkarna enbart med hjälp av ett enkelt uttryck. Läs mer om personalisering i [det här avsnittet](personalization/personalization-syntax.md).

1. Spara ändringarna.

1. När länken har skapats kan du fortfarande ändra den från rutan **[!UICONTROL Component settings]** till höger.

   * Klicka på pennikonen för att redigera länken.
   * Du kan välja att stryka under länken eller inte genom att markera motsvarande alternativ.

   ![](assets/message-tracking-link-settings.png)

## Länka till en spegelsida {#mirror-page}

Spegelsidan är en HTML-sida som är tillgänglig online via en webbläsare. Innehållet är identiskt med innehållet i ditt e-postmeddelande.

Om du vill lägga till en länk till en spegelsida i ditt e-postmeddelande [infogar du en länk](#insert-links) och väljer **[!UICONTROL Mirror page]** som typ av länk.

![](assets/message-tracking-mirror-page.png)

Spegelsidan skapas automatiskt.

>[!NOTE]
>
>Du kan inte redigera den automatiskt genererade länken.

När e-postmeddelandet har skickats visas innehållet i e-postmeddelandet i sin standardwebbläsare när mottagarna klickar på länken för spegelsidan.

>[!NOTE]
>
>I det [korrektur](preview.md#send-proofs) som skickas till testprofilerna är länken till spegelsidan inte aktiv. Den aktiveras endast i de slutliga meddelandena.

Kvarhållningsperioden för en spegelsida är 60 dagar. Efter den fördröjningen är spegelsidan inte längre tillgänglig.

## Hantera spårning {#manage-tracking}

Med [e-postdesignern](create-email-content.md) kan du hantera spårningsbara URL:er, till exempel redigera spårningstypen för varje länk.

1. Klicka på ikonen **[!UICONTROL Links]** i den vänstra rutan för att visa listan över alla URL:er för ditt innehåll som ska spåras.

   Med den här listan kan du ha en centraliserad vy och hitta varje URL i e-postinnehållet.

1. Om du vill redigera en länk klickar du på motsvarande pennikon.

   ![](assets/message-tracking-edit-links.png)

1. Du kan ändra **[!UICONTROL Tracking Type]** om det behövs:


   ![](assets/message-tracking-edit-a-link.png)

   För varje spårad URL kan du ange spårningsläget till något av följande värden:

   * **[!UICONTROL Tracked]**: Aktiverar spårning på denna URL.
   * **[!UICONTROL Opt out]**: Betraktar denna URL som en avanmälnings- eller avanmälnings-URL.
   * **[!UICONTROL Mirror page]**: Den här URL:en är en URL för en spegelsida.
   * **[!UICONTROL Never]**: Aktiverar aldrig spårning av den här URL:en.  <!--This information is saved: if the URL appears again in a future message, its tracking is automatically deactivated.-->

Antalet meddelanden som har öppnats och antalet länkar som har klickats visas på fliken [Körningar](message-monitoring.md).

Rapportering om öppningar och klick finns i [e-postLive-rapporten](reports/email-live-report.md) och i [e-postGlobal-rapporten](reports/email-global-report.md).


