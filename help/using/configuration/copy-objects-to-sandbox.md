---
solution: Journey Optimizer
product: journey optimizer
title: Kopiera Journey Optimizer-objekt mellan sandlådor
description: Lär dig hur du kopierar resor, innehållsmallar och fragment mellan sandlådor.
feature: Journeys, Sandboxes
topic: Content Management
role: User, Developer, Data Engineer
level: Experienced
keywords: sandlåda, resa, kopia, miljö
exl-id: 356d56a5-9a90-4eba-9875-c7ba96967da9
source-git-commit: 23cd384354a7b3f6a4c6c35030fbd9275952c0b1
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 0%

---

# Exportera objekt till en annan sandlåda {#copy-to-sandbox}

Du kan kopiera objekt som resor, anpassade åtgärder, innehållsmallar eller fragment över flera sandlådor med hjälp av funktioner för paketexport och -import. Ett paket kan bestå av ett eller flera objekt. Alla objekt som ingår i ett paket måste komma från samma sandlåda.

Den här sidan beskriver hur du använder sandlådeverktyg i Journey Optimizer. Mer information om själva funktionen finns i [Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/sandbox-tooling.html).

>[!NOTE]
>
>Den här funktionen kräver följande behörigheter från funktionen **Sandlådeadministration**: Hantera sandlådor (eller Visa sandlådor) och Hantera paket. [Läs mer](../administration/ootb-permissions.md)

Kopieringsprocessen utförs via en paketexport och import mellan käll- och målsandlådorna. Här är de allmänna stegen för att kopiera en resa från en sandlåda till en annan:

1. Lägg till objektet som ska exporteras som ett paket i källsandlådan.
1. Exportera paketet till målsandlådan.

## Exporterade objekt och bästa praxis {#objects}

Journey Optimizer tillåter export av resor, anpassade åtgärder, innehållsmallar och fragment till en annan sandlåda. I följande avsnitt finns information och metodtips för varje typ av objekt.

### Allmän bästa praxis {#global}

* När du kopierar ett objekt uppdateras alla beroenden (till exempel kapslade fragment, målgrupper för resan eller åtgärder) korrekt i det överordnade objektet, vilket garanterar korrekt mappning i målsandlådan.

* Om ett exporterat objekt innehåller profilanpassning kontrollerar du att det finns ett lämpligt schema i målsandlådan för att undvika eventuella personaliseringsproblem.

### Resor {#journeys}

