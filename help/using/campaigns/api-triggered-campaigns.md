---
solution: Journey Optimizer
product: journey optimizer
title: Utlösa kampanjer med API:er
description: Lär dig hur du aktiverar kampanjer med Journey Optimizer API:er
topic: Content Management
role: Developer, Admin
level: Intermediate, Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
exl-id: 0ef03d33-da11-43fa-8e10-8e4b80c90acb
source-git-commit: 11c1945f8e7f7ca74a2c9ca33ff85fea77bcf5db
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 0%

---

# Utlösa kampanjer med API:er {#trigger-campaigns}

## Om API-utlösta kampanjer {#about}

Med [!DNL Journey Optimizer]kan ni skapa kampanjer och sedan anropa dem från ett externt system baserat på användarens utlösare med [REST API för körning av interaktivt meddelande](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution). På så sätt kan ni täcka olika behov av marknadsföring och transaktionsmeddelanden, som lösenordsåterställningar, OTP-token, bland annat.

För att göra detta måste du först skapa en API-utlöst kampanj i Journey Optimizer och sedan starta körningen via ett API-anrop.

Tillgängliga kanaler för API-utlösta kampanjer är e-post-, SMS- och push-meddelanden.

## Skapa en API-utlöst kampanj {#create}

### Konfigurera och aktivera kampanjen {#create-activate}

Följ stegen nedan för att skapa en API-utlöst kampanj. Detaljerad information om hur du skapar en kampanj finns i [det här avsnittet](create-campaign.md).

1. Skapa en ny kampanj med **[!UICONTROL API-triggered]** typ.

1. Välj **[!UICONTROL Marketing]** eller **[!UICONTROL Transactional]** -kategorin beroende på vilken typ av kommunikation du vill skicka.

1. Välj en av kanalerna som stöds och den associerade kanalytan som ska användas för att skicka meddelandet, och klicka sedan på **[!UICONTROL Create]**.

   ![](assets/api-triggered-type.png)

   >[!NOTE]
   >
   >För närvarande stöds inte snabb leverans för kampanjer som triggas av API:t för push-meddelanden.

1. Ange en rubrik och en beskrivning för kampanjen och klicka sedan på **[!UICONTROL Edit content]** för att konfigurera meddelandet som ska skickas.

   >[!NOTE]
   >
   >Du kan skicka ytterligare data till API-nyttolasten som du kan använda för att anpassa meddelandet. [Läs mer](#contextual)
   >
   >Om du använder ett stort antal eller stora sammanhangsberoende data i ditt innehåll kan det påverka prestanda.

1. I **[!UICONTROL Audience]** anger du namnutrymmet som ska användas för att identifiera de enskilda personerna.

   * Om du skapar en **transaktionsbaserad**-typkampanj måste målprofilerna definieras i API-anropet. The **[!UICONTROL Create new profiles]** kan du automatiskt skapa profiler som inte finns i databasen. [Läs mer om att skapa profiler vid kampanjkörning](#profile-creation)

   * För **marknadsföring** liknande kampanjer, klicka på **[!UICONTROL Audience]** för att välja målgrupp.

1. Konfigurera kampanjens start- och slutdatum.

   Om du konfigurerar ett specifikt start- och/eller slutdatum för en kampanj körs det inte utanför dessa datum, och API-anrop misslyckas om kampanjen aktiveras av API:er.

1. Klicka **[!UICONTROL Review to activate]** för att kontrollera att kampanjen är korrekt konfigurerad aktiverar du den.

Nu kan du köra kampanjen från API:erna. [Läs mer](#execute)

### Kör kampanjen {#execute}

När kampanjen har aktiverats måste du hämta den genererade cURL-exempelbegäran och använda den i API:t för att skapa din nyttolast och utlösa kampanjen.

1. Öppna kampanjen och kopiera och klistra sedan in exempelbegäran från **[!UICONTROL cURL request]** -avsnitt.

   ![](assets/api-triggered-curl.png)

1. Använd denna cURL-begäran i API:erna för att bygga upp din nyttolast och utlösa kampanjen. Mer information finns i [API-dokumentation för interaktiv meddelandekörning](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution).

   Exempel på API-anrop finns också i [den här sidan](https://developer.adobe.com/journey-optimizer-apis/references/messaging-samples/).

   >[!NOTE]
   >
   >Om du har konfigurerat ett specifikt start- och/eller slutdatum när du skapar kampanjen kommer den inte att köras utanför dessa datum och API-anrop misslyckas.

## Använd kontextuella attribut i API-utlösta kampanjer {#contextual}

Med kampanjer som triggas av API kan ni skicka ytterligare data i API-nyttolasten och använda dem i kampanjen för att personalisera ert budskap.

Låt oss ta det här exemplet där kunderna vill återställa sitt lösenord och du vill skicka en URL för återställning av lösenord som genereras i ett verktyg från tredje part. Med API-utlösta kampanjer kan du skicka den här genererade URL:en till API-nyttolasten och sedan använda den i kampanjen för att lägga till den i meddelandet.

>[!NOTE]
>
>Till skillnad från profilaktiverade händelser används kontextdata som skickas i REST API för engångskommunikation och lagras inte mot profil. Profilen skapas med namnutrymmesinformationen om den saknas.

Om du vill använda dessa data i dina kampanjer måste du skicka dem till API-nyttolasten och lägga till dem i meddelandet med uttrycksredigeraren. Om du vill göra det använder du `{{context.<contextualAttribute>}}` syntax, där `<contextualAttribute>` ska matcha namnet på variabeln i API-nyttolasten som innehåller de data som du vill skicka.

The `{{context.<contextualAttribute>}}` syntaxen mappas endast till datatypen String.

![](assets/api-triggered-context.png)


>[!IMPORTANT]
>
>Kontextattributen som skickas till begäran får inte överstiga 50 kB och är alltid av typen sträng.
>
>The `context.system` syntaxen är begränsad till intern användning i Adobe och ska inte användas för att skicka kontextuella attribut.

Observera att det för närvarande inte finns något sammanhangsberoende attribut tillgängligt för användning på den vänstra menyn. Attribut måste anges direkt i ditt personaliseringsuttryck, utan att någon kontroll utförs av [!DNL Journey Optimizer].

## Skapa profiler vid kampanjkörning {#profile-creation}

I vissa fall kan du behöva skicka transaktionsmeddelanden till profiler som inte finns i systemet. Om en okänd användare till exempel försöker återställa lösenordet på webbplatsen.

När det inte finns någon profil i databasen kan du i Journey Optimizer automatiskt skapa den när kampanjen körs för att tillåta att meddelandet skickas till den här profilen.

>[!IMPORTANT]
>
>I händelse av transaktionsmeddelanden finns den här funktionen **mycket små volymprofiler** i en stor volym transaktionsbaserad sändningsanvändning, med en stor del av de profiler som redan finns på plattformen.

Om du vill aktivera skapande av profiler vid kampanjkörning växlar du **[!UICONTROL Create new profiles]** på i **[!UICONTROL Audience]** -avsnitt. Om det här alternativet är inaktiverat kommer okända profiler att avvisas för alla utskickningar och API-anropet kommer att misslyckas.

![](assets/api-triggered-create-profile.png)

>[!NOTE]
>
>Okända profiler skapas i **AJO Interactive Messaging Profile - datauppsättning** datauppsättningen, i tre standardnamnutrymmen (e-post, telefon och ECID) för varje utgående kanal (e-post, SMS och push).
