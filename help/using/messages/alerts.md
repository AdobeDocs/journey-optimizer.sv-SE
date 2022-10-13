---
title: Varningar i meddelanden
description: Lär dig hur du kontrollerar validering och felsökning av meddelandeinnehåll
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 89f445f2-df8a-4d2d-afe8-4f8b9cb001d9
source-git-commit: 32c69ef268c78ba834612d16b2ac1c721fb5df56
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---

# Kontrollera aviseringar i meddelanden {#messages-alerts}

## Kontroller före sändning {#message-alerting}

När du utformar meddelanden visas varningar i gränssnittet när nyckelinställningar saknas.

Varningar visas högst upp till höger på skärmen när meddelandeinnehållet redigeras.

![](assets/alerts-details.png)

>[!NOTE]
>
>Om knappen inte visas har ingen varning identifierats.

Två typer av varningar kan inträffa:

* **Varningar** hänvisa till rekommendationer och bästa praxis. Ett meddelande visas till exempel om länken för avanmälan saknas.

* **Fel** hindra dig från att testa eller aktivera resan så länge som de inte är lösta. Du får t.ex. en varning om att ämnesraden saknas.

Alla möjliga varningar och fel är detaljerade [nedan](#alerts-and-warnings).

>[!CAUTION]
>
> Du måste lösa alla **fel** varningar innan resan testas eller aktiveras med meddelandet.

## Lista över varningar och fel {#alerts-and-warnings}

De inställningar och element som kontrolleras av systemet visas nedan. Du hittar även information om hur du anpassar konfigurationen för att lösa motsvarande problem.

**Varningar**:

* **[!UICONTROL The opt-out link is not present in the email body]**: det är bra att lägga till en länk för att avbryta prenumerationen i e-postmeddelandet. Lär dig hur du konfigurerar det i [det här avsnittet](../privacy/opt-out.md#opt-out-management).

   >[!NOTE]
   >
   >E-postmeddelanden av marknadsföringstyp måste innehålla en länk för avanmälan, vilket inte krävs för transaktionsmeddelanden. Meddelandekategorin (**[!UICONTROL Marketing]** eller **[!UICONTROL Transactional]**) definieras i [kanalyta](../configuration/channel-surfaces.md#email-type) (t.ex. meddelandeförinställning) nivå och när [skapar meddelandet](get-started-content.md#create-new-message).

* **[!UICONTROL Text version of HTML is empty]**: Glöm inte att definiera en textversion av e-posttexten, eftersom den kommer att användas när HTML inte kan visas. Lär dig hur du skapar textversionen i [det här avsnittet](../design/text-version-email.md).

* **[!UICONTROL Empty link is present in email body]**: kontrollera att alla länkar i e-postmeddelandet är korrekta. Lär dig hantera innehåll och länkar i [det här avsnittet](../design/create-email-content.md).

* **[!UICONTROL Email size has exceeded the limit of 100KB]**: för optimal leverans bör du kontrollera att e-postens storlek inte överstiger 100 kB. Lär dig hur du redigerar e-postinnehåll i [det här avsnittet](../design/create-email-content.md).

**Fel**:

* **[!UICONTROL The subject line is missing]**: Ämnesraden för e-post är obligatorisk. Lär dig definiera och personalisera det i [det här avsnittet](create-email.md).

   <!--HTML is empty when Amp HTML is present-->

* **[!UICONTROL The push version of the message is empty]**: det här felet visas när meddelandetexten eller titeln för push-meddelanden saknas. Lär dig definiera innehåll för push-meddelanden i [det här avsnittet](create-push.md).

* **[!UICONTROL The email version of the message is empty]**: det här felet visas när e-postinnehållet inte har konfigurerats. Lär dig designa e-postinnehåll i [det här avsnittet](../design/design-emails.md).

* **[!UICONTROL Surface doesn’t exist]**: Du kan inte använda meddelandet om den yta som du har markerat tas bort efter att meddelandet har skapats. Om det här felet inträffar väljer du en annan yta i meddelandet **[!UICONTROL Properties]**. Läs mer om kanalytor i [det här avsnittet](../configuration/channel-surfaces.md).

* **[!UICONTROL Push iOS/Android payload has exceeded limit of 4KB]**: storleken på push-meddelanden får inte överskrida 4 kB. Om du vill iaktta den här gränsen försöker du minska användningen av bilder eller känslolägesikoner. Lär dig hur du hanterar ditt push-meddelandeinnehåll i [det här avsnittet](create-push.md).

>[!CAUTION]
>
> För att kunna använda meddelandet måste du åtgärda alla **fel** varningar.

<!--Other issues can stop publication such as:
* The push notification title is empty-->
