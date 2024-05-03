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
source-git-commit: 5c4b7cde5514f60f61050837fc9ae325f7bef2e8
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# SMS-generering med AI-assistenten {#generative-sms}

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* [Kom igång med AI-assistenten](gs-generative.md)
* [E-postgenerering med AI-assistenten](generative-email.md)
* [SMS-generering med AI-assistenten](generative-sms.md)
* **[Push-generering med AI Assistant](generative-push.md)**
* [Experimentera med AI-assistenten](generative-experimentation.md)

>[!ENDSHADEBOX]

När du har skapat och skräddarsytt dina SMS-meddelanden så att de passar er målgrupp kan du kommunicera med AI Assistant i Journey Optimizer.

Den här resursen ger insiktsfulla rekommendationer för att finjustera ert innehåll, vilket hjälper ert budskap att få genklang och öka engagemanget.

Gå igenom flikarna nedan och lär dig hur du använder AI Assistant i Journey Optimizer.

>[!NOTE]
>
>Innan du börjar använda den här funktionen bör du läsa upp relaterade [Gardrutor och begränsningar](gs-generative.md#generative-guardrails).

>[!BEGINTABS]

>[!TAB Full SMS-generering]

1. När du har skapat och konfigurerat din SMS-kampanj klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din SMS-kampanj finns i [den här sidan](../sms/create-sms.md).

1. Fyll i **[!UICONTROL Basic details]** för er kampanj. När du är klar klickar du **[!UICONTROL Edit content]**.

1. Anpassa SMS-meddelandet efter behov. [Läs mer](../sms/create-sms.md)

1. Öppna **[!UICONTROL Show AI Assistant]** -menyn.

   ![](assets/sms-genai-1.png){zoomable=&quot;yes&quot;}

1. Aktivera **[!UICONTROL Use original content]** för AI Assistant för att anpassa nytt innehåll baserat på kampanjinnehåll, namn och vald målgrupp.

   Din fråga måste alltid vara kopplad till ett visst sammanhang.

1. Finjustera innehållet genom att beskriva vad du vill generera i **[!UICONTROL Prompt]** fält.

   Om du behöver hjälp med att skapa din fråga kan du gå till **[!UICONTROL Prompt Library]** som ger ett brett urval av snabba idéer för att förbättra era kampanjer.

   ![](assets/sms-genai-2.png){zoomable=&quot;yes&quot;}

1. Välj **[!UICONTROL Upload brand asset]** om du vill lägga till alla varumärkesresurser som innehåller innehåll som kan ge ytterligare kontext i AI-assistenten.

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Communication strategy]**: Välj önskat kommunikationssätt för den genererade texten.
   * **[!UICONTROL Language]**: Välj språk för variantens innehåll.
   * **[!UICONTROL Tone]**: Se till att texten är lämplig för din målgrupp och ditt syfte.
   * **[!UICONTROL Length]**: Välj längden på innehållet med intervallreglaget.

   ![](assets/sms-genai-3.png){zoomable=&quot;yes&quot;}

1. När frågan är klar klickar du på **[!UICONTROL Generate]**.

1. Bläddra bland de genererade **[!UICONTROL Variations]** och klicka **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den valda varianten.

1. Navigera till **[!UICONTROL Refine]** i **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner och finjustera dina varianter:

   * **[!UICONTROL Use as reference content]**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **[!UICONTROL Rephrase]**:AI-assistenten kan omformulera sitt budskap på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **[!UICONTROL Use simpler language]**: Utnyttja AI-assistenten för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   ![](assets/sms-genai-4.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Select]** när du hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. Infoga anpassningsfält för att anpassa ditt SMS-innehåll baserat på profildata. [Läs mer om innehållspersonalisering](../personalization/personalize.md)

1. När du har definierat meddelandeinnehållet klickar du på **[!UICONTROL Simulate content]** för att styra återgivningen och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](../personalization/personalize.md)

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er SMS-kampanj. [Läs mer](../campaigns/review-activate-campaign.md)

