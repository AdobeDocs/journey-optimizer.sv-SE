---
solution: Journey Optimizer
product: journey optimizer
title: Anpassa innehåll med data från en extern slutpunkt
description: Lär dig hur du hämtar data dynamiskt från en extern slutpunkt för att personalisera inkommande innehåll.
badge: label="Begränsad tillgänglighet" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare
source-git-commit: f5d1bc27afadbf875fe4dd3149ce090a8773e0f9
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 0%

---


# Anpassa innehåll med data från en extern slutpunkt {#data-endpoint}

>[!AVAILABILITY]
>
>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet).

Med Journey Optimizer kan ni utnyttja data från en extern slutpunkt för att personalisera ert innehåll i inkommande kanaler som t.ex. kodbaserade upplevelser, webbkanaler och meddelandekanaler i appen.

En dedikerad hjälpfunktion, `externalDataLookup`, är tillgänglig i personaliseringsredigeraren. Om du vill använda hjälpen måste du först definiera en [!DNL Journey Optimizer] **åtgärd** där du konfigurerar information om den externa slutpunkten.

## Måste läsas

### Körning vid körning

När en inkommande åtgärd innehåller en hjälp för externalDataLookup anropas slutpunkten dynamiskt när personaliseringsbegäran tas emot och bearbetas av Edge Network [!DNL Adobe Experience Platform]. Det innebär att den externa slutpunkten måste kunna hantera minst lika mycket samtidig belastning och genomströmning som klienten skickar för den angivna ytan till AEP Edge Network.

### Autentisering

Autentiseringsalternativen i åtgärdskonfigurationen stöds för närvarande inte av hjälpen externalDataLookup.
Under tiden kan du ange dem som rubrikfält i åtgärdskonfigurationen för API-nyckelbaserad autentisering eller andra klartextautentiseringsnycklar.
Endast för Adobe-interna slutpunkter: kontakta AJO Engineering för att aktivera tjänsttokenbaserad autentisering för en slutpunkt.

### Gardrutor och begränsningar

Se även Custom Actions in AJO Inbound Channels Campaigns and Journeys#GuardrailandGuidelines.

Som standard använder AJO en timeout på 300 ms när en extern slutpunkt anropas. Kontakta AJO Engineering för att öka tidsgränsen för en slutpunkt.
I Personalization Editor kan du inte bläddra i schemat för slutpunktssvaret när du infogar uttryck och validerar inte referenser till JSON-attribut från svaret som används i uttryck.
De datatyper som stöds för variabelparametrar för nyttolast som ska ersättas via externalDataLookup-hjälpen är String, Integer, Decimal, Boolean, listString, listInt, listInteger, listDecimal
Ändringar i en åtgärdskonfiguration återspeglas inte i motsvarande externalDataLookup-anrop i livekampanjer och resor. För att en ändring ska återspeglas måste du kopiera eller ändra alla live-kampanjer eller resor som använder åtgärden i en externalDataLookup-hjälpreda.
Variabler stöds ännu inte i externa hjälpparametrar för datasökning.
Dynamisk URL-sökväg stöds för närvarande inte.  - Förbättringar av inkommande anpassade åtgärder#DynamicPathSegments

## Skapa en åtgärd

Skapa en åtgärd för att konfigurera slutpunkten för sökningen. Detta behöver bara göras en gång för varje slutpunkt och bör göras av en teknisk användare. Se den här sidan.

Samma åtgärd kan användas både i en **[!UICONTROL Custom Action]**-aktivitet för att hämta innehåll i en resa och i en `externalDataLookup`-hjälpfunktion för att hämta data i en inkommande åtgärd i en resa eller kampanj.

Bläddra till menyn **[!UICONTROL Administration]** / **[!UICONTROL Configurations]**.

Observera åtgärds-ID:t och kopiera det för användning i steg 6.


## Anpassa innehållet med hjälp av hämtade data

### Lägg till hjälpfunktionen i ditt innehåll

1. Skapa en inkommande kampanj eller en reseåtgärd och redigera innehållet.

1. Leta upp innehållet där du vill använda data som hämtats från den externa slutpunkten och öppna personaliseringsredigeraren.

1. Välj menyn Hjälpfunktioner och leta upp hjälpfunktionen `externalDataLookup`.

1. Välj att infoga den associerade syntaxen i koden och ersätta parametervärdena `actionId` och `result` enligt följande:

   * `actionId` : Klistra in åtgärds-ID:t som kopierades när åtgärden skapades.
   * `result`: Ange den här parametern till valfritt namn. Du kommer att använda den här resultatvariabeln för att komma åt det hämtade innehållet.

1. Lägg till variabelparametervärden som ska skickas som en del av slutpunktsanropet. Här kan du till exempel skicka en språkparameter och en max items-parameter.

### Anpassa med hämtade data

Om du vill få åtkomst till data som hämtats från ett externt sökanrop för slutpunkter, kan du referera till fält som definierats i svarsnyttolasten i åtgärdsdefinitionen med hjälp av personaliseringsuttryck och hjälpfunktioner.

