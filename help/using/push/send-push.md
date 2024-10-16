---
solution: Journey Optimizer
product: journey optimizer
title: Kontrollera och skicka push-meddelanden
description: Lär dig hur du kontrollerar och skickar push-meddelanden i Journey Optimizer
feature: Push
topic: Content Management
role: User
level: Beginner
exl-id: aad4e08a-3369-454d-9e32-974347a3b393
source-git-commit: 47482adb84e05fe41eb1c50479a8b50e00469ec4
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 1%

---

# Kontrollera och skicka push-meddelanden {#send-push}

## Förhandsgranska ditt push-meddelande {#preview-push}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska innehållet. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet med hjälp av testprofildata.

Klicka på **[!UICONTROL Simulate content]** och lägg sedan till en testprofil för att göra detta. Du kan sedan välja typ av enhet för att förhandsgranska innehåll: **[!UICONTROL iOS]** eller **[!UICONTROL Android]**.

![](assets/push_preview_3.png)

Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehåll finns i avsnittet [Innehållshantering](../content-management/preview-test.md).

## Validera ditt push-meddelande {#push-validate}

Du måste kontrollera varningar i den övre delen av redigeraren. Vissa av dem är enkla varningar, men andra kan hindra dig från att skicka meddelandet. Två typer av varningar kan inträffa: varningar och fel.

* **Varningar** hänvisar till rekommendationer och bästa praxis.

* **Fel** hindrar dig från att testa eller aktivera resan så länge som de inte har lösts, till exempel:

   * **[!UICONTROL The push version of the message is empty]**: Det här felet visas när meddelandetexten eller titeln för push-meddelanden saknas. Lär dig hur du definierar innehåll för push-meddelanden i [det här avsnittet](create-push.md).

   * **[!UICONTROL configuration doesn't exist]**: Du kan inte använda meddelandet om den konfiguration du har valt tas bort efter att meddelandet har skapats. Om det här felet inträffar väljer du en annan konfiguration i meddelandet **[!UICONTROL Properties]**. Läs mer om kanalkonfigurationer i [det här avsnittet](../configuration/channel-surfaces.md).

   * **[!UICONTROL Push iOS/Android payload has exceeded limit of 4KB]**: storleken på push-meddelandet får inte överskrida 4 kB. Om du vill iaktta den här gränsen försöker du minska användningen av bilder eller känslolägesikoner. Lär dig hur du hanterar ditt push-meddelandeinnehåll i [det här avsnittet](../push/create-push.md).

  ![](assets/push_alert.png)


>[!NOTE]
>
> För bättre leverans bör du alltid använda telefonnumren i de format som stöds av leverantören. Twilio och Sinch har till exempel bara stöd för telefonnummer i E.164-format.

## Skicka push-meddelanden{#push-send}

>[!IMPORTANT]
>
>Från och med versionen från september kan ni med en ny kampanjupplevelse och upplevelse av aktivering av resor hantera hela godkännandeprocessen och säkerställa att kampanjer och resor granskas noggrant och godkänns av lämpliga intressenter innan de publiceras. Den här funktionen är tillgänglig med begränsad tillgänglighet. [Läs mer](../test-approve/gs-approval.md)

När ditt push-meddelande är klart slutför du konfigurationen av din [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md) för att skicka det.

**Relaterade ämnen**

* [Konfigurera push-kanal](push-configuration.md)
* [Rapport om push-meddelanden](../reports/journey-global-report-cja-push.md)
* [Skapa ett push-meddelande](create-push.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
* [Lägg till ett meddelande i en kampanj](../campaigns/create-campaign.md)

