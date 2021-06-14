---
title: Konfigurera ett push-meddelande
description: Lär dig hur du skapar ett push-meddelande i Journey Optimizer
feature: Översikt
topic: Innehållshantering
role: User
level: Beginner
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 10%

---

# Skapa ett push-meddelande {#create-push-notification}

![](assets/do-not-localize/badge.png)

När du har [skapat ett meddelande](create-message.md) klickar du på fliken **[!UICONTROL Push Notification]** för att definiera inställningar och innehåll för push-meddelandet.

![](assets/create-content-push.png)

Använd de dedikerade flikarna för att definiera inställningar för push-meddelanden för operativsystemen **iOS** och **Android**.

>[!NOTE]
>
>Avsnittet **[!UICONTROL Compose Message]** är gemensamt för flikarna **[!UICONTROL iOS]** och **[!UICONTROL Android]**. Alla ändringar i det här avsnittet gäller båda flikarna.

## Titel och brödtext

Klicka på fälten **[!UICONTROL Title]** och **[!UICONTROL Body]** för att skapa meddelandet. Använd uttrycksredigeraren för att definiera innehåll och personaliseringsdata. Läs mer om personalisering i uttrycksredigeraren i [det här avsnittet](personalization/personalize.md)

Använd det centrala avsnittet för att visualisera hur push-meddelanden visas på iOS- och Android-enheter.

## Vid klickbeteende {#on-click-behavior}

Välj beteende när en mottagare klickar på texten i push-meddelandet.

![](assets/title-body-push.png)

* Använd alternativet **[!UICONTROL Open app]** för att öppna programmet som är associerat med meddelandet **[!UICONTROL Preset]**.
* Använd alternativet **[!UICONTROL Deeplink]** för att dirigera om mottagaren till ett visst innehåll som finns inuti programmet. Ange länken till länken i det associerade fältet.
* Använd alternativet **[!UICONTROL Web URL]** för att dirigera om mottagaren till en extern URL. Ange URL-adressen i det associerade fältet.

## Lägg till media

I iOS-versionen av ditt push-meddelande kan du lägga till en bild, en video eller en GIF-fil som visas i meddelandet.

I Android-versionen kan du bara lägga till en bildikon och en bild för utökade meddelanden.

![](assets/push-config-add-media.png)

Det finns två alternativ. Ni kan:

* Klicka på knappen **[!UICONTROL Add media]** för att välja en resurs i **[!DNL Adobe Experience Manager Assets Essentials]**.

   Lär dig hur du använder **[!DNL Adobe Experience Manager Assets Essentials]** i [den här sidan](assets-essentials.md).

* Du kan också ange mediets URL genom att klicka på fältet **[!UICONTROL Add media]**. I så fall kan ni lägga till personalisering.

När mediet har lagts till visas det till höger om meddelandetexten.


## Lägg till knappar

Du kan skapa ett användbart meddelande genom att lägga till knappar i ditt push-innehåll.

Om enhetsskärmen är låst visas inte dessa knappar: Endast **titeln** och **meddelandet** för meddelandet visas. Om enheten är olåst ser mottagarna knapparna.

I iOS-versionen kan du lägga till upp till fyra knappar. I Android-versionen kan du lägga till upp till tre knappar.

