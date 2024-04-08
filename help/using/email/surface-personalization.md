---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera dynamiska e-postdomäner
description: Lär dig hur du konfigurerar dynamiska underdomäner på e-postkanalens ytnivå
feature: Surface, Subdomains
topic: Administration
role: Admin
level: Experienced
keywords: inställningar, e-post, konfiguration, underdomän
hide: true
hidefromtoc: true
badge: label="Beta"
source-git-commit: e63823dc2f901b870f11b0478e682e2af61b5b98
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 0%

---

# Anpassa inställningar för e-postyta {#surface-personalization}

För större flexibilitet och bättre kontroll över e-postinställningarna [!DNL Journey Optimizer] gör att du kan definiera personaliserade värden för underdomäner och rubriker<!--and URL tracking parameters--> när du skapar e-postytor.

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande endast tillgänglig som betaversion för utvalda användare. <!--To join the beta program, contact Adobe Customer Care.-->

## Lägg till dynamiska underdomäner {#dynamic-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_surface_perso_not_available"
>title="Personalisering är inte tillgängligt"
>abstract="Den här ytan skapades utan några personaliseringsattribut. Läs dokumentationen om hur du löser ett problem med personalisering."

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain"
>title="Aktivera dynamiska underdomäner"
>abstract="När du skapar en e-postyta kan du konfigurera dynamiska underdomäner baserat på villkor som du definierar med hjälp av uttrycksredigeraren. Du kan lägga till upp till 50 dynamiska underdomäner."

>[!CONTEXTUALHELP]
>id="ajo_surface_dynamic_subdomain_list"
>title="Vissa underdomäner kanske inte är tillgängliga"
>abstract="Vissa underdomäner är för närvarande inte tillgängliga för val på grund av väntande registrering av feedbackloop. Den här processen kan ta upp till 10 arbetsdagar. När du är klar kan du välja bland alla tillgängliga underdomäner."

När du skapar en e-postyta kan du konfigurera dynamiska underdomäner baserat på specifika villkor.

Om du till exempel har juridiska begränsningar för att skicka meddelanden från en dedikerad e-postadress per land kan du använda dynamiska underdomäner. På så sätt kan du skapa en enda yta med flera sändande underdomäner som motsvarar olika länder, i stället för att skapa flera ytor för varje land. Sedan kan ni inrikta er på kunder i olika länder som samlas i en enda kampanj.

Följ stegen nedan för att definiera dynamiska underdomäner i en e-postkanal.

1. Innan du skapar en yta ska du ställa in de underdomäner som du vill använda för att skicka e-postmeddelanden utifrån ditt användningsfall. [Lär dig mer](../configuration/about-subdomain-delegation.md)

   Anta att du vill använda olika underdomäner för olika länder: konfigurera en underdomän som är specifik för USA, en som är specifik för Storbritannien, osv.

1. Skapa en kanalyta. [Lär dig mer](../configuration/channel-surfaces.md)

1. Välj **[!UICONTROL Email]** kanal.

1. I **Underdomän** -sektion, aktivera **[!UICONTROL Dynamic Subdomain]** alternativ.

   ![](assets/surface-email-dynamic-subdomain.png)

1. Välj redigeringsikonen bredvid den första **[!UICONTROL Condition]** fält.

1. The [Uttrycksredigeraren](../personalization/personalization-build-expressions.md) öppnas. I det här exemplet anger du ett villkor som `Country` är lika med `US`.

   ![](assets/surface-email-edit-condition.png)

