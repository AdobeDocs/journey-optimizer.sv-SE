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
source-git-commit: c082d9329949fd8dc68929e3934daf2d9dfdbd46
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 0%

---

# Konfigurera dynamiska e-postdomäner {#surface-personalization}

För ökad flexibilitet och kontroll över e-postinställningarna när du skapar e-postytor [!DNL Journey Optimizer] gör att du kan definiera personaliserade värden för underdomäner, rubriker och URL-spårningsparametrar.

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

Följ stegen nedan för att definiera dynamiska underdomäner.

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

1. Ange en annan dynamisk underdomän efter behov. Du kan lägga till upp till 50 objekt.

   ![](assets/surface-email-add-dynamic-subdomain.png)

1. Välj [IP-pool](../configuration/ip-pools.md) för att associera med ytan. [Läs mer](email-settings.md#subdomains-and-ip-pools)

När du har lagt till en eller flera dynamiska underdomäner till en yta fylls följande objekt i baserat på den lösta dynamiska underdomänen för den här ytan:

* Alla URL:er (resurs-URL, URL för spegelsida och URL för spårning)

* The [avbeställ URL](email-settings.md#list-unsubscribe)

* The **Från e-post** och **E-postfel** suffix

## Anpassa sidhuvudet (#personalize-header)

Du kan också använda personalisering för alla rubrikparametrar som definieras i en yta.

Om du till exempel har flera varumärken kan du skapa en enda yta och använda anpassade värden för dina e-posthuvuden. På så sätt kan ni se till att alla e-postmeddelanden som skickas från olika varumärken adresseras till var och en av era kunder med rätt **Från** namn och e-post. När mottagarna trycker på **Svara** i e-postklientprogramvaran vill du ha **Svara till** namn och e-post motsvarar rätt varumärke för rätt användare.

Följ stegen nedan om du vill använda personaliserade variabler för sidhuvudsparametrarna på ytan.

1. Definiera sidhuvudsparametrarna som vanligt. [Lär dig mer](email-settings.md#email-header)

1. För varje fält väljer du ikonen Redigera.

   ![](assets/surface-email-personalize-header.png)

1. The [Uttrycksredigeraren](../personalization/personalization-build-expressions.md) öppnas. Definiera ditt tillstånd så som du vill ha det och spara dina ändringar.<!--In this example, set a condition such as -->

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

select the profile attribute of your choice from the expression editor.

1. Repeat the steps above for each tracking parameter you want to personalize.

Now when the email is sent out, this parameter will be automatically appended to the end of the URL. You can then capture this parameter in web analytics tools or in performance reports.
-->
