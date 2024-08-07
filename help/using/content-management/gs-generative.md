---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med AI-assistenten
description: Lär dig använda och arbeta med Journey Optimizer AI Assistant
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
badge: label="Beta" type="Informative"
hide: true
hidefromtoc: true
exl-id: 6e291ce3-f324-4e5d-975b-5229dea4d581
source-git-commit: 930070843c2c1ce022beb5dc6e8a61c8d4f70365
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Kom igång med AI-assistenten {#gs-content-assistant}

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_settings"
>title="AI-assistenten"
>abstract="När du har skapat och skräddarsytt din leverans kan du använda AI-assistenten för att förbättra innehållet. Den här funktionen förenklar processen med personalisering och innehållsförbättring genom att du kan finjustera innehållet genom att beskriva vad du vill generera."


>[!CONTEXTUALHELP]
>id="ajo_ai_generation_context"
>title="Ladda upp varumärkesresurs"
>abstract="På menyn Överför varumärkesresurser kan du lägga till alla varumärkesresurser som innehåller innehåll som kan ge ytterligare kontext för AI-assistenten eller välja en tidigare överförd resurs. Med det här alternativet får AI-assistenten tillgång till allt material som behövs för att förbättra funktionaliteten och relevansen."


>[!CONTEXTUALHELP]
>id="ajo_ai_generation_start"
>title="Adobe Generative AI terms"
>abstract="Du måste godkänna Adobe Experience Cloud Generative AI User Guidelines. Granska alla utdata från den här funktionen för att se om de är korrekta och se till att de passar ditt sätt att arbeta."
>additional-url="https://www.adobe.com/legal/licenses-terms/adobe-gen-ai-user-guidelines.html" text="Adobe Generative AI User Guidelines"

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* Kom igång med AI-assistenten
* [E-postgenerering med AI-assistenten](generative-email.md)
* [SMS-generering med AI-assistenten](generative-sms.md)
* [Push-generering med AI Assistant](generative-push.md)
* [Experimentera med AI-assistenten](generative-experimentation.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>AI Assistant i Adobe Journey Optimizer finns för närvarande endast som betaversion för vissa användare.

AI Assistant i Adobe Journey Optimizer, som drivs av Azure OpenAI, ger proaktiva innehållsvariationsförslag för text och bilder. Det är tillgängligt för e-post-, push- och SMS-kanaler. Den nya funktionen ger snabb generering av text och bilder. Bildgenereringen hanteras med Adobe Firefly.

Använd AI Assistant i Journey Optimizer för att optimera budskapets genomslagskraft genom att experimentera med olika förtexter och bilder. Generera flera varianter och skapa ett experiment för att jämföra dem. Genom att utnyttja Journey Optimizer Content Experiment kan ni definiera flera olika meddelandebehandlingar för att mäta vilken som fungerar bäst för er målgrupp. Du kan välja att variera leveransinnehållet eller ämnet. Meddelandemålgruppen fördelas slumpmässigt till varje behandling för att avgöra vilken som fungerar bäst med det angivna måttet. Läs mer om Content Experiment i [det här avsnittet](../content-management/content-experiment.md).

## Skyddsritningar och begränsningar {#generative-guardrails}

Allmänna riktlinjer för hur du använder AI Assistant i Journey Optimizer för att generera e-post anges nedan:

* Kvaliteten på det genererade innehållet påverkas i hög grad av det marknadsföringsmål/den uppmaning du anger. Använd en väldefinierad uppmaning för GenAI-modellen att tolka korrekt. 
* Ladda upp varumärkesresurser för att få korrekt varumärkesinnehåll. Annars baseras innehållet på offentligt tillgänglig information. Det överförda innehållet kan ha följande format: PDF, JPEG, PNG eller ZIP-filer (med filformat som stöds).
* Den maximala storleken för överförda varumärkesresurser är 50 MB. Större filer eller mycket bilder kan fungera, men bearbetningstiden ökar.
* Använd en e-postmall som skapats av Adobe Campaign, helst [inbyggda e-postmallar](../email/use-email-templates.md), en varumärkesspecifik mall eller anpassad mall för att skapa ditt e-postinnehåll. E-postmall med upp till 8-10 bilder rekommenderas.
* Var noga med att rapportera eventuella problematiska utdata med ikonerna för tummen uppåt, tummen nedåt eller flagga när du väljer varianter.
* Din användning av AI-assistenten regleras av Adobe Experience Cloud Generative AI User Guidelines. [Läs mer](https://www.adobe.com/legal/licenses-terms/adobe-gen-ai-user-guidelines.html)

Följande begränsningar gäller för AI Assistant i Journey Optimizer:

* Språket som stöds är endast engelska.
* Endast tillgängligt för e-post-, push- och SMS-kanalerna.
* GenAI-innehåll kanske inte alltid är korrekt: dela med dig av dina synpunkter så att våra tekniker kan förfina modellerna.
* Ni kan överföra flera varumärkesresurser, men ni kan bara utnyttja en för en viss generation.

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="generative-email.md">
<img alt="E-postgenerering" src="assets/do-not-localize/text-genai.jpeg">
</a>
<div>
<a href="generative-email.md"><strong>E-postgenerering</strong></a>
</div>
<p>
</td>
<td>
<a href="generative-sms.md">
<img alt="SMS-generering" src="assets/do-not-localize/image-genai.jpeg">
</a>
<div><a href="generative-sms.md"><strong>SMS-generering</strong>
</div>
<p>
</td>
<td>
<a href="generative-push.md">
<img alt="Push-generering" src="assets/do-not-localize/email-genai.jpeg">
</a>
<div>
<a href="generative-push.md"><strong>Generering av push-meddelanden</strong></a>
</div>
<p></td>
</tr></table>
