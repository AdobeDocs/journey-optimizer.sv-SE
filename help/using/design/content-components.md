---
title: Använda e-postdesigners innehållskomponenter
description: Lär dig hur du använder innehållskomponenter i e-postmeddelanden
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: a4aaa814-3fd4-439e-8f34-faf97208378a
source-git-commit: 3c1da5b789ad3f1b010f3d5be9c521f296035b83
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 1%

---

# Använda e-postdesignerns innehållskomponenter {#content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components_email"
>title="Om innehållskomponenter"
>abstract="Innehållskomponenterna är tomma platshållare för innehåll som du kan använda för att skapa layouten för ett e-postmeddelande."

>[!CONTEXTUALHELP]
>id="ac_content_components_landing_page"
>title="Om innehållskomponenter"
>abstract="Innehållskomponenterna är tomma platshållare för innehåll som du kan använda för att skapa layouten för en landningssida."

>[!CONTEXTUALHELP]
>id="ac_content_components_fragment"
>title="Om innehållskomponenter"
>abstract="Innehållskomponenter är tomma platshållare för innehåll som du kan använda för att skapa layouten för ett fragment."

>[!CONTEXTUALHELP]
>id="ac_content_components_template"
>title="Om innehållskomponenter"
>abstract="Innehållskomponenter är tomma platshållare för innehåll som du kan använda för att skapa layouten för en mall."


När du skapar ditt e-postinnehåll från grunden, **[!UICONTROL Content components]** gör att du kan anpassa e-postmeddelandet ytterligare med råa, tomma komponenter som du kan använda en gång i ett e-postmeddelande.
Du kan lägga till så många **[!UICONTROL Content components]** som du behöver i en **[!UICONTROL Structure component]** som definierar layouten för ditt e-postmeddelande.

## Knapp {#buttons}

Använd **[!UICONTROL Button]** om du vill infoga flera knappar i e-postmeddelandet och dirigera om din e-postpublik till en annan sida.

1. Från **[!UICONTROL Content components]**, dra och släppa **[!UICONTROL Button]** i en **[!UICONTROL Structure component]**.

   ![](assets/email_designer_13.png)

1. Klicka på den nya knappen för att anpassa texten och få tillgång till **[!UICONTROL Components Settings]** i den högra rutan i e-postdesignern.

   ![](assets/email_designer_14.png)

1. I **[!UICONTROL Link]** fält för **[!UICONTROL Components Settings]** lägger du till den URL som du vill att målgruppen ska omdirigeras till när du klickar på knappen.

1. Välj hur er målgrupp ska omdirigeras med **[!UICONTROL Target]** nedrullningsbar meny:

   * **[!UICONTROL None]**: öppnar länken i samma ram som den klickades på (standard).
   * **[!UICONTROL Blank]**: öppnar länken i ett nytt fönster eller på en ny flik.
   * **[!UICONTROL Self]**: öppnar länken i samma ram som den klickades på.
   * **[!UICONTROL Parent]**: öppnar länken i den överordnade ramen.
   * **[!UICONTROL Top]**: öppnar länken i hela fönstret.

   ![](assets/email_designer_15.png)

1. Nu kan du anpassa knappen ytterligare genom att ändra **[!UICONTROL Style]**, **[!UICONTROL Margin]** och **[!UICONTROL Border]** till exempel.

## Text {#text}

Använd **[!UICONTROL Text]** om du vill infoga text i e-postmeddelandet. Du kan justera färg, stil och storlek på texten i **[!UICONTROL Component Settings]**.

1. I **[!UICONTROL Content Components]**, dra och släppa **[!UICONTROL Text]** i en **[!UICONTROL Structure component]**.

   ![](assets/email_designer_11.png)

1. Klicka på den nya komponenten som du har lagt till för att anpassa texten och få tillgång till **[!UICONTROL Components Settings]** i den högra rutan i e-postdesignern.