* När du exporterar en resa kopierar Journey Optimizer, förutom själva resan, även de flesta objekt som resan är beroende av: målgrupper, anpassade åtgärder, scheman, händelser och åtgärder. Mer information om kopierade objekt finns i [avsnittet](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/sandbox-tooling.html#abobe-journey-optimizer-objects).

* Vi garanterar inte att alla länkade element kopieras till målsandlådan. Vi rekommenderar att du gör en grundlig kontroll, till exempel innan du publicerar en resa. På så sätt kan du identifiera eventuella saknade objekt.

* De kopierade objekten i målsandlådan är unika och det finns ingen risk för att befintliga element skrivs över. Både resan och alla meddelanden under resan överförs i utkastläge. På så sätt kan du utföra en grundlig validering innan den publiceras i målsandlådan.

* Kopieringsprocessen kopierar bara metadata om resan och objekten i den resan. Inga profil- eller datauppsättningsdata kopieras som en del av den här processen.

### Anpassade åtgärder {#custom-actions}

* När du exporterar anpassade åtgärder kopieras URL-konfigurationen och nyttolastparametrarna. Av säkerhetsskäl kopieras inte autentiseringsparametrar över och ersätts istället av INSERT SECRET HERE. Parametervärden för en konstant begäran och frågeparametrar ersätts också med INSERT SECRET HERE.

  Detta inkluderar anpassade specialåtgärder ([!DNL Adobe Campaign Standard], [!DNL Campaign Classic], [!DNL Marketo Engage]).

* När du kopierar en resa till en annan sandlåda och väljer &quot;använd befintlig&quot; för en anpassad åtgärd under importprocessen, måste den befintliga anpassade åtgärden du väljer vara densamma som den anpassade källåtgärden (d.v.s. samma konfiguration, parametrar osv.). Annars kommer den nya kopian att innehålla fel som inte kan lösas på arbetsytan.

### Kampanjer {#campaigns}

Kampanjer kopieras tillsammans med alla objekt som hör till profilen, målgruppen, schemat, textbundna meddelanden och beroende objekt. Följande objekt kopieras **inte**:

* Flerspråkiga varianter och språkinställningar.
* Affärsregler,
* Taggar,
* DULE-etiketter (Data Usage Labeling and Enforcement).

När du kopierar kampanjer måste du se till att objektet som listas nedan valideras i målsandlådan för att undvika felkonfigurationer:

* **Kanalkonfigurationer**: Kanalkonfigurationer kopieras tillsammans med kampanjer. När kampanjer har kopierats måste kanalkonfigurationer väljas manuellt i målsandlådan.
* **Experimentationsvarianter och inställningar**: Experimentella varianter och inställningar ingår i kampanjkopieringsprocessen. Validera dessa inställningar i målsandlådan efter importen.
* **Enhetligt beslutsfattande**: Beslutsprinciper och beslutsobjekt stöds för export och import. Kontrollera att beslutsrelaterade beroenden mappas korrekt i målsandlådan.

### Innehållsmallar {#content-templates}

* När du exporterar en innehållsmall kopieras även alla kapslade fragment tillsammans med den.

* När du exporterar innehållsmallar kan det ibland leda till fragmentduplicering. Om till exempel två mallar delar samma fragment och kopieras i separata paket, måste båda mallarna återanvända samma fragment i målsandlådan. Om du vill undvika duplicering väljer du alternativet &quot;Använd befintlig&quot; under importprocessen. [Lär dig hur du importerar ett paket](#import)

* Du bör exportera innehållsmallar i ett och samma paket för att undvika dubbletter. På så sätt kan systemet hantera borttagning av dubbletter effektivt.

### Fragment {#fragments}

* Fragment kan ha flera statusar, till exempel Live, Utkast och Live med pågående utkast. När du exporterar ett fragment kopieras dess senaste utkastläge till målsandlådan.

* När du exporterar ett fragment kopieras även alla kapslade fragment tillsammans med det.

## Lägga till objekt som ett paket{#export}

Om du vill kopiera objekt till en annan sandlåda måste du först lägga till dem som ett paket i källsandlådan. Följ de här stegen:

1. Navigera till lagret där det första objektet som du vill kopiera lagras, till exempel reselistan. Klicka på ikonen **Fler åtgärder** (de tre punkterna bredvid objektnamnet) och klicka på **Lägg till i paket**.

   ![](assets/journey-sandbox1.png)

1. I fönstret **Lägg till i paket** väljer du om du vill lägga till objektet i ett befintligt paket eller skapa ett nytt paket:

   ![](assets/journey-sandbox2.png)

   * **Befintligt paket**: välj paketet i listrutan.
   * **Skapa ett nytt paket**: skriv paketnamnet. Du kan också lägga till en beskrivning.

1. Upprepa de här stegen för att lägga till alla objekt som du vill exportera med paketet.

>[!NOTE]
>
>Vid export av resor kopierar Journey Optimizer även merparten av de objekt som resan är beroende av: målgrupper, scheman, händelser och handlingar. Mer information om reseexport finns i [det här avsnittet](../building-journeys/copy-to-sandbox.md).

## Publicera paketet som ska exporteras {#publish}

Så här publicerar du paketet:

1. Gå till menyn **[!UICONTROL Administration]** > **[!UICONTROL Sandboxes]** och välj fliken **Paket**.

1. Öppna det paket som du vill exportera, markera de objekt som du vill exportera och klicka på **Publicera**.

   I det här exemplet vill vi exportera en resa, en innehållsmall och ett fragment.

   ![](assets/journey-sandbox4.png)

1. Om du vill spåra status för paketets publikation från fliken **[!UICONTROL Jobs]**. Om du vill ha mer information om ett jobb markerar du det i listan och klickar på knappen **[!UICONTROL View import details]**.

   ![](assets/journey-sandbox9.png)

## Importera paketet i målsandlådan {#import}

När paketet har publicerats måste du importera det till målsandlådan. Följ de här stegen:

1. Navigera till menyn **[!UICONTROL Sandboxes]** och välj fliken **[!UICONTROL Browse]**.

1. Sök efter sandlådan där du vill importera paketet och klicka sedan på plusikonen bredvid dess namn.

   ![](assets/journey-sandbox5.png)

   >[!NOTE]
   >
   >Endast sandlådor i din organisation är tillgängliga.

1. I fältet **Målsandlåda** kontrollerar du att rätt målsandlådor är markerad och väljer det paket som ska importeras från listrutan **[!UICONTROL Package name]**. Klicka på **Nästa**.

   ![](assets/journey-sandbox6.png)

1. Granska paketobjekten och beroendena. Det här är listan över objekt som har lagts till i paketet, tillsammans med andra objektresor som är beroende av t.ex. målgrupper, scheman, händelser eller åtgärder.

   För varje objekt kan du välja att skapa ett nytt eller använda ett befintligt objekt i målsandlådan. På så sätt kan du till exempel undvika fragmentduplicering som kan inträffa när du importerar innehållsmallar med vanliga fragment.

   ![](assets/journey-sandbox7.png)

1. Klicka på knappen **Slutför** i det övre högra hörnet för att börja kopiera paketet till målsandlådan. Kopieringsprocessen varierar beroende på hur komplexa objekten är och hur många objekt som behöver kopieras.

1. Klicka på importjobbet för att granska kopieringsresultatet:

   * Klicka på knappen **Visa importerade objekt** om du vill visa varje kopierat objekt.
   * Klicka på knappen **Visa importinformation** för att kontrollera importresultaten för varje objekt.

   ![](assets/journey-sandbox8.png)

1. Få åtkomst till målsandlådan och kontrollera alla kopierade objekt noggrant.
