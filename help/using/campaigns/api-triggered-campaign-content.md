---
solution: Journey Optimizer
product: journey optimizer
title: Redigera API-utlöst kampanjinnehåll
description: Lär dig hur du redigerar det API-utlösta kampanjinnehållet.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
exl-id: b7f12c65-c1af-4c49-b126-c13a51940a43
source-git-commit: d93b7ce225294257f49caee6ac08cfb575611a93
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Redigera API-utlöst kampanjinnehåll {#api-content}

Om du vill konfigurera meddelandeinnehållet går du till fliken **[!UICONTROL Content]** eller klickar på knappen **[!UICONTROL Edit content]**.

![](assets/campaign-content.png)

## Utforma innehållet {#design}

Hur du skapar innehåll beror på vilken kanal du har valt. Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sidor:

<table style="table-layout:fixed"><tr style="border: 0;">
<td><a href="../email/create-email.md"><img alt="e-post" src="../channels/assets/do-not-localize/email.png"></a>
<div align="center"><a href="../email/create-email.md"><strong>E-post</strong></a></div></td>
<td><a href="../sms/create-sms.md"><img alt="sms" src="../channels/assets/do-not-localize/sms.png"></a>
<div align="center"><a href="../sms/create-sms.md"><strong>SMS</strong></a></div></td>
<td><a href="../push/create-push.md"><img alt="push" src="../channels/assets/do-not-localize/push.png"></a>
<div align="center"><a href="../push/create-push.md"><strong>Push-meddelande</strong></a></div></td>
</tr></table>

>[!IMPORTANT]
>
>[Högeffektiva genomströmningskampanjer](../campaigns/api-triggered-high-throughput.md) är inte beroende av Adobe-profiler. All personalisering måste inkluderas i API-nyttolasten som kontextdata, vilket beskrivs nedan. Det här läget är endast tillgängligt för e-postkanalen och i USA-regionen.

## Anpassa innehåll med kontextuella data {#contextual}

Du kan skicka ytterligare data till API-nyttolasten som du kan använda för att anpassa meddelandet.

Låt oss ta det här exemplet där kunderna vill återställa sitt lösenord och du vill skicka en URL för återställning av lösenord som genereras i ett verktyg från tredje part. Med API-utlösta kampanjer kan du skicka den här genererade URL:en till API-nyttolasten och använda den i kampanjen för att lägga till den i meddelandet.

För att göra detta måste du skicka dem till API-nyttolasten och lägga till dem i meddelandet med personaliseringsredigeraren. Använd syntaxen `{{context.<contextualAttribute>}}`, där `<contextualAttribute>` ska matcha namnet på variabeln i API-nyttolasten som innehåller de data som du vill skicka.

Observera att det för närvarande inte finns något sammanhangsberoende attribut tillgängligt för användning på den vänstra menyn. Attribut måste anges direkt i ditt personaliseringsuttryck utan att någon kontroll utförs av [!DNL Journey Optimizer].

![](assets/api-triggered-context.png)

**Måste läsa**

* Kontextattributen som skickas till begäran får inte överstiga 200 kB och betraktas alltid som en typ av sträng.
* Syntaxen `context.system` är begränsad till Adobe enbart för intern användning och ska inte användas för att skicka kontextuella attribut.
* Till skillnad från profilaktiverade händelser används kontextdata som skickas i REST API för engångskommunikation och lagras inte mot profil. Profilen skapas med namnutrymmesinformationen om den saknas.
* Om du använder ett stort antal eller stora sammanhangsberoende data i ditt innehåll kan det påverka prestanda.

## Testa och kontrollera innehållet

När innehållet har definierats kan du använda knappen **[!UICONTROL Simulate content]** för att förhandsgranska och testa innehållet med testprofiler eller exempelindata som har överförts från en CSV-/JSON-fil, eller lägga till manuellt. [Lär dig hur du förhandsgranskar och testar innehåll](../content-management/preview-test.md). Klicka på vänsterpilen om du vill gå tillbaka till skärmen där kampanjen skapades.

![](assets/create-campaign-design.png)

## Nästa steg {#next}

När kampanjens konfiguration och innehåll är klart kan ni definiera kampanjens målgrupp. [Läs mer](api-triggered-campaign-audience.md)
