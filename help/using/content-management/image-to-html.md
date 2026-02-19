---
solution: Journey Optimizer
product: journey optimizer
title: Konvertera bilder till HTML-mallar
description: Lär dig hur du använder AI-baserade bilder till HTML-konverterare för att konvertera bildmaterial till redigerbara HTML e-postmallar
feature: Email Design
topic: Content Management, Artificial Intelligence
role: User
level: Beginner
badge: label="Begränsad tillgänglighet" type="Informative"
keywords: e-post, mall, bild, HTML, AI, design, konverterare
exl-id: d13467b7-2f3c-4707-a7e0-9b46cb6cafb1
source-git-commit: e5b02fe84f00dec189d4002280e9a69b782cd91f
workflow-type: tm+mt
source-wordcount: '1640'
ht-degree: 0%

---

# Konvertera bilder till HTML-mallar {#image-to-html}

>[!AVAILABILITY]
>
>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

[!DNL Journey Optimizer] hjälper dig att avsevärt snabba upp e-postproduktionen genom att konvertera statiska bilddesigner till fullt anpassningsbara, modulära mallar för e-postinnehåll från HTML.

Genom att utnyttja generativ AI-teknik analyserar ett integrerat verktyg layouten, typografin, färgerna och de visuella elementen i bilden och genererar ren, modulär HTML-kod som bevarar designtroheten samtidigt som den är helt redigerbar med [Email Designer](../email/get-started-email-design.md) .

Denna kodningslösa kapacitet gör att marknadsförare kan omvandla visuella resurser från grafiska designers eller designverktyg till responsiva, redigerbara e-postmallar som kan sparas och återanvändas på flera resor och i flera kampanjer - utan att man behöver ha någon teknisk expertis.

De viktigaste fördelarna är följande:

* **Snabbare än manuell kodning** - Konverteraren omvandlar bilder till redigerbara HTML på några minuter, så att du kan hoppa över det tidskrävande arbetsflödet från mockup till HTML.
* **Inga tekniska kunskaper krävs** - Marknadsförarna kan producera och justera mallar utan design- eller utvecklingsstöd.
* **Återanvändbart mellan kampanjer** - Spara mallar i biblioteket och använd dem i alla resor och kampanjer.
* **Står för designen** - Utdata matchar layouten och formateringen samtidigt som de är helt kompatibla med e-post-Designer.

<!--* **Design fidelity**: Maintain visual consistency with your original design while creating fully editable content
* **Email compatibility**: Generate HTML that works seamlessly with the Email Designer and across email clients-->

+++ Vanliga användningsfall

Bilden till HTML-konverteraren är perfekt för:

* **Plattformsmigrering**: Migrerar från en annan e-postmarknadsföringsplattform? Konvertera dina befintliga e-postdesigner till [!DNL Journey Optimizer]-färdiga HTML-mallar utan att behöva bygga om från grunden.
* **Konvertering av designmodeller**: Omvandla designmodeller från verktyg som Photoshop, Figma eller andra designprogram till funktionella e-postmallar.
* **Skapa mallar snabbt**: Generera e-postmallar snabbt för tidskänsliga kampanjer utan att vänta på utvecklarresurser.
* **Skapa mallbibliotek**: Skapa ett omfattande bibliotek med varumärkeskonsekventa mallar som icke-tekniska teammedlemmar kan anpassa och distribuera.
* **Minska tekniska beroenden**: Gör det möjligt för marknadsförare att skapa och iterera på e-postmallar oberoende av varandra, vilket snabbar upp kampanjkörningen.

+++

## Skyddsutkast och rekommendationer {#limitations}

Tänk på följande begränsningar när du konverterar bilder till HTML innehållsmallar.

* **AI-tolkning**: AI genererar HTML baserat på den visuella tolkningen av din bild. Komplexa eller ovanliga designer kan kräva manuella justeringar efter konverteringen.

* **Textprecision**: Även om AI försöker identifiera och återge text korrekt måste du alltid verifiera textinnehållet och göra nödvändiga korrigeringar.

* **Dynamiskt innehåll**: Vid konverteringen skapas statisk HTML baserat på din bild. Ni måste lägga till personalisering, dynamiskt innehåll och spårning manuellt efter konverteringen.

* **Komplexa layouter**: Mycket komplexa designer med komplicerade lager, ovanliga former eller element som inte är standard kanske inte konverteras perfekt. Enklare design ger i allmänhet bättre resultat.

* **Bearbetningstid**: Konverteringsprocessen kan ta upp till 5 minuter beroende på bildens komplexitet och storlek. AI-bearbetningen sker i bakgrunden, vilket gör att du kan arbeta med andra uppgifter utan att behöva hålla skärmen öppen. Mallen sparas automatiskt som ett utkast när konverteringen är klar.

