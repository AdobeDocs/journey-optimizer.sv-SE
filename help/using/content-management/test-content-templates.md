---
solution: Journey Optimizer
product: journey optimizer
title: Testa innehållsmallar
description: Lär dig hur du testar återgivningen av vissa mallar för e-postinnehåll
feature: Templates
topic: Content Management
role: User
level: Beginner
exl-id: 01726ab6-f581-4d19-aedd-2541bc0f27c6
source-git-commit: 22a8742bf9000ed1cc8437d7ac89747276284dbf
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Testa mallar för e-postinnehåll {#test-template}

Du kan testa återgivningen av vissa e-postmallar, oavsett om de har skapats från grunden eller från ett befintligt innehåll. Följ stegen nedan för att göra det.

1. Öppna listan med innehållsmallar via menyn **[!UICONTROL Content Management]** > **[!UICONTROL Content Templates]** och välj en e-postmall.

1. Klicka på **[!UICONTROL Edit content]** i **[!UICONTROL Template properties]**.

1. Klicka på **[!UICONTROL Simulate Content]** och välj en testprofil för att kontrollera återgivningen. [Läs mer](../content-management/preview-test.md)

   ![](assets/content-template-stimulate.png)

   >[!NOTE]
   >
   >I [!DNL Journey optimizer] kan du också testa olika varianter av dina innehållsmallar genom att förhandsgranska dem och skicka korrektur med exempelindata som har överförts från en CSV-/JSON-fil, eller lagts till manuellt. [Lär dig hur du simulerar innehållsvariationer](../test-approve/simulate-sample-input.md)

1. Du kan skicka ett bevis för att testa ditt innehåll och få det godkänt av vissa interna användare innan du använder det under en resa eller i en kampanj.

   * Om du vill göra det klickar du på knappen **[!UICONTROL Send proof]** och följer stegen som beskrivs i [det här avsnittet](../content-management/proofs.md).

   * Innan du skickar korrekturet måste du välja den [e-postkonfiguration](../configuration/channel-surfaces.md) som ska användas för att testa ditt innehåll.

     ![](assets/content-template-stimulate-proof-surface.png)

>[!CAUTION]
>
>Spårning stöds för närvarande inte vid testning av mallar för e-postinnehåll, vilket innebär att spårningshändelser, UTM-parametrar och länkar på landningssidor inte kommer att vara effektiva i korrektur som skickas från en mall. Om du vill testa spårning [använder du innehållsmallen](../email/use-email-templates.md) i ett e-postmeddelande och skickar ett korrektur med testprofiler, eller exempelindata som överförts från en CSV-/JSON-fil, eller läggs till manuellt. [Lär dig hur du förhandsgranskar och testar innehåll](../content-management/preview-test.md)