Klicka på **[!UICONTROL Add button]** för att definiera inställningar: etiketten och tillhörande åtgärd. Möjliga åtgärder är desamma som för [klickbeteendet](#on-click-behavior).


>[!NOTE]
>
>För iOS använder du fältet **[!UICONTROL iOS category]** för att associera åtgärder med en meddelandekategori.


## Skicka ett tyst meddelande

Ett tyst push-meddelande (eller bakgrundsmeddelande) är en dold instruktion som skickas till programmet. Den används till exempel för att meddela programmet om att nytt innehåll är tillgängligt eller för att initiera en hämtning i bakgrunden.

Välj alternativet **[!UICONTROL Silent Notification]** för att tyst meddela programmet: I detta fall överförs anmälan direkt till ansökan. Ingen varning visas på enhetsskärmen.

Använd avsnittet **[!UICONTROL Custom data]** för att lägga till nyckel/värde-par.

## Anpassade data

I avsnittet **[!UICONTROL Custom data]** kan du lägga till anpassade variabler i nyttolasten, beroende på din mobilprogramkonfiguration. Mer information om hur du ställer in push-meddelanden i Adobe Experience Platform och Adobe Launch finns i [det här avsnittet](push-gs.md)

## Avancerade alternativ

Du kan konfigurera **[!UICONTROL Advanced options]** för ditt push-meddelande. Tillgängliga parametrar visas nedan:

| Parameter | Beskrivning |
|---------|---------|
| **[!UICONTROL Collapsible]** (iOS / Android) | Ett komprimerbart meddelande är ett meddelande som kan ersättas av ett nytt. Ett program som till exempel uppdaterar användarna med de senaste nyheterna om ett ämne. I så fall är det bara det senaste meddelandet som är relevant. Å andra sidan, med icke-komprimeringsbara meddelanden, är alla meddelanden viktiga för klientappen och måste levereras. |
| **[!UICONTROL Custom sound]** (iOS / Android) | Det ljud som ska spelas upp av mobilterminalen när meddelandet tas emot. Ljudet måste paketeras i appen. |
| **[!UICONTROL Badges]** (iOS / Android) | Ett märke används för att visa antalet nya olästa uppgifter direkt på programikonen. <br/>Märkesvärdet försvinner när användaren öppnar eller läser det nya innehållet från programmet. När ett meddelande tas emot på en enhet kan det uppdatera eller lägga till ett märkesvärde för den relaterade appen.<br/>Om du till exempel lagrar antalet olästa artiklar för dina kunder kan du använda personalisering för att skicka det unika märket för olästa artiklar för varje kund. Mer personalisering finns i [det här avsnittet](personalization/personalize.md). |
| **[!UICONTROL Notification group]**  (endast iOS) | Associera en meddelandegrupp med push-meddelandet.<br/>Från och med iOS 12 kan du med meddelandegrupper konsolidera meddelandetrådar och meddelandeämnen i trådar-ID:n. Ett varumärke kan t.ex. skicka marknadsföringsmeddelanden under ett grupp-ID samtidigt som det behåller fler typmeddelanden under ett eller flera olika ID:n.<br/>Om du vill illustrera detta kan du ha groupID: 123&quot;kolla in den nya vårsamlingen av tröjor&quot; och grupp-ID: 456 Meddelandegrupper för&quot;ditt paket levererades&quot;. I det här exemplet paketeras alla leveransmeddelanden under grupp-ID: 456. |
| **[!UICONTROL Notification channel]** (Endast Android) | Koppla en meddelandekanal till push-meddelandet.<br/>Från och med Android 8.0 (API-nivå 26) måste alla meddelanden tilldelas en kanal för att kunna visas. Mer information finns i [dokumentationen för Android-utvecklare](https://developer.android.com/guide/topics/ui/notifiers/notifications#ManageChannels). |
| **[!UICONTROL Add content-availability flag]** (endast iOS) | Skickar flaggan för tillgängligt innehåll i push-nyttolasten för att säkerställa att appen aktiveras så fort den får push-meddelandet, vilket innebär att appen kan komma åt nyttolastdata.<br/> Detta fungerar även om appen körs i bakgrunden och utan att användaren behöver göra något (t.ex. trycka på ett push-meddelande). Detta gäller dock inte om programmet inte körs. Mer information om detta hittar du i [Apples dokumentation för utvecklare](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| **[!UICONTROL Add mutable-content flag]** (endast iOS) | Skickar flaggan för ändringsbart innehåll i push-nyttolasten och tillåter att push-meddelandeinnehållet ändras med ett meddelandetjänstprogramtillägg som tillhandahålls i iOS SDK. Mer information om detta hittar du i [Apples dokumentation för utvecklare](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).<br/>Du kan sedan utnyttja dina mobilappstillägg för att ytterligare ändra innehållet i eller presentationen av inkommande push-meddelanden som skickas från  [!DNL Journey Optimizer] Användare kan till exempel utnyttja det här alternativet för att dekryptera data, ändra brödtexten eller titeltexten i ett meddelande, lägga till en trådidentifierare i ett meddelande osv. |
| **[!UICONTROL Notification visibility]** (Endast Android) | Anger om push-meddelandet ska visas. <br/><b>Privatpersoner </b> visar meddelandet på alla låsskärmar, men döljer känslig eller privat information på säkra låsskärmar. <br/><b>Meddelandet </b> visas i sin helhet på alla låsskärmar. <br/><b>Sekretessen </b> visar inte någon del av meddelandet på en säker låsskärm. <br/>Mer information finns i dokumentationen [ för ](https://developer.android.com/reference/android/app/Notification)Android-utvecklare. |
| **[!UICONTROL Notification priority]** (Endast Android) | Definierar push-meddelandets prioritet från Låg till Max. Detta avgör hur påträngande push-meddelandet blir när det levereras. Mer information finns i [dokumentationen till Android-utvecklare](https://developer.android.com/guide/topics/ui/notifiers/notifications#importance) |
| **[!UICONTROL Delivery priority]** (Endast Android) | Ställer in hög eller normal prioritet för dina push-meddelanden. Mer information om meddelandeprioritet finns i [Googles dokumentation för utvecklare](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message). |


**Relaterade ämnen**

<!--
* [Understand push notification flow](push-gs.md)
-->

* [Konfigurera push-kanal](push-gs.md)
* [Skapa ett nytt meddelande](create-message.md)
* [Lägg till ett meddelande i en resa](building-journeys/journeys-message.md)

