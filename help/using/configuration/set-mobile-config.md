---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera mobil och webb
description: Lär dig hur du konfigurerar och övervakar mobil- och webbkanaler
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: kanal, yta, teknik, parametrar, optimerare
exl-id: 846e0d11-798b-4f3b-80db-848a17d32830
source-git-commit: d793d9eccde3b0b548e778040bdcd8817e80c90a
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 3%

---

# Kom igång med konfiguration av guidade kanaler {#set-mobile-config}

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_name"
>title="Mobil- och webbkonfigurationsnamn"
>abstract="Ange namnet på din mobil- eller webbkonfiguration. Det här namnet kommer att användas för alla resurser som skapas automatiskt med inställningen för guidad kanal."

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_validate_assurance"
>title="Validera med Assurance"
>abstract="Adobe Experience Platform Assurance är inbäddat i detta arbetsflöde för att hjälpa dig inspektera implementeringen av SDK samt simulera och validera programhändelser."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/assurance/home" text="Adobe Experience Platform Assurance - översikt"

**Guided Channel Setup** är ett smidigt arbetsflöde i Adobe Journey Optimizer som hjälper dig att snabbt konfigurera marknadsföringskanaler för mobiler och webben. Den finns under **Administration** > **Kanaler** > **Kanalkonfiguration** och automatiserar skapandet av viktiga resurser - som taggegenskaper, datastreams och kanalkonfigurationer - i Adobe Experience Platform, Journey Optimizer och Data Collection. I stället för att konfigurera varje komponent manuellt följer ni ett guidat flöde som ställer in allt åt er, så att marknadsföringsteamet kan börja skapa meddelanden i appen, push-meddelanden och webbupplevelser utan dröjsmål.

Guided Channel Setup har stöd för följande plattformar och kanaler.

>[!BEGINTABS]

>[!TAB iOS]

**SDK:** Swift by Apple

**Kanaler:** Mobil-i-app, mobilpush-meddelande

>[!TAB Android]

**SDK:** Kotlin

**Kanaler:** Mobil-i-app, mobilpush-meddelande

>[!TAB Webb]

**SDK:** JavaScript

**Kanaler:** Web Basic

>[!ENDTABS]

Observera att för varje plattform som du vill konfigurera måste du skapa en separat konfiguration. Det beror på att varje program kräver en unik kanalkonfiguration, vilket ger flexibilitet att avgöra vilka kanaler du vill ha för varje plattform.

## Förutsättningar {#prereq}

* För att implementera detta effektivt är det viktigt att en medlem i organisationen med behörighet och teknisk möjlighet att ändra webbplats eller mobilkod övervakar konfigurationen.

  Nedan visas de behörigheter som krävs för att köra installationen av den guidade kanalen.

  +++ Nödvändiga behörigheter

  <table>
    <thead>
      <tr>
        <th><strong>Lösning</strong></th>
        <th><strong>Behörigheter</strong></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <p>Datainsamling</p>
        </td>
        <td>
          <ul>
            <li>Företagsrättigheter &gt; Egenskaper</li>
            <li>Egenskaper: Utveckla, publicera, hantera tillägg och miljöer</li>
            <li>Appytor: Hantera appkonfiguration</li>
         </ul>
        </td>
      </tr>
      <tr>
        <td>
          <p>Adobe Experience Platform</p>
        </td>
        <td>
        <ul>
            <li>Datainsamling: Hantera datastreams</li>
           <li>Sandlåda: bevilja åtkomst till sandlådor</li>
            <li>Hantera segment: läsa, skapa, redigera och ta bort segmentdefinitioner</li>
            <li>Hantera profiler: läsa, skapa, redigera och ta bort profiler</li>
            <li>Läs datauppsättningar: skrivskyddad åtkomst till datauppsättningar</li>
            <li>Läsa scheman: skrivskyddad åtkomst till scheman</li>
            <li>Namnutrymme för läsidentitet: skrivskyddad åtkomst till namnutrymme för identitet</li>
          </ul>
        </td>
      </tr>
      <tr>
        <td>
         <p>Adobe Journey Optimizer</p>
        </td>
        <td>
          <p>Kampanjer: Hantera och publicera kampanjer</p>
        </td>
      </tr>
    </tbody>
  </table>

  +++

* Om du använder konfigurationsalternativet Befintlig kontrollerar du att du använder följande tilläggsversioner för Adobe Experience Platform Mobile SDK. Mer information om SDK-konfigurationen, inklusive nödvändiga beroenden och initieringskod, finns i [följande dokumentation](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/install-sdks).

  För Android

   * Mobile Core v3.1.0 eller senare
   * Adobe Journey Optimizer v3.1.0 eller senare

  För iOS

   * Mobile Core v5.2.0 eller senare
   * Adobe Journey Optimizer v5.1.1 eller senare

## Automatiskt skapade resurser {#auto-create-resources}

Guided Channel Setup förenklar den snabba konfigurationen av marknadsföringskanaler och gör alla nödvändiga resurser tillgängliga i Experience Platform-, Journey Optimizer- och Data Collection-apparna. På så sätt kan marknadsföringsteamet snabbt börja skapa kampanjer och resor. Nedan visas en lista över resurser som genereras automatiskt och konfigureras som en del av inställningen för guidad kanal.

