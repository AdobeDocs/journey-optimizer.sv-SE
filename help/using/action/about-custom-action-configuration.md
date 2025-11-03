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
source-git-commit: 5eddbb1f9ab53f1666ccd8518785677018e10f6f
workflow-type: tm+mt
source-wordcount: '1784'
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

Den här gränsen har fastställts baserat på kundanvändning för att skydda externa slutpunkter som är inriktade på anpassade åtgärder. Du måste ta hänsyn till detta vid målgruppsbaserade resor genom att definiera en lämplig läsfrekvens (5 000 profiler/er när anpassade åtgärder används). Om det behövs kan du åsidosätta den här inställningen genom att definiera en större begränsning för begränsning eller begränsning via våra API:er för begränsning/begränsning. Läs [den här sidan](../configuration/external-systems.md).

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

Samuell TLS-autentisering (mTLS) stöds i anpassade åtgärder. Det krävs ingen ytterligare konfiguration i den anpassade åtgärden eller resan för att aktivera mTLS. Den sker automatiskt när en mTLS-aktiverad slutpunkt identifieras. [Läs mer](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/governance-privacy-security/encryption#mtls-protocol-support).

## Definiera nyttolastparametrarna {#define-the-message-parameters}

Du kan definiera nyttolastparametern så som beskrivs nedan:

1. I avsnittet **[!UICONTROL Request]** klistrar du in ett exempel på JSON-nyttolasten som ska skickas till den externa tjänsten. Det här fältet är valfritt och endast tillgängligt för POST- och PUT-anropsmetoder.

   Aktivera alternativet **[!UICONTROL Allow NULL values]** om du vill behålla Null-värden i det externa anropet. Observera att sändande arrayer av int, string osv. med Null-värden i stöds inte fullständigt. Följande array med heltal `[1, null, 2, 3]` skickas som `[1, 2, 3]` även om det här alternativet är markerat. Om arrayen är null skickas den dessutom som en tom array.

   ![](assets/null-values.png){width="70%" align="left"}

1. Klistra in ett exempel på nyttolasten som returneras av anropet i avsnittet **[!UICONTROL Response]**. Det här fältet är valfritt och tillgängligt för alla anropsmetoder. Mer information om hur du använder API-anropssvar i anpassade åtgärder finns på [den här sidan](../action/action-response.md).

>[!NOTE]
>
>Fältnamn i nyttolasten får inte innehålla en punkt `.` eller börja med ett `$`-tecken.
>

![](assets/customactionpayloadmessage2.png)

I fältkonfigurationen måste du:

* Välj parametertyp, t.ex. sträng, heltal osv.

* Definiera en konstant eller en variabelparameter:

   * **Konstant** betyder att parameterns värde definieras av en teknisk person i åtgärdskonfigurationsfönstret. Värdet är alltid detsamma oavsett resa. Den varierar inte och marknadsföraren kan inte se den när den anpassade åtgärden används under resan. Det kan till exempel vara ett ID som tredjepartssystemet förväntar sig. I så fall ställs konstantvärdet in i fältet till höger om växlingskonstanten/variabeln.

   * **Variabel** innebär att parameterns värde kan variera. Marknadsförare som använder den här anpassade åtgärden under en resa kan skicka det värde de vill ha eller ange var värdet för den här parametern ska hämtas (t.ex. från händelsen, från Adobe Experience Platform). I så fall är fältet till höger om växlingskonstanten/variabeln den etikett marknadsförarna kommer att se under resan för att namnge den här parametern.

  Aktivera alternativet **[!UICONTROL Is optional]** i slutet av raden för valfria parametrar. Genom att markera det här alternativet markerar du parametern som icke-obligatorisk och låter resenärerna välja att fylla i den eller inte när de redigerar den anpassade åtgärden under en resa.

>[!NOTE]
>
>Om du konfigurerar valfria parametrar samtidigt som du tillåter Null-värden, skickas parametrar som inte fyllts i av en reseadministratör som Null.
>


* [Felsökning av anpassad åtgärd](../action/troubleshoot-custom-action.md) - Lär dig hur du felsöker en anpassad åtgärd


## Ytterligare resurser

Bläddra i avsnitten nedan om du vill veta mer om hur du konfigurerar, använder och felsöker anpassade åtgärder:

* [Kom igång med anpassade åtgärder](../action/action.md) - Lär dig vad som är en anpassad åtgärd och hur de hjälper dig att ansluta till tredjepartssystem
* [Använd anpassade åtgärder](../building-journeys/using-custom-actions.md) - Lär dig hur du använder anpassade åtgärder på dina resor
* [Felsökning av anpassad åtgärd](../action/troubleshoot-custom-action.md) - Lär dig hur du felsöker en anpassad åtgärd
* [Skicka samlingar till anpassade åtgärdsparametrar](../building-journeys/collections.md) - Lär dig hur du skickar en samling i anpassade åtgärdsparametrar som fylls i dynamiskt vid körning

