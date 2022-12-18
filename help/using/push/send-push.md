---
solution: Journey Optimizer
product: journey optimizer
title: Skicka push-meddelanden
description: Lär dig hur du förhandsgranskar och testar push-meddelanden i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: aad4e08a-3369-454d-9e32-974347a3b393
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Skicka push-meddelanden {#send-push}

## Förhandsgranska ditt push-meddelande {#preview-push}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet genom att utnyttja testprofildata.

1. Klicka på **[!UICONTROL Simulate content]**.

1. Klicka **[!UICONTROL Manage test profiles]** för att lägga till en testprofil.

1. Hitta din testprofil med **[!UICONTROL Identity namespace]** och **[!UICONTROL Identity value]** fält. Klicka sedan på **[!UICONTROL Add profile]**.

   ![](assets/push_preview_1.png)

1. Använd samma steg som beskrivs ovan för att välja en testprofil, och

   ![](assets/push_preview_2.png)

1. I push-förhandsgranskningen används testprofildata i meddelandeinnehållet.

   Välj den typ av enhet som du vill förhandsgranska innehåll på: **[!UICONTROL iOS]** eller **[!UICONTROL Android]**.

   ![](assets/push_preview_3.png)

## Validera ditt push-meddelande {#push-validate}

>[!NOTE]
>
> För bättre leverans bör du alltid använda telefonnumren i de format som stöds av leverantören. Twilio och Sinch har till exempel bara stöd för telefonnummer i E.164-format.

Du måste även kontrollera varningar i den övre delen av redigeraren.  Vissa av dem är enkla varningar, men andra kan hindra dig från att använda meddelandet. Två typer av varningar kan inträffa:

* **Varningar** hänvisa till rekommendationer och bästa praxis.

* **Fel** hindra dig från att testa eller aktivera resan så länge som de inte är lösta, till exempel:

   * **[!UICONTROL The push version of the message is empty]**: det här felet visas när meddelandetexten eller titeln för push-meddelanden saknas. Lär dig definiera innehåll för push-meddelanden i [det här avsnittet](create-push.md).

   * **[!UICONTROL Surface doesn't exist]**: Du kan inte använda meddelandet om den yta som du har markerat tas bort efter att meddelandet har skapats. Om det här felet inträffar väljer du en annan yta i meddelandet **[!UICONTROL Properties]**. Läs mer om kanalytor i [det här avsnittet](../configuration/channel-surfaces.md).

   * **[!UICONTROL Push iOS/Android payload has exceeded limit of 4KB]**: storleken på push-meddelanden får inte överskrida 4 kB. Om du vill iaktta den här gränsen försöker du minska användningen av bilder eller känslolägesikoner. Lär dig hur du hanterar ditt push-meddelandeinnehåll i [det här avsnittet](../push/create-push.md).

![](assets/push_alert.png)

När push-meddelandet är klart slutför du konfigurationen av [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md) för att skicka den.
