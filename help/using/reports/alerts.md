---
solution: Journey Optimizer
product: journey optimizer
title: Åtkomst och prenumeration på systemvarningar
description: Lär dig hur du får åtkomst till och prenumererar på systemvarningar
feature: Journeys, Alerts
topic: Administration
role: User
level: Intermediate
exl-id: 0855ca5b-c7af-41c4-ad51-bed820ae5ecf
source-git-commit: da2fb137a8af82a8487638dc3d762377dd5dc506
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 0%

---

# Åtkomst och prenumeration på systemvarningar {#alerts}

När du skapar resor och kampanjer använder du knappen **Varningar** för att kontrollera och åtgärda fel innan du kör eller publicerar dem. Lär dig hur du felsöker dina resor på [den här sidan](../building-journeys/troubleshooting.md). Lär dig hur du granskar kampanjer på [den här sidan](../campaigns/review-activate-campaign.md).

Du kan även prenumerera på Adobe Journey Optimizer systemaviseringar så som beskrivs på den här sidan.

## Få åtkomst till och prenumerera på aviseringar {#alerting-capabilities}

När ett fel inträffar kan du få systemvarningar i Journey Optimizer meddelandecenter (varningar i appen) och/eller få ett e-postmeddelande.

På menyn **Varningar** kan du visa tillgängliga varningar och prenumerera på dem. När en viss uppsättning villkor för dina åtgärder har nåtts (t.ex. ett eventuellt problem när systemet överskrider ett tröskelvärde), skickas varningsmeddelanden till alla användare i organisationen som prenumererar på dem.

<!--These messages can repeat over a pre-defined time interval until the alert has been resolved.-->

Läs mer om varningar i Adobe Experience Platform i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html?lang=sv-SE){target="_blank"}.

Klicka på **Varningar** under **Administration** på den vänstra menyn. Det finns två förkonfigurerade aviseringar för Journey Optimizer: aviseringen [Fel vid anpassad åtgärd på resa](#alert-custom-actions) och aviseringen [Läs utlösare på målgrupp misslyckades](#alert-read-audiences). Dessa varningar beskrivs nedan.

Du kan prenumerera på varje varning individuellt från användargränssnittet genom att välja alternativet **Prenumerera** på kontrollpanelen **Varningar**. Använd samma metod för att avsluta prenumerationen.

![](assets/alert-subscribe.png)

Du kan också prenumerera på aviseringar via [I/O-händelsemeddelanden](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html?lang=sv-SE){target="_blank"}. Varningsregler är ordnade i olika prenumerationspaket. Evenemangsprenumerationer som motsvarar specifika Journey Optimizer-varningar beskrivs nedan.

Om ett oväntat beteende inträffar skickas ett varningsmeddelande till prenumeranterna. Varningar skickas med e-post och/eller direkt från Journey Optimizer meddelandecenter i det övre högra hörnet av användargränssnittet, baserat på användarinställningarna. Som standard är endast varningar i appen aktiverade. Information om hur du aktiverar e-postvarningar finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html?lang=sv-SE#enable-email-alerts){target="_blank"}.

När en varning har lösts får prenumeranterna ett meddelande om att den har lösts.

>[!CAUTION]
>
>Adobe Journey Optimizer-specifika aviseringar gäller endast för **live**-resor. Varningar utlöses inte för resor i testläge.

## Fel i anpassad åtgärd för resa {#alert-custom-actions}

Den här varningen varnar dig om en anpassad åtgärd misslyckas. Vi anser att det finns ett fel där det har förekommit mer än 1 procent av felen i en specifik anpassad åtgärd under de senaste fem minuterna. Detta utvärderas var 30:e sekund.

![](assets/alerts-custom-action.png)

Varningar om anpassade åtgärder löses när, under de senaste fem minuterna:

* det inte har förekommit något fel i den anpassade åtgärden (eller fel under tröskelvärdet 1 %),

* eller så har ingen profil nått den anpassade åtgärden.

Prenumerationsnamnet för en I/O-händelse som motsvarar den anpassade åtgärdsaviseringen är **Fel vid anpassad åtgärd för resan**.

## Det gick inte att läsa målutlösaren {#alert-read-audiences}

Den här varningen varnar dig om en **Läs målgrupp**-aktivitet inte har bearbetat någon profil 10 minuter efter den schemalagda körningen. Felet kan bero på tekniska problem eller på att målgruppen är tom. Om det här felet orsakas av tekniska problem ska du vara medveten om att försök fortfarande kan göras, beroende på typ av problem (t.ex. om det inte går att skapa exportjobbet kommer vi att försöka igen var 10:e minut med maximalt 1 timme).

![](assets/alerts1.png)

Varningar för **Läs målgruppsaktiviteter** gäller endast återkommande resor. **Läs målgruppsaktiviteter** i liveresor som har ett schema för att köra **En gång** eller **Så snart som möjligt** ignoreras.

Varningar på **Läs målgrupp** löses när en profil kommer in i noden **Läs målgrupp** .

Prenumerationsnamnet för I/O-händelsen som motsvarar aviseringen **Read Audience Trigger Unsuccess** är **Fördröjningar, fel och fel för läsningspubliken på resan**.

## Felsökning {#alert-troubleshooting}

Om du vill felsöka **Läs publikaviseringar** kontrollerar du antalet målgrupper i Experience Platform-gränssnittet.

![](assets/alert-troubleshooting-0.png)

![](assets/alert-troubleshooting-1.png)

Så här felsöker du **anpassade åtgärdsmeddelanden**:

* Kontrollera din anpassade åtgärd med testläge på en annan resa:

  ![](assets/alert-troubleshooting-2.png)

* Se felen i reserapporten.

  ![](assets/alert-troubleshooting-3.png)

* Kontrollera kundens resaHändelser för att hitta mer information om &quot;errorReason&quot;.

* Kontrollera din konfiguration för anpassad åtgärd och verifiera att autentiseringen fortfarande är OK. Gör till exempel en manuell kontroll med Postman.
