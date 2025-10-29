---
solution: Journey Optimizer
product: journey optimizer
title: Konvertera bilder till HTML-mallar med Template Accelerator
description: Lär dig använda AI-driven Template Accelerator för att konvertera bildmaterial till redigerbara e-postmallar från HTML
feature: Email Design
topic: Content Management
role: User
level: Beginner
keywords: e-post, mall, bild, HTML, AI, design, accelerator
hide: true
hidefromtoc: true
source-git-commit: ddbab603e4ac612a49a3853fcac428950def1d98
workflow-type: tm+mt
source-wordcount: '1538'
ht-degree: 0%

---

# Konvertera bilder till HTML-mallar med Template Accelerator {#image-to-html}

>[!CONTEXTUALHELP]
>id="ajo_template_accelerator"
>title="Template Accelerator"
>abstract="Använd Template Accelerator för att konvertera statisk bilddesign (JPEG eller PNG) till fullt anpassningsbara HTML e-postmallar. Den här AI-baserade funktionen hjälper dig att snabbt omvandla visuell design till responsivt, redigerbart e-postinnehåll. Obs! Allt befintligt innehåll i e-postmeddelandet tas bort när du överför en bild för konvertering."

>[!AVAILABILITY]
>
>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

## Översikt {#overview}

Template Accelerator är en innovativ AI-baserad funktion på menyn **Innehållsmallar** som dramatiskt snabbar upp e-postskapandet genom att konvertera statiska bilddesigner till fullt anpassningsbara HTML-mallar för e-postinnehåll. Med det här verktyget kan marknadsförare omvandla visuell design från grafiska designers eller designverktyg till responsiva, redigerbara e-postmallar som kan sparas i biblioteket Innehållsmallar och sedan återanvändas på flera resor och i flera kampanjer.

Genom att utnyttja generativ AI-teknik analyserar Template Accelerator layouten, typografin, färgerna och de visuella elementen i bilden och genererar ren, strukturerad HTML-kod som bevarar designtroheten samtidigt som den säkerställer fullständig redigerbarhet och kompatibilitet med Email Designer.

**Viktiga fördelar:**

* **Snabbare redigering**: Minska tiden det tar att skapa e-post genom att direkt konvertera designmodeller till återanvändbara innehållsmallar
* **Designer-developer bridge**: Eliminera behovet av manuell HTML-kodning när du arbetar med visuell design
* **Designåtergivning**: Behåll integriteten i den ursprungliga designen när du skapar redigerbart innehåll
* **Återanvändbarhet**: Spara mallar i biblioteket Innehållsmallar för användning på flera resor och i flera kampanjer
* **E-postkompatibilitet**: Generera HTML som fungerar smidigt med e-post-Designer och mellan e-postklienter

## Förhandskrav {#prerequisites}

Kontrollera att du har:

* Åtkomst till Adobe Journey Optimizer med e-post-Designer
* En bildfil i JPEG- eller PNG-format som innehåller din e-postdesign
* Begränsad tillgänglighet för funktionen Template Accelerator (kontakta Adobe)

>[!NOTE]
>
>För bästa resultat bör du använda bilder med hög kvalitet med tydliga visuella element och läsbar text. Bilderna bör helst vara 600-800 pixlar breda för att matcha e-postens standardmått.

## Konvertera en bild till en HTML-mall {#convert-image}

Så här konverterar du en bilddesign till en helt anpassningsbar e-postmall från HTML:

1. Öppna listan Innehållsmallar genom att välja **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** på den vänstra menyn.

1. Klicka på **[!UICONTROL Create template]**.

1. Fyll i mallinformationen och välj **[!UICONTROL Email]** som kanal.

1. Klicka på **[!UICONTROL Create]** för att komma åt e-post-Designer.

1. Välj **[!UICONTROL Import HTML]** på startsidan för e-post till Designer.

   ![](assets/import-html_2.png)

1. I importdialogrutan visas avsnittet **[!UICONTROL Convert image to HTML]**.

   >[!CAUTION]
   >
   >När du överför en bild för konvertering tas **allt innehåll som för närvarande läggs till i e-postmeddelandet bort och ersätts** med den genererade mallen. Om du har befintligt innehåll i ditt e-postmeddelande måste du spara det innan du fortsätter med bildkonverteringen.

1. Klicka på knappen **[!UICONTROL Load image]** för att välja bildfilen.

1. Dra och släpp bildfilen (JPEG eller PNG) eller klicka för att bläddra och markera bildfilen.

