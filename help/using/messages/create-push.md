---
title: Konfigurera ett push-meddelande
description: Lär dig hur du skapar ett push-meddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 2ebbcd7d-dcfc-4528-974d-6230fc0dca3d
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 10%

---

# Skapa ett push-meddelande {#create-push-notification}

Push-meddelanden hjälper dig att nå mobilappsanvändare när som helst, särskilt när de inte aktivt använder din app. Push-meddelanden kan hjälpa dig att få en mängd olika användningsfall, som att tillhandahålla uppdateringar om tjänsten, be en användare att vidta åtgärder, varna användaren för ett nytt avtal osv. Enhetsplattformar kräver deltagande innan slutanvändarna kan ta emot eller visa dina meddelanden. Användaranmälan kan tas emot så snart appen startats för första gången efter installationen, eller i en efterföljande session eller arbetsflöde efter behov.

[!DNL Journey Optimizer] har stöd för push-meddelanden och hjälper dig att skicka mycket relevanta meddelanden med branschledande dataöverföringshastigheter. Push-meddelanden kan omfatta personalisering och resebaserade sammanhang för att utnyttja de datainsikter ert varumärke har med Adobe Experience Cloud.

En gång [skapade ett meddelande](create-message.md)klickar du på **[!UICONTROL Push Notification]** för att definiera inställningar och innehåll för push-meddelandet.

![](assets/create-content-push.png)

Använd de dedikerade flikarna för att definiera inställningar för push-meddelanden för **iOS** och **Android** operativsystem.

>[!NOTE]
>
>The **[!UICONTROL Compose Message]** -avsnittet är gemensamt för båda **[!UICONTROL iOS]** och **[!UICONTROL Android]** -tabbar. Alla ändringar i det här avsnittet gäller för båda inställningarna.

## Titel och brödtext {#push-title-body}

Klicka på knappen **[!UICONTROL Title]** och **[!UICONTROL Body]** fält. Använd uttrycksredigeraren för att definiera innehåll och personaliseringsdata. Läs mer om personalisering i Expression Editor i [det här avsnittet](../personalization/personalize.md)

Använd enhetens förhandsgranskningssektion för att visualisera hur push-meddelanden visas på iOS- och Android-enheter.

## Beteende vid klickning {#on-click-behavior}

>[!CONTEXTUALHELP]
>id="ajo-message-push-onclick"
>title="Om klickbeteende"
>abstract="Välj beteende när en mottagare klickar på texten i push-meddelandet."

Du kan välja beteende när en användare klickar på texten i push-meddelandet.

![](assets/title-body-push.png)

* Om du vill öppna appen väljer du **[!UICONTROL Open app]** alternativ. Appen som är associerad med meddelandet definieras i meddelandet **[!UICONTROL Preset]**. [Läs mer](../configuration/message-presets.md) om meddelandeförinställningar.
* Om du vill dirigera om användaren till en viss del av innehållet i en app väljer du **[!UICONTROL Deeplink]** alternativ.  Det specifika innehållet kan vara en specifik vy, ett visst avsnitt på en sida eller en viss flik. När alternativet är markerat anger du länken i det tillhörande fältet.
* Om du vill dirigera om användaren till en extern URL använder du **[!UICONTROL Web URL]** alternativ. När alternativet är markerat anger du URL-adressen i det associerade fältet.

## Lägg till media {#add-media-push}

I iOS-versionen av ditt push-meddelande kan du lägga till en bild, en video eller ett GIF som visas i meddelandet.

I Android-versionen kan du bara lägga till en bildikon och en bild för utökade meddelanden.

![](assets/push-config-add-media.png)

Det finns två alternativ. Du kan:

* Använd **[!UICONTROL Add media]** knapp för att välja en resurs i **[!DNL Adobe Experience Manager Assets Essentials]**.

   Lär dig använda **[!DNL Adobe Experience Manager Assets Essentials]** in [den här sidan](assets-essentials.md).

* Eller ange URL:en för mediet i **[!UICONTROL Add media]** fält. I så fall kan du lägga till personalisering i URL:en.

När mediet har lagts till visas det till höger om meddelandetexten.

## Lägg till knappar {#add-buttons-push}

Skapa ett användbart meddelande genom att lägga till knappar i ditt push-innehåll.

Om enhetsskärmen är låst visas inte dessa knappar: bara **Titel** och **Meddelande** om meddelandet visas. Om enheten är olåst ser mottagarna knapparna.

I iOS-versionen kan du lägga till upp till fyra knappar. I Android-versionen kan du lägga till upp till tre knappar.

>[!NOTE]
>
>För iOS använder du **[!UICONTROL iOS category]** fält för att associera åtgärder med en meddelandekategori.