>[!TAB Textgenerering]

1. När du har skapat och konfigurerat din SMS-kampanj klickar du på **[!UICONTROL Edit content]**.

   Mer information om hur du konfigurerar din SMS-kampanj finns i [den här sidan](../sms/create-sms.md).

1. Fyll i **[!UICONTROL Basic details]** för er kampanj. När du är klar klickar du **[!UICONTROL Edit content]**.

1. Anpassa SMS-meddelandet efter behov. [Läs mer](../sms/create-sms.md)

1. Öppna **[!UICONTROL Edit text with AI Assistant]** -menyn bredvid **[!UICONTROL Message]** fält.

   ![](assets/sms-text-genai-1.png){zoomable=&quot;yes&quot;}

1. Aktivera **[!UICONTROL Use reference content]** för AI Assistant för att anpassa nytt innehåll baserat på kampanjinnehåll, namn och vald målgrupp.

   Din fråga måste alltid vara kopplad till ett visst sammanhang.

1. Finjustera innehållet genom att beskriva vad du vill generera i **[!UICONTROL Prompt]** fält.

   Om du behöver hjälp med att skapa din fråga kan du gå till **[!UICONTROL Prompt Library]** som ger ett brett urval av snabba idéer för att förbättra era kampanjer.

   ![](assets/sms-text-genai-1.png){zoomable=&quot;yes&quot;}

1. Välj **[!UICONTROL Upload brand asset]** om du vill lägga till alla varumärkesresurser som innehåller innehåll som kan ge ytterligare kontext i AI-assistenten.

1. Skräddarsy uppmaningen med de olika alternativen:

   * **[!UICONTROL Communication strategy]**: Välj önskat kommunikationssätt för den genererade texten.
   * **[!UICONTROL Language]**: Välj språk för variantens innehåll.
   * **[!UICONTROL Tone]**: Se till att texten är lämplig för din målgrupp och ditt syfte.
   * **[!UICONTROL Length]**: Välj längden på innehållet med intervallreglaget.

   ![](assets/sms-text-genai-3.png){zoomable=&quot;yes&quot;}

1. När frågan är klar klickar du på **[!UICONTROL Generate]**.

1. Bläddra bland de genererade **[!UICONTROL Variations]** och klicka **[!UICONTROL Preview]** om du vill visa en fullskärmsversion av den valda varianten.

1. Navigera till **[!UICONTROL Refine]** i **[!UICONTROL Preview]** för att få tillgång till ytterligare anpassningsfunktioner och finjustera dina varianter:

   * **[!UICONTROL Use as reference content]**: Den valda varianten fungerar som referensinnehåll för att generera andra resultat.

   * **[!UICONTROL Rephrase]**:AI-assistenten kan omformulera sitt budskap på olika sätt, vilket håller skrivandet aktuellt och engagerande för olika målgrupper.

   * **[!UICONTROL Use simpler language]**: Utnyttja AI-assistenten för att förenkla ditt språk och säkerställa tydlighet och tillgänglighet för en större publik.

   ![](assets/sms-text-genai-4.png){zoomable=&quot;yes&quot;}

1. Klicka **[!UICONTROL Select]** när du hittat rätt innehåll.

   Du kan också göra det möjligt att experimentera med ditt innehåll. [Läs mer](generative-experimentation.md)

1. Infoga anpassningsfält för att anpassa ditt SMS-innehåll baserat på profildata. [Läs mer om innehållspersonalisering](../personalization/personalize.md)

1. När du har definierat meddelandeinnehållet klickar du på **[!UICONTROL Simulate content]** för att styra återgivningen och kontrollera personaliseringsinställningarna med testprofiler.

När ni har definierat ert innehåll, er målgrupp och ert schema är ni redo att förbereda er SMS-kampanj. [Läs mer](../campaigns/review-activate-campaign.md)

>[!ENDTABS]