1. Klicka på **[!UICONTROL Generate]** för att starta den AI-baserade konverteringsprocessen.

   >[!NOTE]
   >
   >Genereringsprocessen kan ta upp till 5 minuter beroende på hur komplex och stor din bilddesign är. Var tålmodig medan AI analyserar och konverterar bilden.

1. När konverteringen är klar sparas innehållsmallen automatiskt som ett utkast. Du kan sedan granska och redigera den genererade HTML-mallen på Designer arbetsyta för e-post.

1. Den konverterade mallen öppnas i e-post-Designer med fullständiga redigeringsfunktioner. Nu kan du:

   * Redigera textinnehåll och tillämpa personalisering
   * Ändra bilder och lägga till länkar
   * Justera färger, teckensnitt och format
   * Lägga till, ta bort eller ordna om innehållskomponenter
   * Utnyttja alla e-post-Designer-funktioner på samma sätt som andra mallar

   ![](assets/email_designer_structure_components.png)

1. Gör nödvändiga justeringar för att förfina mallen och anpassa den efter varumärkesriktlinjerna.

1. När du är nöjd med mallen klickar du på **[!UICONTROL Save]** för att spara innehållsmallen.

1. Din mall är nu tillgänglig i biblioteket Innehållsmallar och kan användas när du skapar e-postmeddelanden under resor eller kampanjer. [Lär dig använda innehållsmallar](use-email-templates.md)

## Använd den konverterade mallen i e-postmeddelanden {#use-template}

När du har skapat och sparat din innehållsmall med Template Accelerator kan du använda den när du utformar e-postmeddelanden under resor eller kampanjer:

1. När du skapar ett e-postmeddelande i en resa eller kampanj öppnar du e-post-Designer från skärmen **[!UICONTROL Edit content]**.

1. Gå till fliken **[!UICONTROL Saved templates]** på Designer hemsida för e-post.

1. Välj mallacceleratorgenererad mall i listan.

1. Klicka på **[!UICONTROL Use this template]** om du vill använda den i ditt e-postmeddelande.

1. Fortsätt redigera och anpassa e-postinnehållet efter behov.

Läs mer om [att arbeta med e-postmallar](use-email-templates.md) och [skapa innehållsmallar](../content-management/content-templates.md).

## Bästa praxis {#best-practices}

Följ de här rekommendationerna för att få optimala resultat när du använder Template Accelerator:

**Innan du börjar**

* **Spara befintligt innehåll**: Om du konverterar en bild till HTML ersätts allt befintligt innehåll i e-postmeddelandet. Spara alltid ditt aktuella arbete innan du använder den här funktionen.
* **Planera ditt arbetsflöde**: Använd mallaccelerator i början av e-postprocessen eller kontrollera att du är redo att ersätta allt aktuellt innehåll.

**Bildförberedelse**

* **Upplösning**: Använd högupplösta bilder (minst 1 200 pixlar bred) för bättre textigenkänning och elementidentifiering
* **Klarhet**: Kontrollera att texten är tydligt läsbar och att visuella element är väldefinierade
* **Bredd**: Designa bilder med standardbredder för e-post (600-800px) så att de matchar vanliga krav för e-postklient
* **Filformat**: Använd JPEG- eller PNG-format - undvik komprimerade bilder eller bilder med låg kvalitet
* **Fullständig design**: Inkludera den fullständiga e-postdesignen i en enda bild, från sidhuvud till sidfot

**Designöverväganden**

* **Enkla layouter**: Enklare, välstrukturerade layouter konverteras exaktare än mycket komplexa designer
* **Standardelement**: Använd vanliga designmönster för e-post (sidhuvud, brödavsnitt, CTA:er, sidfot)
* **Textläsbarhet**: Kontrollera att texten och bakgrunden har tillräckligt hög kontrast
* **Webbsäkra teckensnitt**: Designer som använder vanliga webbsäkra teckensnitt har bättre återgivning
* **Undvik överlappande element**: Behåll designelement tydligt separerade för bättre strukturegenkänning

**Efter konvertering**

* **Granska utkastet**: När konverteringen är klar sparas mallen automatiskt som ett utkast. Granska den genererade HTML noggrant
* **Testa noggrant**: Testa e-postmeddelandet på olika e-postklienter och enheter
* **Förfina manuellt**: Gör ändringar efter behov med e-postprogrammets fullständiga redigeringsfunktioner i Designer
* **Varumärkesjustering**: Verifiera att färger, teckensnitt och format matchar varumärkesriktlinjerna
* **Personalization**: Lägg till dynamiska innehålls- och personaliseringstoken efter behov
* **Hjälpmedel**: Granska och förbättra tillgänglighetsfunktioner om det behövs

