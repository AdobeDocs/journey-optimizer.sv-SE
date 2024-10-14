---
title: Tilldela prioritetspoäng till resor och kampanjer
description: Lär dig hur du tilldelar prioritetspoäng till resor och kampanjer.
role: User
level: Beginner
badge: label="Begränsad tillgänglighet"
hide: true
hidefromtoc: true
source-git-commit: e1121d998711ea4751da5293efdd7c1578ee44a2
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---


# Tilldela prioritetspoäng till resor och kampanjer {#priority}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med konflikthantering och -prioritering](gs-conflict-prioritization.md)
* [Upptäck potentiella konflikter i resor och kampanjer](conflicts.md)
* **[Tilldela prioritetspoäng till resor och kampanjer](priority-scores.md)**
* [Resebegränsning och skiljeförfarande](journey-capping.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Konflikthanterings- och prioriteringsverktygen är för närvarande tillgängliga som begränsad tillgänglighet endast för utvalda användare.

Med Journey Optimizer kan ni tilldela en prioritetspoäng till en resa eller kampanj. Prioritet är viktigt för att prioritera en resa, kampanj eller åtgärd när det finns en begränsning (t.ex. ett frekvenstak). I situationer där en kund är berättigad till många resor, kampanjer eller kommunikationer och du vill vara selektiv vad de ska delta i och ta emot, bör du använda det här fältet.

>[!NOTE]
>
>Prioritetspoäng är tillgängligt för inkommande kanaler: webbkanaler, appkanaler och kodbaserade kanaler. Prioritetspoäng är endast tillgänglig för kanalerna **i appen** och **kodbaserad**.

Det är viktigt att du tilldelar en prioritetspoäng för inkommande kommunikation, som webben, mobiler och appar. Om du har flera kampanjer med samma kanalkonfiguration (t.ex. en banderoll högst upp på webbsidan) kan det vara problematiskt eftersom bara innehåll från en kampanj kan visas. Prioritetspoängen är den plats där du infogar din inställning för vilken kampanj ska visas när mottagaren kan kvalificera sig för mer än en kampanj.

Om du vill tilldela en prioritetspoäng till en resa eller kampanj anger du ett numeriskt värde (från 0-100) i fältet **[!UICONTROL Priority score]** som finns i resans eller kampanjens egenskaper. Observera att ju högre tal desto högre prioritet. Om ni redigerade den här kampanjen och ville se till att kampanjinnehållet visas ger ni den 100 poäng.

![](assets/priority-score.png)

I situationer där två kampanjer har samma prioritetspoäng visas den kampanj som aktiverades först.
