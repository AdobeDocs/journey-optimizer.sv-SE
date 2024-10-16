---
solution: Journey Optimizer
product: journey optimizer
title: Anpassa inställningar för e-postkonfiguration
description: Lär dig hur du definierar anpassade värden för dina inställningar på e-postkanalens konfigurationsnivå
feature: Surface, Subdomains
topic: Administration
role: Admin
level: Experienced
keywords: inställningar, e-post, konfiguration, underdomän
badge: label="Begränsad tillgänglighet"
exl-id: 1e004a76-5d6d-43a1-b198-5c9b41f5332c
source-git-commit: f8a6c2a3b27d5dca422dfdc868f802c6a10b001d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Anpassa inställningar för e-postkonfiguration {#surface-personalization}

För större flexibilitet och kontroll över e-postinställningarna kan du med [!DNL Journey Optimizer] definiera anpassade värden för underdomäner och rubriker <!--and URL tracking parameters--> när du skapar e-postkonfigurationer.

>[!AVAILABILITY]
>
>Anpassning av e-postkonfiguration är för närvarande bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

## Lägg till dynamiska underdomäner {#dynamic-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_surface_perso_not_available"
>title="Personalization är inte tillgängligt"
>abstract="Den här konfigurationen skapades utan några personaliseringsattribut. Läs dokumentationen om hur du löser ett problem med personalisering."

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain"
>title="Aktivera dynamiska underdomäner"
>abstract="När du skapar en e-postkonfiguration kan du konfigurera dynamiska underdomäner baserat på villkor som du definierar med personaliseringsredigeraren. Du kan lägga till upp till 50 dynamiska underdomäner."

När du skapar en e-postkonfiguration kan du konfigurera dynamiska underdomäner baserat på specifika villkor.

Om du till exempel har juridiska begränsningar för att skicka meddelanden från en dedikerad e-postadress per land kan du använda dynamiska underdomäner. Detta gör att du kan skapa en enda konfiguration med flera sändande underdomäner som motsvarar olika länder, i stället för att skapa flera konfigurationer för varje land. Sedan kan ni inrikta er på kunder i olika länder som samlas i en enda kampanj.

Följ stegen nedan för att definiera dynamiska underdomäner i en e-postkanalskonfiguration.

1. Innan du skapar en konfiguration ska du konfigurera de underdomäner som du vill använda för att skicka e-post enligt ditt användningsexempel. [Lär dig hur](../configuration/about-subdomain-delegation.md)

   Anta att du vill använda olika underdomäner för olika länder: konfigurera en underdomän som är specifik för USA, en som är specifik för Storbritannien, osv.

1. Skapa en kanalkonfiguration. [Lär dig hur](../configuration/channel-surfaces.md)

1. Välj kanalen **[!UICONTROL Email]**.

1. Aktivera alternativet **[!UICONTROL Dynamic Subdomain]** i avsnittet **Underdomän**.

   ![](assets/surface-email-dynamic-subdomain.png)

1. Välj redigeringsikonen bredvid det första **[!UICONTROL Condition]**-fältet.

1. [Anpassningsredigeraren](../personalization/personalization-build-expressions.md) öppnas. I det här exemplet anger du ett villkor som `Country` är lika med `US`.

   ![](assets/surface-email-edit-condition.png)

1. Markera den underdomän som du vill associera med det här villkoret. [Läs mer om underdomäner](../configuration/about-subdomain-delegation.md)

   >[!NOTE]
   >
   >Vissa underdomäner är för närvarande inte tillgängliga för markering på grund av registrering av [feedbackloop](../reports/deliverability.md#feedback-loops). Den här processen kan ta upp till 10 arbetsdagar. När du är klar kan du välja bland alla tillgängliga underdomäner. <!--where FL registration happens? is it when delegating a subdomain and you're awaiting from subdomain validation? or is it on ISP side only?-->

   ![](assets/surface-email-select-subdomain.png)

   Alla mottagare som är baserade i USA får meddelanden med den valda underdomänen för det landet, vilket innebär att alla URL:er (som spegelsida, spårnings-URL eller länk för att avbryta prenumerationen) fylls i baserat på den underdomänen.

1. Ange andra dynamiska underdomäner efter behov. Du kan lägga till upp till 50 objekt.

   ![](assets/surface-email-add-dynamic-subdomain.png)

   <!--Select the [IP pool](../configuration/ip-pools.md) to associate with the configuration. [Learn more](email-settings.md#subdomains-and-ip-pools)-->

1. Definiera alla andra [e-postinställningar](email-settings.md) och [skicka](../configuration/channel-surfaces.md#create-channel-surface) i din konfiguration.

När du har lagt till en eller flera dynamiska underdomäner i en konfiguration fylls följande objekt i baserat på den lösta dynamiska underdomänen för den här konfigurationen:

* Alla URL:er (resurs-URL, URL för spegelsida och URL för spårning)

* URL:en [för att avbryta prenumerationen](email-settings.md#list-unsubscribe)

* Suffixen **Från e-post** och **Felmeddelande**

>[!NOTE]
>
>Om du konfigurerar dynamiska underdomäner och sedan inaktiverar alternativet **[!UICONTROL Dynamic Subdomain]** tas alla dynamiska värden bort. Välj en underdomän och skicka konfigurationen så att ändringarna börjar gälla.

## Anpassa sidhuvudet {#personalize-header}

Du kan också använda personalisering för alla huvudparametrar som definieras i en konfiguration.

Om du till exempel har flera varumärken kan du skapa en enda konfiguration och använda anpassade värden för dina e-posthuvuden. På så sätt kan du se till att alla e-postmeddelanden som skickas från dina olika varumärken adresseras till var och en av dina kunder med rätt **From**-namn och e-postmeddelanden. När mottagarna trycker på knappen **Svara** i e-postklientprogramvaran vill du på liknande sätt att **Svara på** namn och e-post motsvarar rätt varumärke för rätt användare.

Följ stegen nedan om du vill använda personaliserade variabler för konfigurationshuvudets parametrar.

>[!NOTE]
>
>Du kan anpassa alla **[!UICONTROL Header parameters]**-fält utom fältet **[!UICONTROL Error email prefix]**.


1. Definiera sidhuvudsparametrarna som vanligt. [Lär dig hur](email-settings.md#email-header)

1. För varje fält väljer du ikonen Redigera.

   ![](assets/surface-email-personalize-header.png)

1. [Anpassningsredigeraren](../personalization/personalization-build-expressions.md) öppnas. Definiera ditt tillstånd så som du vill ha det och spara dina ändringar.

   Ange till exempel ett villkor som varje mottagare får ett e-postmeddelande från sin egen varumärkesrepresentant.

   >[!NOTE]
   >
   >Du kan bara välja **[!UICONTROL Profile attributes]** och **[!UICONTROL Helper functions]**.

1. Upprepa stegen ovan för varje parameter som du vill lägga till personalisering i.

>[!NOTE]
>
>Om du har lagt till en eller flera dynamiska underdomäner i din konfiguration fylls suffixen **Från e-post** och **Fel-e-post** i baserat på den matchade [dynamiska underdomänen](#dynamic-subdomains).

<!--
## Use personalized URL tracking {#personalize-url-tracking}

To use personalized URL tracking prameters, follow the steps below.

1. Select the profile attribute of your choice from the personalization editor.

1. Repeat the steps above for each tracking parameter you want to personalize.

Now when the email is sent out, this parameter will be automatically appended to the end of the URL. You can then capture this parameter in web analytics tools or in performance reports.
-->

## Visa konfigurationsinformation {#view-surface-details}

När du använder en konfiguration med anpassade inställningar i en kampanj eller konfiguration kan du visa konfigurationsinformationen direkt i kampanjen eller konfigurationen. Följ stegen nedan.

1. Skapa ett [kampanj](../campaigns/create-campaign.md) eller [resa](../building-journeys/journey-gs.md) via e-post.

1. Markera knappen **[!UICONTROL Edit content]**.

1. Klicka på knappen **[!UICONTROL View configuration details]**.

   ![](assets/campaign-view-surface-details.png)

1. Fönstret **[!UICONTROL Delivery settings]** visas. Du kan visa alla konfigurationsinställningar, inklusive dynamiska underdomäner och anpassade huvudparametrar.

   >[!NOTE]
   >
   >All information på den här skärmen är skrivskyddad.

1. Välj **[!UICONTROL Expand]** om du vill visa information om de dynamiska underdomänerna.

   ![](assets/campaign-delivery-settings-subdomain-expand.png)
