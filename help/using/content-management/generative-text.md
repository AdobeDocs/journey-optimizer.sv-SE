---
solution: Journey Optimizer
product: journey optimizer
title: Generera text med AI Assistant
description: Lär dig hur du skapar textinnehåll med AI Assistant i Journey Optimizer.
feature: Content Assistant
topic: Content Management, Artificial Intelligence
role: User
level: Beginner
source-git-commit: 619db0a371b96fbe9480300a874839b7b919268d
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 2%

---

# Generera text med AI Assistant {#generative-text}

>[!IMPORTANT]
>
>Innan du börjar använda den här funktionen bör du läsa upp relaterade [säkerhetsutkast och begränsningar](gs-generative.md#generative-guardrails).
></br>
>
>Du måste godkänna ett [användaravtal](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html) innan du kan använda AI Assistant i Journey Optimizer. Kontakta din Adobe-representant om du vill veta mer.

Använd AI Assistant i Journey Optimizer för att generera engagerande textmaterial som får genklang hos er målgrupp. Vare sig du vill förbättra e-postkopieringen, skapa övertygande webbinnehåll, skapa övertygande text på landningssidor, skriva push-meddelanden eller skriva SMS-meddelanden kan AI Assistant hjälpa dig att leverera slagkraftig text.

## För e-post- och webbkanaler {#email-web-channels}

AI Assistant kan generera högklassigt textinnehåll för e-postkampanjer, webbupplevelser och landningssidor. Med den här funktionen kan ni skapa övertygande varumärkesanpassade meddelanden som kan kommunicera med er målgrupp över olika digitala kontaktytor.

### Åtkomst och konfiguration {#access-configure}

Innan du kan börja generera textinnehåll med AI Assistant måste du konfigurera kampanjen eller resan och få tillgång till innehållsredigeraren. Följ de här stegen för att förbereda arbetsytan och öppna AI-assistentpanelen.

1. Skapa och konfigurera kampanj eller resa:

   * **E-post**: När du har skapat och konfigurerat din e-postkampanj klickar du på **[!UICONTROL Edit content]**. [Läs mer](../email/create-email.md)
   * **Webb**: När du har skapat och konfigurerat webbsidan klickar du på **[!UICONTROL Edit web page]**. [Läs mer](../web/create-web.md)
   * **Landningssida**: När du har skapat och konfigurerat landningssidan klickar du på **[!UICONTROL Open designer]**. [Läs mer](../landing-pages/create-lp.md)

1. Välj en **[!UICONTROL Text component]** om du bara vill ange ett specifikt innehåll som mål och få tillgång till **[!UICONTROL AI Assistant]**-menyn (eller **[!UICONTROL Show AI Assistant]** för webben).

   ![Textkomponent markerad med AI Assistant-menyn öppen](assets/text-genai-1.png){zoomable="yes"}

### Generera innehåll {#generate-content}

Lär dig skapa tydliga uppmaningar, finjustera inställningarna och generera skräddarsydd text med hjälp av AI Assistant, och se till att era meddelanden passar ert varumärke och era kommunikationsmål.

1. Aktivera alternativet **[!UICONTROL Use original content]** för AI Assistant för att anpassa nytt innehåll baserat på det valda innehållet.

1. Välj din **[!UICONTROL Brand]** för att se till att det AI-genererade innehållet följer varumärkesspecifikationerna. [Läs mer](brands.md) om varumärken.

1. Finjustera innehållet genom att beskriva vad du vill generera i fältet **[!UICONTROL Prompt]**.

   Om du vill ha hjälp med att skapa din fråga kan du få tillgång till **[!UICONTROL Prompt Library]**, som innehåller en mängd olika tips för att förbättra dina kampanjer.

   ![Textgenereringspanelen i AI Assistant med fältet Fråga och varumärkesväljaren](assets/text-genai-2.png){zoomable="yes"}

1. Skräddarsy din fråga med alternativet **[!UICONTROL Text settings]**:

   * **[!UICONTROL Communication strategy]**: Välj den lämpligaste kommunikationsstilen för den genererade texten.
   * **[!UICONTROL Languages]**: Välj språk för det genererade innehållet.
   * **[!UICONTROL Tone]**: Tonen bör återges med din målgrupp. Vare sig du vill låta informativ, lekfull eller övertygande kan AI Assistant anpassa budskapet därefter.
   * **Textlängd**: Använd reglaget för att välja önskad längd på texten.

   ![Textinställningar utökade med visningsalternativ](assets/text-genai-4.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Brand assets]** på menyn **[!UICONTROL Upload brand asset]** om du vill lägga till en varumärkesresurs som innehåller innehåll som kan ge ytterligare kontext-AI Assistant eller välja en tidigare överförd.

   Tidigare överförda filer är tillgängliga i listrutan **[!UICONTROL Uploaded brand assets]**. Du behöver bara växla mellan de resurser du vill ha med i din generation.

   ![Listrutan varumärkesresurser](assets/text-genai-3.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Generate]** när din fråga är klar.

### Förfina och slutför {#refine-finalize}

Lär dig hur du granskar den genererade texten, gör förbättringar och tillämpar personalisering för att färdigställa innehållet och skapa snygga och engagerande meddelanden som är klara för leverans.

1. Bläddra igenom den genererade **[!UICONTROL Variations]**.

   Klicka på **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den markerade varianten eller klicka på **[!UICONTROL Apply]** om du vill ersätta det aktuella innehållet.

1. Klicka på procentikonen för att visa din **[!UICONTROL Brand Alignment Score]** och identifiera eventuella feljusteringar av ditt varumärke.

   Läs mer om [varumärkesjusteringspoäng](brands-score.md).

   ![Genererade textvariationer med bakgrundsjusteringspoäng](assets/text-genai-6.png){zoomable="yes"}

1. Navigera till alternativet **[!UICONTROL Refine]** i fönstret **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner:

   * **[!UICONTROL Use as reference content]**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **[!UICONTROL Rephrase]**: Skriv om meddelandet med bibehållen betydelse. Med det här alternativet kan du generera alternativa ordalydelser, förbättra flödet eller justera fraser utan att ändra huvudbudskapet.

   * **[!UICONTROL Use simpler language]**: Använd AI Assistant för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   * **[!UICONTROL Change tone]**: Justera tonen i meddelandet så att det bättre matchar din kommunikationsstil, dvs. gör det mer användarvänligt, professionellt, brådskande eller inspirerande.

   * **[!UICONTROL Change Communication strategy]**: Ändra meddelandetillvägagångssättet baserat på dina mål, till exempel skapa en tränglighet eller framhäva en spännande tilltalande upplevelse.

   ![Menyn Förfina alternativ](assets/text-genai-5.png){zoomable="yes"}

1. Öppna fliken **[!UICONTROL Brand Alignment]** och se hur ditt innehåll överensstämmer med [varumärkesriktlinjerna](brands.md).

1. Klicka på **[!UICONTROL Select]** när du har hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. Infoga anpassningsfält för att anpassa innehållet baserat på profildata. Klicka sedan på knappen **[!UICONTROL Simulate content]** för att kontrollera återgivningen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../personalization/personalize.md)

