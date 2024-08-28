---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera mobil och webb
description: Lär dig hur du konfigurerar och övervakar mobil- och webbkanaler
feature: Surface, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: kanal, yta, teknik, parametrar, optimerare
hide: true
hidefromtoc: true
source-git-commit: 4a089308cfc2fa90cc4c0a6baa15a89598e8edd6
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Kom igång med konfiguration av guidade kanaler {#set-mobile-config}

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_name"
>title="Mobil- och webbkonfigurationsnamn"
>abstract="Ange namnet på din mobil- eller webbkonfiguration. Det här namnet kommer att användas för alla resurser som skapas automatiskt med inställningen för guidad kanal."

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_validate_assurance"
>title="Validera med Assurance"
>abstract="Adobe Experience Platform Assurance är inbäddat i det här arbetsflödet så att du kan inspektera SDK-implementeringen samt simulera och validera programhändelser."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/assurance/home" text="Adobe Experience Platform Assurance - översikt"


Denna installation underlättar snabb konfigurering av marknadsföringskanaler och säkerställer att alla nödvändiga resurser finns tillgängliga i Experience Platform, Journey Optimizer och Data Collection. På så sätt kan marknadsföringsteamet omedelbart börja med att skapa kampanjer och resor.

För att implementera detta effektivt är det viktigt att en medlem i organisationen med behörighet och teknisk möjlighet att ändra webbplats eller mobilkod övervakar konfigurationen.

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
++

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="set-mobile-android.md">
<img alt="Lead" src="assets/do-not-localize/config-android.jpeg">
</a>
<div><a href="set-mobile-android.md"><strong>Konfigurera Android-mobilkonfiguration</strong>
</div>
<p>
</td>
<td>
<a href="set-mobile-ios.md">
<img alt="Sällan" src="assets/do-not-localize/config-ios.jpeg">
</a>
<div>
<a href="set-mobile-ios.md"><strong>Konfigurera iOS-mobilkonfiguration</strong></a>
</div>
<p></td>
<td>
<a href="set-mobile-web.md">
<img alt="Validering" src="assets/do-not-localize/config-web.jpeg">
</a>
<div>
<a href="set-mobile-web.md"><strong>Konfigurera webbkonfiguration</strong></a>
</div>
<p>
</td>
</tr></table>
