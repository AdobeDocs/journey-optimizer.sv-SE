---
title: Förhandsgranska och testa ditt innehåll
description: Lär dig hur du förhandsgranskar och testar innehåll.
feature: Preview, Proofs
role: User
level: Beginner
exl-id: 736fc861-17f2-47b7-8635-9afd261ea3a8
source-git-commit: 3f363a006ed25c07f3ea5b516f5fc306b230d029
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 0%

---

# Förhandsgranska och testa ditt innehåll {#preview-test}

>[!CONTEXTUALHELP]
>id="ac_preview_testprofiles"
>title="Kontrollera hur innehållet renderar"
>abstract="När innehållet har definierats kan du använda testprofiler för att förhandsgranska det och kontrollera om återgivningen är korrekt enligt den kanal du använder."

>[!CONTEXTUALHELP]
>id="ajo_preview_simulate"
>title="Kontrollera hur innehållet renderar"
>abstract="När innehållet har definierats kan du förhandsgranska det och kontrollera om återgivningen är korrekt enligt den kanal du använder."

När innehållet har definierats kan du förhandsgranska innehållet innan du skickar meddelandet. Detta är ett viktigt steg för att säkerställa att det är korrekt, men även fritt från fel, både i innehålls- och personaliseringsinställningarna.

Du kan också skicka testleveranser av e-postmeddelanden till specifika mottagare eller prenumeranter för testning och validering, och kontrollera återgivningen i populära dator-, mobil- och webbaserade klienter. Dessutom kan du utvärdera allmänna aspekter av innehållskvaliteten, som läsbarhet och effektivitet. [Läs mer om validering av innehållskvalitet](brands-score.md#validate-quality)

Alla dessa åtgärder kan utföras med knappen **[!UICONTROL Simulate Content]**, som du kommer åt från redigeringsfönstret i ditt meddelande, eller från e-post- och webbdesigners för e-post- och webbkanalerna.

![](../email/assets/email-preview-button.png)

## Testa med data för testprofiler eller exempelindata {#methods}

Journey Optimizer tillhandahåller två upplevelser för att testa ert innehåll:

* **Testa innehåll med testprofildata**

  Du kan använda testprofiler för att förhandsgranska ditt innehåll, skicka e-postkorrektur och kontrollera e-poståtergivningen. Om du har lagt till anpassade fält kan du kontrollera hur de visas med testprofildata. Mer information finns i följande avsnitt:

  ➡️ [Välj testprofiler](test-profiles.md)
➡️ [Förhandsgranska med testprofiler ](preview.md)
➡️ [Skicka e-postkorrektur](proofs.md)
➡️ [Kontrollera e-poståtergivning](rendering.md)
➡️ [Förhandsgranska och korrekturgranska din e-post (video) ](#video-preview)

* **Testa innehållsvariationer med exempelindata**

  Med [!DNL Journey optimizer] kan du förhandsgranska och skicka korrektur för olika varianter av ditt innehåll med exempelindata som har överförts från en CSV-/JSON-fil, eller lagts till manuellt.

  Alla profilattribut som används i ditt innehåll för personalisering identifieras automatiskt av systemet och kan användas för dina tester för att skapa flera varianter.

  ➡️ [Simulera innehållsvariationer](../test-approve/simulate-sample-input.md)

## Måste läsas

* **Nödvändig behörighet** - Du måste ha behörigheten **[!DNL Manage Simulate Content]** inkluderad i produktprofilen **[!DNL Content Library Manager]**. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager).

  Om du vill skicka korrektur måste du ha behörighet **Godkänn och publicera** för den specifika resurs (kampanj eller resa) som är associerad med e-postmeddelandet. Om du dessutom vill skicka korrektur på en resa måste du ha behörighet **Publiceringsresa**. [Läs mer om behörigheter](../administration/ootb-permissions.md).

* **Personalization med kontextdata** - När du förhandsgranskar ett meddelande eller skickar korrektur visas endast profilpersonaliseringsdata. Personalization baserat på kontextdata, t.ex. händelseinformation, kan bara testas i samband med en resa. Lär dig hur i [det här användningsfallet](../personalization/personalization-use-case.md).

* **Förhandsgranska innehåll med flera villkorsstyrda varianter** - När du simulerar eller återger korrektur för e-postmeddelanden som innehåller flera villkorsstyrda varianter kan Journey Optimizer kräva mer bearbetningstid. Om du får timeout eller felmeddelanden kan du minska det totala antalet varianter eller förenkla villkorliga regler. Läs mer om villkorligt innehåll på [den här sidan](../personalization/dynamic-content.md).

## Instruktionsvideo {#video-preview}

Lär dig hur du använder testprofiler för att testa e-poståtergivning i inkorgar, förhandsgranska dina personaliserade e-postmeddelanden mot testprofiler och skicka korrektur.

>[!VIDEO](https://video.tv.adobe.com/v/3425026?quality=12)
