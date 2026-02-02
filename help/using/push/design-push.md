---
solution: Journey Optimizer
product: journey optimizer
title: Utforma ett push-meddelande
description: Lär dig hur du utformar ett push-meddelande i Journey Optimizer
feature: Push
topic: Content Management
role: User
level: Beginner
exl-id: 6f6d693d-11f2-48b7-82a8-171829bf8045
source-git-commit: 083545ff7b2dc5ce45ef3766321fdf12e1b96c5c
workflow-type: tm+mt
source-wordcount: '1775'
ht-degree: 3%

---

# Utforma ett push-meddelande {#design-push-notification}

När du har skapat ett push-meddelande kan du utforma dess innehåll för iOS- och Android-plattformar. På den här sidan får du hjälp med att komponera ditt meddelande, konfigurera klickbeteenden, lägga till media och knappar och ange avancerade alternativ för att skapa engagerande push-meddelanden som får genklang hos publiken.

## Titel och brödtext {#push-title-body}

>[!CONTEXTUALHELP]
>id="ajo-message-push-compose"
>title="Anpassa ditt push-meddelande."
>abstract="Skriv innehållet i fälten **Titel** och **Brödtext** för att skapa meddelandet. Om du vill ta med personaliseringstoken öppnar du dialogrutan för personalisering."

![](assets/title-body.png)

Klicka på fälten **[!UICONTROL Title]** och **[!UICONTROL Body]** för att skapa meddelandet. Använd personaliseringsredigeraren för att definiera innehåll, personalisera data och lägga till dynamiskt innehåll. Läs mer om [personalisering](../personalization/personalize.md) och [dynamiskt innehåll](../personalization/get-started-dynamic-content.md) i personaliseringsredigeraren.

Använd enhetens förhandsgranskningssektion för att se hur push-meddelanden visas på iOS och Android.

Snabba upp skapandet av ditt innehåll med AI Assistant och generera övertygande push-meddelanden med [AI Assistant för textgenerering](../content-management/generative-text.md) eller skapa kompletta push-meddelanden med [AI Assistant för generering av fullständigt innehåll](../content-management/generative-full-content.md).

## Beteende vid klickning {#on-click-behavior}

>[!CONTEXTUALHELP]
>id="ajo-message-push-onclick"
>title="Om klickbeteende"
>abstract="Välj beteende när en mottagare klickar på texten i push-meddelandet."

Konfigurera den åtgärd som ska utföras när mottagarna trycker på texten i push-meddelandet. Välj bland följande alternativ:

![](assets/title-body-push.png)

* **[!UICONTROL Open app]**: Startar programmet som är associerat med meddelandet. Appen anges i din [kanalkonfiguration](../configuration/channel-surfaces.md) (d.v.s. meddelandeförinställning).
* **[!UICONTROL Deeplink]**: dirigerar användare till specifikt innehåll i din app, till exempel en viss vy, ett visst sidavsnitt eller en viss flik. Ange URL-adressen för överordnad länk i fältet.
* **[!UICONTROL Web URL]**: dirigerar användare till en extern webbsida. Ange mål-URL i det angivna fältet.

## Lägg till media {#add-media-push}

>[!CONTEXTUALHELP]
>id="ajo-message-push-media"
>title="Lägg till media i ditt push-meddelande"
>abstract="Du kan lägga till en bild, en video eller en GIF som visas i meddelandet."

Förbättra dina push-meddelanden genom att lägga till visuella medier. Tillgängliga medietyper och implementeringsmetoder varierar beroende på operativsystem, vilket visas på flikarna nedan.

>[!BEGINTABS]

>[!TAB Android]

I Android kan du bara lägga till en bildikon och en bild för utökade meddelanden.

![](assets/push-config-add-media.png)

Du kan lägga till media på något av följande sätt:

* **[!UICONTROL Add media]**-knapp: Välj en resurs från [Adobe Experience Manager Assets](../integrations/assets.md) eller öppna AI-assistenten för att generera [engagerande bilder](../content-management/generative-image.md) för push-meddelanden.

* **[!UICONTROL Add media]**-fält: Ange medie-URL:en direkt. Du kan inkludera personaliseringstoken i URL:en.

När mediet har lagts till visas det till höger om meddelandetexten.