1. Markera den underdomän som du vill associera med det här villkoret. [Läs mer om underdomäner](../configuration/about-subdomain-delegation.md)

   >[!NOTE]
   >
   >Vissa underdomäner är för närvarande inte tillgängliga för val på grund av väntande [feedback-slinga](../reports/deliverability.md#feedback-loops) registrering. Den här processen kan ta upp till 10 arbetsdagar. När du är klar kan du välja bland alla tillgängliga underdomäner. <!--where FL registration happens? is it when delegating a subdomain and you're awaiting from subdomain validation? or is it on ISP side only?-->

   ![](assets/surface-email-select-subdomain.png)

   Alla mottagare som är baserade i USA får meddelanden med den valda underdomänen för det landet, vilket innebär att alla URL:er (som spegelsida, spårnings-URL eller länk för att avbryta prenumerationen) fylls i baserat på den underdomänen.

1. Ange andra dynamiska underdomäner efter behov. Du kan lägga till upp till 50 objekt.

   ![](assets/surface-email-add-dynamic-subdomain.png)

<!--Select the [IP pool](../configuration/ip-pools.md) to associate with the surface. [Learn more](email-settings.md#subdomains-and-ip-pools)-->

1. Definiera alla andra [e-postinställningar](email-settings.md) och [skicka](../configuration/channel-surfaces.md#create-channel-surface) din yta.

När du har lagt till en eller flera dynamiska underdomäner till en yta fylls följande objekt i baserat på den lösta dynamiska underdomänen för den här ytan:

* Alla URL:er (resurs-URL, URL för spegelsida och URL för spårning)

* The [avbeställ URL](email-settings.md#list-unsubscribe)

* The **Från e-post** och **E-postfel** suffix

>[!NOTE]
>
>Om du konfigurerar dynamiska underdomäner och sedan inaktiverar **[!UICONTROL Dynamic Subdomain]** tas alla dynamiska värden bort. Markera en underdomän och skicka ytan så att ändringarna börjar gälla.

## Anpassa sidhuvudet {#personalize-header}

Du kan också använda personalisering för alla rubrikparametrar som definieras i en yta.

Om du till exempel har flera varumärken kan du skapa en enda yta och använda anpassade värden för dina e-posthuvuden. På så sätt kan ni se till att alla e-postmeddelanden som skickas från olika varumärken adresseras till var och en av era kunder med rätt **Från** namn och e-post. När mottagarna trycker på **Svara** i e-postklientprogramvaran vill du ha **Svara till** namn och e-post motsvarar rätt varumärke för rätt användare.

Följ stegen nedan om du vill använda personaliserade variabler för sidhuvudsparametrarna på ytan.

>[!NOTE]
>
>Ni kan personalisera alla **[!UICONTROL Header parameters]** fält, utom **[!UICONTROL Error email prefix]** fält.


1. Definiera sidhuvudsparametrarna som vanligt. [Lär dig mer](email-settings.md#email-header)

1. För varje fält väljer du ikonen Redigera.

   ![](assets/surface-email-personalize-header.png)

1. The [Uttrycksredigeraren](../personalization/personalization-build-expressions.md) öppnas. Definiera ditt tillstånd så som du vill ha det och spara dina ändringar.

   Ange till exempel ett villkor som varje mottagare får ett e-postmeddelande från sin egen varumärkesrepresentant.

   >[!NOTE]
   >
   >Du kan bara välja **[!UICONTROL Profile attributes]** och **[!UICONTROL Helper functions]**.

1. Upprepa stegen ovan för varje parameter som du vill lägga till personalisering i.

>[!NOTE]
>
>Om du har lagt till en eller flera dynamiska underdomäner på ytan, visas **Från e-post** och **E-postfel** suffix fylls i baserat på de lösta [dynamisk underdomän](#dynamic-subdomains).

<!--
## Use personalized URL tracking {#personalize-url-tracking}

To use personalized URL tracking prameters, follow the steps below.

1. Select the profile attribute of your choice from the expression editor.

1. Repeat the steps above for each tracking parameter you want to personalize.

Now when the email is sent out, this parameter will be automatically appended to the end of the URL. You can then capture this parameter in web analytics tools or in performance reports.
-->

## Visa ytinformation {#view-surface-details}

När du använder en yta med personaliserade inställningar i en kampanj eller en yta kan du visa ytdetaljer direkt i kampanjen eller ytan. Följ stegen nedan.

1. Skapa ett e-postmeddelande [kampanj](../campaigns/create-campaign.md) eller [resa](../building-journeys/journey-gs.md).

1. Markera knappen **[!UICONTROL Edit content]**.

1. Klicka på knappen **[!UICONTROL View surface details]**.

   ![](assets/campaign-view-surface-details.png)

1. The **[!UICONTROL Delivery settings]** visas. Du kan visa alla ytinställningar, inklusive dynamiska underdomäner och anpassade huvudparametrar.

   >[!NOTE]
   >
   >All information på den här skärmen är skrivskyddad.

1. Välj **[!UICONTROL Expand]** för att visa information om de dynamiska underdomänerna.

   ![](assets/campaign-delivery-settings-subdomain-expand.png)

