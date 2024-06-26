---
solution: Journey Optimizer
product: journey optimizer
title: Testa innehållsmallar
description: Lär dig hur du testar återgivningen av vissa mallar för e-postinnehåll
feature: Templates
topic: Content Management
role: User
level: Beginner
source-git-commit: 59c675dd2ac94b6967cfb3a93f74b2016a090190
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%

---

# Testa mallar för e-postinnehåll {#test-template}

Du kan testa återgivningen av vissa e-postmallar, oavsett om de har skapats från grunden eller från ett befintligt innehåll. Följ stegen nedan för att göra det.

1. Få åtkomst till innehållsmalllistan via **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** och välj en e-postmall.

1. Klicka **[!UICONTROL Edit content]** från **[!UICONTROL Template properties]**.

1. Klicka **[!UICONTROL Simulate Content]** och välj en testprofil för att kontrollera återgivningen. [Läs mer](../content-management/preview-test.md)

   ![](assets/content-template-stimulate.png)

1. Du kan skicka ett bevis för att testa ditt innehåll och få det godkänt av vissa interna användare innan du använder det under en resa eller i en kampanj.

   * Klicka på **[!UICONTROL Send proof]** och följer stegen som beskrivs i [det här avsnittet](../content-management/proofs.md).

   * Innan du skickar korrekturet måste du välja [e-postyta](../configuration/channel-surfaces.md) som kommer att användas för att testa ditt innehåll.

     ![](assets/content-template-stimulate-proof-surface.png)

>[!CAUTION]
>
>Spårning stöds för närvarande inte vid testning av mallar för e-postinnehåll, vilket innebär att spårningshändelser, UTM-parametrar och länkar på landningssidor inte kommer att vara effektiva i korrektur som skickas från en mall. Testa spårning [använda innehållsmallen](../email/use-email-templates.md) i ett mejl och [skicka ett bevis](../content-management/preview-test.md#send-proofs).