1. Ändra texten med följande alternativ i verktygsfältet:

   ![](assets/email_designer_27.png)

   * **[!UICONTROL Change text style]**: använda fet, kursiv, understrykning eller genomstrykning i texten.
   * **Ändra justering**: Välj mellan vänster, höger, centrerad eller marginaljusterad justering för texten.
   * **[!UICONTROL Create list]**: lägg till punkt- eller nummerlista i texten.
   * **[!UICONTROL Set heading]**: kan du lägga till upp till sex rubriknivåer i texten.
   * **Teckenstorlek**: markera teckensnittsstorleken för texten i pixlar.
   * **[!UICONTROL Edit image]**: lägga till en bild eller en resurs i textkomponenten. [Läs mer om resurshantering](assets-essentials.md).
   * **[!UICONTROL Show the source code]**: visa textens källkod. Den kan inte ändras.
   * **[!UICONTROL Duplicate]**: lägga till en kopia av textkomponenten.
   * **[!UICONTROL Delete]**: ta bort den markerade textkomponenten från e-postmeddelandet.
   * **[!UICONTROL Add personalization]**: lägga till anpassningsfält för att anpassa innehållet utifrån dina profildata. [Läs mer om innehållspersonalisering](../personalization/personalize.md).

1. För en bättre användarupplevelse kan ni lägga till anpassningsfält för att rikta in er målgrupp. Mer information om detta hittar du i det här [avsnittet](../personalization/personalize.md).

1. Justera **[!UICONTROL Text color]**, **[!UICONTROL Font family]** och **[!UICONTROL Size]** i **[!UICONTROL Components Settings]**.

   ![](assets/email_designer_12.png)

## Delare {#divider}

Använd **[!UICONTROL Divider]** om du vill infoga en delningslinje för att ordna layouten och innehållet i ditt e-postmeddelande.
Du kan välja färg, stil och storlek för den brutna linjen i **[!UICONTROL Component Settings]**.

![](assets/email_designer_16.png)

## HTML {#HTML}

Använd **[!UICONTROL HTML]** om du vill kopiera och klistra in de olika delarna av din befintliga HTML. På så sätt kan du skapa kostnadsfria modulära HTML-komponenter.

Adobe rekommenderar att du skapar ett meddelande från grunden och kopierar innehållet från ditt befintliga e-postmeddelande till komponenter, så att det externa innehållet helt enkelt blir kompatibelt med e-postdesignern.

1. I **[!UICONTROL Content Components]**, dra och släppa **[!UICONTROL HTML]** i en **[!UICONTROL Structure component]**.

   ![](assets/email_designer_22.png)

1. Klicka på den nya komponenten och sedan **[!UICONTROL Show the source code]** för att lägga till HTML.

   ![](assets/email_designer_23.png)

1. Kopiera och klistra in den HTML-kod som du vill lägga till i e-postmeddelandet och klicka på **[!UICONTROL Save]**.

1. Nu kan du anpassa HTML ytterligare genom att ändra **[!UICONTROL Style]**, **[!UICONTROL Margin]** och **[!UICONTROL Border]** eller lägga till en länk för att dirigera om målgruppen till ett annat innehåll.

## Bild {#image}

Använd **[!UICONTROL Image]** om du vill infoga en bildfil från datorn i e-postmeddelandet.

1. I **[!UICONTROL Content Components]**, dra och släppa **[!UICONTROL Image]** i en **[!UICONTROL Structure component]**.

   ![](assets/email_designer_9.png)

1. Klicka **[!UICONTROL Browse]** om du vill välja en bildfil bland dina resurser.

   Om du vill veta mer om [!DNL Assets Essentials], se [Adobe Experience Manager Assets Essentials-dokumentation](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/introduction.html){target=&quot;_blank&quot;}.

1. Klicka på den nyligen tillagda komponenten för att börja konfigurera **[!UICONTROL Content Components]** och få tillgång till **[!UICONTROL Components Settings]** i den högra rutan i e-postdesignern.

1. Ange bildegenskaper:

   * **[!UICONTROL Image Title]** I kan du definiera en titel för bilden.
   * **[!UICONTROL Alt text]** I kan du definiera den bildtext som är länkad till bilden. Detta motsvarar attributet alt HTML.

   ![](assets/email_designer_10.png)

1. Du kan nu anpassa din bild ytterligare genom att ändra **[!UICONTROL Style]**, **[!UICONTROL Margin]** och **[!UICONTROL Border]** eller lägga till en länk för att dirigera om målgruppen till ett annat innehåll.

