---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera e-postinställningar
description: Lär dig hur du konfigurerar e-postinställningar på kanalytnivå
feature: Surface
topic: Administration
role: Admin
level: Intermediate
keywords: inställningar, e-post, konfiguration
exl-id: 13536962-7541-4eb6-9ccb-4f97e167734a
source-git-commit: 9555c37f8bac295a668f64990e229c6e0e5ceb8d
workflow-type: tm+mt
source-wordcount: '1436'
ht-degree: 1%

---

# Konfigurera e-postinställningar {#email-settings}

Om du vill börja skapa ett e-postmeddelande måste du skapa e-postkanalsytor som definierar alla tekniska parametrar som krävs för dina meddelanden. [Lär dig hur du skapar ytor](../configuration/channel-surfaces.md)

Definiera e-postinställningarna i det dedikerade avsnittet i kanalytans konfiguration.

![](assets/preset-email-settings.png)

E-postytans konfiguration hämtas för att skicka kommunikation enligt logiken nedan:

* För batch- och burst-resor gäller det inte batch- eller burst-körning som redan hade startats innan e-postytans konfiguration gjordes. Ändringarna hämtas vid nästa upprepning eller vid nästa körning.

* För transaktionsmeddelanden hämtas ändringen omedelbart för nästa kommunikation (upp till fem minuters fördröjning).

>[!NOTE]
>
>De uppdaterade inställningarna för e-postyta hämtas automatiskt under den eller de resor eller kampanjer där ytan används.

## Typ av e-post {#email-type}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_emailtype"
>title="Definiera e-postkategorin"
>abstract="Välj den typ av e-postmeddelanden som ska skickas när du använder den här ytan: Marknadsföring för e-postreklam, som kräver användargodkännande, eller Transactional för icke-kommersiella e-postmeddelanden, som också kan skickas till profiler som inte längre prenumererar i specifika sammanhang."

I **E-POSTTYP** väljer du den typ av meddelande som ska skickas med ytan: **Marknadsföring** eller **Transactional**.

* Välj **Marknadsföring** för e-postreklam: dessa meddelanden kräver användarens samtycke.

* Välj **Transactional** för icke-kommersiell e-post, t.ex. orderbekräftelse, meddelanden om lösenordsåterställning eller leveransinformation.

>[!CAUTION]
>
>**Transactional** e-postmeddelanden kan skickas till profiler som avbeställer marknadskommunikation. Dessa meddelanden kan bara skickas i särskilda sammanhang.

När du skapar ett meddelande måste du välja en giltig kanalyta som matchar den kategori du valde för e-postmeddelandet.

## Underdomän- och IP-pooler {#subdomains-and-ip-pools}

I **Underdomän- och IP-pooler** måste du

1. Välj den underdomän som ska användas för att skicka e-postmeddelanden. [Läs mer](../configuration/about-subdomain-delegation.md)

1. Välj den IP-pool som ska associeras med ytan. [Läs mer](../configuration/ip-pools.md)

![](assets/preset-subdomain-ip-pool.png)

