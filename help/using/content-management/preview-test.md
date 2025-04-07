---
title: Förhandsgranska och testa ditt innehåll
description: Lär dig hur du förhandsgranskar och testar innehåll.
feature: Preview, Proofs
role: User
level: Beginner
exl-id: 736fc861-17f2-47b7-8635-9afd261ea3a8
source-git-commit: 47185cdcfb243d7cb3becd861fec87abcef1f929
workflow-type: tm+mt
source-wordcount: '478'
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

## Förhandsgranska och testa {#about}

När innehållet har definierats kan du förhandsgranska innehållet innan du skickar meddelandet. Detta är ett viktigt steg för att säkerställa att det är korrekt, men även fritt från fel, både i innehålls- och personaliseringsinställningarna.

Du kan också skicka testleveranser av e-postmeddelanden till specifika mottagare eller prenumeranter för testning och validering, och kontrollera återgivningen i populära dator-, mobil- och webbaserade klienter.

Alla dessa åtgärder kan utföras med knappen **[!UICONTROL Simulate Content]**, som du kommer åt från redigeringsfönstret i ditt meddelande, eller från e-post- och webbdesigners för e-post- och webbkanalerna.

![](../email/assets/email-preview-button.png)

Observera att du måste ha behörigheten **[!DNL Manage Simulate Content]** inkluderad i produktprofilen **[!DNL Content Library Manager]**. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager).


>[!CAUTION]
>
>* När du förhandsgranskar ett meddelande eller skickar korrektur visas endast profilpersonaliseringsdata. Personalization baserat på kontextdata, t.ex. händelseinformation, kan bara testas i samband med en resa. Lär dig hur du testar personalisering i [det här användningsexemplet](../personalization/personalization-use-case.md).
>
>* När du simulerar eller återger korrektur för e-postmeddelanden som innehåller flera villkorliga varianter kan Journey Optimizer kräva mer bearbetningstid. Om du får timeout eller felmeddelanden kan du minska det totala antalet varianter eller förenkla villkorliga regler. Läs mer om villkorligt innehåll på [den här sidan](../personalization/dynamic-content.md).


## Testa med testprofiler eller exempelindata {#methods}

Du kan förhandsgranska och testa ditt innehåll med:

* **Testprofiler**

  Använd testprofiler för att förhandsgranska ditt innehåll, skicka e-postkorrektur och kontrollera e-poståtergivningen. Om du har lagt till anpassade fält kan du kontrollera hur de visas med testprofildata. Mer information finns i följande avsnitt:

  ➡️ [Välj testprofiler](test-profiles.md)

  ➡️ [Förhandsgranska ditt innehåll med testprofiler](preview.md)

  ➡️ [Skicka e-postkorrektur](proofs.md)

  ➡️ [Kontrollera e-poståtergivning](rendering.md)

  ➡️ [Förhandsgranska och korrekturgranska din e-post (video)](#video-preview)

* **Exempelindata**

  Med [!DNL Journey optimizer] kan du testa olika varianter av ditt innehåll genom att förhandsgranska det och skicka korrektur med exempelindata som har överförts från en CSV-/JSON-fil, eller lagts till manuellt.

  Alla profilattribut som används i ditt innehåll för personalisering identifieras automatiskt av systemet och kan användas för dina tester för att skapa flera varianter.

  ➡️ [Lär dig hur du testar innehåll med exempelindata](../test-approve/simulate-sample-input.md)

  >[!NOTE]
  >
  >Den här funktionen är för närvarande tillgänglig för alla kunder som en offentlig betaversion av enbart meddelandekanalerna för e-post, SMS och push.

## Instruktionsvideo {#video-preview}

Lär dig hur du använder testprofiler för att testa e-poståtergivning i inkorgar, förhandsgranska dina personaliserade e-postmeddelanden mot testprofiler och skicka korrektur.

>[!VIDEO](https://video.tv.adobe.com/v/3425026?quality=12)
