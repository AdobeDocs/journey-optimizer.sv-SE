---
solution: Journey Optimizer
product: journey optimizer
title: Lägg till anpassad CSS i e-postinnehållet
description: Lär dig hur du lägger till anpassad CSS i ditt e-postinnehåll direkt i e-post-Designer i Journey Optimizer
feature: Email Design
topic: Content Management
role: User
level: Intermediate
keywords: css, editor, summary, email
source-git-commit: feb3576c230f2fb28ab031f87cc5f99263329b57
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# Lägg till metadata i e-postinnehåll {#email-metadata}

>[!CONTEXTUALHELP]
>id="ac_edition_css"
>title="Lägg till anpassad CSS"
>abstract="xxx."

När du utformar dina e-postmeddelanden kan du lägga till din egen anpassade CSS direkt i [!DNL Journey Optimizer] [e-postmeddelandet för Designer](get-started-email-design.md).

Det som förväntas i textområdet Lägg till anpassad CSS är en giltig CSS-sträng.

![](assets/email-body-css.png)

Villkor för tillgänglighet

Funktionen Lägg till anpassad CSS är bara tillgänglig när det finns ett innehåll definierat i redigeraren. Användaren måste lägga till innehåll i redigeraren för att kunna se avsnittet Lägg till anpassad CSS. Om användaren tar bort allt innehåll försvinner avsnittet och de anpassade CSS:erna används inte. Om användaren lägger till innehåll igen är avsnittet tillgängligt och den anpassade CSS-koden används.

**Exempel på ogiltiga CSS-indata**

Ogiltig CSS kan inte sparas och om CSS är ogiltig visas en röd popup som anger att CSS inte kunde sparas.

`<style>` accepteras inte


```
<style type="text/css">
  .acr-Form {
    width: 100%;
    padding: 20px 100px;
    border-spacing: 0px 8px;
    box-sizing: border-box;
    margin: 0;
  }
</style>
```


den saknade klammerparentesen är ogiltig

```
body {
 background: red; 
```