>[!NOTE]
>
>När du inkluderar mediebilagor i nyttolasten för push-meddelanden (till exempel bilder i anpassade datafält som `adb_media`), måste ditt mobilprogram implementera en specifik hantering på klientsidan för bilderna som ska återges på enheter. Ditt program måste implementera det [automatiska arbetsflödet för visning och spårning](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/push-notification/android/automatic-display-and-tracking/){target="_blank"} för att hantera bildbilagor från nyttolasten.

>[!TAB iOS]

För iOS kan du lägga till en bild, video eller GIF som ska visas i ditt meddelande.

![](assets/push-config-add-media-ios.png)

Du kan lägga till media på något av följande sätt:

* **[!UICONTROL Add media]**-knapp: Välj en resurs från **[!DNL Adobe Experience Manager Assets]**. Läs mer om hur du använder **[!DNL Adobe Experience Manager Assets]** på [den här sidan](../integrations/assets.md).

* **[!UICONTROL Add media]**-fält: Ange medie-URL:en direkt. Du kan inkludera personaliseringstoken i URL:en.

När mediet har lagts till visas det till höger om meddelandetexten.

>[!NOTE]
>
>När du inkluderar mediebilagor i nyttolasten för push-meddelanden (till exempel bilder i anpassade datafält som `adb_media`), måste ditt mobilprogram implementera en specifik hantering på klientsidan för bilderna som ska återges på enheter. Din app måste implementera ett [Notification Service-tillägg](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications){target="_blank"} för att kunna hämta och bearbeta medieinnehåll från nyttolasten. Dessutom måste alternativet **[!UICONTROL Add mutable-content flag]** aktiveras i avsnittet [Avancerade alternativ](#advanced-options-push).

<!--
>[!TAB Web]

Enter the media URL in the **[!UICONTROL Add media]** field. You can also include personalization tokens in the URL to customize the content for each user.

Click ![Edit text with the AI assistant](assets/do-not-localize/Smock_ImageAdd_18_N.svg) to quickly generate media using the Journey Optimizer AI Assistant.

![](assets/web-media.png)
-->

>[!ENDTABS]

## Lägg till knappar {#add-buttons-push}

>[!CONTEXTUALHELP]
>id="ajo-message-push-buttons"
>title="Lägg till knappar så att användarna kan interagera med push-meddelanden."
>abstract="I det här avsnittet lägger du till call-to-action-knappar i meddelandet. Ange en meddelandekategoriidentifierare för Apple iOS. För Google Android kan du inkludera anpassad text och mål för varje knapp."

Skapa ett användbart meddelande genom att lägga till knappar i ditt push-innehåll. Bläddra bland flikarna nedan baserat på ditt operativsystem.

Om enhetsskärmen är låst visas inte dessa knappar: bara **Rubrik** och **Meddelande** i meddelandet visas. Om enheten är olåst ser mottagarna knapparna.

>[!BEGINTABS]

>[!TAB Android]

För Android kan du lägga till upp till tre knappar.

1. Använd **[!UICONTROL Add button]** för att definiera inställningar: etiketten och den associerade åtgärden. Möjliga åtgärder är desamma som för [klickbeteendet](#on-click-behavior).

   ![](assets/push_buttons.png)

1. Använd ikonen **[!UICONTROL Expand view]** under den centrala förhandsvisningsbilden för att förhandsgranska dina anpassade knappar.

>[!TAB iOS]

![](assets/push_buttons-ios.png)

För iOS anges en meddelandekategoriidentifierare. Meddelandekategorier måste vara förkonfigurerade i iOS-appen, som definierar vilka knappar som ska visas och vilka åtgärder som ska vidtas. Mer information finns i [Apple-dokumentationen](https://developer.apple.com/documentation/usernotifications/declaring_your_actionable_notification_types).

<!--
>[!TAB Web]

![](assets/push_buttons-web.png)

Use the **[!UICONTROL Add Button]** option to define each button's label and associated action, as detailed below:

* **[!UICONTROL Deeplink]**: Redirect users to a specific view, section, or tab within your app. Enter the deeplink URL in the associated field.

* **[!UICONTROL Web URL]**: Redirect users to an external webpage. Enter the URL in the associated field.
-->

>[!ENDTABS]

## Skicka ett tyst meddelande {#silent-notification}

>[!CONTEXTUALHELP]
>id="ajo_message_push_silent_notification"
>title="Om tyst meddelande"
>abstract="Skicka meddelanden utan att störa användaren. Meddelanden visas inte i meddelandecentret eller meddelandefältet."

<!--
>[!AVAILABILITY]
>
>Web push notifications in Journey Optimizer do not support the **Silent Notification** feature.
-->

Ett tyst push-meddelande (eller bakgrundsmeddelande) är en dold instruktion som skickas till programmet. Den används till exempel för att meddela programmet om att nytt innehåll är tillgängligt eller för att initiera en nedladdning i bakgrunden.

Välj alternativet **[!UICONTROL Silent Notification]** om du vill meddela programmet tyst: i det här fallet överförs meddelandet direkt till programmet. Ingen varning visas på enhetsskärmen.

Använd avsnittet **[!UICONTROL Custom data]** för att lägga till nyckelvärdepar.

## Anpassade data {#custom-data}

>[!CONTEXTUALHELP]
>id="ajo-message-push-custom"
>title="Konfigurera anpassade data för push-meddelanden."
>abstract="Lägg till anpassade variabler i nyttolasten, beroende på din mobilprogramkonfiguration."

I avsnittet **[!UICONTROL Custom data]** kan du lägga till anpassade variabler i nyttolasten, beroende på din mobilprogramkonfiguration. Mer information om hur du ställer in push-meddelanden i Adobe Experience Platform finns i [det här avsnittet](push-gs.md)

## Personalisera med Experience Decision {#decisioning-push}

Du kan anpassa och optimera innehållet i dina push-meddelanden med **Experience Decision**. Med den här funktionen kan ni använda prioriteringspoäng, formler eller AI-modeller för att dynamiskt välja och visa det bästa innehållet för era kunder.

Mer information om hur du skapar och använder beslutsprinciper i push-meddelanden finns i [det här avsnittet](../experience-decisioning/create-decision.md).

## Avancerade alternativ {#advanced-options-push}

>[!CONTEXTUALHELP]
>id="ajo-message-push-advanced"
>title="Konfigurera avancerade alternativ för push-meddelanden."
>abstract="I det här avsnittet kan du förbättra personaliseringen av ditt push-meddelande."

Du kan konfigurera **[!UICONTROL Advanced options]** för ditt push-meddelande. Tillgängliga parametrar visas nedan:

| Parameter | Beskrivning |
|---------|---------|
| **[!UICONTROL Collapsible]** (iOS/Android) | Ett komprimerbart meddelande är ett meddelande som kan ersättas av ett nytt meddelande om det har blivit inaktuellt. Ett vanligt användningsfall för komprimerbara meddelanden är meddelanden som används för att instruera en mobilapp att synkronisera data från servern. Ett exempel är en sportapp som uppdaterar användare med den senaste poängen. Endast det senaste meddelandet är relevant. Å andra sidan, med icke-komprimeringsbart meddelande, är alla meddelanden viktiga för klientappen och måste levereras. |
| **[!UICONTROL Custom sound]** (iOS/Android) | Det ljud som ska spelas upp av mobilterminalen när meddelandet tas emot. Ljudet måste paketeras i appen. |
| **[!UICONTROL Badges]** (iOS/Android) | Ett märke används för att visa antalet nya olästa uppgifter direkt på programikonen. <br/>Värdet för märket försvinner när användaren öppnar eller läser det nya innehållet från programmet. När ett meddelande tas emot på en enhet kan det uppdatera eller lägga till ett badge-värde för den relaterade appen.<br/>Om du till exempel lagrar antalet olästa artiklar för dina kunder kan du använda personalisering för att skicka det unika värdet för olästa artiklar för varje kund. Mer personalisering finns i [det här avsnittet](../personalization/personalize.md). |
| **[!UICONTROL Notification group]** (endast iOS) | Associera en meddelandegrupp med push-meddelandet.<br/>Från och med iOS 12 kan du med meddelandegrupper konsolidera meddelandetrådar och meddelandeämnen i kopplade ID:n. Ett varumärke kan t.ex. skicka marknadsföringsmeddelanden under ett grupp-ID samtidigt som det behåller fler typmeddelanden under ett eller flera olika ID:n.<br/>För att illustrera detta kan du ha groupID: 123&quot;check out the new spring collection of sweaters&quot; och groupID: 456&quot;your package was delivery&quot; notification groups. I det här exemplet paketeras alla leveransmeddelanden under grupp-ID: 456. |
| **[!UICONTROL Notification channel]** (endast Android) | Koppla en meddelandekanal till push-meddelandet.<br/>Från och med Android 8.0 (API-nivå 26) måste alla meddelanden tilldelas en kanal för att kunna visas. Mer information finns i [dokumentationen för Android-utvecklare](https://developer.android.com/guide/topics/ui/notifiers/notifications#ManageChannels). |
| **[!UICONTROL Add content-availability flag]** (endast iOS) | Skickar flaggan för tillgängligt innehåll i push-nyttolasten för att säkerställa att appen aktiveras så fort den får push-meddelandet, vilket innebär att appen kan komma åt nyttolastdata.<br/> Detta fungerar även om appen körs i bakgrunden och utan att någon användarinteraktion behövs (t.ex. när användaren trycker på ett push-meddelande). Detta gäller dock inte om programmet inte körs. Mer information om detta hittar du i [Apples dokumentation för utvecklare](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| **[!UICONTROL Add mutable-content flag]** (endast iOS) | Skickar flaggan för ändringsbart innehåll i push-nyttolasten och tillåter att push-meddelandeinnehållet ändras med ett meddelandetjänsttillägg som tillhandahålls i iOS SDK. Mer information om detta hittar du i [Apples dokumentation för utvecklare](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).<br/>Du kan sedan använda dina mobilappstillägg för att ytterligare ändra innehållet eller presentationen för inkommande push-meddelanden som skickas från [!DNL Journey Optimizer]. Användare kan till exempel utnyttja det här alternativet för att dekryptera data, ändra brödtexten eller titeltexten i ett meddelande, lägga till en trådidentifierare i ett meddelande osv.<br/>**Viktigt**: Den här flaggan måste aktiveras när mediebilagor (bilder, videor) via nyttolastfält (till exempel `adb_media`) inkluderas för återgivning på iOS-enheter. Din app måste också implementera ett meddelandetjänsttillägg för att kunna hämta och bearbeta medieinnehållet från nyttolasten. |
| **[!UICONTROL Add Push expiration]** (endast iOS) | Välj **Datum och tid** för din push-förfallotid. På iOS används meddelandets förfallodatum som en stoppåtgärd, vilket innebär att meddelanden som når Apple Push Notification Service (APNS) efter att förfallotiden inte levereras, vilket säkerställer att kunderna aldrig får inaktuella eller irrelevanta meddelanden. Mer information om detta hittar du i [Apples dokumentation för utvecklare](https://developer.apple.com/documentation/usernotifications/sending-notification-requests-to-apns). |
| **[!UICONTROL Notification visibility]** (endast Android) | Anger om push-meddelandet ska visas. <br/><b>Privat</b> visar meddelandet på alla låsskärmar, men döljer känslig eller privat information på säkra låsskärmar. <br/><b>Offentlig</b> visar meddelandet i sin helhet på alla låsskärmar. <br/><b>Hemlighet</b> visar inte någon del av meddelandet på en säker låsskärm. <br/>Mer information finns i [dokumentationen för Android-utvecklare](https://developer.android.com/reference/android/app/Notification). |
| **[!UICONTROL Notification priority]** (endast Android) | Definierar push-meddelandets prioritet från Låg till Max. Detta avgör hur påträngande push-meddelandet blir när det levereras. Mer information finns i [Android utvecklardokumentation](https://developer.android.com/guide/topics/ui/notifiers/notifications#importance) |
| **[!UICONTROL Delivery priority]** (endast Android) | Ställer in hög eller normal prioritet för dina push-meddelanden. Mer information om meddelandeprioritet finns i [Googles dokumentation för utvecklare](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message). |
| **[!UICONTROL Time to live]** (endast Android) | Ange antalet sekunder som meddelandet ska förfalla. I Android behandlas förfallodatum som ett leveransfönster: i Firebase Cloud Messaging (FCM) konverteras förfallotiden till ett TTL-värde (time-to-live) som börjar när meddelandet tas emot, vilket innebär att olevererade kampanjer kan skickas senare än förväntat eller till och med utanför den önskade tidsramen. Mer information finns i [dokumentationen för Android-utvecklare](https://firebase.google.com/docs/cloud-messaging/concept-options#ttl). |
