---
solution: Journey Optimizer
product: journey optimizer
title: Utlösa kampanjer med API:er
description: Lär dig hur du aktiverar kampanjer med Journey Optimizer API:er
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
exl-id: 0ef03d33-da11-43fa-8e10-8e4b80c90acb
source-git-commit: 47185cdcfb243d7cb3becd861fec87abcef1f929
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 0%

---

# Utlösa kampanjer med API:er {#trigger-campaigns}

## Om API-utlösta kampanjer {#about}

Med [!DNL Journey Optimizer] kan du skapa kampanjer och sedan köra dem från ett externt system baserat på användarutlösare med hjälp av [Interactive Message Execution REST API](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution). På så sätt kan ni täcka olika behov av marknadsföring och transaktionsmeddelanden, som lösenordsåterställningar, OTP-token, bland annat.

För att göra detta måste du först skapa en API-utlöst kampanj i Journey Optimizer och sedan starta körningen via ett API-anrop.

![](../rn/assets/do-not-localize/api-triggered.gif)

Tillgängliga kanaler för API-utlösta kampanjer är e-post-, SMS- och push-meddelanden.

>[!NOTE]
>
>Från och med nu stöds inte läget för snabb leverans för kampanjer som triggas av API:t för push-meddelanden.

➡️ [Upptäck den här funktionen i videon](#video)

## Skapa en API-utlöst kampanj {#create}

### Konfigurera och aktivera kampanjen {#create-activate}

Följ stegen nedan för att skapa en API-utlöst kampanj. Detaljerad information om hur du skapar en kampanj finns i [det här avsnittet](create-campaign.md).

1. Skapa en ny kampanj med typen **[!UICONTROL API-triggered]**.

1. Välj kategorin **[!UICONTROL Marketing]** eller **[!UICONTROL Transactional]** beroende på vilken typ av kommunikation du vill skicka.

1. Välj en av kanalerna som stöds och den associerade kanalkonfigurationen som ska användas för att skicka meddelandet och klicka sedan på **[!UICONTROL Create]**.

   ![](assets/api-triggered-type.png)

1. Ange en titel och en beskrivning för kampanjen och klicka sedan på **[!UICONTROL Edit content]** för att konfigurera meddelandet som ska skickas.

   >[!NOTE]
   >
   >Du kan skicka ytterligare data till API-nyttolasten som du kan använda för att anpassa meddelandet. [Läs mer](#contextual)
   >
   >Om du använder ett stort antal eller stora sammanhangsberoende data i ditt innehåll kan det påverka prestanda.

1. I avsnittet **[!UICONTROL Audience]** anger du det namnutrymme som ska användas för att identifiera de enskilda personerna.

   * Om du skapar en kampanj av typen **transactional** måste målprofilerna definieras i API-anropet. Med alternativet **[!UICONTROL Create new profiles]** kan du automatiskt skapa profiler som inte finns i databasen. [Läs mer om att skapa profiler vid kampanjkörning](#profile-creation)

     >[!NOTE]
     >
     >Ett enda API-anrop stöder upp till 20 unika mottagare. Varje mottagare måste ha ett unikt användar-ID. Dubblerade användar-ID tillåts inte. Läs mer i [API-dokumentationen för interaktiv meddelandekörning](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution/operation/postIMUnitaryMessageExecution){target="_blank"}

   * Klicka på knappen **[!UICONTROL Audience]** för att välja målgrupp för kampanjer av typen **marketing**.

1. Konfigurera kampanjens start- och slutdatum.

   Om du konfigurerar ett specifikt start- och/eller slutdatum för en kampanj körs det inte utanför dessa datum, och API-anrop misslyckas om kampanjen aktiveras av API:er.

1. Klicka på **[!UICONTROL Review to activate]** för att kontrollera att kampanjen är korrekt konfigurerad och aktivera den sedan.

Du är nu redo att köra kampanjen från API:erna. [Läs mer](#execute)

### Kör kampanjen {#execute}

När kampanjen har aktiverats måste du hämta den genererade cURL-exempelbegäran och använda den i API:t för att skapa din nyttolast och utlösa kampanjen.

1. Öppna kampanjen och kopiera och klistra sedan in nyttolastbegäran från avsnittet **[!UICONTROL cURL request]**. Den här nyttolasten innehåller alla personaliseringsvariabler (profil och kontext) som används i meddelandet. Den blir tillgänglig när kampanjen är live.

   ![](assets/api-triggered-curl.png)

1. Använd denna cURL-begäran i API:erna för att bygga upp din nyttolast och utlösa kampanjen. Mer information finns i [API-dokumentationen för interaktiv meddelandekörning](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution).


   Exempel på API-anrop finns också på [den här sidan](https://developer.adobe.com/journey-optimizer-apis/references/messaging-samples/).

   >[!NOTE]
   >
   >Om du har konfigurerat ett specifikt start- och/eller slutdatum när du skapar kampanjen kommer den inte att köras utanför dessa datum och API-anrop misslyckas.

## Använd kontextuella attribut i API-utlösta kampanjer {#contextual}

Med kampanjer som triggas av API kan ni skicka ytterligare data i API-nyttolasten och använda dem i kampanjen för att personalisera ert budskap.

Låt oss ta det här exemplet där kunderna vill återställa sitt lösenord och du vill skicka en URL för återställning av lösenord som genereras i ett verktyg från tredje part. Med API-utlösta kampanjer kan du skicka den här genererade URL:en till API-nyttolasten och sedan använda den i kampanjen för att lägga till den i meddelandet.

>[!NOTE]
>
>Till skillnad från profilaktiverade händelser används kontextdata som skickas i REST API för engångskommunikation och lagras inte mot profil. Profilen skapas med namnutrymmesinformationen om den saknas.

För att kunna använda dessa data i era kampanjer måste ni skicka dem till API-nyttolasten och lägga till dem i meddelandet med personaliseringsredigeraren. Använd syntaxen `{{context.<contextualAttribute>}}` där `<contextualAttribute>` ska matcha namnet på variabeln i API-nyttolasten som innehåller de data som du vill skicka.

Syntaxen `{{context.<contextualAttribute>}}` är endast mappad till datatypen String.

![](assets/api-triggered-context.png)


>[!IMPORTANT]
>
>Kontextattributen som skickas till begäran får inte överstiga 200 kB och är alltid av typen sträng.
>
>Syntaxen `context.system` är begränsad till Adobe enbart för intern användning och ska inte användas för att skicka kontextuella attribut.

Observera att det för närvarande inte finns något sammanhangsberoende attribut tillgängligt för användning på den vänstra menyn. Attribut måste anges direkt i ditt personaliseringsuttryck utan att någon kontroll utförs av [!DNL Journey Optimizer].

## Skapa profiler vid kampanjkörning {#profile-creation}

I vissa fall kan du behöva skicka transaktionsmeddelanden till profiler som inte finns i systemet. Om en okänd användare till exempel försöker återställa lösenordet på webbplatsen.

När det inte finns någon profil i databasen kan du i Journey Optimizer automatiskt skapa den när kampanjen körs för att tillåta att meddelandet skickas till den här profilen.

>[!IMPORTANT]
>
>I händelse av transaktionsmeddelanden tillhandahålls den här funktionen för att skapa **mycket små volymprofiler** i ett stort transaktionssändningsfall, med en stor del av de profiler som redan finns på plattformen.

Aktivera alternativet **[!UICONTROL Create new profiles]** i avsnittet **[!UICONTROL Audience]** om du vill aktivera skapande av profiler vid kampanjkörning. Om det här alternativet är inaktiverat kommer okända profiler att avvisas för alla utskickningar och API-anropet kommer att misslyckas.

![](assets/api-triggered-create-profile.png)

>[!NOTE]
>
>Okända profiler skapas i datauppsättningen **AJO Interactive Messaging Profile** i tre standardnamnutrymmen (e-post, telefon och ECID) för varje utgående kanal (e-post, SMS och push). Om du använder ett anpassat namnutrymme skapas emellertid identiteten med samma anpassade namnutrymme.

## Instruktionsvideo {#video}

Lär dig hur du skapar en kampanj och utlöser den från ett externt system baserat på användarinteraktioner med hjälp av REST-API:t för interaktiv meddelandekörning.

>[!VIDEO](https://video.tv.adobe.com/v/3425358?quality=12)
