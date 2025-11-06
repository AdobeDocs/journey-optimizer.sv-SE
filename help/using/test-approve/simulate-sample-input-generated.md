---
solution: Journey Optimizer
product: journey optimizer
title: Automatisk generering av innehållsvarianter (Beta)
description: Lär dig generera innehållsvarianter automatiskt med hjälp av AI-baserad simulering.
feature: Email, Email Rendering, Personalization, Preview, Proofs
topic: Content Management
role: User
level: Intermediate
badge: label="Privat beta" type="Informative"
hidefromtoc: true
hide: true
exl-id: 9b7fbd43-3d90-458b-8a2f-0bf0ac5437c3
source-git-commit: 45ebae048a748429a1918326526f3756a3e93c4c
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# Automatisk generering av innehållsvarianter (Beta){#auto-generate-variants}

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst.

[!DNL Journey Optimizer] introducerar AI-baserad simulering som automatiskt kan generera flera varianter för att testa ditt innehåll. Den här funktionen minskar behovet av att skapa varianter manuellt, vilket gör det enklare att validera personaliseringslogiken i komplexa mallar.

När du återger innehåll för simulering eller korrektur analyserar systemet innehållet och identifierar alla personaliseringstoken och förgreningsregler. Det ersätter personaliseringstoken med meningsfulla värden som ger en nästan realistisk förhandsvisning av det slutliga innehållet.

Överväg en e-postmall för finansiella tjänster med förgreningslogik baserad på **investerartyp**, **åldersgrupp**, **civilstånd**, **verifiering av skatte-ID** och **plats**. Utan variantgenerering måste du skapa dussintals varianter manuellt för att validera alla sökvägar. Med autogenererade varianter skapar systemet representativa varianter som automatiskt täcker dessa förhållanden.  Varje genererad variant återges i förhandsgranskningsfönstret och visar exakt vilka block och villkor som används.

## Generera innehållsvarianter

Följ de här stegen för att generera variationer för ditt innehåll och förhandsgranska dem:

1. Öppna ditt innehåll och välj **[!UICONTROL Simulate content]** / **[!UICONTROL Simulate content variations]**.

   ![](assets/simulate-sample.png)

2. Klicka på knappen **[!UICONTROL Generate]**.

   ![](assets/simulate-generate-variant.png)

3. [!DNL Journey Optimizer] genererar automatiskt varianter baserat på identifierade attribut.

4. Granska listan över genererade varianter i den vänstra rutan och välj en variant för att se den anpassade återgivningen i förhandsgranskningsfönstret.

>[!NOTE]
>
>Den här funktionen fungerar på samma sätt som funktionen för simulering av innehållsvariationer. Mer information om simuleringar av innehållsvariationer och tillhörande skyddsutkast och begränsningar finns i det här avsnittet: [Simulera innehållsvariationer](../test-approve/simulate-sample-input.md)