1. Använd **[!UICONTROL Add button]** för att definiera inställningar: etiketten och tillhörande åtgärd. Möjliga åtgärder är desamma som för [klickbeteende](#on-click-behavior).

1. Använd **[!UICONTROL Expand view]** -ikonen under den centrala förhandsvisningsbilden för att förhandsgranska dina anpassade knappar.

![](assets/push_buttons.png)

## Skicka ett tyst meddelande {#silent-notification}

Ett tyst push-meddelande (eller bakgrundsmeddelande) är en dold instruktion som skickas till programmet. Den används till exempel för att meddela programmet om att nytt innehåll är tillgängligt eller för att initiera en nedladdning i bakgrunden.

Välj **[!UICONTROL Silent Notification]** möjlighet att tyst meddela ansökan: I detta fall överförs anmälan direkt till ansökan. Ingen varning visas på enhetsskärmen.

Använd **[!UICONTROL Custom data]** för att lägga till nyckelvärdepar.

## Anpassade data

I **[!UICONTROL Custom data]** kan du lägga till anpassade variabler i nyttolasten, beroende på din mobilprogramkonfiguration. Mer information om hur du ställer in push-meddelanden i Adobe Experience Platform och Adobe Launch finns i [det här avsnittet](push-gs.md)

## Avancerade alternativ {#advanced-options-push}

Du kan konfigurera **[!UICONTROL Advanced options]** för ditt push-meddelande. Tillgängliga parametrar visas nedan:

| Parameter | Beskrivning |
|---------|---------|
| **[!UICONTROL Collapsible]** (iOS/Android) | Ett komprimerbart meddelande är ett meddelande som kan ersättas av ett nytt meddelande om det har blivit inaktuellt. Ett vanligt användningsfall för komprimerbara meddelanden är meddelanden som används för att instruera en mobilapp att synkronisera data från servern. Ett exempel är en sportapp som uppdaterar användare med den senaste poängen. Endast det senaste meddelandet är relevant. Å andra sidan, med icke-komprimerbara meddelanden, är varje meddelande viktigt för klientappen och måste levereras. |
| **[!UICONTROL Custom sound]** (iOS/Android) | Det ljud som ska spelas upp av mobilterminalen när meddelandet tas emot. Ljudet måste paketeras i appen. |
| **[!UICONTROL Badges]** (iOS/Android) | Ett märke används för att visa antalet nya olästa uppgifter direkt på programikonen. <br/>Märkesvärdet försvinner när användaren öppnar eller läser det nya innehållet från programmet. När ett meddelande tas emot på en enhet kan det uppdatera eller lägga till ett märkesvärde för den relaterade appen.<br/>Om du till exempel lagrar antalet olästa artiklar för dina kunder kan du använda personalisering för att skicka det unika märket för olästa artiklar för varje kund. Mer personalisering finns i [det här avsnittet](../personalization/personalize.md). |
| **[!UICONTROL Notification group]**  (endast iOS) | Associera en meddelandegrupp med push-meddelandet.<br/>Från och med iOS 12 kan du med meddelandegrupper konsolidera meddelandetrådar och meddelandeämnen i kopplade ID:n. Ett varumärke kan t.ex. skicka marknadsföringsmeddelanden under ett grupp-ID samtidigt som det behåller fler typmeddelanden under ett eller flera olika ID:n.<br/>Om du vill illustrera detta kan du ha groupID: 123&quot;kolla in den nya vårsamlingen av tröjor&quot; och grupp-ID: 456 Meddelandegrupper för&quot;ditt paket levererades&quot;. I det här exemplet paketeras alla leveransmeddelanden under grupp-ID: 456. |
| **[!UICONTROL Notification channel]** (Endast Android) | Koppla en meddelandekanal till push-meddelandet.<br/>Från och med Android 8.0 (API-nivå 26) måste alla meddelanden tilldelas en kanal för att kunna visas. Mer information finns i [Dokumentation för Android-utvecklare](https://developer.android.com/guide/topics/ui/notifiers/notifications#ManageChannels). |
| **[!UICONTROL Add content-availability flag]** (endast iOS) | Skickar flaggan för tillgängligt innehåll i push-nyttolasten för att säkerställa att appen aktiveras så fort den får push-meddelandet, vilket innebär att appen kan komma åt nyttolastdata.<br/> Detta fungerar även om appen körs i bakgrunden och utan att användaren behöver göra något (t.ex. trycka på ett push-meddelande). Detta gäller dock inte om programmet inte körs. Mer information om detta hittar du i [Apples dokumentation för utvecklare](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| **[!UICONTROL Add mutable-content flag]** (endast iOS) | Skickar flaggan för ändringsbart innehåll i push-nyttolasten och tillåter att push-meddelandeinnehållet ändras med ett meddelandetjänstprogramtillägg som tillhandahålls i iOS SDK. Mer information om detta hittar du i [Apples dokumentation för utvecklare](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).<br/>Sedan kan du utnyttja dina mobilappstillägg för att ytterligare ändra innehållet eller presentationen av inkommande push-meddelanden som skickas från [!DNL Journey Optimizer]. Användare kan till exempel utnyttja det här alternativet för att dekryptera data, ändra brödtexten eller rubriktexten i ett meddelande, lägga till en trådidentifierare i ett meddelande osv. |
| **[!UICONTROL Notification visibility]** (Endast Android) | Anger om push-meddelandet ska visas. <br/><b>Privat</b> visar meddelandet på alla låsskärmar, men döljer känslig eller privat information på säkra låsskärmar. <br/><b>Offentlig</b> visar meddelandet i sin helhet på alla låsskärmar. <br/><b>Hemlighet</b> visar inte någon del av meddelandet på en säker låsskärm. <br/>Mer information finns i [Dokumentation för Android-utvecklare](https://developer.android.com/reference/android/app/Notification). |
| **[!UICONTROL Notification priority]** (Endast Android) | Definierar push-meddelandets prioritet från Låg till Max. Detta avgör hur påträngande push-meddelandet blir när det levereras. Mer information finns i [Dokumentation för Android-utvecklare](https://developer.android.com/guide/topics/ui/notifiers/notifications#importance) |
| **[!UICONTROL Delivery priority]** (Endast Android) | Ställer in hög eller normal prioritet för dina push-meddelanden. Mer information om meddelandeprioritet finns i [Googles dokumentation för utvecklare](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message). |

**Relaterade ämnen**

<!--
* [Understand push notification flow](push-gs.md)
-->

* [Konfigurera push-kanal](push-gs.md)
* [Skapa ett nytt meddelande](create-message.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
