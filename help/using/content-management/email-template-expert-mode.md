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
source-git-commit: 2240a4bf85d3f5f41a12d128afdc15431dbab75b
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 2%

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

När du använder den avancerade HTML-redigeraren skyddar följande skyddsutkast innehållets kompatibilitet och ställer in förväntningar.

* Den avancerade HTML-redigeraren **validerar inte** din kod. Syntaxfel och trasiga layouter kontrolleras inte. Granska innehållet noggrant innan du sparar.

* Framtida systemuppdateringar kan skriva över ändringar som du gör i standardkoden. **Ändringarna kanske inte kvarstår**.

* [!DNL Adobe]-supportteamet **kan inte felsöka eller lösa**-problem som orsakas av anpassad kod och manuella ändringar. Spara en säkerhetskopia av innehållet ifall du skulle behöva återställa det.

* Du kan inte simulera innehåll i avancerad HTML-vy. Växla till skrivbordsvyn om du vill förhandsgranska innehållet.

* **Du kan inte spara** i den avancerade HTML-vyn för att säkerställa innehållskompatibiliteten. Växla tillbaka till skrivbordsvyn när du är redo att spara ändringarna.

>[!WARNING]
>
>Den avancerade HTML-redigeraren i innehållsmallen är inte samma läge som **[!UICONTROL Code your own]** i Designer för e-post. I [!UICONTROL Code your own]-läget kan du inte växla tillbaka till den visuella redigeraren. När du väl har valt den sökvägen förblir du i redigering med endast kod. Med den avancerade HTML-redigeraren kan du växla mellan HTML-vyn och skrivbordsvyn när du vill. [Läs mer om kodredigeraren](../email/code-content.md)

## Växla till avancerad HTML-vy {#switch-to-html-view}

Följ de här stegen för att öppna den avancerade HTML-redigeraren och redigera mallkällan.

1. Öppna eller skapa en [e-postmall](../content-management/create-content-templates.md) och öppna [Skicka e-post till Designer](../email/get-started-email-design.md) för att redigera innehållet.

1. Klicka på knappen **[!UICONTROL HTML]** i skärmens övre högra hörn.

   ![Plats för HTML-knappen i e-postverktygsfältet i Designer](assets/email-template-expert-mode-button.png)

1. Första gången du öppnar den avancerade HTML-redigeraren visas ett varningsmeddelande. Granska det noggrant och klicka på **[!UICONTROL OK]** för att fortsätta. [Läs mer](#guardrails)

   ![Varningsdialogruta när den avancerade HTML-redigeraren öppnas för första gången](assets/email-template-expert-mode-warning.png){zoomable="yes"}

   >[!NOTE]
   >
   >Den här varningen visas endast första gången du öppnar den avancerade HTML-redigeraren och återställer den varje månad.

1. Den avancerade HTML-redigeraren visas.

   ![Avancerat HTML-redigeringsgränssnitt som visar källkod för e-postmallar](assets/email-template-expert-mode.png)

1. Lägg till önskade ändringar i e-postinnehållet.

   >[!WARNING]
   >
   >Ange korrekt HTML- och CSS-kod eftersom det inte finns någon syntaxverifieringsprocess och [!DNL Adobe] saknar stöd. [Läs mer](#guardrails)

1. Simulering och sparande av innehåll är inte tillgängligt i avancerad HTML-vy av kompatibilitetsskäl. Växla tillbaka till skrivbordsvyn för att förhandsgranska innehållet och spara ändringarna.

   ![Växla tillbaka till skrivbordsvyn för att spara ändringarna](assets/email-template-expert-mode-save.png){zoomable="yes"}

   >[!NOTE]
   >
   >Dina redigeringar bevaras när du byter vy.

<!--
    ![](assets/email-template-expert-mode-simulate.png){zoomable="yes"}-->

## Relaterade ämnen

* [Koda eget e-postinnehåll](../email/code-content.md)
* [Skapa innehållsmallar](create-content-templates.md)
* [Komma igång med e-postdesignern](../email/get-started-email-design.md)

