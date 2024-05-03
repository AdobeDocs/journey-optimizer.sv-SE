---
solution: Journey Optimizer
product: journey optimizer
title: E-postgenerering med AI-assistenten
description: Börja generera e-postinnehåll och resurser med AI-assistenten
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
badge: label="Beta" type="Informative"
hide: true
hidefromtoc: true
exl-id: 1b3930ff-f7b0-43f0-bcf2-5c3de0a88b25
source-git-commit: 6cb05e3356d9e57eca5434ef677ba121e06b0370
workflow-type: tm+mt
source-wordcount: '1265'
ht-degree: 1%

---

# E-postgenerering med AI-assistenten {#generative-email}

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* [Kom igång med AI-assistenten](gs-generative.md)
* **[E-postgenerering med AI-assistenten](generative-email.md)**
* [SMS-generering med AI-assistenten](generative-sms.md)
* [Push-generering med AI Assistant](generative-push.md)
* [Experimentera med AI-assistenten](generative-experimentation.md)

>[!ENDSHADEBOX]

>[!NOTE]
>
>Innan du börjar använda den här funktionen bör du läsa upp relaterade [Gardrutor och begränsningar](gs-generative.md#generative-guardrails).

När du har skapat och anpassat dina e-postmeddelanden kan du utnyttja kraften i AI Assistant i Journey Optimizer, som drivs av generativ AI, för att lyfta fram ditt innehåll.

Använd AI Assistant för att effektivisera era kampanjer genom att skapa kompletta e-postmeddelanden, skräddarsydda textutdrag och anpassade bilder som talar direkt till er målgrupp, vilket ökar engagemanget och interaktionen.

Gå igenom flikarna nedan och lär dig hur du använder AI Assistant i Journey Optimizer.

>[!BEGINTABS]

>[!TAB Fullständig e-postgenerering]

I följande exempel använder vi AI-assistenten för att förfina en befintlig e-postmall.

1. När du har skapat och konfigurerat din e-postkampanj klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din e-postkampanj finns i [den här sidan](../campaigns/create-campaign.md).

1. Anpassa din e-post efter behov och få tillgång till **[!UICONTROL AI Assistant]** -menyn.

   ![](assets/full-email-1.png){zoomable=&quot;yes&quot;}

1. Aktivera **[!UICONTROL Use original content]** för AI-assistenten att anpassa nytt innehåll baserat på kampanjinnehåll, namn och vald målgrupp.

   Din fråga måste alltid vara knuten till ditt aktuella innehåll.

1. Finjustera innehållet genom att beskriva vad du vill generera i **[!UICONTROL Prompt]** fält.

   Om du behöver hjälp med att skapa din fråga kan du gå till **[!UICONTROL Prompt Library]** som ger ett brett urval av snabba idéer för att förbättra era kampanjer.

   ![](assets/full-email-2.png){zoomable=&quot;yes&quot;}

1. Du kan växla **[!UICONTROL Subject line]** och **[!UICONTROL Preheader]** för att inkludera dem i variantgenereringen.

1. Klicka **[!UICONTROL Upload brand asset]** om du vill lägga till en varumärkesresurs som innehåller innehåll som kan ge ytterligare kontext i AI-assistenten eller välja en som har överförts tidigare.

   ![](assets/full-email-3.png){zoomable=&quot;yes&quot;}

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Communication strategy]**: Välj det format som passar bäst för den genererade texten.
   * **[!UICONTROL Language]**: Välj vilket språk du vill att innehållet ska skapas på.
   * **[!UICONTROL Tone]**: Tonen i e-postmeddelandet bör få genklang hos er målgrupp. Vare sig du vill låta informativ, lekfull eller övertygande kan AI-assistenten anpassa meddelandet därefter.

   ![](assets/full-email-4.png){zoomable=&quot;yes&quot;}

1. När frågan är klar klickar du på **[!UICONTROL Generate]**.

1. Bläddra bland de genererade **[!UICONTROL Variations]** och klicka **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den valda varianten.

1. Navigera till **[!UICONTROL Refine]** i **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner:

   * **[!UICONTROL Rephrase]**: AI-assistenten kan omformulera sitt budskap på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **[!UICONTROL Use simpler language]**: Utnyttja AI-assistenten för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   ![](assets/full-email-5.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Select]** när du hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. Infoga anpassningsfält för att anpassa ditt e-postinnehåll baserat på profildata. Klicka sedan på **[!UICONTROL Simulate content]** för att styra återgivningen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../personalization/personalize.md)

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er e-postkampanj. [Läs mer](../campaigns/review-activate-campaign.md)

>[!TAB Textgenerering]

I följande exempel använder vi AI-assistenten för att förbättra innehållet i vårt e-postmeddelande.

1. När du har skapat och konfigurerat din e-postkampanj klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din e-postkampanj finns i [den här sidan](../email/create-email.md).

1. Välj en **[!UICONTROL Text component]** för att endast rikta in sig på ett visst innehåll. och få tillgång till **[!UICONTROL AI Assistant]** -menyn.

   ![](assets/text-genai-1.png){zoomable=&quot;yes&quot;}

1. Aktivera **[!UICONTROL Use original content]** för AI-assistenten att anpassa nytt innehåll baserat på kampanjinnehåll, namn och vald målgrupp.

   Din fråga måste alltid vara knuten till ditt aktuella innehåll.

