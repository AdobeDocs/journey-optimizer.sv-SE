---
solution: Journey Optimizer
product: journey optimizer
title: Felsöka anpassade åtgärder
description: Lär dig hur du felsöker en anpassad åtgärd
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Engineer, Admin
level: Experienced
keywords: åtgärd, tredje part, anpassad, resor, API
exl-id: c0bb473a-82dc-4604-bd8a-020447ac0c93
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---

# Felsöka anpassade åtgärder {#troubleshoot-a-custom-action}

Du kan testa dina anpassade åtgärder genom att skicka API-anrop från administrationsdelen av Journey Optimizer användargränssnitt. Den här funktionen hjälper dig att felsöka anpassade åtgärder före eller efter att du har använt dem under en resa.

Som administratör kan du använda funktionen **[!UICONTROL Send test request]** för att validera dina anpassade åtgärdskonfigurationer genom att göra riktiga API-anrop direkt från Adobe Journey Optimizer. Med den här funktionen säkerställs att begärandestrukturen, rubrikerna, autentiseringen och nyttolasterna är korrekt formaterade innan de används under en resa.

![](assets/send-test-request.png){width="70%" align="left"}

Använd den här funktionen för att effektivisera testnings- och valideringsprocessen och säkerställa att anpassade åtgärder fungerar korrekt på liveresor.

## Förhandskrav {#troubleshoot-custom-action-prereq}

Om du vill använda funktionen **[!UICONTROL Send test request]** måste en **anpassad åtgärd** vara förkonfigurerad med en URL, rubriker och autentiseringsinställningar.

För att administratörerna ska kunna använda den här funktionen krävs följande behörigheter:

* Användare måste ha behörighet **[!DNL Manage journeys events, data sources and actions]**.
* Den här behörigheten ingår i rollen *Reseadministratörer*.
* Enbart behörigheten **[!DNL View journeys events]** är inte tillräcklig.

Läs mer om resebehörigheter i [det här avsnittet](../administration/high-low-permissions.md#journey-capability).

## Så här använder du funktionen Skicka testbegäran {#troubleshoot-custom-action-use}

Så här testar du en anpassad åtgärd:

1. Navigera till konfigurationsskärmen **Åtgärder** och välj en anpassad åtgärd.
1. Klicka på knappen **[!UICONTROL Send test request]** längst ned i åtgärdskonfigurationsfönstret.
   ![Skicka testbegärandeknapp på åtgärdskonfigurationspanelen](assets/test-request.png){width="70%" align="left"}
1. I popup-fönstret kan du ange frågeparametrar:

   * Om den anpassade åtgärdsmetoden **är GET** krävs ingen nyttolast.
   * Om den anpassade åtgärdsmetoden **är POST** måste du ange en JSON-nyttolast.

     >[!NOTE]
     >
     >Adobe Journey Optimizer genererar ett fel om strukturen för denna JSON är felaktig, men gör det inte om det finns en felmatchning med en datatyp. Det finns till exempel inget fel om en heltalsparameter används för vad som ska vara en sträng.

   * Om autentisering är definierad uppmanas du att ange autentiseringsinformation.

1. Klicka på **Skicka** för att köra begäran.
1. Svaret från API:t, inklusive rubriker och statuskoder, visas i gränssnittet.

## Autentiseringshantering {#troubleshoot-custom-action-auth}

När en anpassad åtgärd innehåller autentisering kräver Adobe Journey Optimizer att användaren anger autentiseringsinformation för varje testbegäran:

* **Grundläggande autentisering:** Användaren måste ange *lösenordet*.
* **API-nyckelautentisering:** Användaren måste ange API-nyckeln *värde*.
* **Anpassad autentisering:** Användaren måste ange autentiseringsparametrarna i begäran *bodyParam*. Två avsnitt läggs till i det här fallet: **Autentiseringsbegäran** och **Autentiseringssvar**.

## Viktiga fördelar {#troubleshoot-custom-action-benefits}

Som Journey Optimizer-administratör kan du även använda externa verktyg (t.ex. Postman) för att testa dina anpassade åtgärder. De viktigaste fördelarna med felsökningsfunktionen i produkten jämfört med en extern testning är följande:

* Testbegäran körs av **AJO Journey**, vilket innebär:

   * Exakt begärandestruktur (inklusive Adobe Journey Optimizer-specifika rubriker) används.
   * Källans IP och rubriker matchar dem som används i direktresor.

* Funktionen **[!UICONTROL Send test request]** kan användas för felsökning av **direktresor** eftersom den anpassade åtgärden redan har distribuerats.

* Denna testfunktion i produkten eliminerar behovet av att manuellt kopiera konfigurationsinformation mellan verktyg, vilket minskar risken för fel.

## Felsökning {#troubleshoot-custom-action-check}

Om begäran misslyckas kan du kontrollera:

* Autentiseringsuppgifterna som angavs i testet.
* Begärandemetoden (GET kontra POST) och motsvarande nyttolast.
* API-slutpunkten och -rubrikerna som definieras i den anpassade åtgärden.
* Använd svarsdata för att identifiera potentiella felkonfigurationer.

## Ytterligare resurser

Bläddra i avsnitten nedan om du vill veta mer om hur du konfigurerar och använder dina anpassade åtgärder:

* [Kom igång med anpassade åtgärder](../action/action.md) - Lär dig vad som är en anpassad åtgärd och hur de hjälper dig att ansluta till tredjepartssystem
* [Konfigurera dina anpassade åtgärder](../action/about-custom-action-configuration.md) - Lär dig hur du skapar och konfigurerar en anpassad åtgärd
* [Använd anpassade åtgärder](../building-journeys/using-custom-actions.md) - Lär dig hur du använder anpassade åtgärder på dina resor
* [Skicka samlingar till anpassade åtgärdsparametrar](../building-journeys/collections.md) - Lär dig hur du skickar en samling i anpassade åtgärdsparametrar som fylls i dynamiskt vid körning

