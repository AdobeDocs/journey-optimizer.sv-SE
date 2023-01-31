---
solution: Journey Optimizer
product: journey optimizer
title: Skapa innehållsmallar
description: Lär dig skapa mallar för återanvändning av innehåll i Journey Optimizer kampanjer och resor
feature: Overview
topic: Content Management
role: User
level: Beginner
source-git-commit: 4df89a36705fb53984ba04ba1ae2f45554e47f77
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 1%

---

# Skapa innehållsmallar {#content-templates}

>[!CONTEXTUALHELP]
>id="ajo_content_templates"
>title="Skapa innehållsmallar"
>abstract="Skapa fristående mallar för att återanvända innehåll över resor och kampanjer."

För en accelererad och förbättrad designprocess kan du skapa fristående mallar för att enkelt återanvända anpassat innehåll i [!DNL Journey Optimizer] kampanjer och resor.

Med den här funktionen kan innehållsorienterade användare arbeta med mallar utanför kampanjer eller resor. Marknadsförare kan sedan återanvända och anpassa dessa fristående innehållsmallar på sina egna resor eller i sina egna kampanjer.

>[!CAUTION]
>
>Om du vill skapa, redigera och ta bort innehållsmallar måste du ha **[!DNL Manage Library Items]** behörighet som ingår i **[!DNL Content Library Manager]** produktprofil. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)

En användare i företaget ansvarar t.ex. bara för innehållet och har därför inte tillgång till kampanjer eller resor. Den här användaren kan dock skapa en e-postmall som organisationens marknadsförare kan välja att använda i alla e-postmeddelanden som utgångspunkt.

>[!NOTE]
>
>* Ändringar som görs i innehållsmallar sprids inte till kampanjer eller resor, vare sig de är live eller utkast.
>
>* När mallar används i en kampanj eller en resa påverkas inte heller de ändringar du gör i kampanj- och reseinnehållet som du har använt tidigare.


➡️ [Lär dig hur du skapar och använder mallar i den här videon](#video-templates)

Följ stegen nedan för att skapa en innehållsmall.

1. Välj **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** från den vänstra menyn.

   ![](assets/content-template-list.png)

1. Alla mallar som skapades i den aktuella sandlådan - antingen från en resa, en kampanj eller från **[!UICONTROL Content Templates]** -menyn visas.

   >[!NOTE]
   >
   >Du kan sortera innehållsmallar efter skapad- eller ändringsdatum.

1. Välj **[!UICONTROL Create template]**.

1. Fyll i mallinformationen.

   ![](assets/content-template-details.png)

   >[!NOTE]
   >
   >För närvarande bara **E-post** kanal och **HTML** type stöds.

1. Om du vill tilldela etiketter för anpassad eller grundläggande dataanvändning till mallen väljer du **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Klicka **[!UICONTROL Create]** och välj hur du vill utforma e-postmeddelandet bland följande alternativ:

   * **[!UICONTROL Design from scratch]**
   * **[!UICONTROL Code your own]**
   * **[!UICONTROL Import HTML]**
   * **[!UICONTROL Select design template]**

   ![](assets/content-template-design.png)

   >[!NOTE]
   >
   >Om du väljer en mall kan du välja mellan **[!UICONTROL Sample templates]**, som är färdiga e-postmallar, och **[!UICONTROL Saved templates]**, som är de som skapats antingen från en resa, en kampanj eller från **[!UICONTROL Content Templates]** -menyn. [Läs mer](email-templates.md#save-as-template)

1. E-postdesignern visas. Redigera ditt innehåll efter behov, på samma sätt som du gör för e-post inuti en resa eller kampanj, enligt det alternativ du valt:

   * [Designa din e-post från grunden](content-from-scratch.md) genom designerns gränssnitt och utnyttja bilder från [Adobe Experience Manager Assets Essentials](assets-essentials.md).

   * [Kod eller kopiera-klistra in Raw-HTML](code-content.md) direkt in i e-postdesignern.

   * [Importera befintligt HTML-innehåll](existing-content.md) från en fil eller en ZIP-mapp.

   * [Använd befintligt innehåll](email-templates.md) från en lista med inbyggda eller anpassade mallar.

   ![](assets/content-template-designer.png)

1. Klicka **[!UICONTROL Simulate Content]** för att kontrollera din e-poståtergivning. Du kan välja skrivbordsvy eller mobilvy. [Läs mer](preview.md)

   >[!CAUTION]
   >
   >Om du vill simulera innehåll måste du ha **[!DNL Manage Simulate Content]** behörighet som ingår i **[!DNL Content Library Manager]** produktprofil. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)

   ![](assets/content-template-stimulate.png)

1. Du kan skicka ett bevis för att testa ditt innehåll och få det godkänt av vissa interna användare innan du använder det under en resa eller i en kampanj.

   * Om du vill göra det klickar du på **[!UICONTROL Send proof]** och följer stegen som beskrivs i [det här avsnittet](preview.md#send-proofs).

   * Innan du skickar korrekturet måste du välja [e-postyta](../configuration/channel-surfaces.md) som kommer att användas för att testa ditt innehåll.

      ![](assets/content-template-stimulate-proof-surface.png)

1. När mallen är klar klickar du på **[!UICONTROL Save]**.

1. Klicka vid behov på pilen bredvid mallnamnet för att gå tillbaka till **[!UICONTROL Details]** och redigera mallen.

   ![](assets/content-template-designer-back.png)

1. Du kan nu använda den här innehållsmallen när du skapar [e-post](get-started-email-design.md) inom [!DNL Journey Optimizer]. Läs mer på [använda en sparad mall](email-templates.md#use-saved-template).

   ![](assets/email_designer-saved-templates.png)

## Instruktionsvideo{#video-templates}

Lär dig hur du skapar, redigerar och använder innehållsmallar i [!DNL Journey Optimizer].

>[!VIDEO](https://video.tv.adobe.com/v/3413743/?quality=12)