1. Granska och aktivera ditt innehåll:
   * **E-post**: När du har definierat ditt innehåll, din målgrupp och ditt schema är du redo att förbereda din e-postkampanj. [Läs mer](../campaigns/review-activate-campaign.md)
   * **Webb**: När du har definierat inställningarna för webbkampanjen och redigerat innehållet efter behov kan du granska och aktivera webbkampanjen. [Läs mer](../web/create-web.md#activate-web-campaign)
   * **Landningssida**: När landningssidan är klar kan du publicera den och göra den tillgänglig för användning i ett meddelande. [Läs mer](../landing-pages/create-lp.md#publish-landing-page)

## För mobila kanaler {#mobile-channels}

AI Assistant kan generera övertygande textinnehåll för dina push-meddelanden och SMS-meddelanden, så att du kan skapa engagerande mobilkommunikation som får genklang hos publiken över alla mobila kontaktytor.

### Åtkomst och konfiguration {#mobile-access-configure}

Innan du börjar generera text med AI Assistant för mobila kanaler måste du konfigurera kampanjen och få tillgång till AI Assistant. Åtkomstmetoden varierar något mellan push-meddelanden och SMS-meddelanden.

1. Skapa och konfigurera en mobilkampanj:
   * **Push-meddelanden**: När du har skapat och konfigurerat din push-meddelandekampanj klickar du på **[!UICONTROL Edit content]**. [Läs mer](../push/create-push.md)
   * **SMS**: När du har skapat och konfigurerat din SMS-kampanj klickar du på **[!UICONTROL Edit content]**. [Läs mer](../sms/create-sms.md)

1. Fyll i **[!UICONTROL Basic details]** för din kampanj. Klicka på **[!UICONTROL Edit content]** när du är klar.

1. Anpassa meddelandet efter behov:
   * **Push-meddelanden**: [Läs mer](../push/design-push.md)
   * **SMS**: [Läs mer](../sms/create-sms.md)

1. Access AI Assistant:
   * **För push-meddelanden**: Klicka på menyn **[!UICONTROL Edit text with AI Assistant]** bredvid dina **[!UICONTROL Title]** - eller **[!UICONTROL Message]**-fält. Du kan även komma åt **AI-assistentmenyn** direkt.

     ![Skärm för push-meddelandekomposition med knappen Redigera text med AI-assistenten](assets/push-text-1.png){zoomable="yes"}

   * **För SMS**: Klicka på menyn **[!UICONTROL Edit text with AI Assistant]** bredvid **[!UICONTROL Message]** eller öppna menyn **[!UICONTROL Show AI Assistant]** .

     ![SMS-meddelanderedigeraren med AI Assistant-panelen öppen](assets/sms-genai-1.png){zoomable="yes"}

### Generera innehåll {#mobile-generate-content}

När du har använt AI Assistant kan du konfigurera genereringsinställningarna för att skapa mobilt innehåll som matchar ert varumärke och era kampanjmål. Anpassa textparametrar, lägg till varumärkesresurser och ge anvisningar om hur AI genererar relevanta variationer.

1. Välj din **[!UICONTROL Brand]** för att se till att det AI-genererade innehållet följer varumärkesspecifikationerna. [Läs mer](brands.md) om varumärken.

   Observera att funktionen Varumärke släpps som en privat betaversion och kommer att finnas tillgänglig för alla kunder i framtida versioner.

1. Finjustera innehållet genom att beskriva vad du vill generera i fältet **[!UICONTROL Prompt]**.

   Om du vill ha hjälp med att skapa din fråga kan du få tillgång till **[!UICONTROL Prompt Library]**, som innehåller en mängd olika tips för att förbättra dina kampanjer. [Läs mer om god praxis](ai-assistant-prompting-guide.md)

   ![AI-assistenten med snabbfält och alternativ](assets/push-genai-2.png){zoomable="yes"}

1. **För push-meddelanden** väljer du vilket fält du vill generera: Titel och/eller Meddelande.

1. Skräddarsy din fråga med alternativet **[!UICONTROL Text settings]**:

   * **[!UICONTROL Communication strategy]**: Välj den lämpligaste kommunikationsstilen för den genererade texten.
   * **[!UICONTROL Languages]**: Välj språk för det genererade innehållet.
   * **[!UICONTROL Tone]**: Tonen bör återges med din målgrupp. Vare sig du vill låta informativ, lekfull eller övertygande kan AI Assistant anpassa budskapet därefter.

     ![Panelen Textinställningar](assets/push-genai-4.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Reference content]** på menyn **[!UICONTROL Upload file]** om du vill lägga till en varumärkesresurs som innehåller innehåll som kan ge ytterligare kontext-AI Assistant eller välja en tidigare överförd.

   Tidigare överförda filer är tillgängliga i listrutan **[!UICONTROL Uploaded reference content]**. Du behöver bara växla mellan de resurser du vill ha med i din generation.

1. Klicka på **[!UICONTROL Generate]** när din fråga är klar.

### Förfina och slutför {#mobile-refine-finalize}

När du har genererat textvarianter för dina mobilmeddelanden kan du finjustera resultatet för att säkerställa att de uppfyller dina exakta krav. Granska varumärkesjusteringen, justera ton och språk och förbered innehållet för aktivering.

1. Bläddra igenom **[!UICONTROL Variations]** efter generering.

1. Klicka på procentikonen för att visa din **[!UICONTROL Brand Alignment Score]** och identifiera eventuella feljusteringar av ditt varumärke.

   Läs mer om [varumärkesjusteringspoäng](brands-score.md).

   ![Genererade textvariationer med bakgrundsjusteringspoäng](assets/push-genai-5.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den markerade varianten eller klicka på **[!UICONTROL Apply]** om du vill ersätta det aktuella innehållet.

1. Navigera till alternativet **[!UICONTROL Refine]** i fönstret **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner:

   * **[!UICONTROL Use as reference content]**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **[!UICONTROL Rephrase]**: Skriv om meddelandet med bibehållen betydelse. Med det här alternativet kan du generera alternativa ordalydelser, förbättra flödet eller justera fraser utan att ändra huvudbudskapet.

   * **[!UICONTROL Use simpler language]**: Använd AI Assistant för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   * **[!UICONTROL Translate]**: Förenkla ditt språk för att säkerställa tydlighet och tillgänglighet för en större publik.

   * **[!UICONTROL Change tone]**: Justera tonen i meddelandet så att det bättre matchar din kommunikationsstil, dvs. gör det mer användarvänligt, professionellt, brådskande eller inspirerande.

   * **[!UICONTROL Change Communication strategy]**: Ändra meddelandetillvägagångssättet baserat på dina mål, till exempel skapa en tränglighet eller framhäva en spännande tilltalande upplevelse.

     ![Förfina meny](assets/push-genai-6.png){zoomable="yes"}

1. Öppna fliken **[!UICONTROL Brand Alignment]** och se hur ditt innehåll överensstämmer med [varumärkesriktlinjerna](brands.md).

1. Klicka på **[!UICONTROL Select]** när du har hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. Infoga anpassningsfält för att anpassa innehållet baserat på profildata. Klicka sedan på knappen **[!UICONTROL Simulate content]** för att kontrollera återgivningen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../personalization/personalize.md)

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er mobilkampanj. [Läs mer](../campaigns/review-activate-campaign.md)

