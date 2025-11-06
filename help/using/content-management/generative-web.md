---
solution: Journey Optimizer
product: journey optimizer
title: Skapa webbsidor med AI Assistant
description: Börja generera webbsidesinnehåll och -resurser med AI Assistant i Journey Optimizer.
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
exl-id: ebe2df77-4aaa-45b1-a8ce-931d4191cc67
source-git-commit: 50933d991c6a337e6d1739652d680778759ef0d5
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 1%

---

# Skapa webbsidor med AI Assistant {#generative-web}

>[!IMPORTANT]
>
>Innan du börjar använda den här funktionen bör du läsa upp relaterade [säkerhetsutkast och begränsningar](gs-generative.md#generative-guardrails).
></br>
>
>Du måste godkänna ett [användaravtal](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html) innan du kan använda AI Assistant i Journey Optimizer. Kontakta din Adobe-representant om du vill veta mer.

När du har skapat och personaliserat dina webbsidor kan du använda AI Assistant i Journey Optimizer med generativ AI för att ta ditt innehåll till nästa nivå.

AI Assistant i Journey Optimizer kan hjälpa er att optimera effekten av era leveranser genom att föreslå olika typer av innehåll som troligtvis får genklang hos er målgrupp.

>[!BEGINTABS]

>[!TAB Skapa webbsidestext]

1. När du har skapat och konfigurerat webbsidan klickar du på **[!UICONTROL Edit web page]**.

   Mer information om hur du konfigurerar webbsidan finns på [den här sidan](../web/create-web.md).

1. Välj en **[!UICONTROL Text component]** om du bara vill ha ett specifikt innehåll som mål. och gå till menyn **[!UICONTROL Show AI Assistant]**.

   ![](assets/web-gen-full-1.png){zoomable="yes"}

1. Aktivera alternativet **[!UICONTROL Use original content]** för AI Assistant för att anpassa nytt innehåll baserat på det valda innehållet.

1. Välj din **[!UICONTROL Brand]** för att se till att det AI-genererade innehållet följer varumärkesspecifikationerna. [Läs mer](brands.md) om varumärken.

   Observera att funktionen Varumärke släpps som en privat betaversion och kommer att finnas tillgänglig för alla kunder i framtida versioner.

1. Finjustera innehållet genom att beskriva vad du vill generera i fältet **[!UICONTROL Prompt]**.

   Om du vill ha hjälp med att skapa din fråga kan du få tillgång till **[!UICONTROL Prompt Library]**, som innehåller en mängd olika tips för att förbättra dina kampanjer.

   ![](assets/web-gen-full-2.png){zoomable="yes"}

1. Skräddarsy din fråga med alternativet **[!UICONTROL Text settings]**:

   * **[!UICONTROL Communication strategy]**: Välj den lämpligaste kommunikationsstilen för den genererade texten.
   * **[!UICONTROL Languages]**: Välj språk för det genererade innehållet.
   * **[!UICONTROL Tone]**: Din webbsidas ton ska tolkas som målgruppen. Vare sig du vill låta informativ, lekfull eller övertygande kan AI Assistant anpassa budskapet därefter.
   * **Textlängd**: Använd reglaget för att välja önskad längd på texten.

   ![](assets/web-gen-full-3.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Brand assets]** på menyn **[!UICONTROL Upload brand asset]** om du vill lägga till en varumärkesresurs som innehåller innehåll som kan ge ytterligare kontext-AI Assistant eller välja en tidigare överförd.

   Tidigare överförda filer är tillgängliga i listrutan **[!UICONTROL Uploaded brand assets]**. Du behöver bara växla mellan de resurser du vill ha med i din generation.

1. Klicka på **[!UICONTROL Generate]** när din fråga är klar.

1. Bläddra igenom den genererade **[!UICONTROL Variations]**.

   Klicka på **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den markerade varianten eller klicka på **[!UICONTROL Apply]** om du vill ersätta det aktuella innehållet.

1. Klicka på procentikonen för att visa din **[!UICONTROL Brand Alignment Score]** och identifiera eventuella feljusteringar av ditt varumärke.

   Läs mer om [varumärkesjusteringspoäng](brands-score.md).

   ![](assets/web-gen-full-4.png){zoomable="yes"}

1. Navigera till alternativet **[!UICONTROL Refine]** i fönstret **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner:

   * **[!UICONTROL Use as reference content]**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **[!UICONTROL Elaborate]**: AI-assistenten kan hjälpa dig att expandera specifika ämnen och ge ytterligare information för bättre förståelse och engagemang.

   * **[!UICONTROL Summarize]**: Långvarig information kan överlagra mottagare. Använd AI Assistant för att komprimera viktiga punkter till tydliga, kortfattade sammanfattningar som får dem att lyssna och uppmuntrar dem att läsa vidare.

   * **[!UICONTROL Rephrase]**:TheAI Assistant kan omformulera ditt meddelande på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **[!UICONTROL Use simpler language]**: Använd AI Assistant för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   Du kan också ändra **[!UICONTROL Tone]** och **[!UICONTROL Communication strategy]** för texten.

   ![](assets/web-gen-full-5.png){zoomable="yes"}

1. Öppna fliken **[!UICONTROL Brand Alignment]** och se hur ditt innehåll överensstämmer med [varumärkesriktlinjerna](brands.md).

1. Klicka på **[!UICONTROL Select]** när du har hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

När du har definierat inställningarna för webbkampanjen och redigerat innehållet som du vill med webbdesignern kan du granska och aktivera webbkampanjen. [Läs mer](../web/create-web.md#activate-web-campaign)

>[!TAB Skapa webbsidesbilder]

I exemplet nedan kan du lära dig hur du använder AI Assistant i Journey Optimizer för att optimera och förbättra dina resurser, vilket ger en mer användarvänlig upplevelse.

1. När du har skapat och konfigurerat webbsidan klickar du på **[!UICONTROL Edit web page]**.

   Mer information om hur du konfigurerar webbsidan finns på [den här sidan](../web/create-web.md).

1. Markera den resurs som du vill ändra med AI Assistant.

1. Välj **[!UICONTROL Show AI Assistant]** på den högra menyn.

   ![](assets/web-gen-img-1.png){zoomable="yes"}

1. Aktivera alternativet **[!UICONTROL Reference style]** för AI Assistant för att anpassa nytt innehåll baserat på referensinnehållet. Du kan också överföra en bild för att lägga till kontext till variationen.

1. Välj din **[!UICONTROL Brand]** för att se till att det AI-genererade innehållet följer varumärkesspecifikationerna. [Läs mer](brands.md) om varumärken.

   Observera att funktionen Varumärke släpps som en privat betaversion och kommer att finnas tillgänglig för alla kunder i framtida versioner.

1. Finjustera innehållet genom att beskriva vad du vill generera i fältet **[!UICONTROL Prompt]**.

   Om du vill ha hjälp med att skapa din fråga kan du få tillgång till **[!UICONTROL Prompt Library]**, som innehåller en mängd olika tips för att förbättra dina kampanjer.

   ![](assets/web-gen-img-2.png){zoomable="yes"}

1. Skräddarsy din fråga med alternativet **[!UICONTROL Image settings]**:

   * **[!UICONTROL Aspect ratio]**: Detta avgör resursens bredd och höjd. Du kan välja bland vanliga proportioner som 16:9, 4:3, 3:2 eller 1:1, eller så kan du ange en anpassad storlek.
   * **[!UICONTROL Content type]**: Detta kategoriserar det visuella elementets karaktär och skiljer mellan olika former av visuell representation, t.ex. foton, grafik eller grafik.
   * **[!UICONTROL Visual intensity]**: Du kan styra bildens effekt genom att justera dess intensitet. En lägre inställning (2) ger ett mjukare och mer återhållsam utseende, medan en högre inställning (10) gör bilden mer levande och visuellt kraftfull.
   * **[!UICONTROL Color & tone]**: Det övergripande utseendet på färgerna i en bild och stämningen eller atmosfären som den förmedlar.
   * **[!UICONTROL Lighting]**: Det här refererar till blixten i en bild, som formar atmosfären och markerar specifika element.
   * **[!UICONTROL Composition]**: Det här refererar till elementens placering i en bilds bildruta

   ![](assets/web-gen-img-3.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Brand assets]** på menyn **[!UICONTROL Upload brand asset]** om du vill lägga till en varumärkesresurs som innehåller innehåll som kan ge ytterligare kontext-AI Assistant eller välja en tidigare överförd.

   Tidigare överförda filer är tillgängliga i listrutan **[!UICONTROL Uploaded brand assets]**. Du behöver bara växla mellan de resurser du vill ha med i din generation.

1. När du är nöjd med promptkonfigurationen klickar du på **[!UICONTROL Generate]**.

1. Bläddra igenom den genererade **[!UICONTROL Variations]**.

   Klicka på **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den markerade varianten eller klicka på **[!UICONTROL Apply]** om du vill ersätta det aktuella innehållet.

1. Klicka på procentikonen för att visa din **[!UICONTROL Brand Alignment Score]** och identifiera eventuella feljusteringar av ditt varumärke.

   Läs mer om [varumärkesjusteringspoäng](brands-score.md).

   ![](assets/web-gen-img-4.png){zoomable="yes"}

1. Navigera till alternativet **[!UICONTROL Refine]** i fönstret **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner:

   * **[!UICONTROL Generate Similar]** om du vill visa relaterade bilder till den här varianten.
   * **[!UICONTROL Edit in Adobe Express]** om du vill anpassa resursen ytterligare.

[Läs mer om Adobe Express-integrering](../integrations/express.md)

   * **[!UICONTROL Save]** om du vill lagra resurserna för senare åtkomst.

   ![](assets/web-gen-img-5.png){zoomable="yes"}

1. Öppna fliken **[!UICONTROL Brand Alignment]** och se hur ditt innehåll överensstämmer med [varumärkesriktlinjerna](brands.md).

1. Klicka på **[!UICONTROL Select]** när du har hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

När du har definierat inställningarna för webbkampanjen och redigerat innehållet som du vill med webbdesignern kan du granska och aktivera webbkampanjen. [Läs mer](../web/create-web.md#activate-web-campaign)

>[!ENDTABS]