* **Begränsad tillgänglighet**: Som en begränsad tillgänglighetsfunktion förbättras kontinuerligt bilden till HTML-konverteraren. Funktionaliteten och exaktheten kan variera och din feedback förbättrar funktionen.

>[!NOTE]
>
>Konverteraren för bilder till HTML är utformad för att ge en bra startpunkt för e-postgenerering. Den genererade HTML bör granskas och förfinas med e-post-Designer för att säkerställa att den uppfyller dina exakta krav.

## Konvertera en bild till en HTML-mall {#convert-image}

Följ stegen nedan för att konvertera en bilddesign till en helt anpassningsbar e-postmall från HTML.

1. Kontrollera att du har en bildfil i JPEG- eller PNG-format som innehåller din e-postdesign.

   >[!NOTE]
   >
   >För bästa resultat bör du använda bilder med hög kvalitet med tydliga visuella element och läsbar text. Bilderna bör helst vara 600-800 pixlar breda för att matcha e-postens standardmått.

1. Du kommer åt innehållsmalllistan genom att välja **[!UICONTROL Content Management]** > **[!UICONTROL Content templates]** på den vänstra menyn.

1. Klicka på **[!UICONTROL Create template]**.

1. Fyll i mallinformationen och välj **[!UICONTROL Email]** som kanal och klicka på **[!UICONTROL Create]**.

1. Utför följande steg i avsnittet **[!UICONTROL Convert image to template]**:

   * (Valfritt) Om din organisation har definierade teman för varumärket i Journey Optimizer kan du välja ett tema som indata så att den genererade HTML formateras enligt dina varumärkestemaparametrar. [Läs mer om teman](../email/apply-email-themes.md)

     Formatering som bakgrundsfärg, knappfärg, teckensnitt, radavstånd, marginaler och utfyllnad tillämpas på den genererade mallen, vilket minskar ytterligare designarbete och skapar en mall som är klar att användas med minimala redigeringar.

   * Om du vill kunna överföra en bild måste du se till att den inte innehåller någon personligt identifierbar information (PII) eller andra känsliga data, och kontrollera motsvarande alternativ för att bekräfta att du har granskat filen.

   * Klicka på knappen **[!UICONTROL Upload image]** för att välja bildfilen.

     ![](../email/assets/email_designer_convert_img.png)

     >[!CAUTION]
     >
     >När du överför en bild för konvertering tas allt innehåll som för närvarande läggs till i e-postmeddelandet bort och ersätts med den genererade mallen.


1. När du har valt bilden klickar du på **[!UICONTROL Open]** för att starta den AI-baserade konverteringsprocessen.

   >[!NOTE]
   >
   >Genereringsprocessen kan ta upp till 5 minuter beroende på hur komplex och stor din bilddesign är. Du kan navigera bort från den här skärmen och arbeta med andra åtgärder medan konverteringen pågår.

1. När konverteringen är klar sparas innehållsmallen automatiskt som ett utkast.

   ![](../email/assets/email_designer_converted_img.png)

1. Klicka på **[!UICONTROL Edit email body]**. Den konverterade mallen öppnas i [e-post-Designer](../email/get-started-email-design.md) med fullständiga redigeringsfunktioner. Nu kan du:

   * Granska, redigera textinnehåll och tillämpa personalisering
   * Ändra bilder och lägga till länkar
   * Justera färger, teckensnitt och format
   * Lägga till, ta bort eller ordna om innehållskomponenter
   * Utnyttja alla e-post-Designer-funktioner på samma sätt som andra mallar

   ![](../email/assets/email_designer_html_components.png)

1. Gör nödvändiga justeringar för att förfina mallen och anpassa den efter varumärkesriktlinjerna.

1. När du är nöjd med mallen klickar du på **[!UICONTROL Save]**.

Din mall är nu tillgänglig i innehållsmallbiblioteket och kan användas när du skapar e-postmeddelanden under resor eller kampanjer. [Lär dig använda innehållsmallar](../email/use-email-templates.md)

## Bästa praxis {#best-practices}

Följ de här rekommendationerna för att få optimala resultat när du konverterar bilder till HTML innehållsmallar.

+++Innan du börjar

* **Spara befintligt innehåll**: Om du konverterar en bild till HTML ersätts allt befintligt innehåll i e-postmeddelandet. Spara alltid ditt aktuella arbete innan du använder den här funktionen.
* **Planera ditt arbetsflöde**: Använd konverteraren för bilden till HTML i början av e-postprocessen eller kontrollera att du är redo att ersätta allt aktuellt innehåll.

+++

+++Bildförberedelse

* **Upplösning**: Använd högupplösta bilder (minst 1 200 pixlar bred) för bättre textigenkänning och elementidentifiering
* **Klarhet**: Kontrollera att texten är tydligt läsbar och att visuella element är väldefinierade
* **Bredd**: Designa bilder med standardbredder för e-post (600-800px) så att de matchar vanliga krav för e-postklient
* **Filformat**: Använd JPEG- eller PNG-format - undvik komprimerade bilder eller bilder med låg kvalitet
* **Fullständig design**: Inkludera den fullständiga e-postdesignen i en enda bild, från sidhuvud till sidfot

