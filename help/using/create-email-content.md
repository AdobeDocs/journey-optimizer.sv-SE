---
title: Designa e-postmeddelanden i Journey Optimizer
description: Lär dig hur du utformar e-postinnehåll
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%

---

# Designa ditt e-postinnehåll i användargränssnittet {#create-email-content}

![](assets/do-not-localize/badge.png)

När du har [skapat meddelandet](create-message.md) kan du börja skapa ditt e-postinnehåll.

1. Välj **[!UICONTROL Email designer]** i avsnittet **[!UICONTROL Edit content]** från det nya meddelandet.

   ![](assets/import-html_1.png)

1. På hemsidan för e-postdesignern väljer du hur du vill utforma e-postmeddelandet bland följande alternativ:

   * Välj **[!UICONTROL Design from scratch]** om du vill använda e-postdesignerfunktionerna för att skapa e-postinnehåll.

   * Välj **[!UICONTROL Start from template]** om du vill skapa e-postmeddelandet från en inbyggd lista med mallar. Observera att du inte kan skapa andra mallar.

   * Välj **[!UICONTROL Code your own]** om du vill ange eller klistra in HTML Raw-kod. [Läs mer](existing-content.md#import-raw-html-code).

   * Välj **[!UICONTROL Import HTML]** om du vill importera en HTML-fil eller en ZIP-mapp. [Läs mer](existing-content.md#import-html-content-from-file).

   ![](assets/email_designer_25.png)

## Designa från grunden

Följ stegen nedan för att börja skapa e-postinnehåll med e-postdesignern:

1. När du har valt alternativet **[!UICONTROL Design from scratch]** börjar du utforma e-postinnehållet genom att dra och släppa **[!UICONTROL Structure components]** för att definiera layouten för e-postmeddelandet.

   ![](assets/email_designer_2.png)

1. I listrutan **[!UICONTROL Content components]** kan du lägga till så många **[!UICONTROL Content components]** som du behöver i strukturkomponenten. [Läs mer om innehållskomponenter](content-components.md).

   ![](assets/email_designer_3.png)

1. Varje komponent kan anpassas ytterligare med **[!UICONTROL Component settings]**-avsnittet. Du kan till exempel ändra textstil, utfyllnad eller marginal för komponenten. [Läs mer om format i e-postredigeraren](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/styles.html).

   ![](assets/email_designer_4.png)

1. Från **[!UICONTROL Assets picker]** kan du lägga till resurser som lagras i **[!UICONTROL Assets library]** direkt i e-postmeddelandet. [Läs mer om resurshantering](assets-essentials.md).

   Dubbelklicka på mappen som innehåller dina resurser och dra och släpp den resurs som du vill lägga till i e-postmeddelandet.

   ![](assets/email_designer_5.png)

1. Lägg till anpassningsfält för att anpassa innehållet utifrån dina profildata. [Läs mer om innehållspersonalisering](personalization/personalize.md).

   ![](assets/email_designer_6.png)

1. På fliken **[!UICONTROL Links]** i den vänstra rutan kontrollerar du listan med alla URL:er för ditt innehåll som ska spåras. Du kan ändra deras **[!UICONTROL Tracking Type]**, **[!UICONTROL Label]** och **[!UICONTROL Tags]** om det behövs.

   ![](assets/email_designer_7.png)

1. Om det behövs kan du växla till kodredigeraren för att anpassa e-postmeddelandet ytterligare genom att klicka på **[!UICONTROL Switch to code editor]** på den avancerade menyn. Mer information om kodredigeraren finns på den här [sidan](existing-content.md#import-raw-html-code).

   >[!NOTE]
   >
   >Du kommer inte att kunna använda den visuella designern för det här e-postmeddelandet när du har växlat till kodredigeraren.

   ![](assets/email_designer_26.png)

1. Klicka på **[!UICONTROL Preview]** för att kontrollera din e-poståtergivning. Du kan välja skrivbordsvy eller mobilvy.

   ![](assets/email_designer_8.png)

1. När e-postmeddelandet är klart klickar du på **[!UICONTROL Save & Close]**.

Ditt e-postinnehåll kan nu användas i ett meddelande. [Lär dig hur du skickar ett meddelande](publish-manage-message.md).

## Definiera e-poststrukturen {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="Om strukturkomponenter"
>abstract="Strukturkomponenter definierar layouten för e-postmeddelandet."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Definiera e-postkolumner"
>abstract="Med e-postdesignern kan du enkelt definiera layouten för e-postmeddelandet genom att definiera kolumnstrukturen."

Med e-postdesignern kan du enkelt definiera e-postens struktur. Genom att lägga till och flytta strukturella element med enkla dra-och-släpp-åtgärder kan du designa formen på e-postmeddelandet på några sekunder.

Så här redigerar du strukturen för ett e-postmeddelande:

1. Öppna ett befintligt innehåll eller skapa ett nytt e-postinnehåll.
1. Du kommer åt **[!UICONTROL Structure components]** genom att välja ikonen **+** till vänster.
1. Dra och släpp de strukturkomponenter som du behöver för att forma e-postmeddelandet.
En blå linje visar strukturkomponenternas exakta placering innan du släpper den. Du kan släppa det ovanför, mellan eller under en annan komponent, men inte inuti.

   >[!NOTE]
   >
   >Observera att stapeln med kolumner inte är kompatibel med alla e-postprogram. Om det inte finns stöd för det här alternativet staplas inte kolumner.
   >
   >När du har placerat i e-postmeddelandet kan du inte flytta eller ta bort dina komponenter om det inte redan finns en innehållskomponent eller ett fragment inuti.

1. Flera strukturkomponenter som består av en eller flera kolumner är tillgängliga.

   Välj **[!UICONTROL n:n column]**-komponenten för att definiera antalet kolumner du vill använda (mellan 3 och 10). Du kan också definiera bredden på varje kolumn genom att flytta pilarna längst ned i varje kolumn.

   >[!NOTE]
   >
   >Varje kolumnstorlek får inte vara mindre än 10 % av strukturkomponentens totala bredd. Du kan inte ta bort en kolumn som inte är tom.

När strukturen har definierats kan du lägga till innehållsfragment och komponenter i e-postmeddelandet.

## Använda en förrubrik {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Använda en förrubrik"
>abstract="Med preheader kan du konfigurera en kort sammanfattningstext som hjälper dig att spåra och anpassa e-postmeddelanden."

En preheader är en kort sammanfattningstext som följer efter ämnesraden när du visar ett e-postmeddelande från din e-postklient. Förrubriken kan hjälpa dig att spåra och anpassa dina e-postmeddelanden bättre.

Markera redigeringsrutan **[!UICONTROL Preheader]** och lägg till innehåll.

Du kan lägga till en **[!UICONTROL Content block]**, en **[!UICONTROL Dynamic content]** eller en **[!UICONTROL Personalization fields]** i innehållet i preheader.

>[!NOTE]
>
>Observera att sidhuvuden inte är kompatibla med alla e-postklienter. Om det inte stöds visas inte prerubriken.

## Bakgrundsinställningar {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="Bakgrundsinställningar"
>abstract="Med e-postdesignern kan du anpassa bakgrundsfärg eller bakgrundsbild för innehållet.Observera att bakgrundsbilden inte stöds av alla e-postklienter."
>additional-url="https://docs.google.com/spreadsheets/d/1TLo62YKm3tThUWDOIliCQFWs3dpNjpDfw6DdTr1oGOw/edit#gid=0" text="Ytterligare information"

När det gäller att ange bakgrunder med e-postdesignern rekommenderar Adobe följande:

1. Använd en bakgrundsfärg på e-postmeddelandets brödtext om det behövs i designen.
1. I de flesta fall anger du bakgrundsfärger på kolumnnivå.
1. Försök att inte använda bakgrundsfärger i bild- eller textkomponenter eftersom de är svåra att hantera.

Nedan visas de tillgängliga bakgrundsinställningarna som du kan använda.

* Ange ett **[!UICONTROL Background color]**-värde för hela e-postmeddelandet. Se till att du väljer brödtextinställningarna i navigeringsträdet som du kommer åt från den vänstra paletten.

* Ange samma bakgrundsfärg för alla strukturkomponenter genom att välja **[!UICONTROL Viewport background color]**. Med det här alternativet kan du välja en annan inställning från bakgrundsfärgen.

* Ange olika bakgrundsfärger för varje strukturelement. Välj en struktur i navigeringsträdet som du kommer åt från den vänstra paletten om du bara vill använda en viss bakgrundsfärg på den strukturen.

   Se till att du inte anger någon bakgrundsfärg för visningsrutan eftersom den kan dölja strukturens bakgrundsfärger.

* Ange **[!UICONTROL Background image]** som innehåll för en strukturkomponent.

   >[!NOTE]
   >
   >Vissa e-postprogram stöder inte bakgrundsbilder. Om alternativet inte stöds används radens bakgrundsfärg i stället. Se till att du väljer en lämplig bakgrundsfärg om bilden inte kan visas.

* Ange en bakgrundsfärg på kolumnnivå.

   >[!NOTE]
   >
   >Detta är det vanligaste användningsfallet. Adobe rekommenderar att du ställer in bakgrundsfärger på kolumnnivå eftersom detta ger större flexibilitet när du redigerar hela e-postinnehållet.

   Du kan också ange en bakgrundsbild på kolumnnivå, men den används sällan.

### Exempel: justera lodrät justering och utfyllnad {#example--adjusting-vertical-alignment-and-padding}

Du vill justera utfyllnaden och den lodräta justeringen inuti en strukturkomponent som består av tre kolumner. Följ stegen nedan för att göra detta:

1. Markera strukturkomponenten direkt i e-postmeddelandet eller använd det strukturträd som finns till vänster **Palett**.
1. Klicka på **[!UICONTROL Select a column]** i det sammanhangsberoende verktygsfältet **och välj det som du vill redigera.** Du kan också välja det i strukturträdet.

   De redigerbara parametrarna för den kolumnen visas i rutan **[!UICONTROL Settings]** till höger.

1. Under **[!UICONTROL Vertical alignment]** väljer du **[!UICONTROL Up]**.

   Innehållskomponenten visas ovanpå kolumnen.

1. Ange den översta utfyllnaden i kolumnen under **[!UICONTROL Padding]**. Klicka på låsikonen om du vill bryta synkroniseringen med den nedre utfyllnaden.

   Definiera vänster och höger utfyllnad för den kolumnen.

1. Gör på samma sätt om du vill justera justeringen och utfyllnaden för de andra kolumnerna.

1. Spara ändringarna.

## Definiera ett format för länkar {#about-styling-links}

Du kan stryka under en länk och välja dess färg och mål i e-postdesignern.

1. I en komponent där en länk infogas, markerar du etikettexten för länken.

1. Markera **[!UICONTROL Underline link]** i komponentinställningarna för att stryka under etikettexten för länken.

1. Välj en **[!UICONTROL Target]** om du vill välja i vilket webbläsarsammanhang länken ska öppnas.

1. Om du vill ändra färg på länken klickar du på **[!UICONTROL Link color]**.

1. Välj den färg du behöver.

1. Spara ändringarna.

## Lägg till textbundna formatattribut {#adding-inline-styling-attributes}

När du markerar ett element och visar dess inställningar på sidopanelen i gränssnittet för e-postdesignern kan du anpassa infogade attribut och deras värde för det specifika elementet.

1. Markera ett element i innehållet.
1. På sidopanelen letar du efter **[!UICONTROL Styles Inline]**-inställningarna.

1. Ändra värdena för befintliga attribut eller lägg till nya med knappen **+**. Du kan lägga till alla attribut och värden som är CSS-kompatibla.

Formateringen används sedan på det markerade elementet. Om de underordnade elementen inte har några definierade formatattribut ärvs det överordnade elementets formatering.


## Skapa textversionen av ett e-postmeddelande {#generate-text-version}

Vi rekommenderar att du skapar en textversion av e-postbrödtexten, som används när HTML-innehåll inte kan visas.

Som standard skapar e-postdesignern en **[!UICONTROL Plain text]**-version av ditt e-postmeddelande, inklusive anpassningsfält. Den här versionen genereras och synkroniseras automatiskt med HTML-versionen av ditt innehåll.

Om du föredrar att använda ett annat innehåll för den oformaterade textversionen följer du stegen nedan:

1. Välj fliken **[!UICONTROL Plain text]** i ditt e-postmeddelande.

1. Använd alternativet **[!UICONTROL Sync with HTML]** för att inaktivera synkronisering.

   ![](assets/text_version_1.png)

1. Bekräfta ditt val genom att klicka på bockmarkeringen.

   ![](assets/text_version_2.png)

1. Du kan sedan redigera den oformaterade textversionen efter behov.

>[!CAUTION]
>
>* Ändringar som görs i vyn **[!UICONTROL Plain text]** återspeglas inte i HTML-vyn.
   >
   >
* Om du aktiverar alternativet **[!UICONTROL Sync with HTML]** igen efter att du har uppdaterat innehållet i oformaterad text, kommer ändringarna att gå förlorade och ersättas med textinnehåll som genererats från HTML-versionen.

>


