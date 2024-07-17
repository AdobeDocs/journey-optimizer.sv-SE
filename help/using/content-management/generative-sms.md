---
solution: Journey Optimizer
product: journey optimizer
title: SMS-generering med AI-assistenten
description: Börja generera SMS-innehåll med AI-assistenten
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
badge: label="Beta" type="Informative"
hide: true
hidefromtoc: true
exl-id: 5fd1cc3a-c023-4e8e-bfac-9a86bd33bbb3
source-git-commit: b62f8954e09f50896ad5e70784c5a93943617e85
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 1%

---

# SMS-generering med AI-assistenten {#generative-sms}

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* [Kom igång med AI-assistenten](gs-generative.md)
* [E-postgenerering med AI-assistenten](generative-email.md)
* SMS-generering med AI-assistenten
* [Push-generering med AI Assistant](generative-push.md)
* [Experimentera med AI-assistenten](generative-experimentation.md)

>[!ENDSHADEBOX]

När du har skapat och skräddarsytt dina SMS-meddelanden så att de passar er målgrupp kan du kommunicera med AI Assistant i Journey Optimizer.

Den här resursen ger insiktsfulla rekommendationer för att finjustera ert innehåll, vilket hjälper ert budskap att få genklang och öka engagemanget.

Gå igenom flikarna nedan och lär dig hur du använder AI Assistant i Journey Optimizer.

>[!NOTE]
>
>Innan du börjar använda den här funktionen bör du läsa upp relaterade [säkerhetsutkast och begränsningar](gs-generative.md#generative-guardrails).

>[!BEGINTABS]

>[!TAB Fullständig SMS-generering]

1. När du har skapat och konfigurerat din SMS-kampanj klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din SMS-kampanj finns på [den här sidan](../sms/create-sms.md).

1. Fyll i **[!UICONTROL Basic details]** för din kampanj. Klicka på **[!UICONTROL Edit content]** när du är klar.

1. Anpassa SMS-meddelandet efter behov. [Läs mer](../sms/create-sms.md)

1. Öppna menyn **[!UICONTROL Show AI Assistant]**.

   ![](assets/sms-genai-1.png){zoomable="yes"}

1. Aktivera alternativet **[!UICONTROL Use original content]** för AI-assistenten för att anpassa nytt innehåll baserat på kampanjinnehåll, namn och vald målgrupp.

   Din fråga måste alltid vara kopplad till ett visst sammanhang.

1. Finjustera innehållet genom att beskriva vad du vill generera i fältet **[!UICONTROL Prompt]**.

   Om du vill ha hjälp med att skapa din fråga kan du få tillgång till **[!UICONTROL Prompt Library]**, som innehåller en mängd olika tips för att förbättra dina kampanjer.

   ![](assets/sms-genai-2.png){zoomable="yes"}

1. Välj **[!UICONTROL Upload brand asset]** om du vill lägga till en varumärkesresurs som innehåller innehåll som kan ge ytterligare kontext till AI-assistenten.

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Communication strategy]**: Välj önskad kommunikationsmetod för den genererade texten.
   * **[!UICONTROL Language]**: Välj språk för variantens innehåll.
   * **[!UICONTROL Tone]**: Se till att texten passar din målgrupp och ditt syfte.
   * **[!UICONTROL Length]**: Välj längden på ditt innehåll med intervallreglaget.

   ![](assets/sms-genai-3.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Generate]** när din fråga är klar.

1. Bläddra igenom den genererade **[!UICONTROL Variations]** och klicka på **[!UICONTROL Preview]** för att visa en fullskärmsversion av den valda varianten.

1. Navigera till alternativet **[!UICONTROL Refine]** i fönstret **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner och finjustera variationerna efter dina inställningar:

   * **[!UICONTROL Use as reference content]**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **[!UICONTROL Rephrase]**:AI-assistenten kan omformulera ditt meddelande på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **[!UICONTROL Use simpler language]**: Utnyttja AI-assistenten för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   ![](assets/sms-genai-4.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Select]** när du har hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. Infoga anpassningsfält för att anpassa ditt SMS-innehåll baserat på profildata. [Läs mer om innehållspersonalisering](../personalization/personalize.md)

1. När du har definierat meddelandeinnehållet klickar du på knappen **[!UICONTROL Simulate content]** för att kontrollera återgivningen och kontrollerar personaliseringsinställningarna med testprofiler. [Läs mer](../personalization/personalize.md)

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er SMS-kampanj. [Läs mer](../campaigns/review-activate-campaign.md)

>[!TAB Textgenerering]

1. När du har skapat och konfigurerat din SMS-kampanj klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din SMS-kampanj finns på [den här sidan](../sms/create-sms.md).

1. Fyll i **[!UICONTROL Basic details]** för din kampanj. Klicka på **[!UICONTROL Edit content]** när du är klar.

1. Anpassa SMS-meddelandet efter behov. [Läs mer](../sms/create-sms.md)

1. Gå till menyn **[!UICONTROL Edit text with AI Assistant]** bredvid fältet **[!UICONTROL Message]**.

   ![](assets/sms-text-genai-1.png){zoomable="yes"}

1. Aktivera alternativet **[!UICONTROL Use reference content]** för AI-assistenten för att anpassa nytt innehåll baserat på kampanjinnehåll, namn och vald målgrupp.

   Din fråga måste alltid vara kopplad till ett visst sammanhang.

1. Finjustera innehållet genom att beskriva vad du vill generera i fältet **[!UICONTROL Prompt]**.

   Om du vill ha hjälp med att skapa din fråga kan du få tillgång till **[!UICONTROL Prompt Library]**, som innehåller en mängd olika tips för att förbättra dina kampanjer.

   ![](assets/sms-text-genai-1.png){zoomable="yes"}

1. Välj **[!UICONTROL Upload brand asset]** om du vill lägga till en varumärkesresurs som innehåller innehåll som kan ge ytterligare kontext till AI-assistenten.

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Communication strategy]**: Välj önskad kommunikationsmetod för den genererade texten.
   * **[!UICONTROL Language]**: Välj språk för variantens innehåll.
   * **[!UICONTROL Tone]**: Se till att texten passar din målgrupp och ditt syfte.
   * **[!UICONTROL Length]**: Välj längden på ditt innehåll med intervallreglaget.

   ![](assets/sms-text-genai-3.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Generate]** när din fråga är klar.

1. Bläddra igenom den genererade **[!UICONTROL Variations]** och klicka på **[!UICONTROL Preview]** för att visa en fullskärmsversion av den valda varianten.

1. Navigera till alternativet **[!UICONTROL Refine]** i fönstret **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner och finjustera variationerna efter dina inställningar:

   * **[!UICONTROL Use as reference content]**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **[!UICONTROL Rephrase]**:AI-assistenten kan omformulera ditt meddelande på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **[!UICONTROL Use simpler language]**: Utnyttja AI-assistenten för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   ![](assets/sms-text-genai-4.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Select]** när du har hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. Infoga anpassningsfält för att anpassa ditt SMS-innehåll baserat på profildata. [Läs mer om innehållspersonalisering](../personalization/personalize.md)

1. När du har definierat meddelandeinnehållet klickar du på knappen **[!UICONTROL Simulate content]** för att kontrollera återgivningen och kontrollerar personaliseringsinställningarna med testprofiler.

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er SMS-kampanj. [Läs mer](../campaigns/review-activate-campaign.md)

>[!ENDTABS]
