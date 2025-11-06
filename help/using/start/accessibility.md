---
solution: Journey Optimizer
product: journey optimizer
title: Tillgänglighetsfunktioner i Journey Optimizer
description: Läs mer om tillgänglighet i Journey Optimizer användargränssnitt
feature: Accessibility
role: User
level: Beginner
exl-id: d971c04c-9b37-4cd7-8a2d-b915e394079b
source-git-commit: 95e50386d4190d0b967d133a327c25ab1681b5c1
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 2%

---

# Tillgänglighet i Journey Optimizer{#accessibility}

Hjälpmedel är en serie funktioner som gör en programprodukt användbar, med så lite ansträngning som möjligt, för användare med visuella, auditiva, kognitiva, motoriska eller andra typer av funktionshinder. Adobe är ledande inom tillgänglighet och stöder framtagning av enastående webbupplevelser genom att uppmuntra utvecklare att producera engagerande material som är tillgängligt för alla användare. Läs mer om Adobe engagemang för tillgänglighet på [Adobe Accessibility-sidan](https://www.adobe.com/accessibility.html){target="_blank"}.

[!DNL Journey Optimizer] följer den internationellt erkända bästa metoden i Web Content Accessibility Guidelines (WCAG) 2.1 Level A och Level AA för att uppnå målet om tillgänglighet. Läs mer i den senaste [Adobe Journey Optimizer Accessibility Conformance Report](https://www.adobe.com/accessibility/compliance/adobe-journey-optimizer.html){target="_blank"}.

>[!NOTE]
>
>Riktlinjer för att utforma hjälpmedelsanpassat innehåll för e-postmeddelanden och landningssidor finns i [det här avsnittet](../email/accessible-content.md).

Tillgänglighetsfunktionerna i [!DNL Adobe Journey Optimizer] ärvs från Adobe Experience Platform:

* Tangentbordstillgänglighet
* Färgkontrast
* Validering av obligatoriska fält

Hjälpmedelsfunktionerna i Adobe Experience Platform är detaljerade [i den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html){target="_blank"}.

Följande vanliga kortkommandon är tillgängliga i [!DNL Journey Optimizer]:

| Åtgärd | Genväg |
| --- | --- |
| Växla mellan element, avsnitt och menygrupper i användargränssnittet | Tabb |
| Gå bakåt mellan element, avsnitt och menygrupper i användargränssnittet | Skift+Tabb |
| Flytta inom avsnitt för att ange fokus till enskilda element | Pil |
| Markera eller rensa ett element som är i fokus | Enter eller mellanslagstangenten |
| Avbryt en markering, komprimera en ruta eller stänga en dialogruta | Esc |

Du kan använda dessa genvägar i specifika områden i användargränssnittet för [!DNL Journey Optimizer]:

<table>
  <thead>
    <tr>
      <th>Gränssnittselement</th>
      <th>Åtgärd</th>
      <th>Genväg</th>
    </tr>
  </thead>
  <tr>
    <td rowspan="8">Researbetsyta med utkaststatus</td>
    <td>Lägg till en aktivitet från den vänstra paletten vid den första tillgängliga positionen, uppifrån och ned</td>
    <td>Dubbelklicka på aktiviteten</td>
  </tr>
  <tr>
    <td>Välj alla aktiviteter</td>
    <td>CTRL + A (Windows)<br/>CMD + A (Mac)</td>
  </tr>
  <tr>
    <td>Ta bort de valda aktiviteterna</td>
    <td>Ta bort eller Backsteg, och bekräfta sedan borttagningen genom att ange</td>
  </tr>
  <tr>
    <td>Zooma in och ut (fokus på arbetsytan eller något av dess underordnade element)</td>
    <td>CTRL +/- (Windows) eller CMD +/- (Mac)</td>
  </tr>  
  <tr>
    <td>Navigera mellan varje aktivitet och bana (fokus på arbetsytan) eller mellan knappar i verktygsfältet (fokus på verktygsfältet)</td>
    <td>PIL-tangenter</td>
  </tr>   
  <tr>
    <td>Flytta fokus till nästa åtgärdbara element på arbetsytan, där verktygsfältet är det första</td>
    <td>Tabb</td>
  </tr>  
  <tr>
    <td>Öppna den högra konfigurationsrutan (fokus på en aktivitet)</td>
    <td>ANGE</td>
  </tr>   
  <tr>
    <td>Flytta en aktivitet på arbetsytan (fokus på en aktivitet)</td>
    <td>SKIFT + piltangenter</td>
  </tr>  
  <tr>
  <td rowspan="3">
  Konfigurationsruta för dessa element:
<ul>
  <li>Aktivitet under en resa</li>
  <li>Händelse</li>
  <li>Datakälla</li>
  <li>Åtgärd</li>
</ul>
  </td>
    <td>Flytta till nästa fält som ska konfigureras</td>
    <td>Tabb</td>
  </tr>
  <tr>
    <td>Spara ändringar och stäng konfigurationsfönstret</td>
    <td>Retur</td>
  </tr>
  <tr>
    <td>Ignorera ändringar och stäng konfigurationsfönstret</td>
    <td>Esc</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>Textfält</td>
    <td>Markera all text i det markerade fältet</td>
    <td>Ctrl + A (Windows)<br/>Kommando + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">Popup-fönster</td>
    <td>Spara ändringarna eller bekräfta åtgärden</td>
    <td>Retur</td>
  </tr>
  <tr>
    <td>Stäng fönstret</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td>Enkel uttrycksredigerare</td>
    <td>Markera och lägga till ett fält</td>
    <td>Dubbelklicka på ett fält</td>
  </tr>
  <tr>
    <td>Bläddra bland XDM-fält</td>
    <td>Markera alla fält i en nod</td>
    <td>Markera den överordnade noden</td>
  </tr>
  <tr>
    <td>Förhandsgranska nyttolast</td>
    <td>Välj nyttolast</td>
    <td>Ctrl + A (Windows)<br/>Kommando + A (Mac)</td>
  </tr>
</table>
