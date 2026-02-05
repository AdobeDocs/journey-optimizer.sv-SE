---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera en anpassad åtgärd
description: Lär dig hur du konfigurerar en anpassad åtgärd
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Developer, Admin
level: Experienced
keywords: åtgärd, tredje part, anpassad, resor, API
exl-id: 4df2fc7c-85cb-410a-a31f-1bc1ece237bb
source-git-commit: 30241f4504ad82bf8ef9f6b58d3bb9482f572dae
workflow-type: tm+mt
source-wordcount: '2376'
ht-degree: 1%

---

# Konfigurera en anpassad åtgärd {#configure-a-custom-action}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom_configuration"
>title="Anpassade åtgärder"
>abstract="Om du använder ett tredjepartssystem för att skicka meddelanden eller om du vill att resor ska skicka API-anrop till ett tredjepartssystem, använder du anpassade åtgärder för att konfigurera anslutningen till din resa."

Om du använder ett tredjepartssystem för att skicka meddelanden eller om du vill att resor ska skicka API-anrop till ett tredjepartssystem, använder du anpassade åtgärder för att konfigurera anslutningen till din resa. Du kan till exempel ansluta till följande system med anpassade åtgärder: Epsilon, Slack, [Adobe Developer](https://developer.adobe.com){target="_blank"}, Firebase osv.

Anpassade åtgärder är ytterligare åtgärder som definieras av tekniska användare och görs tillgängliga för marknadsförare. När de har konfigurerats visas de i den vänstra paletten på din resa i kategorin **[!UICONTROL Action]**. Läs mer på [den här sidan](../building-journeys/about-journey-activities.md#action-activities).


## Konfigurationssteg {#configuration-steps}

Här följer de huvudsteg som krävs för att konfigurera en anpassad åtgärd:

1. Välj **[!UICONTROL Configurations]** på menyn Administration. Klicka på **[!UICONTROL Actions]** i avsnittet **[!UICONTROL Manage]**. Klicka på **[!UICONTROL Create Action]** om du vill skapa en ny åtgärd. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](assets/custom2.png)

1. Ange ett namn för åtgärden.

   >[!NOTE]
   >
   >Endast alfanumeriska tecken och understreck tillåts. Maximala längden är 30 tecken.

1. Lägg till en beskrivning av åtgärden. Det här steget är valfritt.
1. Antalet resor som använder den här åtgärden visas i fältet **[!UICONTROL Used in]**. Du kan klicka på knappen **[!UICONTROL View journeys]** om du vill visa listan över resor som använder den här åtgärden.
1. Definiera de olika **[!UICONTROL URL Configuration]**-parametrarna. Läs [den här sidan](../action/about-custom-action-configuration.md#url-configuration).
1. Konfigurera avsnittet **[!UICONTROL Authentication]**. Den här konfigurationen är densamma som för datakällor.  Se [det här avsnittet](../datasource/external-data-sources.md#custom-authentication-mode).
1. Definiera **[!UICONTROL Action parameters]**. Läs [den här sidan](../action/about-custom-action-configuration.md#define-the-message-parameters).
1. Klicka på **[!UICONTROL Save]**.

   Den anpassade åtgärden är nu konfigurerad och klar att användas på dina resor. Läs [den här sidan](../building-journeys/about-journey-activities.md#action-activities).

   >[!NOTE]
   >
   >När en anpassad åtgärd används i en resa är de flesta parametrar skrivskyddade. Du kan bara ändra fälten **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** och avsnittet **[!UICONTROL Authentication]**.

## Begränsningar{#custom-actions-limitations}

Anpassade åtgärder har några begränsningar angivna på [den här sidan](../start/guardrails.md).

I anpassade åtgärdsparametrar kan du skicka en enkel samling samt en samling med objekt. Läs mer om samlingsbegränsningar på [den här sidan](../building-journeys/collections.md#limitations).

Observera också att de anpassade åtgärdsparametrarna har ett förväntat format (till exempel sträng, decimal). Du måste vara försiktig med att ta hänsyn till dessa förväntade format. Läs mer i det här [användningsexemplet](../building-journeys/collections.md).

Anpassade åtgärder stöder bara JSON-format när [request](../action/about-custom-action-configuration.md#define-the-message-parameters) eller [response nyttloads](../action/action-response.md) används.

>[!NOTE]
>
>När en slutpunkt har en svarstid på mer än 0,75 sekunder dirigeras dess anpassade åtgärdsanrop via en dedikerad långsam [anpassad åtgärdstjänst](../configuration/external-systems.md#response-time) i stället för standardtjänsten.


## Bästa praxis{#custom-action-enhancements-best-practices}

När du väljer en slutpunkt som ska användas som mål med en anpassad åtgärd ska du se till att:

* Den här slutpunkten kan ha stöd för resans genomströmning genom att använda konfigurationer från [API:t för begränsning](../configuration/throttling.md) eller [API:t för begränsning](../configuration/capping.md). Var försiktig med att en begränsningskonfiguration inte får vara lägre än 200 TPS. Alla målpunkter måste ha stöd för minst 200 TPS. Läs mer om hastigheter för resebearbetning i [det här avsnittet](../building-journeys/entry-management.md#journey-processing-rate).
* Den här slutpunkten måste ha en svarstid som är så låg som möjligt. Beroende på förväntat dataflöde kan en hög svarstid påverka det faktiska dataflödet.

En begränsning på 300 000 anrop över en minut har definierats för alla anpassade åtgärder. Dessutom utförs standardcapping per värd och per sandlåda. Om du till exempel har två slutpunkter med samma värd (till exempel `https://www.adobe.com/endpoint1` och `https://www.adobe.com/endpoint2`) i en sandlåda, gäller det för alla slutpunkter under adobe.com. &quot;endpoint1&quot; och &quot;endpoint2&quot; har samma begränsningskonfiguration och om en slutpunkt når gränsen påverkas den andra slutpunkten.

>[!NOTE]
>
>300 000 anrop per minut används som ett **skjutningsfönster** per sandlåda och per slutpunkt för slutpunkter med svarstider som är mindre än 0,75 sekunder. Skjutningsfönstret kan börja när som helst i millisekunder, vilket innebär att det kan uppstå ett cappningsfel även om hastigheten är under 300 k/min vid justering till klockminuter. För slutpunkter med svarstider som är större än 0,75 sekunder gäller en separat gräns på 150 000 anrop per 30 sekunder (även ett skjutfönster). Läs mer om långsamma slutpunkter på [den här sidan](../configuration/external-systems.md#response-time).

Standardgränsen på 300 000 anrop per minut gäller på domännivå (t.ex. example.com). Om du vill ha en högre gräns kan du kontakta Adobe Support med användningsbevis och bekräfta slutpunktens dataflöde. Ange information om den förväntade samtalsvolymen och slutpunktskapaciteten om du vill begära en ökning av antalet samtal. Adobe kan anpassa capping om kapacitetstestning visar att slutpunkten kan hantera högre genomströmning. För bästa praxis bör man överväga att omstrukturera resorna eller genomföra vänteaktiviteter för att stagnera utgående samtal och undvika att få fel.

Den här gränsen har fastställts baserat på kundanvändning för att skydda externa slutpunkter som är inriktade på anpassade åtgärder. Om det behövs kan du åsidosätta den här inställningen genom att definiera en större begränsning för begränsning eller begränsning via våra API:er för begränsning/begränsning. Läs [den här sidan](../configuration/external-systems.md).

Du bör inte ange allmänna slutpunkter som mål med anpassade åtgärder av olika anledningar:

* Utan korrekt capping eller strypning finns det risk för att för många anrop skickas till en offentlig slutpunkt som kanske inte stöder den volymen.
* Profildata kan skickas via anpassade åtgärder, så att målgruppsanpassning för en publik slutpunkt kan leda till oavsiktlig delning av personlig information externt.
* Du har ingen kontroll över vilka data som returneras av offentliga slutpunkter. Om en slutpunkt ändrar sitt API eller börjar skicka felaktig information, kommer dessa att göras tillgängliga i den kommunikation som skickas, med potentiella negativa konsekvenser.

## Samtycke- och datahantering {#privacy}

I Journey Optimizer kan du tillämpa policyer för datastyrning och samtycke på anpassade åtgärder för att förhindra att specifika fält exporteras till tredjepartssystem eller utesluta kunder som inte har samtyckt till att ta emot e-post, push eller SMS-kommunikation. Mer information finns på följande sidor:

* [Datastyrning](../action/action-privacy.md).
* [Samtycke](../action/action-privacy.md).


## Konfiguration av slutpunkt {#url-configuration}

När du konfigurerar en anpassad åtgärd måste du definiera följande **[!UICONTROL Endpoint Configuration]**-parametrar:

![](assets/action-response1bis.png){width="70%" align="left"}

1. Ange URL-adressen för den externa tjänsten i fältet **[!UICONTROL URL]**:

   * Om URL:en är statisk anger du URL:en i det här fältet.

   * Om URL:en innehåller en dynamisk sökväg anger du bara den statiska delen av URL:en, det vill säga schemat, värden, porten och, eventuellt, en statisk del av sökvägen.

     Exempel: `https://xxx.yyy.com/somethingstatic/`

     Du anger den dynamiska sökvägen för URL:en när du lägger till den anpassade åtgärden på en resa. [Läs mer](../building-journeys/using-custom-actions.md).

   >[!NOTE]
   >
   >Av säkerhetsskäl rekommenderar vi starkt att du använder HTTPS-schemat för URL:en. Vi tillåter inte användning av Adobe-adresser som inte är offentliga och användning av IP-adresser.
   >
   >Endast standardportar tillåts när en anpassad åtgärd definieras: 80 för http och 443 för https.

1. Välj anropet **[!UICONTROL Method]**: det kan vara antingen **[!UICONTROL POST]**, **[!UICONTROL GET]** eller **[!UICONTROL PUT]**.

   >[!NOTE]
   >
   > Metoden **DELETE** stöds inte. Om du behöver uppdatera en befintlig resurs väljer du metoden **PUT**.

1. Hantera potentiella omdirigeringar (302 svar). **Anpassade åtgärder** följer automatiskt HTTP 302-omdirigeringar per begäran.

1. Definiera rubriker och frågeparametrar:

   * I avsnittet **[!UICONTROL Headers]** klickar du på **[!UICONTROL Add a header field]** för att definiera HTTP-rubrikerna för det begärandemeddelande som ska skickas till den externa tjänsten. Rubrikfälten **[!UICONTROL Content-Type]** och **[!UICONTROL Charset]** anges som standard. Du kan inte ta bort dessa fält. Endast rubriken **[!UICONTROL Content-Type]** kan ändras. Dess värde ska följa JSON-formatet. Här är standardvärdet:

   ![](assets/content-type-header.png)

   * I avsnittet **[!UICONTROL Query parameters]** klickar du på **[!UICONTROL Add a Query parameter field]** för att definiera de parametrar som du vill lägga till i URL:en.

   ![](assets/journeyurlconfiguration2bis.png)

1. Ange fältets etikett eller namn.

1. Välj typ: **[!UICONTROL Constant]** eller **[!UICONTROL Variable]**. Om du har markerat **[!UICONTROL Constant]** anger du det konstanta värdet i fältet **[!UICONTROL Value]**. Om du har valt **[!UICONTROL Variable]** anger du den här variabeln när du lägger till den anpassade åtgärden på en resa. [Läs mer](../building-journeys/using-custom-actions.md).

   ![](assets/journeyurlconfiguration2.png)

   >[!NOTE]
   >
   >När du har lagt till den anpassade åtgärden för en resa kan du fortfarande lägga till huvud- eller frågeparameterfält i den om resan är i utkaststatus. Om du inte vill att resan ska påverkas av konfigurationsändringar duplicerar du den anpassade åtgärden och lägger till fälten till den nya anpassade åtgärden.
   >
   >Huvuden valideras enligt fälttolkningsregler. Läs mer i [den här dokumentationen](https://tools.ietf.org/html/rfc7230#section-3.2.4){_blank}.

## Transportsäkerhetsskikt {#tls}

### Stöd för TLS-protokoll {#tls-protocol-support}

Adobe Journey Optimizer stöder TLS 1.3 som standard för anpassade åtgärder. Om en kund även stöder TLS 1.3 sker kommunikationen via TLS 1.3. I annat fall kan TLS-förhandlingarna återgå till TLS 1.2.

### Stöd för mTLS-protokoll {#mtls-protocol-support}

Du kan använda mTLS (Mutual Transport Layer Security) för att säkerställa förbättrad säkerhet vid utgående anslutningar till anpassade Adobe Journey Optimizer-åtgärder. mTLS är en heltäckande säkerhetsmetod för ömsesidig autentisering som ser till att båda parter delar information är de som gör anspråk på att vara innan data delas. mTLS innehåller ytterligare ett steg jämfört med TLS, där servern också frågar efter klientens certifikat och verifierar det i slutet.

Samuell TLS-autentisering (mTLS) stöds i anpassade åtgärder. Det krävs ingen ytterligare konfiguration i den anpassade åtgärden eller resan för att aktivera mTLS. Den sker automatiskt när en mTLS-aktiverad slutpunkt identifieras. [Läs mer](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption#mtls-protocol-support).

## Definiera nyttolastparametrarna {#define-the-message-parameters}

Du kan definiera nyttolastparametern så som beskrivs nedan:

1. I avsnittet **[!UICONTROL Request]** klistrar du in ett exempel på JSON-nyttolasten som ska skickas till den externa tjänsten. Det här fältet är valfritt och endast tillgängligt för POST- och PUT-anropsmetoder.

   Aktivera alternativet **[!UICONTROL Allow NULL values]** om du vill behålla Null-värden i det externa anropet. Observera att sändande arrayer av int, string osv. med Null-värden i stöds inte fullständigt. Följande array med heltal `[1, null, 2, 3]` skickas som `[1, 2, 3]` även om det här alternativet är markerat. Om arrayen är null skickas den dessutom som en tom array.

   ![](assets/null-values.png){width="70%" align="left"}

1. I avsnittet **[!UICONTROL Response]** klistrar du in ett exempel på nyttolasten som returneras när anropet lyckas. Det här fältet är valfritt och tillgängligt för alla anropsmetoder. Mer information om hur du använder API-anropssvar i anpassade åtgärder finns på [den här sidan](../action/action-response.md).

   ![](assets/response-values.png){width="70%" align="left"}

1. (Valfritt) Välj **[!UICONTROL Define a failure response payload]** om du vill aktivera nyttolastfältet för felsvar. När det här alternativet är aktiverat använder du avsnittet **[!UICONTROL Error Response]** för att klistra in ett exempel på nyttolasten som returneras när anropet misslyckas. Samma krav gäller som för svarsnyttolasten (fälttyper och format). Lär dig hur du kan utnyttja nyttolasten för felsvar på resor [här](../action/action-response.md).

   ![](assets/response-values.png){width="70%" align="left"}

>[!NOTE]
>
>Fältnamn i nyttolasten får inte innehålla en punkt `.` eller börja med ett `$`-tecken.
>

![](assets/customactionpayloadmessage2.png)

I den här fältkonfigurationen måste du:

* Välj parametertyp, t.ex. sträng, heltal osv.

* Definiera en konstant eller en variabelparameter:

   * **Konstant** betyder att parameterns värde definieras av en teknisk person i åtgärdskonfigurationsfönstret. Värdet är alltid detsamma oavsett resa. Den varierar inte och marknadsföraren kan inte se den när den anpassade åtgärden används under resan. Det kan till exempel vara ett ID som tredjepartssystemet förväntar sig. I så fall ställs konstantvärdet in i fältet till höger om växlingskonstanten/variabeln.

   * **Variabel** innebär att parameterns värde kan variera. Marknadsförare som använder den här anpassade åtgärden under en resa kan skicka det värde de vill ha eller ange var värdet för den här parametern ska hämtas (t.ex. från händelsen, från Adobe Experience Platform). I så fall är fältet till höger om växlingskonstanten/variabeln den etikett marknadsförarna kommer att se under resan för att namnge den här parametern.

  Aktivera alternativet **[!UICONTROL Is optional]** i slutet av raden för valfria parametrar. Genom att markera det här alternativet markerar du parametern som icke-obligatorisk och låter resenärerna välja att fylla i den eller inte när de redigerar den anpassade åtgärden under en resa.

>[!NOTE]
>
>Om du konfigurerar valfria parametrar samtidigt som du tillåter Null-värden, skickas parametrar som inte fyllts i av en reseadministratör som Null.
>

## Omfattande JSON-exempel {#json-examples}

I det här avsnittet finns fullständiga JSON-exempel som visar alla parametertyper och konfigurationer som stöds för anpassade åtgärder.

### Exempel 1: Grundläggande parametertyper

I det här exemplet visas hur du använder olika datatyper i din anpassade åtgärdsnyttolast:

```json
{
  "requestData": {
    "userId": "@{profile.person.name.firstName}",
    "accountId": "ABC123",
    "age": "@{profile.person.age}",
    "isActive": true,
    "loyaltyScore": "@{profile.customField.score}"
  }
}
```

I åtgärdskonfigurationen:
* `userId` - Variabelparameter (String) - Mappar till profilen firstName
* `accountId` - Konstant parameter (String) - Skickar alltid &quot;ABC123&quot;
* `age` - Variabelparameter (heltal) - Mappar till profilsida
* `isActive` - Konstant parameter (Boolean) - Skickar alltid true
* `loyaltyScore` - Variabelparameter (decimal) - Mappar till anpassat profilfält

### Exempel 2: Använda systemkonstanter och resekontext

Du kan referera till kundspecifik information och systemvärden:

```json
{
  "metadata": {
    "sandboxName": "prod",
    "executionTimestamp": "@{journey.startTime}",
    "journeyId": "@{journey.id}",
    "journeyName": "@{journey.name}",
    "journeyVersion": "@{journey.version}",
    "stepId": "@{journey.stepId}",
    "profileId": "@{profile.identityMap.ECID[0].id}"
  }
}
```

**Tillgängliga variabler för resekontext:**

>[!NOTE]
>
>Syntaxen för resekontextvariabler verifieras av produktteamet. De faktiska fältnamnen kan vara: travelUID, travelVersionName, travelVersion, currentNodeId, currentNodeName baserat på dokumentationen för reseegenskaper.

* `@{journey.id}` - Unik identifierare för resan
* `@{journey.name}` - Namn på resan
* `@{journey.version}` - Resans versionsnummer
* `@{journey.startTime}` - Tidsstämpel när resan påbörjades för den här profilen (verifiering krävs)
* `@{journey.stepId}` - ID för aktuellt steg
* `@{journey.stepName}` - Namnet på det aktuella steget

### Exempel 3: Valfria och obligatoriska parametrar

Konfigurera parametrar som resenärerna kan fylla i:

```json
{
  "customer": {
    "email": "@{profile.personalEmail.address}",
    "mobilePhone": "@{profile.mobilePhone.number}",
    "preferredLanguage": "@{profile.preferredLanguage}"
  }
}
```

I gränssnittet för åtgärdskonfigurationen:
* Ange `email` som **obligatoriskt** (markera inte Är valfritt)
* Ange `mobilePhone` som **valfri** (markera &quot;Är valfri&quot;)
* Ange `preferredLanguage` som **valfri** med standardvärde

>[!TIP]
>
>När en parameter är markerad som valfri och inte ifylld av resebyrån, utelämnas den från nyttolasten eller skickas som null (om Tillåt NULL-värden är aktiverat).

### Exempel 4: Arbeta med arrayer och samlingar

Skicka datainsamlingar till dina anpassade åtgärder:

```json
{
  "products": [
    {
      "id": "@{product1.id}",
      "name": "@{product1.name}",
      "price": "@{product1.price}"
    },
    {
      "id": "@{product2.id}",
      "name": "@{product2.name}",
      "price": "@{product2.price}"
    }
  ],
  "tags": ["premium", "loyalty", "vip"],
  "categoryIds": ["CAT001", "CAT002"]
}
```

>[!NOTE]
>
>Läs mer om hur du skickar samlingar i anpassade åtgärder på [den här sidan](../building-journeys/collections.md).

### Exempel 5: Kapslade objekt och komplexa strukturer

Skapa hierarkiska datastrukturer:

```json
{
  "customer": {
    "personalInfo": {
      "firstName": "@{profile.person.name.firstName}",
      "lastName": "@{profile.person.name.lastName}",
      "email": "@{profile.personalEmail.address}"
    },
    "address": {
      "street": "@{profile.homeAddress.street1}",
      "city": "@{profile.homeAddress.city}",
      "postalCode": "@{profile.homeAddress.postalCode}",
      "country": "@{profile.homeAddress.country}"
    },
    "preferences": {
      "language": "@{profile.preferredLanguage}",
      "timezone": "@{profile.timeZone}",
      "emailOptIn": "@{profile.consents.marketing.email.val}"
    }
  },
  "context": {
    "channel": "email",
    "campaignId": "CAMPAIGN_2025_Q1",
    "segment": "@{segmentMembership.status}"
  }
}
```

### Exempel 6: En fullständig anpassad åtgärd i verkligheten

Ett omfattande exempel som integrerar flera koncept:

```json
{
  "event": {
    "eventType": "journey.action.triggered",
    "eventId": "@{journey.stepId}",
    "timestamp": "@{journey.stepTimestamp}",
    "eventSource": "Adobe Journey Optimizer"
  },
  "profile": {
    "id": "@{profile.identityMap.ECID[0].id}",
    "email": "@{profile.personalEmail.address}",
    "firstName": "@{profile.person.name.firstName}",
    "lastName": "@{profile.person.name.lastName}",
    "loyaltyTier": "@{profile.loyaltyTier}",
    "lifetimeValue": "@{profile.lifetimeValue}"
  },
  "journey": {
    "id": "@{journey.id}",
    "name": "@{journey.name}",
    "version": "@{journey.version}",
    "step": "@{journey.stepName}"
  },
  "customData": {
    "offerName": "@{decisioning.offerName}",
    "offerPlacement": "@{decisioning.placementName}",
    "specialPromotion": "WINTER2025"
  },
  "system": {
    "sandbox": "prod",
    "dataStreamId": "YOUR_DATASTREAM_ID",
    "imsOrgId": "@{imsOrgId}"
  }
}
```

**Konfigurationstips för det här exemplet:**
* Blandning av konstanta värden (`eventSource`, `specialPromotion`, `sandbox`) och variabelparametrar
* Använder resekontext för spårning och felsökning
* Inkluderar profildata för personalisering i tredjepartssystemet
* Lägger till beslutskontext när erbjudanden används
* Systemmetadata för routning och spårning på organisationsnivå

### Tips för konfiguration av konstanter

**Namn på sandlåda:** Använd en konstant parameter som angetts till ditt miljönamn (t.ex. &quot;prod&quot;, &quot;dev&quot;, &quot;stage&quot;)

**Körningstidsstämpel:** Använd `@{journey.startTime}` eller skapa en variabelparameter som reseansvariga kan mappa till funktionen `#{nowWithDelta()}`

**API-version:** Använd en konstant för API-versionsnummer för att säkerställa konsekvens mellan resor

**Autentiseringstoken:** Ange aldrig autentiseringstoken i nyttolasten - använd autentiseringsavsnittet i den anpassade åtgärdskonfigurationen i stället

>[!CAUTION]
>
>Fältnamn i nyttolasten får inte innehålla en punkt `.` eller börja med ett `$`-tecken. Se till att JSON-strukturen följer dessa namnkonventioner.

* [Felsökning av anpassad åtgärd](../action/troubleshoot-custom-action.md) - Lär dig hur du felsöker en anpassad åtgärd


## Ytterligare resurser

Bläddra i avsnitten nedan om du vill veta mer om hur du konfigurerar, använder och felsöker anpassade åtgärder:

* [Kom igång med anpassade åtgärder](../action/action.md) - Lär dig vad som är en anpassad åtgärd och hur de hjälper dig att ansluta till tredjepartssystem
* [Använd anpassade åtgärder](../building-journeys/using-custom-actions.md) - Lär dig hur du använder anpassade åtgärder på dina resor
* [Felsökning av anpassad åtgärd](../action/troubleshoot-custom-action.md) - Lär dig hur du felsöker en anpassad åtgärd
* [Skicka samlingar till anpassade åtgärdsparametrar](../building-journeys/collections.md) - Lär dig hur du skickar en samling i anpassade åtgärdsparametrar som fylls i dynamiskt vid körning

