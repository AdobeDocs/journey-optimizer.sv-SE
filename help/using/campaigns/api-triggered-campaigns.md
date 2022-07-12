---
title: Utlösa kampanjer med API:er
description: Lär dig hur du aktiverar kampanjer med [!DNL Journey Optimizer] API:er
hide: true
hidefromtoc: true
source-git-commit: 6177a33edeb3b8381c3eb5609762b4d974dc93e3
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 1%

---


# Utlösa kampanjer med API:er {#trigger-campaigns}

## Om API-utlösta kampanjer {#about}

Med [!DNL Journey Optimizer]kan ni skapa kampanjer och sedan anropa dem från ett externt system baserat på användarens utlösare med [REST API för körning av interaktivt meddelande](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution). På så sätt kan du täcka olika behov av användnings- och transaktionsmeddelanden, som lösenordsåterställningar och OTP-token.

För att göra detta måste du först skapa en API-utlöst kampanj i Journey Optimizer och sedan starta körningen via ett API-anrop.

Tillgängliga kanaler för API-utlösta kampanjer är e-post-, SMS- och push-meddelanden.

>[!NOTE]
>
>API:t för interaktiv meddelandekörning finns för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande.

## Skapa en API-utlöst kampanj {#create}

Processen att skapa API-utlösta kampanjer är fortfarande densamma som schemalagda kampanjer, med undantag för valet av målgrupp som görs i API-nyttolasten. Detaljerad information om hur du skapar en kampanj finns i [det här avsnittet](create-campaign.md).

Så här skapar du en API-utlöst kampanj:

1. Skapa en ny kampanj med **[!UICONTROL API-triggered]** typ.

1. Välj kanal och meddelandeyta som ska användas för att skicka meddelandet och klicka sedan på **[!UICONTROL Create]**.

   ![](assets/api-triggered-type.png)

1. Ange en titel och en beskrivning för kampanjen och konfigurera sedan meddelandet som ska skickas.

   ![](assets/api-triggered-properties.png)

   >[!NOTE]
   >
   >Du kan skicka ytterligare data till API-nyttolasten som du kan använda för att anpassa meddelandet. [Läs mer](#contextual)

1. Ange det namnutrymme som ska användas för att identifiera individerna från segmentet.

1. Konfigurera kampanjens start- och slutdatum.

   Om du konfigurerar ett specifikt start- och/eller slutdatum för en kampanj körs det inte utanför dessa datum, och API-anrop misslyckas om kampanjen aktiveras av API:er.

1. I **[!UICONTROL cURL request]** -sektion, hämta **[!UICONTROL Campaign ID]** som ska användas i API-nyttolasten.

   ![](assets/api-triggered-curl.png)

1. Klicka **[!UICONTROL Review to activate]** för att kontrollera att kampanjen är korrekt konfigurerad aktiverar du den.

## Använd kontextuella attribut i API-utlösta kampanjer {#contextual}

Med kampanjer som triggas av API kan ni skicka ytterligare data i API-nyttolasten och använda dem i kampanjen för att personalisera ert budskap.

Låt oss ta det här exemplet där kunderna vill återställa sitt lösenord och du vill skicka en URL för återställning av lösenord som genereras i ett verktyg från tredje part. Med API-utlösta kampanjer kan du skicka den här genererade URL:en till API-nyttolasten och sedan använda den i kampanjen för att lägga till den i meddelandet.

>[!NOTE]
>
>Till skillnad från profilaktiverade händelser används kontextdata som skickas i REST API för engångskommunikation och lagras inte mot profil. Profilen skapas med namnutrymmesinformationen om den saknas.

Om du vill använda dessa data i dina kampanjer måste du skicka dem till API-nyttolasten och lägga till dem i meddelandet med Expression Editor. Om du vill göra det använder du `{{context.<contextualAttribute>}}` syntax, där `<contextualAttribute>` ska matcha namnet på variabeln i API-nyttolasten som innehåller de data som du vill skicka.

The `{{context.<contextualAttribute>}}` syntaxen mappas endast till datatypen String.

![](assets/api-triggered-context.png)

>[!IMPORTANT]
>
>The `context.system` syntaxen är begränsad till intern användning i Adobe och ska inte användas för att skicka kontextuella attribut.
Observera att det för närvarande inte finns något sammanhangsberoende attribut tillgängligt för användning på den vänstra menyn. Attribut måste anges direkt i ditt personaliseringsuttryck, utan att någon kontroll utförs av [!DNL Journey Optimizer].

## Kör kampanjen {#execute}

Om du vill köra en API-utlöst kampanj måste du först hämta dess ID och skicka det till API-nyttolasten. Det gör du genom att öppna kampanjen och sedan kopiera och klistra in ID:t från **[!UICONTROL cURL request]** -avsnitt.

![](assets/api-triggered-id.png)

Du kan sedan använda detta ID i API-nyttolasten för att utlösa kampanjen. Se [API-dokumentation för interaktiv meddelandekörning](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution) för mer information.

>[!NOTE]
>
>Om du har konfigurerat ett specifikt start- och/eller slutdatum när du skapar kampanjen kommer den inte att köras utanför dessa datum och API-anrop misslyckas.

## Ytterligare resurser

* [Kom igång med kampanjer](get-started-with-campaigns.md)
* [Skapa en kampanj](create-campaign.md)
* [Ändra eller stoppa en kampanj](modify-stop-campaign.md)
* [Kampanjrapport](campaign-live-report.md)
* [Global kampanjrapport](campaign-global-report.md)
