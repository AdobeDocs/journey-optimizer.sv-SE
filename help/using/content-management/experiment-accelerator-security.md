---
solution: Journey Optimizer
product: journey optimizer
title: Experimentation Accelerator
description: Dataanvändning i AI med Experimentation Accelerator
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: innehåll, experimentera, multipelt, målgrupp, behandling
hide: true
hidefromtoc: true
source-git-commit: 50dcdd30e21fe1b12d502a2b9c478f4ceb546c49
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 0%

---

# Dataanvändning i AI med Experimentation Accelerator{#experiment-accelerator-security}

>[!BEGINSHADEBOX]

* [Kom igång med Experimentation Accelerator](experiment-accelerator.md)
* [Dataanvändning i AI med Experimentation Accelerator](experiment-accelerator-security.md)
* [Experimentation Accelerator bästa praxis](experiment-accelerator-best-practices.md)
* [Monitor Experiments](experiment-accelerator-monitor.md)
* [Experimentationsmått](experiment-accelerator-metrics.md)

>[!ENDSHADEBOX]

Med **Adobe Journey Optimizer Experimentation Accelerator** kan du automatiskt upptäcka insikter och rekommendera möjligheter att förbättra dina experiment- och experimentprogram. Lösningen utnyttjar AI och Machine Learning för att ge dessa rekommendationer. Den här satsen klargör hur dina kunders data används i **Experimentation Accelerator**.

## Vilka data använder experimenteringsacceleratorn?

Det finns för närvarande tre typer av data som används av **Experimentationsacceleratorn**:

* **Experimentmetadata**: experimentets namn, definitionen av målgruppen som användes i experimentet och behandlingarna i experimentet, t.ex. namn, delade procentsatser, plats eller yta som experimentet utförs på.

* **Prestanda för behandlingarna**: antal personer, medelvärde för framgångsmått och standardavvikelse för varje behandling.

* **Innehåll i behandlingen**: den återgivna HTML-filen och skärmbilden av behandlingen så som den skulle visas för en användare på webbplatsen.

## Vad gör experimenteringsacceleratorn med dessa data?

**Experimentationsacceleratorn** tar innehållet för varje behandling och skapar en inbäddning, d.v.s. en matematisk representation av innehållet. Sedan korrelerar inbäddningen med behandlingens prestanda. Denna process gör att innehållsattribut som har utförts bäst för framtida bruk kan extraheras. Dessa attribut matas sedan in i en stor språkmodell från Adobe, som konverterar dem till läsbara satser som används för att generera insikter och föreslå möjligheter.

## Vilka begränsningar har Experimentation Accelerator för de data som används?

Varje kund tilldelas en viss organisation och sandlåda. En dedikerad modell tränas för varje sandlåda. När en sandlåda tas bort tas alla relaterade data, signaler och modeller bort permanent.

* Vi använder bara kunddata för att utbilda eller finjustera modellen från den kunden.

* Vi blandar aldrig kunder för att utbilda eller finjustera en modell.

## Kommer Adobe modeller eller AI att förändra ett varumärkes användarupplevelse automatiskt?

Nej. **Experimentation Accelerator** kan bara göra eq-rekommendationer för vad som kan ändras och hur det kan ändras. Endast användare som har behörighet att ändra upplevelsen med Journey Optimizer eller Target kan agera på dessa rekommendationer. Alla rekommendationer kan granskas och redigeras innan de skickas ut.

## Finns det någon risk för deras data eller systemstabilitet?

**Experimentation Accelerator** importerar och analyserar endast data, vilket ger insikter och rekommendationer för framtida testning. Den har inte åtkomst till att ändra några testinställningar. Alla förslag som genereras i verktyget skickas till Target och Journey Optimizer för implementering, så att ingen påverkan på kundens aktuella aktiviteter säkerställs.
