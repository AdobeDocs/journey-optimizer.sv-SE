---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera en anpassad åtgärd
description: Lär dig hur du konfigurerar en anpassad åtgärd
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: åtgärd, tredje part, anpassad, resor, API
exl-id: 4df2fc7c-85cb-410a-a31f-1bc1ece237bb
source-git-commit: 12423d9fe07e5c757154ae4f732ff20ec6dc2427
workflow-type: tm+mt
source-wordcount: '1750'
ht-degree: 1%

---

# Konfigurera en anpassad åtgärd {#configure-an-action}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom_configuration"
>title="Anpassade åtgärder"
>abstract="Om du använder ett tredjepartssystem för att skicka meddelanden eller om du vill att resor ska skicka API-anrop till ett tredjepartssystem, använder du anpassade åtgärder för att konfigurera anslutningen till din resa. Du kan till exempel ansluta till följande system med anpassade åtgärder: Epsilon, Slack, [Adobe Developer](https://developer.adobe.com), Firebase osv."

Om du använder ett tredjepartssystem för att skicka meddelanden eller om du vill att resor ska skicka API-anrop till ett tredjepartssystem, använder du anpassade åtgärder för att konfigurera anslutningen till din resa. Du kan till exempel ansluta till följande system med anpassade åtgärder: Epsilon, Slack, [Adobe Developer](https://developer.adobe.com){target="_blank"}, Firebase osv.

Anpassade åtgärder är ytterligare åtgärder som definieras av tekniska användare och görs tillgängliga för marknadsförare. När de är konfigurerade visas de på den vänstra paletten på din resa i **[!UICONTROL Action]** kategori. Läs mer på [den här sidan](../building-journeys/about-journey-activities.md#action-activities).

## Begränsningar{#custom-actions-limitations}

Anpassade åtgärder har några begränsningar som anges i [den här sidan](../start/guardrails.md).

I anpassade åtgärdsparametrar kan du skicka en enkel samling samt en samling med objekt. Läs mer om begränsningar för samlingar i [den här sidan](../building-journeys/collections.md#limitations).

Observera också att de anpassade åtgärdsparametrarna har ett förväntat format (till exempel sträng, decimal). Du måste vara försiktig med att ta hänsyn till dessa förväntade format. Läs mer om detta [användningsfall](../building-journeys/collections.md).

Anpassade åtgärder stöder bara JSON-format när du använder [förfrågan](../action/about-custom-action-configuration.md#define-the-message-parameters) eller [svarsnyttolaster](../action/action-response.md).

## Bästa praxis{#custom-action-enhancements-best-practices}

När du väljer en slutpunkt som ska användas som mål med en anpassad åtgärd ska du se till att:

* Den här slutpunkten kan stödja resans genomströmning med hjälp av konfigurationer från [Begränsnings-API](../configuration/throttling.md) eller [API för begränsning](../configuration/capping.md) för att begränsa den. Var försiktig med att en begränsningskonfiguration inte får vara lägre än 200 TPS. Alla målpunkter måste ha stöd för minst 200 TPS.
* Den här slutpunkten måste ha en svarstid som är så låg som möjligt. Beroende på förväntat dataflöde kan en hög svarstid påverka det faktiska dataflödet.

En begränsning på 300 000 anrop över en minut har definierats för alla anpassade åtgärder. Dessutom utförs standardcapping per värd och per sandlåda. Om du till exempel har två slutpunkter med samma värd i en sandlåda (till exempel: `https://www.adobe.com/endpoint1` och `https://www.adobe.com/endpoint2`) gäller det för alla slutpunkter under adobe.com. &quot;endpoint1&quot; och &quot;endpoint2&quot; har samma begränsningskonfiguration och om en slutpunkt når gränsen påverkas den andra slutpunkten.

Den här gränsen har fastställts baserat på kundanvändning för att skydda externa slutpunkter som har anpassats efter anpassade åtgärder. Du måste ta hänsyn till detta vid målgruppsbaserade resor genom att definiera en lämplig läsfrekvens (5 000 profiler/er när anpassade åtgärder används). Om det behövs kan du åsidosätta den här inställningen genom att definiera en större begränsning för begränsning eller begränsning via våra API:er för begränsning/begränsning. Läs [den här sidan](../configuration/external-systems.md).

Du bör inte ange allmänna slutpunkter som mål med anpassade åtgärder av olika anledningar:

* Utan korrekt capping eller strypning finns det risk för att för många anrop skickas till en offentlig slutpunkt som kanske inte stöder den volymen.
* Profildata kan skickas via anpassade åtgärder, så att målgruppsanpassning för en publik slutpunkt kan leda till oavsiktlig delning av personlig information externt.
* Du har ingen kontroll över vilka data som returneras av offentliga slutpunkter. Om en slutpunkt ändrar sitt API eller börjar skicka felaktig information, kommer dessa att göras tillgängliga i den kommunikation som skickas, med potentiella negativa konsekvenser.

## Samtycke- och datahantering {#privacy}

I Journey Optimizer kan du tillämpa policyer för datastyrning och samtycke på anpassade åtgärder för att förhindra att specifika fält exporteras till tredjepartssystem eller utesluta kunder som inte har samtyckt till att ta emot e-post, push eller SMS-kommunikation. Mer information finns på följande sidor:

* [Datastyrning](../action/action-privacy.md).
* [Godkännande](../action/action-privacy.md).


## Konfigurationssteg {#configuration-steps}

Här följer de huvudsteg som krävs för att konfigurera en anpassad åtgärd:

1. I avsnittet ADMINISTRATION-menyn väljer du **[!UICONTROL Configurations]**. I  **[!UICONTROL Actions]** avsnitt, klicka **[!UICONTROL Manage]**. Klicka **[!UICONTROL Create Action]** för att skapa en ny åtgärd. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](assets/custom2.png)

1. Ange ett namn för åtgärden.

   >[!NOTE]
   >
   >Endast alfanumeriska tecken och understreck tillåts. Maximala längden är 30 tecken.

1. Lägg till en beskrivning av åtgärden. Det här steget är valfritt.
1. Antalet resor som använder den här åtgärden visas i **[!UICONTROL Used in]** fält. Du kan klicka på **[!UICONTROL View journeys]** om du vill visa en lista över resor som använder den här åtgärden.
1. Definiera de olika **[!UICONTROL URL Configuration]** parametrar. Läs [den här sidan](../action/about-custom-action-configuration.md#url-configuration).
1. Konfigurera **[!UICONTROL Authentication]** -avsnitt. Den här konfigurationen är densamma som för datakällor.  Se [det här avsnittet](../datasource/external-data-sources.md#custom-authentication-mode).
1. Definiera **[!UICONTROL Action parameters]**. Läs [den här sidan](../action/about-custom-action-configuration.md#define-the-message-parameters).
1. Klicka på **[!UICONTROL Save]**.

   Den anpassade åtgärden är nu konfigurerad och klar att användas på dina resor. Läs [den här sidan](../building-journeys/about-journey-activities.md#action-activities).

   >[!NOTE]
   >
   >När en anpassad åtgärd används i en resa är de flesta parametrar skrivskyddade. Du kan bara ändra **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** fält och **[!UICONTROL Authentication]** -avsnitt.

## Konfiguration av slutpunkt {#url-configuration}

När du konfigurerar en anpassad åtgärd måste du definiera följande **[!UICONTROL Endpoint Configuration]** parametrar:

![](assets/action-response1bis.png){width="70%" align="left"}

1. I **[!UICONTROL URL]** anger du URL-adressen för den externa tjänsten:

   * Om URL:en är statisk anger du URL:en i det här fältet.

   * Om URL:en innehåller en dynamisk sökväg anger du bara den statiska delen av URL:en, det vill säga schemat, värden, porten och, eventuellt, en statisk del av sökvägen.

     Exempel: `https://xxx.yyy.com/somethingstatic/`

     Du anger den dynamiska sökvägen för URL:en när du lägger till den anpassade åtgärden på en resa. [Läs mer](../building-journeys/using-custom-actions.md).

   >[!NOTE]
   >
   >Av säkerhetsskäl rekommenderar vi starkt att du använder HTTPS-schemat för URL:en. Vi tillåter inte användning av Adobe-adresser som inte är offentliga och användning av IP-adresser.
   >
   >Endast standardportar tillåts när en anpassad åtgärd definieras: 80 för http och 443 för https.

1. Välj samtalet **[!UICONTROL Method]**: det kan vara antingen **[!UICONTROL POST]**, **[!UICONTROL GET]** eller **[!UICONTROL PUT]**.

   >[!NOTE]
   >
   > The **DELETE** -metoden stöds inte. Om du behöver uppdatera en befintlig resurs väljer du **PUT** -metod.

1. Definiera rubriker och frågeparametrar:

   * I **[!UICONTROL Headers]** avsnitt, klicka **[!UICONTROL Add a header field]** för att definiera HTTP-rubrikerna för det begärandemeddelande som ska skickas till den externa tjänsten. The **[!UICONTROL Content-Type]** och **[!UICONTROL Charset]** rubrikfält anges som standard. Du kan inte ta bort dessa fält. Endast **[!UICONTROL Content-Type]** kan ändras. Dess värde ska följa JSON-formatet. Här är standardvärdet:

   ![](assets/content-type-header.png)

   * I **[!UICONTROL Query parameters]** avsnitt, klicka **[!UICONTROL Add a Query parameter field]** för att definiera de parametrar som du vill lägga till i URL-adressen.

   ![](assets/journeyurlconfiguration2bis.png)

1. Ange fältets etikett eller namn.

1. Välj typ: **[!UICONTROL Constant]** eller **[!UICONTROL Variable]**. Om du har valt **[!UICONTROL Constant]** anger du sedan det konstanta värdet i **[!UICONTROL Value]** fält. Om du har valt **[!UICONTROL Variable]** anger du den här variabeln när du lägger till den anpassade åtgärden på en resa. [Läs mer](../building-journeys/using-custom-actions.md).

   ![](assets/journeyurlconfiguration2.png)

   >[!NOTE]
   >
   >När du har lagt till den anpassade åtgärden för en resa kan du fortfarande lägga till huvud- eller frågeparameterfält i den om resan är i utkaststatus. Om du inte vill att resan ska påverkas av konfigurationsändringar duplicerar du den anpassade åtgärden och lägger till fälten till den nya anpassade åtgärden.
   >
   >Huvuden valideras enligt fälttolkningsregler. Läs mer i [den här dokumentationen](https://tools.ietf.org/html/rfc7230#section-3.2.4){_blank}.

## Definiera nyttolastparametrarna {#define-the-message-parameters}

1. I **[!UICONTROL Request]** klistra in ett exempel på JSON-nyttolasten som ska skickas till den externa tjänsten. Det här fältet är valfritt och endast tillgängligt för anropsmetoder för POST och PUT.

1. I **[!UICONTROL Response]** klistra in ett exempel på nyttolasten som returneras av anropet. Det här fältet är valfritt och tillgängligt för alla anropsmetoder. Detaljerad information om hur du utnyttjar API-anropssvar i anpassade åtgärder finns i [den här sidan](../action/action-response.md).

>[!NOTE]
>
>Svarsfunktionen finns för närvarande i betaversionen.

![](assets/action-response2bis.png){width="70%" align="left"}

>[!NOTE]
>
>Nyttolastexemplet får inte innehålla null-värden. Fältnamn i nyttolasten får inte innehålla &quot;.&quot; tecken. De kan inte börja med tecknet &quot;$&quot;.

Du kan definiera parametertypen (t.ex. sträng, heltal).

Du kan också välja mellan att ange om en parameter är en konstant eller en variabel:

* **Konstant** betyder att parameterns värde definieras av en teknisk person i åtgärdskonfigurationsfönstret. Värdet är alltid detsamma oavsett resa. Det kommer inte att variera och marknadsföraren kommer inte att se det när han eller hon använder den anpassade åtgärden under resan. Det kan till exempel vara ett ID som tredjepartssystemet förväntar sig. I så fall är fältet till höger om växlingskonstanten/variabeln det värde som skickas.
* **Variabel** betyder att parameterns värde kommer att variera. Marknadsförare som använder den här anpassade åtgärden under en resa kan skicka det värde de vill ha eller ange var värdet för den här parametern ska hämtas (t.ex. från händelsen, från Adobe Experience Platform). I så fall är fältet till höger om växlingskonstanten/variabeln den etikett marknadsförarna kommer att se under resan för att namnge den här parametern.

![](assets/customactionpayloadmessage2.png)

## Stöd för mTLS-protokoll {#mtls-protocol-support}

Nu kan du använda mTLS (Mutual Transport Layer Security) för att förbättra säkerheten för utgående anslutningar till HTTP API-mål och anpassade Adobe Journey Optimizer-åtgärder. mTLS är en heltäckande säkerhetsmetod för ömsesidig autentisering som ser till att båda parter delar information är de som gör anspråk på att vara innan data delas. mTLS innehåller ytterligare ett steg jämfört med TLS, där servern också frågar efter klientens certifikat och verifierar det i slutet.

I Adobe Journey Optimizer används mTLS tillsammans med anpassade åtgärder. Du behöver inte göra någon ytterligare konfiguration för anpassade Adobe Journey Optimizer-åtgärder för att aktivera mTLS. När slutpunkten för en anpassad åtgärd är mTLS-aktiverad hämtar systemet certifikatet från Adobe Experience Platform nyckelbehållare och skickar det automatiskt till slutpunkten (vilket krävs för mTLS-anslutningar).

Om du vill använda mTLS med dessa Adobe Journey Optimizer och Experience Platform HTTP API-målarbetsflöden måste den serveradress som du placerar i Adobe Journey Optimizer kundåtgärdsgränssnitt eller målgränssnittet ha TLS-protokoll inaktiverade och endast mTLS aktiverade. Om TLS 1.2-protokollet fortfarande är aktiverat på den slutpunkten skickas inget certifikat för klientautentisering. Det innebär att om du vill använda mTLS med dessa arbetsflöden måste den&quot;mottagande&quot; serverslutpunkten vara en mTLS **endast** aktiverad slutpunkt för anslutning.

>[!IMPORTANT]
>
>Ingen ytterligare konfiguration krävs i din anpassade Adobe Journey Optimizer-åtgärd eller -resa för att aktivera mTLS. Den här processen sker automatiskt när en mTLS-aktiverad slutpunkt identifieras. Det gemensamma namnet (CN) och SAN (Subject Alternative Names) för varje certifikat finns i dokumentationen som en del av certifikatet och kan användas som ett ytterligare lager av ägarskapsvalidering om du vill.
>
>RFC 2818, som publicerades i maj 2000, tar bort användningen av fältet Gemensamt namn (CN) i HTTPS-certifikat för verifiering av ämnesnamn. Du bör i stället använda tillägget&quot;Alternativt ämnesnamn&quot; (SAN) av typen&quot;DNS-namn&quot;.

Om du vill kontrollera KN eller SAN för att göra ytterligare validering från tredje part, kan ladda ned relevanta certifikat här:

```
Prod:
{
    "serviceName": "AJO Journeys",
    "publicCertificate": "-----BEGIN CERTIFICATE-----
MIIG9TCCBd2gAwIBAgIQBX+pDP5hB0gqDzFKyq5wLjANBgkqhkiG9w0BAQsFADBZ
MQswCQYDVQQGEwJVUzEVMBMGA1UEChMMRGlnaUNlcnQgSW5jMTMwMQYDVQQDEypE
aWdpQ2VydCBHbG9iYWwgRzIgVExTIFJTQSBTSEEyNTYgMjAyMCBDQTEwHhcNMjQw
NTA5MDAwMDAwWhcNMjUwNjA5MjM1OTU5WjB0MQswCQYDVQQGEwJVUzETMBEGA1UE
CBMKQ2FsaWZvcm5pYTERMA8GA1UEBxMIU2FuIEpvc2UxEzARBgNVBAoTCkFkb2Jl
IEluYy4xKDAmBgNVBAMTH2Fqby1qb3VybmV5cy5hZXAtbXRscy5hZG9iZS5jb20w
ggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDaI8HZHzbmPEgTy9O7cYmq
ZVX5283Gw7j7v4/O810jZXItBDmsSiWotvTgAT0s2oZMZZ6tGPbQB7hL+xJJ+yu2
HxFl1WzB4UGHJ+UbrL94hI930xQs0FVgSOGgIarj5HucF2ZxwHIkVHY5whrOq9t4
UxFBG0siUPQrTzV9GfA0wREElugpTbwaM8CTWwOQ9ekroOD2C5zAcLTycXFtSMiU
B4L4u38S9hGoBByzzKv9GnUMQudvt/s5zsGykZgEEYeN6IitfVO6BOD9jT94Aytx
/O3XH5w8v4KNTn+An99bXFmyg3JRUFSYZFxha8s1f6uu0XbdToQ+ao0WkE06nMmV
AgMBAAGjggOcMIIDmDAfBgNVHSMEGDAWgBR0hYDAZsffN97PvSk3qgMdvu3NFzAd
BgNVHQ4EFgQUn8OqtzccNdrsb+fbRnTHmtTZxLMwKgYDVR0RBCMwIYIfYWpvLWpv
dXJuZXlzLmFlcC1tdGxzLmFkb2JlLmNvbTA+BgNVHSAENzA1MDMGBmeBDAECAjAp
MCcGCCsGAQUFBwIBFhtodHRwOi8vd3d3LmRpZ2ljZXJ0LmNvbS9DUFMwDgYDVR0P
AQH/BAQDAgWgMB0GA1UdJQQWMBQGCCsGAQUFBwMBBggrBgEFBQcDAjCBnwYDVR0f
BIGXMIGUMEigRqBEhkJodHRwOi8vY3JsMy5kaWdpY2VydC5jb20vRGlnaUNlcnRH
bG9iYWxHMlRMU1JTQVNIQTI1NjIwMjBDQTEtMS5jcmwwSKBGoESGQmh0dHA6Ly9j
cmw0LmRpZ2ljZXJ0LmNvbS9EaWdpQ2VydEdsb2JhbEcyVExTUlNBU0hBMjU2MjAy
MENBMS0xLmNybDCBhwYIKwYBBQUHAQEEezB5MCQGCCsGAQUFBzABhhhodHRwOi8v
b2NzcC5kaWdpY2VydC5jb20wUQYIKwYBBQUHMAKGRWh0dHA6Ly9jYWNlcnRzLmRp
Z2ljZXJ0LmNvbS9EaWdpQ2VydEdsb2JhbEcyVExTUlNBU0hBMjU2MjAyMENBMS0x
LmNydDAMBgNVHRMBAf8EAjAAMIIBfwYKKwYBBAHWeQIEAgSCAW8EggFrAWkAdwBO
daMnXJoQwzhbbNTfP1LrHfDgjhuNacCx+mSxYpo53wAAAY9ecsWsAAAEAwBIMEYC
IQDQclgq89ZVlwdYBJFEIs8q4WIcZ9Siw+jb9OgCrz+wjwIhALQLnC1WyT+dHjvY
FvZjc99WkjnEwhIevj/Rz7r0EzhmAHUAfVkeEuF4KnscYWd8Xv340IdcFKBOlZ65
Ay/ZDowuebgAAAGPXnLF5AAABAMARjBEAiBy9cNT3CnmSMOdJe+JbG8f7ha1UGgN
TdDlaR9x9fKmKQIgNmGjz5AzP1evB2G1TTvVLkHfWQw0864c4F23WSV+6TsAdwDP
EVbu1S58r/OHW9lpLpvpGnFnSrAX7KwB0lt3zsw7CAAAAY9ecsYnAAAEAwBIMEYC
IQCTcB7s1xDP8Olif3jj4X8jHgVxv5C3bTvG6wDYBByfcQIhAOt8PhR6tWSLtF1V
HB8r7dns7Oth1+QT7WMonQZsP/3WMA0GCSqGSIb3DQEBCwUAA4IBAQAjTy45fbQV
aVTZ71wcIyHnkJfq/8SSc/UNT5//6AMiV6kb3YsFW1+EaQ1wPHZS0Qfjs7aIsXi5
f2TCGps8onELNpOfFfptrOCMfcYGMvV1wPCBy+kuoGY/YRZlsdNUTTzQAGztfRev
79w+XIDzioCrY+sfyUkkw+N/F7/RIjzMKjP6onSfuD+5WjqVKq9kFE0fCyJixedV
BPoPM4Cktgvc9SsK17JmLWkg+V2yH1eDzmjF3sR0/dcmoAM0qgV/CDuhIIqX2o7m
3/aQSNsPUpgBVbkz+SjEtchmw8DXW/Kro8QVulsXdbkiLTOj4JopxdOzrbKgWMwr
pIw7KKJoktDk
-----END CERTIFICATE-----
-----BEGIN CERTIFICATE-----
MIIEyDCCA7CgAwIBAgIQDPW9BitWAvR6uFAsI8zwZjANBgkqhkiG9w0BAQsFADBh
MQswCQYDVQQGEwJVUzEVMBMGA1UEChMMRGlnaUNlcnQgSW5jMRkwFwYDVQQLExB3
d3cuZGlnaWNlcnQuY29tMSAwHgYDVQQDExdEaWdpQ2VydCBHbG9iYWwgUm9vdCBH
MjAeFw0yMTAzMzAwMDAwMDBaFw0zMTAzMjkyMzU5NTlaMFkxCzAJBgNVBAYTAlVT
MRUwEwYDVQQKEwxEaWdpQ2VydCBJbmMxMzAxBgNVBAMTKkRpZ2lDZXJ0IEdsb2Jh
bCBHMiBUTFMgUlNBIFNIQTI1NiAyMDIwIENBMTCCASIwDQYJKoZIhvcNAQEBBQAD
ggEPADCCAQoCggEBAMz3EGJPprtjb+2QUlbFbSd7ehJWivH0+dbn4Y+9lavyYEEV
cNsSAPonCrVXOFt9slGTcZUOakGUWzUb+nv6u8W+JDD+Vu/E832X4xT1FE3LpxDy
FuqrIvAxIhFhaZAmunjZlx/jfWardUSVc8is/+9dCopZQ+GssjoP80j812s3wWPc
3kbW20X+fSP9kOhRBx5Ro1/tSUZUfyyIxfQTnJcVPAPooTncaQwywa8WV0yUR0J8
osicfebUTVSvQpmowQTCd5zWSOTOEeAqgJnwQ3DPP3Zr0UxJqyRewg2C/Uaoq2yT
zGJSQnWS+Jr6Xl6ysGHlHx+5fwmY6D36g39HaaECAwEAAaOCAYIwggF+MBIGA1Ud
EwEB/wQIMAYBAf8CAQAwHQYDVR0OBBYEFHSFgMBmx9833s+9KTeqAx2+7c0XMB8G
A1UdIwQYMBaAFE4iVCAYlebjbuYP+vq5Eu0GF485MA4GA1UdDwEB/wQEAwIBhjAd
BgNVHSUEFjAUBggrBgEFBQcDAQYIKwYBBQUHAwIwdgYIKwYBBQUHAQEEajBoMCQG
CCsGAQUFBzABhhhodHRwOi8vb2NzcC5kaWdpY2VydC5jb20wQAYIKwYBBQUHMAKG
NGh0dHA6Ly9jYWNlcnRzLmRpZ2ljZXJ0LmNvbS9EaWdpQ2VydEdsb2JhbFJvb3RH
Mi5jcnQwQgYDVR0fBDswOTA3oDWgM4YxaHR0cDovL2NybDMuZGlnaWNlcnQuY29t
L0RpZ2lDZXJ0R2xvYmFsUm9vdEcyLmNybDA9BgNVHSAENjA0MAsGCWCGSAGG/WwC
ATAHBgVngQwBATAIBgZngQwBAgEwCAYGZ4EMAQICMAgGBmeBDAECAzANBgkqhkiG
9w0BAQsFAAOCAQEAkPFwyyiXaZd8dP3A+iZ7U6utzWX9upwGnIrXWkOH7U1MVl+t
wcW1BSAuWdH/SvWgKtiwla3JLko716f2b4gp/DA/JIS7w7d7kwcsr4drdjPtAFVS
slme5LnQ89/nD/7d+MS5EHKBCQRfz5eeLjJ1js+aWNJXMX43AYGyZm0pGrFmCW3R
bpD0ufovARTFXFZkAdl9h6g4U5+LXUZtXMYnhIHUfoyMo5tS58aI7Dd8KvvwVVo4
chDYABPPTHPbqjc1qCmBaZx2vN4Ye5DUys/vZwP9BFohFrH/6j/f3IL16/RZkiMN
JCqVJUzKoZHm1Lesh3Sz8W2jmdv51b2EQJ8HmA==
-----END CERTIFICATE-----
-----BEGIN CERTIFICATE-----
MIIDjjCCAnagAwIBAgIQAzrx5qcRqaC7KGSxHQn65TANBgkqhkiG9w0BAQsFADBh
MQswCQYDVQQGEwJVUzEVMBMGA1UEChMMRGlnaUNlcnQgSW5jMRkwFwYDVQQLExB3
d3cuZGlnaWNlcnQuY29tMSAwHgYDVQQDExdEaWdpQ2VydCBHbG9iYWwgUm9vdCBH
MjAeFw0xMzA4MDExMjAwMDBaFw0zODAxMTUxMjAwMDBaMGExCzAJBgNVBAYTAlVT
MRUwEwYDVQQKEwxEaWdpQ2VydCBJbmMxGTAXBgNVBAsTEHd3dy5kaWdpY2VydC5j
b20xIDAeBgNVBAMTF0RpZ2lDZXJ0IEdsb2JhbCBSb290IEcyMIIBIjANBgkqhkiG
9w0BAQEFAAOCAQ8AMIIBCgKCAQEAuzfNNNx7a8myaJCtSnX/RrohCgiN9RlUyfuI
2/Ou8jqJkTx65qsGGmvPrC3oXgkkRLpimn7Wo6h+4FR1IAWsULecYxpsMNzaHxmx
1x7e/dfgy5SDN67sH0NO3Xss0r0upS/kqbitOtSZpLYl6ZtrAGCSYP9PIUkY92eQ
q2EGnI/yuum06ZIya7XzV+hdG82MHauVBJVJ8zUtluNJbd134/tJS7SsVQepj5Wz
tCO7TG1F8PapspUwtP1MVYwnSlcUfIKdzXOS0xZKBgyMUNGPHgm+F6HmIcr9g+UQ
vIOlCsRnKPZzFBQ9RnbDhxSJITRNrw9FDKZJobq7nMWxM4MphQIDAQABo0IwQDAP
BgNVHRMBAf8EBTADAQH/MA4GA1UdDwEB/wQEAwIBhjAdBgNVHQ4EFgQUTiJUIBiV
5uNu5g/6+rkS7QYXjzkwDQYJKoZIhvcNAQELBQADggEBAGBnKJRvDkhj6zHd6mcY
1Yl9PMWLSn/pvtsrF9+wX3N3KjITOYFnQoQj8kVnNeyIv/iPsGEMNKSuIEyExtv4
NeF22d+mQrvHRAiGfzZ0JFrabA0UWTW98kndth/Jsw1HKj2ZL7tcu7XUIOGZX1NG
Fdtom/DzMNU+MeKNhJ7jitralj41E6Vf8PlwUHBHQRFXGU7Aj64GxJUTFy8bJZ91
8rGOmaFvE7FBcf6IKshPECBV1/MUReXgRPTqh5Uykw7+U0b6LJ3/iyK5S9kJRaTe
pLiaWN0bfVKfjllDiIGknibVb63dDcY3fe0Dkhvld1927jyNxF1WW6LZZm6zNTfl
MrY=
-----END CERTIFICATE-----",
    "expiryDate": "2025-06-09T23:59:59Z"
}
```

