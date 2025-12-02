---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med AI Assistant i Journey Optimizer
description: Lär dig komma åt och arbeta med AI Assistant i Journey Optimizer
feature: Content Assistant
topic: Content Management
role: User
level: Beginner
exl-id: 6e291ce3-f324-4e5d-975b-5229dea4d581
source-git-commit: de418dc4feefd99231155c550ad3a51e4850ee66
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 2%

---

# Kom igång med AI Assistant {#gs-content-assistant}

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_settings"
>title="AI Assistant i Journey Optimizer"
>abstract="När du har skapat och skräddarsytt materialet kan du använda AI Assistant i Journey Optimizer för att förbättra innehållet. Den här funktionen förenklar processen med personalisering och innehållsförbättring genom att du kan finjustera innehållet genom att beskriva vad du vill generera."

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_context"
>title="Ladda upp varumärkesresurs"
>abstract="På menyn Överför varumärkesresurser kan du lägga till alla varumärkesresurser som innehåller innehåll som kan ge ytterligare kontext för AI Assistant i Journey Optimizer eller välja en tidigare överförd resurs. Med det här alternativet får AI Assistant tillgång till allt material som behövs för att förbättra funktionaliteten och relevansen."

>[!CONTEXTUALHELP]
>id="ajo_ai_generation_start"
>title="Adobe Generative AI terms"
>abstract="Du måste godkänna Adobe Experience Cloud Generative AI User Guidelines. Granska alla utdata från den här funktionen för att se om de är korrekta och se till att de passar ditt sätt att arbeta."
>additional-url="https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html" text="Adobe Generative AI User Guidelines"