## Begränsningar och överväganden {#limitations}

Tänk på följande begränsningar när du använder Template Accelerator:

* **AI-tolkning**: AI genererar HTML baserat på den visuella tolkningen av din bild. Komplexa eller ovanliga designer kan kräva manuella justeringar efter konverteringen.

* **Textprecision**: Även om AI försöker identifiera och återge text korrekt måste du alltid verifiera textinnehållet och göra nödvändiga korrigeringar.

* **Dynamiskt innehåll**: Vid konverteringen skapas statisk HTML baserat på din bild. Ni måste lägga till personalisering, dynamiskt innehåll och spårning manuellt efter konverteringen.

* **Komplexa layouter**: Mycket komplexa designer med komplicerade lager, ovanliga former eller element som inte är standard kanske inte konverteras perfekt. Enklare design ger i allmänhet bättre resultat.

* **Bearbetningstid**: Konverteringsprocessen kan ta upp till 5 minuter beroende på bildens komplexitet och storlek. Mallen sparas automatiskt som ett utkast när konverteringen är klar.

* **Begränsad tillgänglighet**: Mallacceleratorn förbättras kontinuerligt som en begränsad tillgänglighetsfunktion. Funktionaliteten och exaktheten kan variera och din feedback förbättrar funktionen.

>[!NOTE]
>
>Template Accelerator är utformad för att ge en bra startpunkt för e-postgenerering. Den genererade HTML bör granskas och förfinas med e-post-Designer för att säkerställa att den uppfyller dina exakta krav.

## Vanliga frågor och svar {#faq}

+++Vad händer med mitt befintliga e-postinnehåll när jag använder Template Accelerator?

Allt befintligt innehåll i e-postmeddelandet tas bort och ersätts med den nya mallen när du överför en bild för konvertering. Spara viktigt innehåll innan du använder den här funktionen. Det är bäst att använda Template Accelerator i början av e-postprocessen.

+++

+++Vilka filformat stöds?

Template Accelerator stöder bildformaten JPEG (.jpg, .jpeg) och PNG (.png).

+++

+++Hur lång tid tar konverteringsprocessen?

Konverteringen kan ta upp till 5 minuter, beroende på hur komplex och stor bilddesignen är. När konverteringen är klar sparas filen automatiskt som ett utkast som du kan granska och redigera.

+++

+++Kan jag redigera den genererade mallen?

Ja! Den genererade HTML-mallen öppnas i e-post-Designer med fullständiga redigeringsfunktioner. Du kan ändra alla aspekter av mallen, inklusive text, bilder, format, layout och struktur.

+++

+++Vad händer om konverteringen inte matchar min design exakt?

AI gör sitt bästa för att tolka din design på ett korrekt sätt, men det kan behövas vissa manuella finjusteringar. Använd e-post-Designer för att justera eventuella element som behöver finjusteras.

+++

+++Kan jag använda den här funktionen för landningssidor eller andra innehållstyper?

Template Accelerator är för närvarande specifikt framtagen för e-postmallar. För andra innehållstyper använder du standardalternativen för design och import som finns i e-post-Designer.

+++

+++Behövs särskild behörighet för att använda den här funktionen?

Template Accelerator finns i Begränsad tillgänglighet. Du behöver begränsad tillgänglighetsåtkomst (kontakta din Adobe-representant för att få åtkomst) och Designer-standardbehörigheter för e-post för att använda den här funktionen.

+++

+++Kan jag återanvända konverterade mallar för flera kampanjer?

Ja! Mallar som skapas med mallacceleratorn sparas automatiskt i biblioteket Innehållsmallar. Ni kan komma åt och återanvända dem i alla e-postmeddelanden under era resor och kampanjer. [Läs mer](../content-management/content-templates.md)

+++

## Relaterade ämnen {#related-topics}

* [Kom igång med innehållsmallar](../content-management/content-templates.md)
* [Skapa innehållsmallar](../content-management/create-content-templates.md)
* [Använd e-postmallar](use-email-templates.md)
* [Kom igång med e-postdesign](get-started-email-design.md)
* [Importera e-postinnehåll](existing-content.md)
* [Designa innehåll från grunden](content-from-scratch.md)