Bläddra bland flikarna nedan för att få tillgång till en omfattande lista över alla resurser som genereras automatiskt:

>[!BEGINTABS]

>[!TAB iOS]

Nedan visas en omfattande lista med alla resurser som skapats på skärmen **Konfigurationsinformation** för den inledande **-konfigurationen när du klickar på** Skapa resurser automatiskt **.**

<table>
  <thead>
  <tr>
  <th><strong>Lösning</strong></th>
  <th><strong>Automatiskt skapade resurser</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>Taggar</p>
  </td>
  <td>
  <ul>
  <li>Egenskapen Mobile-tagg</li>
  <li>Regler</li>
  <li>Dataelement</li>
  <li>Bibliotek</li>
  <li>Miljö (staging, produktion, utveckling)</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Tagg Extensions</p>
  </td>
  <td>
  <ul>
  <li>Adobe Experience Platform Edge Network</li>
  <li>Adobe Journey Optimizer</li>
  <li>AEP Assurance</li>
  <li>Godkännande (med standardprinciper för samtycke aktiverat)</li>
  <li>Identitet (med standard-ECID, med standardregler för sammanfogning)</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>Assurance Session</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Dataströmmar</p>
  </td>
  <td>
  <p>Datastream med tjänster</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Experience Platform</p>
  </td>
  <td>
  <ul>
  <li>Datauppsättning</li>
  <li>Schema</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

Nedan finns en omfattande lista med alla resurser som skapats på skärmen **Lägg till kanaler** för **kanalkonfigurationen**.

<table>
  <thead>
  <tr>
  <th><strong>Lösning</strong></th>
  <th><strong>Automatiskt skapade resurser</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>Journey Optimizer</p>
  </td>
  <td>
  <ul>
  <li>Kanalkonfiguration</li>
  <li>Överför push-autentiseringsuppgifter (endast push-meddelanden för mobiler)</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

>[!TAB Android]

Nedan visas en omfattande lista med alla resurser som skapats på skärmen **Konfigurationsinformation** för den inledande **-konfigurationen när du klickar på** Skapa resurser automatiskt **.**

<table>
  <thead>
  <tr>
  <th><strong>Lösning</strong></th>
  <th><strong>Automatiskt skapade resurser</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>Taggar</p>
  </td>
  <td>
  <ul>
  <li>Egenskapen Mobile-tagg</li>
  <li>Regler</li>
  <li>Dataelement</li>
  <li>Bibliotek</li>
  <li>Miljö (staging, produktion, utveckling)</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Tagg Extensions</p>
  </td>
  <td>
  <ul>
  <li>Adobe Experience Platform Edge Network</li>
  <li>Adobe Journey Optimizer</li>
  <li>AEP Assurance</li>
  <li>Godkännande (med standardprinciper för samtycke aktiverat)</li>
  <li>Identitet (med standard-ECID, med standardregler för sammanfogning)</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>Assurance Session</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Dataströmmar</p>
  </td>
  <td>
  <p>Datastream med tjänster</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Experience Platform</p>
  </td>
  <td>
  <ul>
  <li>Datauppsättning</li>
  <li>Schema</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

Nedan finns en omfattande lista med alla resurser som skapats på skärmen **Lägg till kanaler** för **kanalkonfigurationen**.

<table>
  <thead>
  <tr>
  <th><strong>Lösning</strong></th>
  <th><strong>Automatiskt skapade resurser</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>Journey Optimizer</p>
  </td>
  <td>
  <ul>
  <li>Kanalkonfiguration</li>
  <li>Överför push-autentiseringsuppgifter (endast push-meddelanden för mobiler)</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

>[!TAB Webb]

Nedan visas en omfattande lista med alla resurser som skapats på skärmen **Konfigurationsinformation** för den inledande **-konfigurationen när du klickar på** Skapa resurser automatiskt **.**

<table>
  <thead>
  <tr>
  <th><strong>Lösning</strong></th>
  <th><strong>Automatiskt skapade resurser</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>Taggar</p>
  </td>
  <td>
  <ul>
  <li>Egenskapen Mobile-tagg</li>
  <li>Regler</li>
  <li>Dataelement</li>
  <li>Bibliotek</li>
  <li>Miljö (staging, produktion, utveckling)</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Tagg Extensions</p>
  </td>
  <td>
  <ul>
  <li>Adobe Experience Platform Edge Network</li>
  <li>Adobe Journey Optimizer</li>
  <li>AEP Assurance</li>
  <li>Godkännande (med standardprinciper för samtycke aktiverat)</li>
  <li>Identitet (med standard-ECID, med standardregler för sammanfogning)</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>Assurance Session</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Dataströmmar</p>
  </td>
  <td>
  <p>Datastream med tjänster</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Experience Platform</p>
  </td>
  <td>
  <ul>
  <li>Datauppsättning</li>
  <li>Schema</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

>[!ENDTABS]

