---
solution: Journey Optimizer
product: journey optimizer
title: Spåra meddelanden
description: Lär dig hur du lägger till länkar och spårar skickade meddelanden
feature: Email Design, Monitoring
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: länkar, spåra, övervaka, e-post
exl-id: 689e630a-00ca-4893-8bf5-6d1ec60c52e7
source-git-commit: 4847415fa33ebf1c21622ebf4faecafd4decc8d3
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 1%

---

# Lägga till länkar och spåra meddelanden {#tracking}

Använd [!DNL Journey Optimizer] om du vill lägga till länkar till ditt innehåll och spåra meddelanden som skickats för att övervaka mottagarnas beteende.

## Aktivera spårning {#enable-tracking}

Du kan aktivera spårning på e-postmeddelandenivå genom att kontrollera alternativen **[!UICONTROL Email opens]** och/eller **[!UICONTROL Click on email]** när du skapar ditt meddelande inuti en resa eller kampanj.

>[!BEGINTABS]

>[!TAB Aktivera spårning i en resa]

![](assets/message-tracking-journey.png)

>[!TAB Aktivera spårning i en kampanj]

![](assets/message-tracking-campaign.png)

>[!ENDTABS]

>[!NOTE]
>
>Båda alternativen är aktiverade som standard.

På så sätt kan du spåra mottagarnas beteende via:

* **[!UICONTROL Email opens]**: Meddelanden som har öppnats.
* **[!UICONTROL Click on email]**: Klicka på länkar i ett e-postmeddelande.

## Infoga länkar {#insert-links}

När du utformar ett meddelande kan du lägga till länkar till innehållet.