## Video {#Video}

>[!CONTEXTUALHELP]
>id="ac_edition_video_email"
>title="Videoinställningar"
>abstract="Använd den här komponenten för att infoga en video i e-postmeddelandet. Observera att videoklipp inte fungerar på alla e-postklienter. Vi rekommenderar att du ställer in en reservbild."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Ytterligare information"

>[!CONTEXTUALHELP]
>id="ac_edition_video_landing_page"
>title="Videoinställningar"
>abstract="Använd den här komponenten för att infoga en video på landningssidan. Observera att videoklipp inte fungerar på alla meddelandeklienter. Vi rekommenderar att du ställer in en reservbild."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Ytterligare information"

>[!CONTEXTUALHELP]
>id="ac_edition_video_fragment"
>title="Videoinställningar"
>abstract="Använd den här komponenten för att infoga en video i fragmentet. Observera att videoklipp inte fungerar på alla meddelandeklienter. Vi rekommenderar att du ställer in en reservbild."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Ytterligare information"

>[!CONTEXTUALHELP]
>id="ac_edition_video_template"
>title="Videoinställningar"
>abstract="Använd den här komponenten för att infoga en video i mallen. Observera att videoklipp inte fungerar på alla meddelandeklienter. Vi rekommenderar att du ställer in en reservbild."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Ytterligare information"

Använd **[!UICONTROL Video]** om du vill infoga en video i e-postmeddelandet via en URL-länk.

1. I **[!UICONTROL Content Components]**, dra och släppa **[!UICONTROL Video]** i en **[!UICONTROL Structure component]**.

   ![](assets/email_designer_17.png)

1. Klicka på den nyligen tillagda komponenten för att börja konfigurera **[!UICONTROL Content Components]** och få tillgång till **[!UICONTROL Components Settings]** i den högra rutan i e-postdesignern.

1. I **[!UICONTROL Video link]** fält för **[!UICONTROL Components Settings]** lägger du till din video-URL.

   ![](assets/email_designer_18.png)

1. Du kan lägga till en **[!UICONTROL Poster image]** till videon för att ange en bild som ska visas tills publiken klickar på uppspelningsknappen.

1. Du kan nu anpassa din bild ytterligare genom att ändra **[!UICONTROL Style]**, **[!UICONTROL Margin]** och **[!UICONTROL Border]** till exempel.

## Social {#social}

Använd **[!UICONTROL Social]** om du vill infoga länkar till sidor för sociala medier i ditt e-postmeddelande.

1. I **[!UICONTROL Content Components]**, dra och släppa **[!UICONTROL Social]** i en **[!UICONTROL Structure component]**.

   ![](assets/email_designer_19.png)

1. Klicka på den nyligen tillagda komponenten för att börja konfigurera **[!UICONTROL Content Components]** och få tillgång till **[!UICONTROL Components Settings]** i den högra rutan i e-postdesignern.

1. I **[!UICONTROL Social]** fält för **[!UICONTROL Components Settings]** väljer du vilka sociala medier du vill lägga till eller ta bort.

   ![](assets/email_designer_20.png)

1. Välj storlek på ikonerna i dialogrutan **[!UICONTROL Size of images]** fält.

1. Klicka på var och en av dina ikoner för sociala medier för att konfigurera **[!UICONTROL URL]** som er målgrupp kommer att omdirigeras till.

   ![](assets/email_designer_21.png)

1. Du kan också ändra ikonerna för vart och ett av dina sociala medier om det behövs i **[!UICONTROL Image]** fält.

1. Nu kan du anpassa dina ikoner för sociala medier ytterligare genom att ändra **[!UICONTROL Style]**, **[!UICONTROL Margin]** och **[!UICONTROL Border]**.

## Erbjudandebeslut {#offer-decision}

Använd **[!UICONTROL Offer decision]** för att infoga beslut i meddelanden. Besluten kommer att dra nytta av Beslutshantering för att välja det bästa erbjudandet att leverera till era kunder.

Relaterade ämnen:

* [Kom igång med Beslutshantering](../offers/get-started/starting-offer-decisioning.md)
* [Lägg till personaliserade erbjudanden i e-postmeddelanden](deliver-personalized-offers.md)