Du kan inte fortsätta skapa en yta medan den valda IP-poolen är under [utgåva](../configuration/ip-pools.md#edit-ip-pool) (**[!UICONTROL Processing]** status) och har aldrig kopplats till den valda underdomänen. Annars kommer den äldsta versionen av associationen för IP-poolen/underdomänen fortfarande att användas. I så fall sparar du ytan som utkast och försöker igen när IP-poolen har **[!UICONTROL Success]** status.

>[!NOTE]
>
>I icke-produktionsmiljöer skapar inte Adobe körklara testunderdomäner och ger inte heller åtkomst till en delad sändande IP-pool. Du måste [delegera dina egna underdomäner](../configuration/delegate-subdomain.md) och använd IP-adresserna från poolen som tilldelats din organisation.

När en IP-pool har valts visas PTR-information när du hovrar över IP-adresserna som visas under listrutan IP-pool. [Läs mer om PTR-poster](../configuration/ptr-records.md)

![](assets/email-surface-ptr-record.png)

>[!NOTE]
>
>Om en PTR-post inte är konfigurerad kan du kontakta din Adobe-representant.

## List-Unsubscribe {#list-unsubscribe}

Vid [välja en underdomän](#subdomains-and-ip-pools) från listan, **[!UICONTROL Enable List-Unsubscribe]** visas.

![](assets/preset-list-unsubscribe.png)

Det här alternativet är aktiverat som standard.

Om du låter det vara aktiverat inkluderas en länk för att avbryta prenumerationen automatiskt i e-posthuvudet, till exempel:

![](assets/preset-list-unsubscribe-header.png)

Om du inaktiverar det här alternativet visas ingen länk för att avbryta prenumerationen i e-posthuvudet.

Länken för att avbryta prenumerationen består av två element:

* An **avbeställ e-postadress** som alla avbeställningar skickas till.

   I [!DNL Journey Optimizer], är e-postadressen för avanmälan standard **[!UICONTROL Mailto (unsubscribe)]** som visas i kanalytan, baserat på [vald underdomän](#subdomains-and-ip-pools).

   ![](assets/preset-list-unsubscribe-mailto.png)

* The **avbeställ URL**, vilket är URL:en till landningssidan där användaren omdirigeras när prenumerationen har upphört.

   Om du lägger till en [länk för avanmälan med ett klick](../privacy/opt-out.md#one-click-opt-out) för ett meddelande som skapas med den här ytan är avanmälnings-URL:en den URL som definierats för länken med ett klick.

   ![](assets/preset-list-unsubscribe-opt-out-url.png)

   >[!NOTE]
   >
   >Om du inte lägger till en länk för avanmälan med ett enda klick i meddelandeinnehållet visas ingen landningssida för användaren.

Läs mer om hur du lägger till en länk för att avbryta prenumerationen i dina meddelanden i [det här avsnittet](../privacy/opt-out.md#unsubscribe-header).

<!--Select the **[!UICONTROL Custom List-Unsubscribe]** option to enter your own Unsubscribe URL and/or your own Unsubscribe email address.(to add later)-->

## Huvudparametrar {#email-header}

I **[!UICONTROL Header parameters]** anger du avsändarens namn och e-postadresser som är kopplade till den typ av e-post som skickas med den aktuella ytan.

* **[!UICONTROL Sender name]**: Avsändarens namn, till exempel ditt varumärkes namn.

* **[!UICONTROL Sender email]**: E-postadressen som du vill använda för din kommunikation.

* **[!UICONTROL Reply to (name)]**: Namnet som ska användas när mottagaren klickar på **Svara** i klientprogramvaran för e-post.

* **[!UICONTROL Reply to (email)]**: E-postadressen som ska användas när mottagaren klickar på **Svara** i klientprogramvaran för e-post. [Läs mer](#reply-to-email)

* **[!UICONTROL Error email]**: Alla fel som genereras av Internet-leverantörer efter några dagar efter att e-post har levererats (asynkrona studsar) tas emot på den här adressen.

>[!CAUTION]
>
>The **[!UICONTROL Sender email]** och **[!UICONTROL Error email]** adresser måste använda de aktuella markerade [delegerad underdomän](../configuration/about-subdomain-delegation.md). Om den delegerade underdomänen till exempel är *marketing.luma.com* kan du använda *contact@marketing.luma.com* och *error@marketing.luma.com*.

![](assets/preset-header.png)

>[!NOTE]
>
>Adresser måste börja med en bokstav (A-Z) och får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

### Svara på e-post {#reply-to-email}

När du definierar **[!UICONTROL Reply to (email)]** kan du ange vilken e-postadress som helst, förutsatt att det är en giltig adress, i korrekt format och utan att du behöver skriva någon.

Följ nedanstående rekommendationer för att säkerställa korrekt svarshantering:

* Den inkorg som används för svar kommer att få alla svar i e-postmeddelanden, inklusive meddelanden utanför kontoret och svar på frågor, och på så sätt se till att du har en manuell eller automatiserad process för att bearbeta de e-postmeddelanden som landar i den här inkorgen.

* Se till att den dedikerade inkorgen har tillräcklig mottagningskapacitet för att kunna ta emot alla svar som skickas via e-post med e-postytan. Om inkorgen returnerar studsar kanske vissa svar från dina kunder inte tas emot.

* Svar måste behandlas med hänsyn till sekretess och efterlevnadsskyldigheter eftersom de kan innehålla personligt identifierbar information.

* Markera inte meddelanden som skräppost i svarsinkorgen eftersom det påverkar alla andra svar som skickas till den här adressen.

### Vidarebefordra e-post {#forward-email}

Om du vill vidarebefordra till en viss e-postadress får du alla e-postmeddelanden som [!DNL Journey Optimizer] för den delegerade underdomänen, kontakta Adobe kundtjänst. Du måste ange:

* Den e-postadress som du väljer. Observera att domänen för e-postadressen för vidarebefordran inte kan matcha någon underdomän som har delegerats till Adobe.
* Namn på din sandlåda.
* Ytnamnet som e-postadressen ska användas för.
* Aktuell **[!UICONTROL Reply to (email)]** som anges på kanalens ytnivå.

>[!NOTE]
>
>Det får bara finnas en e-postadress per underdomän. Om flera ytor använder samma underdomän måste därför samma e-postadress för alla ytor användas.

E-postadressen för vidarebefordran kommer att konfigureras av Adobe. Detta kan ta 3 till 4 dagar.

## BCC-e-post {#bcc-email}

Du kan skicka en identisk kopia (eller en kopia med kopia) av e-postmeddelanden som skickas av [!DNL Journey Optimizer] till en inkorg för kontroll av webbläsarkompatibilitet där de lagras för att uppfylla regelkrav eller arkiveras.

Aktivera **[!UICONTROL BCC email]** valfri funktion på kanalytnivå. [Läs mer](../configuration/archiving-support.md#bcc-email)

![](assets/preset-bcc.png)

## Parametrar för återförsök av e-post {#email-retry}

>[!CONTEXTUALHELP]
>id="ajo_admin_presets_retryperiod"
>title="Justera tidsperioden för återförsök"
>abstract="Försök utförs i 3,5 dagar (84 timmar) när en e-postleverans misslyckas på grund av ett tillfälligt fel med mjuk avhoppning. Du kan justera den här standardperioden för återförsök så att den passar dina behov bättre."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/monitor-reputation/retries.html" text="Om återförsök"

Du kan konfigurera **Parametrar för återförsök av e-post**.

![](assets/preset-retry-parameters.png)

Som standard är [återförsökstid](../configuration/retries.md#retry-duration) är inställt på 84 timmar, men du kan justera den här inställningen så att den passar dina behov bättre.

Du måste ange ett heltalsvärde (i timmar eller minuter) inom följande intervall:

* För marknadsföringsmeddelanden är den minsta återförsöksperioden 6 timmar.
* För transaktionsmeddelanden är den minsta återförsöksperioden 10 minuter.
* För båda e-posttyperna är den maximala återförsöksperioden 84 timmar (eller 5 040 minuter).

Läs mer om återförsök i [det här avsnittet](../configuration/retries.md).

## URL-spårning {#url-tracking}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_utm"
>title="Definiera parametrar för URL-spårning"
>abstract="Använd det här avsnittet om du automatiskt vill lägga till spårningsparametrar till de URL:er som finns i ditt e-postinnehåll. Den här funktionen är valfri.  "

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_url_preview"
>title="Förhandsgranska parametrar för URL-spårning"
>abstract="Granska hur spårningsparametrar läggs till i de URL:er som finns i ditt e-postinnehåll."

Du kan använda **[!UICONTROL URL tracking parameters]** för att mäta effektiviteten i era marknadsföringssatsningar över olika kanaler. Den här funktionen är valfri.  

Parametrarna som definieras i det här avsnittet läggs till i slutet av de URL:er som ingår i e-postmeddelandeinnehållet. Du kan sedan hämta parametrarna i webbanalysverktyg som Adobe Analytics eller Google Analytics och skapa olika resultatrapporter.

<!--Three URL tracking parameters are auto-populated as an example when you create a channel surface. You can edit these and add up to 10 tracking parameters using the **[!UICONTROL Add new parameter]** button.-->

Du kan lägga till upp till 10 spårningsparametrar med **[!UICONTROL Add new parameter]** -knappen.

![](assets/preset-url-tracking.png)

Om du vill konfigurera en URL-spårningsparameter kan du ange önskade värden direkt i dialogrutan **[!UICONTROL Name]** och **[!UICONTROL Value]** fält.

<!--You can also choose from a list of predefined values by navigating to the following objects:
* Journey attributes: **Source id**, **Source name**, **Source version id**
* Action attributes: **Action id**, **Action name**
* Offer decisioning attributes: **Offer id**, **Offer name**

![](assets/preset-url-tracking-source.png)

>[!CAUTION]
>
>Do not select a folder: make sure to browse to the necessary folder and select a profile attribute to use as a tracking parameter value.-->

Du kan också redigera varje **[!UICONTROL Value]** fält med [Uttrycksredigeraren](../personalization/personalization-build-expressions.md). Klicka på utgåveikonen för att öppna redigeraren. Därifrån kan du välja vilka kontextattribut du vill använda och/eller redigera texten direkt.

![](assets/preset-url-tracking-editor.png)

>[!NOTE]
>
>Du kan kombinera textvärden och använda sammanhangsberoende attribut från uttrycksredigeraren. Varje **[!UICONTROL Value]** fält kan innehålla upp till 255 tecken totalt.

<!--You can drag and drop the parameters to reorder them.-->

Nedan finns exempel på Adobe Analytics- och Google Analytics-kompatibla URL:er.

* Adobe Analytics-kompatibel URL: `www.YourLandingURL.com?cid=email_AJO_{{context.system.source.id}}_image_{{context.system.source.name}}`

* Google Analytics-kompatibel URL: `www.YourLandingURL.com?utm_medium=email&utm_source=AJO&utm_campaign={{context.system.source.id}}&utm_content=image`

Du kan dynamiskt förhandsgranska den resulterande spårnings-URL:en. Varje gång du lägger till, redigerar eller tar bort en parameter uppdateras förhandsvisningen automatiskt.

![](assets/preset-url-tracking-preview.png)