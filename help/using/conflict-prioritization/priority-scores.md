---
title: Tilldela prioritetspoäng till resor och kampanjer
description: Lär dig hur du tilldelar prioritetspoäng till resor och kampanjer.
role: User
level: Beginner
badge: label="Begränsad tillgänglighet"
source-git-commit: 8b1ae663accf6b6c049dc7cc2a427811369a42bc
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 0%

---


# Tilldela prioritetspoäng till resor och kampanjer {#priority}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_priority"
>title="Prioritet"
>abstract="Tilldela kampanjens prioritetspoäng. Prioritet är viktigt för att prioritera en kampanj när det finns en begränsning, till exempel en frekvensbegränsning. Ange ett numeriskt värde (från 0-100). Observera att ju högre tal desto högre prioritet. I situationer där två kampanjer har samma prioritetspoäng visas den kampanj som aktiverades först."

>[!CONTEXTUALHELP]
>id="ajo_journey_priority"
>title="Prioritet"
>abstract="Tilldela en prioritetspoäng till resan. Prioritet är viktigt för att prioritera en resa när det finns en angiven begränsning, t.ex. en övre frekvensgräns. Ange ett numeriskt värde (från 0 till 100). Observera att ju högre tal desto högre prioritet. I situationer där två resor har samma prioriteringspoäng visas den resa som först aktiverades."

>[!AVAILABILITY]
>
>Konflikter och prioriteringsfunktioner är för närvarande tillgängliga i begränsad tillgänglighet för en viss kundgrupp. Observera att dessa funktioner gradvis kommer att lanseras för fler användare i framtiden. Kontakta ditt kontoteam om du vill bli tillagd i väntelistan för dessa funktioner.

Med Journey Optimizer kan ni tilldela en prioritetspoäng till en resa eller kampanj. Prioritet är viktigt för att prioritera en resa, kampanj eller åtgärd när det finns en begränsning (t.ex. ett frekvenstak). I situationer där en kund är berättigad till många resor, kampanjer eller kommunikationer och du vill vara selektiv vad de ska delta i och ta emot, bör du använda det här fältet.

>[!NOTE]
>
>I kampanjer är prioritetspoäng endast tillgängligt för webben, appar och kodbaserade inkommande kanaler.

➡️ [Upptäck den här funktionen i videon](#video)

Det är viktigt att du tilldelar en prioritetspoäng för inkommande kommunikation, som webben, mobiler och appar. Om du har flera kampanjer med samma kanalkonfiguration (t.ex. en banderoll högst upp på webbsidan) kan det vara problematiskt eftersom bara innehåll från en kampanj kan visas. Prioritetspoängen är den plats där du infogar din inställning för vilken kampanj ska visas när mottagaren kan kvalificera sig för mer än en kampanj.

Om du vill tilldela en prioritetspoäng till en resa eller kampanj anger du ett numeriskt värde (från 0-100) i fältet **[!UICONTROL Priority score]** som finns i resans eller kampanjens egenskaper. Observera att ju högre tal desto högre prioritet. Om ni redigerade den här kampanjen och ville se till att kampanjinnehållet visas ger ni den 100 poäng.

![](assets/priority-score.png)

I situationer där två kampanjer har samma prioritetspoäng visas den kampanj som aktiverades först.

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3435529?quality=12)
