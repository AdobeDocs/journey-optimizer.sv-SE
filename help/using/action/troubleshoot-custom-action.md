---
solution: Journey Optimizer
product: journey optimizer
title: Testa en anpassad åtgärd
description: Lär dig hur du felsöker en anpassad åtgärd
badge: label="Begränsad tillgänglighet"
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: åtgärd, tredje part, anpassad, resor, API
source-git-commit: 5ce76bd61a61e1ed5e896f8da224fc20fba74b53
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---


# Felsöka anpassade åtgärder {#troubleshoot-a-custom-action}

>[!AVAILABILITY]
>
>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.
>

## Översikt

Med funktionen **Skicka testbegäran** kan administratörer validera sina anpassade åtgärdskonfigurationer genom att göra riktiga API-anrop direkt från Adobe Journey Optimizer (AJO). Med den här funktionen säkerställs att begärandestrukturen, rubrikerna, autentiseringen och nyttolasterna är korrekt formaterade innan de används under en resa.

![](assets/send-test-request.png){width="70%" align="left"}

## Förhandskrav

- **Administratörsåtkomst krävs:**
   - Användare måste ha behörigheten **Hantera resthändelser, datakällor och åtgärder**.
   - Den här behörigheten ingår i rollen *Reseadministratörer*.
   - Behörigheten **&quot;Visa resthändelser..&quot;** räcker inte.
- En **anpassad åtgärd** måste vara förkonfigurerad med en URL, rubriker och autentiseringsinställningar.

## Så här använder du funktionen Skicka testbegäran

1. Navigera till konfigurationsskärmen **Anpassade åtgärder**.
1. Klicka på knappen **&quot;Skicka testbegäran&quot;**.
1. Ett popup-fönster visas där du kan ange begärandeparametrar:
   - Om den anpassade åtgärdsmetoden **är GET** krävs ingen nyttolast.
   - Om den anpassade åtgärdsmetoden **är POST** måste du ange en JSON-nyttolast.

     >[!NOTE]
     >
     >AJO genererar ett fel om strukturen för denna JSON är felaktig, men inte om det finns en felmatchning med en datatyp. Det finns till exempel inget fel om en heltalsparameter används för vad som ska vara en sträng.

   - Om autentisering är definierad uppmanas du att ange autentiseringsinformation.

1. Klicka på **Skicka** för att köra begäran.
1. Svaret från API:t, inklusive rubriker och statuskoder, visas i gränssnittet.

## Autentiseringshantering

När en anpassad åtgärd innehåller autentisering kräver AJO att användaren anger autentiseringsinformation för varje testbegäran:

- **Grundläggande autentisering:** Användaren måste ange *lösenordet*.
- **API-nyckelautentisering:** Användaren måste ange API-nyckeln *värde*.
- **Anpassad autentisering:** Användaren måste ange autentiseringsparametrarna i begäran *bodyParam*. Två avsnitt som ska slutföras läggs till i det här fallet: **Autentiseringsbegäran** och **Autentiseringssvar**.

## Viktiga skillnader jämfört med externa testverktyg (t.ex. Postman)

- Testbegäran körs av **AJO Journey**, vilket innebär:
   - Exakt begärandestruktur (inklusive AJO-specifika rubriker) används.
   - Källans IP och rubriker matchar dem som används i direktresor.
- Kan användas för felsökning av **direktresor** där den anpassade åtgärden redan är distribuerad.
- Eliminerar behovet av att manuellt kopiera konfigurationsinformation mellan verktyg, vilket minskar risken för fel.

## Felsökning

- Om begäran misslyckas, verifiera:
   - Autentiseringsuppgifterna som angavs i testet.
   - Begärandemetoden (GET kontra POST) och motsvarande nyttolast.
   - API-slutpunkten och -rubrikerna som definieras i den anpassade åtgärden.
- Använd svarsdata för att identifiera potentiella felkonfigurationer.

Den här funktionen effektiviserar testnings- och valideringsprocessen så att anpassade åtgärder fungerar korrekt på AJO-resor.

