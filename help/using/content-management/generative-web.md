---
solution: Journey Optimizer
product: journey optimizer
title: Skapa webbsidor med AI Assistant
description: Börja generera webbsidesinnehåll och -resurser med AI-assistenten
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
badge: label="Beta" type="Informative"
hide: true
hidefromtoc: true
source-git-commit: fc6d1caacae3574cc7400ed9c9c634e3ff3cae5a
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 0%

---

# Webbgenerering med AI Assistant {#generative-web}

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* [Kom igång med AI-assistenten](gs-generative.md)
* [E-postgenerering med AI-assistenten](generative-email.md)
* [SMS-generering med AI-assistenten](generative-SMS.md)
* [Push-generering med AI Assistant](generative-push.md)
* **[Skapa webbsidor med AI Assistant](generative-web.md)**
* [Experimentera med AI-assistenten](generative-experimentation.md)

>[!ENDSHADEBOX]

När ni väl har skapat och personaliserat era e-postmeddelanden kan ni använda Journey Optimizer AI Assistant i Campaign, som bygger på generativ AI, för att ta innehållet till nästa nivå.

AI Assistant kan hjälpa er att optimera effekten av era leveranser genom att föreslå olika typer av innehåll som troligtvis får genklang hos er målgrupp.

>[!NOTE]
>
>Innan du börjar använda den här funktionen bör du läsa upp relaterade [Gardrutor och begränsningar](generative-gs.md#guardrails-and-limitations).

>[!BEGINTABS]

>[!TAB Helgenerering av webbsidor]

I följande exempel använder vi AI-assistenten för att förfina ett befintligt e-postmeddelande och anpassa det för en speciell händelse.

1. När du har skapat och konfigurerat e-postleveransen klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din e-postleverans finns i [den här sidan](../email/create-email-content.md).

1. Anpassa din e-post efter behov och få tillgång till **[!UICONTROL AI Assistant]** -menyn.

   ![](assets/full-email-1.png){zoomable=&quot;yes&quot;}

1. Aktivera **[!UICONTROL Use original content]** för AI Assistant för att anpassa nytt innehåll baserat på leverans, leveransnamn och vald målgrupp.

   Din fråga måste alltid vara kopplad till ett visst sammanhang.

1. Finjustera innehållet genom att beskriva vad du vill generera i **[!UICONTROL Prompt]** fält.

   Om du behöver hjälp med att skapa din fråga kan du gå till **[!UICONTROL Prompt Library]** som ger en mängd olika tips för att förbättra leveransen.

   ![](assets/full-email-2.png){zoomable=&quot;yes&quot;}

1. Du kan växla **[!UICONTROL Subject line]** eller **[!UICONTROL Preheader]** för att inkludera dem i variantgenereringen.

1. Klicka **[!UICONTROL Upload brand asset]** om du vill lägga till en varumärkesresurs som innehåller innehåll som kan ge ytterligare kontext i AI-assistenten eller välja en som har överförts tidigare.

   ![](assets/full-email-3.png){zoomable=&quot;yes&quot;}

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Communication strategy]**: Välj det format som passar bäst för den genererade texten.
   * **[!UICONTROL Language]**: Välj vilket språk du vill att innehållet ska skapas på.
   * **[!UICONTROL Tone]**: Tonen i e-postmeddelandet bör få genklang hos er målgrupp. Vare sig du vill låta informativ, lekfull eller övertygande kan AI-assistenten anpassa meddelandet därefter.
   * **[!UICONTROL Length]**: Välj önskad längd på innehållet med intervallreglaget.

   ![](assets/full-email-4.png){zoomable=&quot;yes&quot;}

1. När frågan är klar klickar du på **[!UICONTROL Generate]**.

1. Bläddra bland de genererade **[!UICONTROL Variations]** och klicka **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den valda varianten.

1. Navigera till **[!UICONTROL Refine]** i **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner:

   * **[!UICONTROL Rephrase]**: AI-assistenten kan omformulera sitt budskap på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **[!UICONTROL Use simple Language]**: Utnyttja AI-assistenten för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   ![](assets/full-email-5.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Select]** när du hittat rätt innehåll.

1. Infoga anpassningsfält för att anpassa ditt e-postinnehåll baserat på profildata. Klicka sedan på **[!UICONTROL Simulate content]** för att styra återgivningen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../preview-test/preview-content.md)

   ![](assets/full-email-6.png){zoomable=&quot;yes&quot;}

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er för att leverera e-post. [Läs mer](../monitor/prepare-send.md)

>[!TAB Skapa text på webbsidor]

I följande exempel använder vi AI-assistenten för att förbättra innehållet i vår e-postinbjudan till vårt kommande evenemang.

1. När du har skapat och konfigurerat e-postleveransen klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din e-postleverans finns i [den här sidan](../email/create-email-content.md).

