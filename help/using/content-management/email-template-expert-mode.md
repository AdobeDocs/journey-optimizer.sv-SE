---
solution: Journey Optimizer
product: journey optimizer
title: Redigera e-postmallar med den avancerade HTML-redigeraren
description: Använd expertläget för att visa och redigera HTML-källan för e-postinnehåll i WYSIWYG-redigeraren, med funktionsflaggskontroll, skyddsritningar och sparad validering.
feature: Templates
topic: Content Management
role: User
hidefromtoc: true
hide: true
level: Experienced
exl-id: 0c586565-0c65-435f-986d-cd08b59de159
source-git-commit: 76bb202375cdfe1c8abacc1670ba6e794175215d
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# Redigera e-postmallar med den avancerade HTML-redigeraren {#email-template-expert-mode}

>[!AVAILABILITY]
>
>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

Den **avancerade HTML-redigeraren** är ett expertläge där du kan visa och redigera råkällkoden för e-postinnehållsmallar direkt från Designer-gränssnittet för e-post i [!DNL Journey Optimizer] .

Med den här funktionen kan du infoga avancerade uttryck - till exempel villkor - direkt i källan. När du växlar tillbaka till den visuella vyn (Skrivbord) återges innehållet på nytt så att du kan kontrollera hur det ser ut och fortsätta redigera i båda vyerna.

>[!NOTE]
>
>Den här funktionen är bara tillgänglig i innehållsmallar och för e-postkanalen.

## Skyddsräcken {#guardrails}

När du använder den avancerade HTML-redigeraren finns det följande skyddsmekanismer för att skydda innehållets kompatibilitet och ställa in förväntningar.

* Det finns för närvarande **ingen valideringsprocess** i den avancerade HTML-redigeraren. Syntaxfel och trasiga layouter kontrolleras inte. Granska innehållet noggrant innan du sparar.

* Framtida systemuppdateringar kan återställa ändringar som gjorts i standardkoden. Observera att **dina ändringar kan skrivas över**.

* Problem som orsakas av anpassad kod och manuella ändringar **kan inte felsökas** eller lösas av [!DNL Adobe]-supportteamet. Se till att du har en säkerhetskopia av ditt innehåll om du skulle behöva gå tillbaka till en tidigare version.

* **Spara är inte tillgängligt** i den avancerade HTML-vyn för att säkerställa innehållskompatibiliteten. När du är redo att spara ändringarna måste du växla tillbaka till skrivbordsvyn.

>[!WARNING]
>
>Den avancerade HTML-redigeraren i innehållsmallen är inte samma läge som **[!UICONTROL Code your own]** i Designer för e-post. I [!UICONTROL Code your own]-läget kan du inte växla tillbaka till den visuella redigeraren. När du väl har valt den sökvägen förblir du i redigering med endast kod. Med den avancerade HTML-redigeraren kan du växla mellan HTML-vyn och skrivbordsvyn när du vill. [Läs mer om kodredigeraren](../email/code-content.md)

## Växla till avancerad HTML-vy {#switch-to-desktop-view}

1. Öppna eller skapa en [e-postmall](../content-management/create-content-templates.md) och öppna [Skicka e-post till Designer](../email/get-started-email-design.md) för att redigera innehållet.

1. Klicka på knappen **[!UICONTROL HTML]** i skärmens övre högra hörn.

   ![](assets/email-template-expert-mode-button.png)

1. Första gången du öppnar den avancerade HTML-redigeraren visas ett varningsmeddelande. Granska det noggrant och klicka på **[!UICONTROL OK]** för att fortsätta. [Läs mer](#guardrails)

   >[!NOTE]
   >
   >Den här varningen visas endast första gången du öppnar den avancerade HTML-redigeraren och återställer den varje månad.

   ![](assets/email-template-expert-mode-warning.png){zoomable="yes"}

1. Den avancerade HTML-redigeraren visas.

   ![](assets/email-template-expert-mode.png)

1. Lägg till önskade ändringar i e-postinnehållet.

   >[!WARNING]
   >
   >Ange korrekt HTML- och CSS-kod eftersom det inte finns någon syntaxverifieringsprocess och [!DNL Adobe] saknar stöd. [Läs mer](#guardrails)

1. Det går inte att spara i den avancerade vyn i HTML. Växla tillbaka till skrivbordsvyn för att spara ändringarna.

   ![](assets/email-template-expert-mode-save.png){zoomable="yes"}

   >[!NOTE]
   >
   >Innehåll kan bara sparas i skrivbordsvyn av kompatibilitetsskäl. Dina redigeringar bevaras när du byter vy.

1. Simulering av innehåll är inte tillgängligt i den avancerade vyn i HTML. Om du vill simulera ditt innehåll växlar du till skrivbordsvyn.

   ![](assets/email-template-expert-mode-simulate.png){zoomable="yes"}