+++

+++Designöverväganden

* **Enkla layouter**: Enklare, välstrukturerade layouter konverteras exaktare än mycket komplexa designer
* **Standardelement**: Använd vanliga designmönster för e-post (sidhuvud, brödavsnitt, CTA:er, sidfot)
* **Textläsbarhet**: Kontrollera att texten och bakgrunden har tillräckligt hög kontrast
* **Webbsäkra teckensnitt**: Designer som använder vanliga webbsäkra teckensnitt har bättre återgivning
* **Undvik överlappande element**: Behåll designelement tydligt separerade för bättre strukturegenkänning

+++

+++Efter konvertering

* **Granska utkastet**: När konverteringen är klar sparas mallen automatiskt som ett utkast. Granska den genererade HTML noggrant
* **Testa noggrant**: Testa e-postmeddelandet på olika e-postklienter och enheter
* **Förfina manuellt**: Gör ändringar efter behov med e-postprogrammets fullständiga redigeringsfunktioner i Designer
* **Varumärkesjustering**: Verifiera att färger, teckensnitt och format matchar varumärkesriktlinjerna
* **Personalization**: Lägg till dynamiska innehålls- och personaliseringstoken efter behov
* **Hjälpmedel**: Granska och förbättra tillgänglighetsfunktioner om det behövs

+++

## Vanliga frågor och svar {#faq}

+++Vad händer med mitt befintliga e-postinnehåll när jag använder bilden till HTML-konverteraren?

Allt befintligt innehåll i e-postmeddelandet tas bort och ersätts med den nya mallen när du överför en bild för konvertering. Spara viktigt innehåll innan du använder den här funktionen. Det är bäst att använda konverteraren för bild till HTML i början av e-postprocessen.

+++

+++Vilka filformat stöds?

Konverteraren för bild till HTML stöder bildformaten JPEG (.jpg, .jpeg) och PNG (.png).

+++

+++Hur lång tid tar konverteringsprocessen?

Konverteringen kan ta upp till 5 minuter, beroende på hur komplex och stor bilddesignen är. AI-bearbetningen sker i bakgrunden, så du kan navigera bort och arbeta med andra åtgärder - du behöver inte hålla skärmen öppen. När konverteringen är klar sparas filen automatiskt som ett utkast som du kan granska och redigera.

+++

+++Kan jag redigera den genererade mallen?

Ja! Den genererade HTML-mallen öppnas i e-post-Designer med fullständiga redigeringsfunktioner. Du kan ändra alla aspekter av mallen, inklusive text, bilder, format, layout och struktur.

+++

+++Vad händer om konverteringen inte matchar min design exakt?

AI gör sitt bästa för att tolka din design på ett korrekt sätt, men det kan behövas vissa manuella finjusteringar. Använd e-post-Designer för att justera eventuella element som behöver finjusteras.

+++

+++Kan jag använda den här funktionen för landningssidor eller andra innehållstyper?

Konverteraren av bilder till HTML är för närvarande särskilt framtagen för e-postmallar. För andra innehållstyper använder du standardalternativen för design och import som finns i e-post-Designer.

+++

+++Behövs särskild behörighet för att använda den här funktionen?

Konverteraren för bilder till HTML är tillgänglig med begränsad tillgänglighet. Du behöver begränsad tillgänglighetsåtkomst (kontakta din Adobe-representant för att få åtkomst) och Designer-standardbehörigheter för e-post för att använda den här funktionen.

+++

+++Kan jag återanvända konverterade mallar för flera kampanjer?

Ja! Mallar som skapas med HTML-konverteraren sparas automatiskt i biblioteket Innehållsmallar. Ni kan komma åt och återanvända dem i alla e-postmeddelanden under era resor och kampanjer. [Läs mer](content-templates.md)

+++

+++Kan jag använda detta för plattformsmigrering?

Ja! Image to HTML converter är idealisk för migrering från andra e-postmarknadsföringsplattformar. Exportera eller ta skärmdumpar av dina e-postdesigner från din tidigare plattform och konvertera dem till HTML-mallar som är redo för AJO utan att behöva bygga om dem från grunden.

+++

## Relaterade ämnen {#related-topics}

* [Kom igång med innehållsmallar](content-templates.md)
* [Skapa innehållsmallar](create-content-templates.md)
* [Använd e-postmallar](../email/use-email-templates.md)
* [Utnyttja e-postteman](../email/apply-email-themes.md)
* [Kom igång med e-postdesign](../email/get-started-email-design.md)
* [Importera e-postinnehåll](../email/existing-content.md)
* [Designa innehåll från grunden](../email/content-from-scratch.md)