>[!NOTE]
>
>När [spårning är aktiverat](#enable-tracking) spåras alla länkar som ingår i meddelandeinnehållet.

Följ stegen nedan om du vill infoga länkar i ditt e-postinnehåll:

1. Markera ett element och klicka på **[!UICONTROL Insert link]** i det sammanhangsberoende verktygsfältet.

   ![](assets/message-tracking-insert-link.png)

1. Välj den typ av länk som du vill skapa:

   * **[!UICONTROL External link]**: Infoga en länk till en extern URL.

   * **[!UICONTROL Landing page]**: Infoga en länk till en landningssida. [Läs mer](../landing-pages/get-started-lp.md)

   * **[!UICONTROL One click Opt-out]**: Infoga en länk så att användare snabbt kan avbryta prenumerationen på dina meddelanden utan att behöva bekräfta att de vill avanmäla sig. [Läs mer](email-opt-out.md#one-click-opt-out).

   * **[!UICONTROL External Opt-in/Subscription]**: Infoga en länk för att ta emot meddelanden från ditt varumärke.

   * **[!UICONTROL External Opt-out/Unsubscription]**: Infoga en länk om du vill avbryta prenumerationen på meddelanden från ditt varumärke. Läs mer om hantering av avanmälan i [det här avsnittet](email-opt-out.md#opt-out-management).

   * **[!UICONTROL Mirror page]**: Lägg till en länk för att visa e-postinnehållet i en webbläsare. [Läs mer](#mirror-page)

1. Ange önskad URL-adress i motsvarande fält eller välj en landningssida och definiera länkinställningar och format. [Läs mer](#adjust-links)

   >[!NOTE]
   >
   >För att tolka URL:er uppfyller [!DNL Journey Optimizer] URI-syntaxen ([RFC 3986 standard](https://datatracker.ietf.org/doc/html/rfc3986){target="_blank"}), som inaktiverar vissa internationella specialtecken i URL:er. När du försöker skicka korrekturet eller e-postmeddelandet och returnerar ett fel som inbegriper en URL som har lagts till i innehållet, kan du URL-koda strängen som en tillfällig lösning.

1. Du kan anpassa länkarna. [Läs mer](../personalization/personalization-syntax.md#perso-urls)

1. Spara ändringarna.

1. När länken har skapats kan du fortfarande ändra den från rutorna **[!UICONTROL Settings]** och **[!UICONTROL Styles]** till höger.

   ![](assets/message-tracking-link-settings.png)

>[!NOTE]
>
>E-postmeddelanden av marknadsföringstyp måste innehålla en [länk för avanmälan](../privacy/opt-out.md#opt-out-management), vilket inte krävs för transaktionsmeddelanden. Meddelandekategorin (**[!UICONTROL Marketing]** eller **[!UICONTROL Transactional]**) definieras i [kanalkonfigurationen](../configuration/channel-surfaces.md#email-type) när meddelandet skapas.

## Justera länkar {#adjust-links}

Du kan justera länkarna med rutorna **[!UICONTROL Settings]** och **[!UICONTROL Styles]** till höger. Du kan stryka under en länk, redigera dess färg och välja dess mål.

1. Markera länken i en **[!UICONTROL Text]**-komponent där en länk infogas.

1. På fliken **[!UICONTROL Settings]** väljer du hur din målgrupp ska omdirigeras med listrutan **[!UICONTROL Target]**:

   * **[!UICONTROL None]**: öppnar länken i samma ram som den klickades på (standard).
   * **[!UICONTROL Blank]**: öppnar länken i ett nytt fönster eller på en ny flik.
   * **[!UICONTROL Self]**: öppnar länken i samma ram som den klickades på.
   * **[!UICONTROL Parent]**: öppnar länken i den överordnade ramen.
   * **[!UICONTROL Top]**: öppnar länken i hela fönstrets brödtext.

   ![](assets/link_2.png)

1. Markera **[!UICONTROL Underline link]** om du vill stryka under etikettexten för länken.

   ![](assets/link_1.png)

1. Om du vill ändra färg på länken klickar du på **[!UICONTROL Link color]** på fliken **[!UICONTROL Styles]**.

   ![](assets/link_3.png)

1. Spara ändringarna.

## Länka till en spegelsida {#mirror-page}

Spegelsidan är en HTML-sida som är tillgänglig online via en webbläsare. Innehållet är identiskt med innehållet i ditt e-postmeddelande.

Om du vill lägga till en länk till en spegelsida i ditt e-postmeddelande [infogar du en länk](#insert-links) och väljer **[!UICONTROL Mirror page]** som typ av länk.

![](assets/message-tracking-mirror-page.png)

Spegelsidan skapas automatiskt.

>[!IMPORTANT]
>
>Länkar för spegelsidor genereras automatiskt och kan inte redigeras. De innehåller alla krypterade, personliga data som krävs för att återge det ursprungliga e-postmeddelandet. Om du använder anpassade attribut med stora värden kan det därför generera långa URL-adresser för spegelsidor, vilket kan förhindra länken från att fungera i webbläsare som har en maximal URL-längd.

När e-postmeddelandet har skickats visas innehållet i e-postmeddelandet i sin standardwebbläsare när mottagarna klickar på länken för spegelsidan.

>[!NOTE]
>
>I det [korrektur](../content-management/proofs.md) som skickas till testprofilerna är länken till spegelsidan inte aktiv. Den aktiveras endast i de slutliga meddelandena.

Kvarhållningsperioden för en spegelsida är 60 dagar. Efter den fördröjningen är spegelsidan inte längre tillgänglig.

## Hantera spårning {#manage-tracking}

Med [e-post-Designer](content-from-scratch.md) kan du hantera spårade URL-adresser, till exempel redigera spårningstypen för varje länk.

1. Klicka på ikonen **[!UICONTROL Links]** i den vänstra rutan om du vill visa en lista över alla URL:er för ditt innehåll som ska spåras.

   Med den här listan kan du ha en centraliserad vy och hitta varje URL i e-postinnehållet.

1. Om du vill redigera en länk klickar du på motsvarande pennikon.

1. Du kan ändra **[!UICONTROL Tracking Type]** om det behövs:

   ![](assets/message-tracking-edit-a-link.png)

   För varje spårad URL kan du ange spårningsläget till något av följande värden:

   * **[!UICONTROL Tracked]**: Aktiverar spårning på den här URL:en.
   * **[!UICONTROL Opt out]**: Utser den här URL:en som en avanmälnings- eller avanmälnings-URL.
   * **[!UICONTROL Mirror page]**: Den här URL:en är en URL för en spegelsida.
   * **[!UICONTROL Never]**: Aktiverar aldrig spårning av den här URL:en.

Det finns rapporter om öppningar och klick i [Live-rapporten](../reports/live-report.md) och i [Customer Journey Analytics-rapporten](../reports/report-gs-cja.md).

## Anpassa URL-spårning {#url-tracking}

Vanligtvis hanteras [URL-spårning](email-settings.md#url-tracking) på konfigurationsnivå, men profilattribut stöds inte. Det enda sättet att göra det är för närvarande att [anpassa URL:er](../personalization/personalization-syntax.md#perso-urls) i e-postdesignern.

Följ stegen nedan om du vill lägga till personaliserade URL-spårningsparametrar för länkarna.

1. Markera en länk och klicka på **[!UICONTROL Insert link]** i det sammanhangsberoende verktygsfältet.

1. Välj personaliseringsikonen. Det är bara tillgängligt för följande typer av länkar: **Extern länk**, **Avprenumerationslänk** och **Avanmäl dig**.

   ![](assets/message-tracking-insert-link-perso.png)

1. Lägg till URL-spårningsparametern och välj det profilattribut du vill i personaliseringsredigeraren.

   ![](assets/message-tracking-perso-parameter.png)

1. Spara ändringarna.

1. Upprepa stegen ovan för varje länk som du vill lägga till spårningsparametern i.

När e-postmeddelandet skickas läggs den här parametern automatiskt till i slutet av URL:en. Du kan sedan hämta den här parametern i webbanalysverktyg eller i resultatrapporter.

>[!NOTE]
>
>Om du vill verifiera den slutliga URL:en kan du [skicka ett korrektur](../content-management/preview-test.md#send-proofs) och klicka på länken i innehållet i e-postmeddelandet när du har fått korrekturet. URL:en ska visa spårningsparametern. I exemplet ovan blir den slutliga URL:en: <https://luma.enablementadobe.com/content/luma/us/en.html?utm_contact=profile.userAccount.contactDetails.homePhone.number>