Använd variabeln `result` för att få åtkomst till hämtade data och infoga dem i innehållet för den inkommande åtgärden. Här kan du till exempel returnera en JSON-array med objekt som hämtats från slutpunkten.

Låt oss ta exemplet nedan, där svarsnyttolasten i åtgärden har konfigurerats enligt följande:

```
{
    "videos": [
        {
            "id": "integer",
            "title": "string",
            "description": "string",
            "thumbnail_url": "string",
            "video_page_url": "string",
            "url": "string",
            "video_type": "string",
            "start_timestamp": "dateOnly",
            "created_on": "dateOnly",
            ...
        }
    ]
}
```

Personalization-exempel 1 - Visa beskrivningen av den första videon i en Code-based Experience HTML-åtgärd:

```
{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result"}}
 
First video description: <b>result.videos[0].description</b>
```

Personalization-exempel 2 - Returnera en objektarray i en kodbaserad Experience JSON-åtgärd:

```
{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result"}}
 
[
{{#each result.videos as |item|}}
    {                                                  
        "title": "{{item.title}}",
        "url": "{{item.video_page_url}}",
        "thumbnail_url": "{{item.thumbnail_url}}",
        "start_timestamp": "{{item.start_timestamp}}"
    },
{{/each}}
]
```

## Timeout och felhantering

AJO använder en strikt tidsgräns när den externa slutpunkten anropas för att behålla prestandaegenskaper med låg fördröjning och hög genomströmning för AEP Edge Network.

Om slutpunkten timeout eller om det finns något annat slags fel som når slutpunkten, kommer variabeln result att vara tom. Alla referenser till attribut i resultatvariabeln i det här fallet kommer också att vara tomma. Om du bara visar attributet i innehållet visas det som tomt. Om du försöker göra en slinga genom ett arrayattribut i resultatet returneras inga objekt.

Om du vill hantera timeout eller fel bättre genom att visa reservinnehåll kan du kontrollera om resultatet av sökningen är tomt och visa reservinnehåll i så fall.

Du kan till exempel visa ett reservvärde för ett enda attribut som detta:

Första videobeskrivningen: {%=result.videos[0].description ?: &quot;none found&quot; %}


eller så kan du villkorligt återge ett helt innehållsblock på följande sätt:

{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result"}}

{%#if result%}
... gör något med resultat ...
{%else%}
... returnera reservinnehåll ...
{%/if%}
Felsökning
I Edge Delivery-vyn i AEP Assurance finns information om timeout och fel för externa datasökning som kan vara till hjälp vid felsökning. Om du inte ser förväntade resultat för en extern DataLookup-hjälp i en inkommande åtgärd kan du starta en Assurance-session, initiera ett AJO-anrop från en webb- eller mobilimplementering och använda Edge Delivery-vyn för att kontrollera timeout- eller felinformation.

Exempel:

Under Edge Delivery-avsnittet av säkringsspårning som en del av körningsinformationen har ett nytt customActions-block lagts till med

förfrågnings- och svarsinformation som liknar den nedan. Felavsnittet bör vara till hjälp vid felsökning om det uppstod några problem när en anpassad åtgärd utfördes

## Vanliga frågor

+++Hur skickar jag ett sammanhangsberoende attribut från begäran som parameter till en extern datasökning?

Använd Kontextuella attribut > Datastream > Event-menyn för att bläddra i det Experience Event-schema som du använder och infoga det relevanta attributet som ett parametervärde enligt följande:

`{{externalDataLookup actionId="..." result="result" query.myQueryParameter=context.datastream.event.<schemaId>.my.xdm.attribute}}`

+++

+++Gör AJO någon cachelagring av externa slutpunktssvar?

Inte just nu. Den här funktionen kommer att stödjas i framtiden.

+++









Syntax
{{externalDataLookup actionId="d130c8e2-9a2d-45d5-bcb6-bc39865b4a56" result="result" optional-parameters...}}



Parametrar skickas
När den externa slutpunkten anropas skickas alla konstanta huvudvärden, frågeparametrar och det nyttolastvärde som definierats i åtgärden med de värden som anges i åtgärdskonfigurationen.

För variabelrubrikvärden, fråge-/sökvägsparametrar eller begär nyttolastvärden kan du skicka värden dynamiskt med parametrar till hjälp för externalDataLookup.

Parameternamn:

Huvudparametrar: header.<parameter-name>
Frågeparametrar: fråga.<parameter-name>
Nyttolastparametrar: nyttolast.<parameter-name>
Sökvägsparametrar: dynamic_path.<parameter-name>
Exempel:

{{externalDataLookup actionId="..." result="result" header.myHeaderParameter="value1" query.myQueryParameter="value2" payload.myPayloadParameter="value3"}}
Parametervärden kan vara fasta värden eller så kan de anpassas genom att referera till profilfält eller andra sammanhangsberoende attribut, t.ex.:

{{externalDataLookup actionId="..." result="result" query.myQueryParameter=profile.myProfileValue}}
Nyttolastparametrar kan anges med punktnotation för att referera till kapslade JSON-attribut, t.ex.:

{{externalDataLookup actionId="..." result="result" payload.context.channel="web"}}