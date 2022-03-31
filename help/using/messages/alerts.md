---
title: Varningar i meddelanden
description: Lär dig hur du kontrollerar validering och felsökning av meddelandeinnehåll
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 89f445f2-df8a-4d2d-afe8-4f8b9cb001d9
source-git-commit: 40c42303b8013c1d9f4dd214ab1acbec2942e094
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%

---

# Kontrollera aviseringar i meddelanden {#publish-manage-messages}

## Kontrollerar före publicering {#message-alerting}

När du skapar ett meddelande varnar du när du behöver vidta viktiga åtgärder innan du publicerar meddelandet.

Varningar visas högst upp till höger på skärmen, som visas nedan:

![](assets/message-alerts.png)

>[!NOTE]
>
>Om knappen inte visas har ingen varning identifierats.

Två typer av varningar kan inträffa:

* **Varningar** hänvisa till rekommendationer och bästa praxis. Ett meddelande visas till exempel om länken för avanmälan saknas.

* **Fel** förhindrar att du publicerar meddelandet så länge de inte är lösta. Du får t.ex. en varning om att ämnesraden saknas.

Alla möjliga varningar och fel är detaljerade [nedan](#alerts-and-warnings).

>[!CAUTION]
>
> Du måste lösa alla **fel** aviseringar före publicering.

## Lista över varningar och fel {#alerts-and-warnings}

De inställningar och element som kontrolleras av systemet visas nedan. Du hittar även information om hur du anpassar konfigurationen för att lösa motsvarande problem.

**Varningar**:

* **[!UICONTROL The opt-out link is not present in the email body.]**: det är bra att lägga till en länk för att avbryta prenumerationen i e-postmeddelandet. Lär dig hur du konfigurerar det i [det här avsnittet](consent.md).

* **[!UICONTROL Text version of HTML is empty.]**: Glöm inte att definiera en textversion av e-posttexten, eftersom den kommer att användas när HTML inte kan visas. Lär dig hur du skapar textversionen i [det här avsnittet](../design/text-version-email.md).

* **[!UICONTROL Empty link is present in email body.]**: kontrollera att alla länkar i e-postmeddelandet är korrekta. Lär dig hantera innehåll och länkar i [det här avsnittet](../design/create-email-content.md).

* **[!UICONTROL Email size has exceeded the limit of 100KB.]**: för optimal leverans bör du kontrollera att e-postens storlek inte överstiger 100 kB. Lär dig hur du redigerar e-postinnehåll i [det här avsnittet](../design/create-email-content.md).

**Fel**:

* **[!UICONTROL The subject line is missing.]**: Ämnesraden för e-post är obligatorisk. Lär dig definiera och personalisera det i [det här avsnittet](create-email.md).

   <!--HTML is empty when Amp HTML is present-->

* **[!UICONTROL The push version of the message is empty.]**: det här felet visas när meddelandetexten eller titeln för push-meddelanden saknas. Lär dig definiera innehåll för push-meddelanden i [det här avsnittet](create-push.md).

* **[!UICONTROL The email version of the message is empty.]**: det här felet visas när e-postinnehållet inte har konfigurerats. Lär dig designa e-postinnehåll i [det här avsnittet](../design/design-emails.md).

* **[!UICONTROL Preset doesn’t exist.]**: Du kan inte publicera meddelandet om den förinställning du har valt tas bort efter att meddelandet har skapats. Om det här felet inträffar väljer du en annan förinställning i meddelandet **[!UICONTROL Properties]**. Läs mer om varumärkesprofilering i [det här avsnittet](../configuration/about-subdomain-delegation.md).

* **[!UICONTROL Push iOS/Android payload has exceeded limit of 4KB.]**: storleken på push-meddelanden får inte överskrida 4 kB. Om du vill iaktta den här gränsen försöker du minska användningen av bilder eller känslolägesikoner. Lär dig hur du hanterar ditt push-meddelandeinnehåll i [det här avsnittet](create-push.md).

>[!CAUTION]
>
> För att kunna publicera ditt meddelande måste du åtgärda alla **fel** varningar.

<!--Other issues can stop publication such as:
* The push notification title is empty-->