>[!INFO]
>
>Fördjupa dig i en praktisk upplevelse med [vår förhandsvisning av aktiva funktioner](https://experienceleague.adobe.com/sv/apps/journey-optimizer/ai-assistant-content-accelerator){target="_blank"}, som är utformad för att du ska kunna utforska dess funktioner först och till fullo förstå dess funktioner.


AI Assistant i Adobe Journey Optimizer, som drivs av Microsoft Azure OpenAI och Adobe Firefly, ger proaktiva förslag på innehållsvarianter för text och bilder. Den här nya funktionen tillhandahåller en **promptbaserad text- och bildgenerering**. Bildgenerering hanteras med Adobe Firefly.

AI Assistant har stöd för generering **på flera språk**, vilket gör att du kan nå och engagera olika globala målgrupper. AI Assistant finns på följande språk:

<table style="table-layout:fixed; margin-top: 0px; margin-bottom: 0px;">
  <tbody>
    <tr style="border: 0;background-color: #FFFFFF;">
      <td>
        <ul>
          <li>Franska</li>
          <li>Spanska</li>
          <li>Tyska</li>
          <li>Italienska</li>
        </ul>
      </td>
      <td>
        <ul>
          <li>Japanska</li>
          <li>Svenska</li>
          <li>Nederländska</li>
          <li>Norska</li>
        </ul>
      </td>
      <td>
      </td>
    </tr>
  </tbody>
</table>

Använd AI Assistant i Adobe Journey Optimizer för att optimera budskapets genomslagskraft genom att experimentera med olika förtexter och bilder. Generera flera varianter och skapa ett experiment för att jämföra dem. Genom att utnyttja **Journey Optimizer Content Experiment** kan du definiera flera meddelandebehandlingar för att mäta vilken som fungerar bäst för målgruppen. Du kan välja att variera leveransinnehållet eller ämnet. Meddelandemålgruppen fördelas slumpmässigt till varje behandling för att avgöra vilken som fungerar bäst med det angivna måttet. Läs mer om Content Experiment i [det här avsnittet](../content-management/content-experiment.md).

>[!IMPORTANT]
>
>* Innan du börjar använda den här funktionen bör du läsa upp relaterade [säkerhetsutkast och begränsningar](#generative-guardrails).
>
>
>* Du måste godkänna ett [användaravtal](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"} innan du kan använda AI Assistant i Adobe Journey Optimizer. Kontakta din Adobe-representant om du vill veta mer.

## Få tillgång till AI-assistenten {#generative-access}

För att få åtkomst till AI Assistant i Adobe Journey Optimizer-funktionen måste användarna ha behörighet att **generera innehåll**. [Läs mer](../administration/permissions.md)

+++  Lär dig hur du tilldelar behörigheter för innehållsgenerering

1. Gå till fliken **Roller** i produkten **Behörigheter** och välj önskad **roll**.

1. Klicka på **Redigera** om du vill ändra behörigheterna.

1. Lägg till resursen **AI Assistant** och välj sedan **Generera innehåll** i listrutan.

   ![](assets/gen-ai-role.png){zoomable="yes"}

1. Klicka på **Spara** om du vill använda ändringarna.

   Alla användare som redan har tilldelats den här rollen får sina behörigheter automatiskt uppdaterade.

1. Om du vill tilldela den här rollen till nya användare går du till fliken **Användare** på kontrollpanelen **Roller** och klickar på **Lägg till användare**.

1. Ange användarens namn, e-postadress eller välj i listan och klicka sedan på **Spara**.

1. Om användaren inte har skapats tidigare, se [den här dokumentationen](https://experienceleague.adobe.com/sv/docs/experience-platform/access-control/abac/permissions-ui/users).

Användaren får ett e-postmeddelande med instruktioner om hur du kommer åt instansen.

+++

## Skyddsritningar och begränsningar {#generative-guardrails}

Allmänna riktlinjer för hur du använder AI Assistant i Adobe Journey Optimizer för e-postgenerering anges nedan:

* Kvaliteten på det genererade innehållet påverkas i hög grad av det marknadsföringsmål / den uppmaning du anger. Använd en väldefinierad uppmaning för GenAI-modellen att tolka korrekt. 
* Ladda upp varumärkesresurser för att få korrekt varumärkesinnehåll. Annars baseras innehållet på offentligt tillgänglig information. Det överförda innehållet kan ha följande format: PDF-, JPEG-, PNG- eller ZIP-filer (med filformat som stöds).
* Den maximala storleken för överförda varumärkesresurser är 50 MB. Större filer eller mycket bilder kan fungera, men bearbetningstiden ökar.
* Använd en varumärkesspecifik eller anpassad mall för att skapa e-postinnehåll med hjälp av AI Assistant i Adobe Journey Optimizer. E-postmallar med upp till 8-10 bilder rekommenderas.
* Var noga med att rapportera eventuella problematiska utdata med ikonerna för tummen uppåt, tummen nedåt eller flagga när du väljer varianter.
* Din användning av AI Assistant regleras av Adobe Experience Cloud Generative AI User Guidelines. [Läs mer](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html)
* Som en del av Adobe strävan att främja transparens i användningen av generativa AI-verktyg för att skapa media kommer Adobe att tillämpa Content Credentials när innehåll eller projekt som innehåller en Firefly-genererad mediefil hämtas eller exporteras. [Läs mer](https://helpx.adobe.com/se/firefly/using/content-credentials.html)

Följande begränsningar gäller för AI Assistant i Adobe Journey Optimizer:

* Endast tillgängligt för e-post-, push-, webb- och SMS-kanaler.
* GenAI-innehåll kanske inte alltid är korrekt: dela med dig av dina synpunkter så att våra tekniker kan förfina modellerna.
* Ni kan överföra flera varumärkesresurser, men ni kan bara utnyttja en för en viss generation.


## Funktioner för innehållsgenerering i AI Assistant {#generative-features}


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="generative-full-content.md">
<img alt="Generering av fullt innehåll" src="assets/do-not-localize/email-genai.jpeg">
</a>
<div>
<a href="generative-full-content.md"><strong>Generera fullständigt innehåll</strong></a>
</div>
<p>
</td>
<td>
<a href="generative-text.md">
<img alt="Textgenerering" src="assets/do-not-localize/text-genai.jpeg">
</a>
<div><a href="generative-text.md"><strong>Generera text</strong>
</div>
<p>
</td>
<td>
<a href="generative-image.md">
<img alt="Bildgenerering" src="assets/do-not-localize/image-genai.jpeg">
</a>
<div>
<a href="generative-image.md"><strong>Generera bilder</strong></a>
</div>
<p></td>
</tr></table>

## Ytterligare resurser

* **[Generativa experiment](generative-experimentation.md)** - Förstå hur AI-genererat innehåll kombineras med experiment.
* **[Användningsexempel för AI-assistenten](generative-uc.md)** - Lär dig mer med användningsexempel om hur du använder AI-assistenten
* **[AI Assistant-självstudiekurser](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/introduction-to-journey-optimizer/ai-assistant){target="_blank"}** - Utforska stegvisa videokurser om AI Assistant-funktioner och metodtips.