1. Finjustera innehållet genom att beskriva vad du vill generera i **[!UICONTROL Prompt]** fält.

   Om du behöver hjälp med att skapa din fråga kan du gå till **[!UICONTROL Prompt Library]** som ger ett brett urval av snabba idéer för att förbättra era kampanjer.

   ![](assets/text-genai-2.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Upload brand asset]** om du vill lägga till alla varumärkesresurser som innehåller innehåll som kan ge ytterligare kontext i AI-assistenten.

   ![](assets/text-genai-3.png){zoomable=&quot;yes&quot;}

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Communication strategy]**: Välj önskat kommunikationssätt för den genererade texten.
   * **[!UICONTROL Language]**: Välj språk för variantens innehåll.
   * **[!UICONTROL Tone]**: Se till att texten är lämplig för din målgrupp och ditt syfte.
   * **[!UICONTROL Length]**: Välj längden på innehållet med intervallreglaget.

   ![](assets/text-genai-4.png){zoomable=&quot;yes&quot;}

1. När frågan är klar klickar du på **[!UICONTROL Generate]**.

1. Bläddra bland de genererade **[!UICONTROL Variations]** och klicka **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den valda varianten.

1. Navigera till **[!UICONTROL Refine]** i **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner:

   * **[!UICONTROL Use as reference content]**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **[!UICONTROL Elaborate]**: AI-assistenten kan hjälpa er att utöka kring specifika ämnen, med ytterligare information för bättre förståelse och engagemang.

   * **[!UICONTROL Summarize]**: Lång information kan överlagra e-postmottagare. Använd AI Assistant för att dra ihop viktiga punkter till tydliga, kortfattade sammanfattningar som får dem att läsa mer.

   * **[!UICONTROL Rephrase]**:AI-assistenten kan omformulera sitt budskap på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **[!UICONTROL Use simpler language]**: Utnyttja AI-assistenten för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   ![](assets/text-genai-5.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Select]** när du hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. Infoga anpassningsfält för att anpassa ditt e-postinnehåll baserat på profildata. Klicka sedan på **[!UICONTROL Simulate content]** för att styra återgivningen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../personalization/personalize.md)

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er e-postkampanj. [Läs mer](../campaigns/review-activate-campaign.md)

>[!TAB Bildgenerering]

I exemplet nedan kan du lära dig hur du använder AI Assistant för att optimera och förbättra dina resurser, vilket ger en mer användarvänlig upplevelse.

1. När du har skapat och konfigurerat din e-postkampanj klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din e-postkampanj finns i [den här sidan](../email/create-email.md).

1. Fyll i **[!UICONTROL Basic details]** för er kampanj. När du är klar klickar du **[!UICONTROL Edit email content]**.

1. Markera den resurs som du vill ändra med AI-assistenten.

1. Välj **[!UICONTROL AI Assistant]**.

   ![](assets/image-genai-1.png){zoomable=&quot;yes&quot;}

1. Aktivera **[!UICONTROL Reference style]** för AI-assistenten att anpassa nytt innehåll baserat på referensinnehållet. Du kan också överföra en bild för att lägga till kontext till variationen.

   Din fråga måste alltid vara knuten till ditt aktuella innehåll.

1. Finjustera innehållet genom att beskriva vad du vill generera i **[!UICONTROL Prompt]** fält.

   Om du behöver hjälp med att skapa din fråga kan du gå till **[!UICONTROL Prompt Library]** som ger ett brett urval av snabba idéer för att förbättra era kampanjer.

   ![](assets/image-genai-2.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Upload brand asset]** om du vill lägga till alla varumärkesresurser som innehåller innehåll som kan ge ytterligare kontext i AI-assistenten.

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Aspect ratio]**: Detta avgör objektets bredd och höjd. Du kan välja mellan vanliga proportioner som 16:9, 4:3, 3:2 eller 1:1, eller ange en anpassad storlek.
   * **[!UICONTROL Color & tone]**: Det övergripande utseendet på färgerna i en bild och stämningen eller atmosfären som bilden förmedlar.
   * **[!UICONTROL Content type]**: Detta kategoriserar det visuella elementets karaktär och skiljer mellan olika former av visuell representation, t.ex. foton, grafik eller grafik.
   * **[!UICONTROL Lighting]**: Detta avser blixten i en bild som formar atmosfären och markerar specifika element.
   * **[!UICONTROL Composition]**: Detta avser elementens placering i en bilds bildruta

   ![](assets/image-genai-4.png){zoomable=&quot;yes&quot;}

1. När du är nöjd med promptkonfigurationen klickar du på **[!UICONTROL Generate]**.

1. Sök i **[!UICONTROL Variation suggestions]** för att hitta den önskade resursen.

   Klicka **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den valda varianten.

   ![](assets/image-genai-5.png){zoomable=&quot;yes&quot;}

1. Välj **[!UICONTROL Show Similar]** om du vill visa relaterade bilder till den här varianten.

   ![](assets/image-genai-6.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Select]** när du hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. När du har definierat meddelandeinnehållet klickar du på **[!UICONTROL Simulate content]** för att styra återgivningen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../personalization/personalize.md)

1. När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er e-postkampanj. [Läs mer](../campaigns/review-activate-campaign.md)

>[!ENDTABS]

## Instruktionsvideo {#video}

Lär dig hur du använder AI-assistenten för att generera fullständig e-post, text eller bilder.

>[!VIDEO](https://video.tv.adobe.com/v/3428341)