1. Välj en **[!UICONTROL Text component]** för att endast rikta in sig på ett visst innehåll. och få tillgång till **[!UICONTROL AI Assistant]** -menyn.

   ![](assets/text-genai-1.png){zoomable=&quot;yes&quot;}

1. Aktivera **[!UICONTROL Use original content]** för AI Assistant för att anpassa nytt innehåll baserat på leverans, leveransnamn och vald målgrupp.

   Din fråga måste alltid vara kopplad till ett visst sammanhang.

1. Finjustera innehållet genom att beskriva vad du vill generera i **[!UICONTROL Prompt]** fält.

   Om du behöver hjälp med att skapa din fråga kan du gå till **[!UICONTROL Prompt Library]** som ger en mängd olika tips för att förbättra leveransen.

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

   * **Använd som referensinnehåll**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **Samarbeta**: AI-assistenten kan hjälpa er att utöka kring specifika ämnen, med ytterligare information för bättre förståelse och engagemang.

   * **Sammanfatta**: Lång information kan överlagra e-postmottagare. Använd AI Assistant för att dra ihop viktiga punkter till tydliga, kortfattade sammanfattningar som får dem att läsa mer.

   * **Återfras**:AI-assistenten kan omformulera sitt budskap på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **Använd enkelt språk**: Utnyttja AI-assistenten för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   ![](assets/text-genai-5.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Select]** när du hittat rätt innehåll.

1. Infoga anpassningsfält för att anpassa ditt e-postinnehåll baserat på profildata. Klicka sedan på **[!UICONTROL Simulate content]** för att styra återgivningen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../preview-test/preview-content.md)

   ![](assets/text-genai-7.png){zoomable=&quot;yes&quot;}

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er för att leverera e-post. [Läs mer](../monitor/prepare-send.md)

>[!TAB Skapa bilder för webbsidor]

I exemplet nedan kan du lära dig hur du använder AI Assistant för att optimera och förbättra dina resurser, vilket ger en mer användarvänlig upplevelse.

1. När du har skapat och konfigurerat e-postleveransen klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din e-postleverans finns i [den här sidan](../email/create-email-content.md).

1. Fyll i **[!UICONTROL Basic details]** för leverans. När du är klar klickar du **[!UICONTROL Edit email content]**.

1. Markera den resurs som du vill ändra med AI-assistenten.

1. Välj **[!UICONTROL AI Assistant]**.

   ![](assets/image-genai-1.png){zoomable=&quot;yes&quot;}

1. Finjustera innehållet genom att beskriva vad du vill generera i **[!UICONTROL Prompt]** fält.

   Om du behöver hjälp med att skapa din fråga kan du gå till **[!UICONTROL Prompt Library]** som ger en mängd olika tips för att förbättra leveransen.

   ![](assets/image-genai-2.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Upload brand asset]** om du vill lägga till alla varumärkesresurser som innehåller innehåll som kan ge ytterligare kontext i AI-assistenten.

   Din fråga måste alltid vara kopplad till ett visst sammanhang.

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Aspect ratio]**: Detta avgör objektets bredd och höjd. Du kan välja mellan vanliga proportioner som 16:9, 4:3, 3:2 eller 1:1, eller ange en anpassad storlek.
   * **[!UICONTROL Color & tone]**: Det övergripande utseendet på färgerna i en bild och stämningen eller atmosfären som bilden förmedlar.
   * **[!UICONTROL Content type]**: Detta kategoriserar det visuella elementets karaktär och skiljer mellan olika former av visuell representation, t.ex. foton, grafik eller grafik.
   * **[!UICONTROL Lighting]**: Detta avser blixten i en bild som formar atmosfären och markerar specifika element.
   * **[!UICONTROL Composition]**: Detta avser elementens placering i en bilds bildruta

   ![](assets/image-genai-3.png){zoomable=&quot;yes&quot;}

1. När du är nöjd med promptkonfigurationen klickar du på **[!UICONTROL Generate]**.

1. Sök i **[!UICONTROL Variation suggestions]** för att hitta den önskade resursen.

   Klicka **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den valda varianten.

   ![](assets/image-genai-5.png){zoomable=&quot;yes&quot;}

1. Välj **[!UICONTROL Show Similar]** om du vill visa relaterade bilder till den här varianten.

1. Klicka **[!UICONTROL Select]** när du hittat rätt innehåll.

   ![](assets/image-genai-6.png){zoomable=&quot;yes&quot;}

1. När du har definierat meddelandeinnehållet klickar du på **[!UICONTROL Simulate content]** för att styra återgivningen och kontrollera personaliseringsinställningarna med testprofiler.  [Läs mer](../preview-test/preview-content.md)

   ![](assets/image-genai-7.png){zoomable=&quot;yes&quot;}

1. När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er för att leverera e-post. [Läs mer](../monitor/prepare-send.md)

>[!ENDTABS]

