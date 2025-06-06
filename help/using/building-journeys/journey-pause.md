---
solution: Journey Optimizer
product: journey optimizer
title: Pausa en resa
description: Lär dig pausa och återuppta en Live-resa
feature: Journeys
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Begränsad tillgänglighet" type="Informative"
keywords: publicera, resa, live, giltighet, kontrollera
source-git-commit: cd85b58350b4f8829aa1bc925c151be9b061b170
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Pausa en resa {#journey-pause}

Du kan pausa dina resor, utföra alla ändringar som behövs och återuppta dem igen när som helst. En resa kan pausas i högst 14 dagar. Du kan välja om resan ska återupptas när pausperioden är slut eller om den ska avbrytas helt.


>[!AVAILABILITY]
>
>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.


## Viktiga fördelar {#journey-dry-run-benefits}

Pausa och återuppta resor ger marknadsförarna större kontroll och flexibilitet genom att tillåta att direktresor tillfälligt pausas utan att kundupplevelsen störs. När det är pausat skickas ingen kommunikation och profilerna förblir i ett uppehåll tills resan återupptas.

Denna funktion minskar risken för att skicka oavsiktliga meddelanden vid fel eller uppdateringar (t.ex. ändring av meddelandeinnehåll), stöder säkrare resehantering och ökar administratörens förtroende. Synligheten till pausade resor och deras status direkt i användargränssnittet ökar insynen och flexibiliteten ytterligare.

>[!CAUTION]
>
>Behörigheter att pausa och återuppta resor är begränsade till användare med högnivåbehörighet **[!DNL Publish journeys]**. Läs mer om hur du hanterar [!DNL Journey Optimizer] användares åtkomsträttigheter i [det här avsnittet](../administration/permissions-overview.md).

## Skyddsutkast och rekommendationer

* En reseversion kan pausas i högst 14 dagar.
* Pausade resor beaktas i alla affärsregler, på samma sätt som om de var levande.
* Profiler tas bort under en pausad resa när de når en åtgärdsaktivitet. Om de stannar på en väntetid under den tid som en resa pausas och lämnar den som väntar när den återupptas, fortsätter resan och tas inte bort.
* Även efter pausen kommer dessa händelser att räknas in i en kvot på 5 ktbit/s efter vilken strypningen görs för att skapa en enhet.
* Profiler som hade passerat resan men ignorerats under pausen räknas fortfarande som profiler som kan användas.
* När profiler hålls i en pausad resa uppdateras profilattributen vid återupptagningstid
* Villkor körs fortfarande i pausade resor, så om en resa har pausats på grund av problem med datakvaliteten kan alla villkor som föregår en åtgärdsnod utvärderas med felaktiga data.
* För inkrementell målgruppsbaserad läsning beaktas den pausade längden. Om en daglig resa till exempel pausades den andra och återupptogs den 5:e i månaden, kommer körningen den 6:e att ta alla profiler som är kvalificerade från den 1:e till den 6:e. Detta gäller inte för målgruppskompetens eller händelsebaserade resor (om en målgruppskompetens eller ett evenemang tas emot under en paus ignoreras dessa händelser).
* Pausade resor räknas in i kvoten för direktresor.
* Den globala tidsgränsen för resan gäller fortfarande för pausade resor. Om en profil till exempel har besökt en resa i 90 dagar och resan har pausats, kommer den här profilen fortfarande att avsluta resan den 91:e dagen.
* En ny status för **Återkommande**-resa är tillgänglig när en resa återupptas. Det börjar lyssna på resehändelser igen när du klickar på **Återuppta**.  Det finns vissa förseningar för profiler på resan som ska återupptas. När resan går från **Återupptar** till **Live** betyder det att alla profiler har återupptagits. **Det kan därför ta lite tid att återuppta**.
* Om profiler hålls på en resa och den här resan automatiskt återupptas efter XX dagar, fortsätter profilerna resan och släpps inte. Om du vill släppa dem måste du återuppta resan manuellt.
  <!--* There is a guardrail (at an org level) on the max number of profiles that can be held in paused journeys. This guardrail is per org, and is visible in the journey inventory on a new bar (only visible when there are paused journeys).-->

## Pausa en resa {#journey-pause-steps}

Du kan pausa en pågående resa.

Så här pausar du din resa:

1. Öppna den resa du vill pausa.
1. Klicka på knappen **...Mer** i den övre högra delen av arbetsytan och välj **Paus**.

   ![Pausa resan](assets/pause-journey-button.png)

1. Välj hur du vill hantera profiler som för närvarande är på resan.

   ![Pausa alternativ för resa](assets/pause-confirm.png){width="50%" align="left"}

   Du kan:

   * Håll kvar profiler
   * Ignorera profiler

1. Bekräfta genom att klicka på knappen **Paus**.

En resa kan pausas i högst 14 dagar.

## Så här återupptar du en pausad resa {#journey-resume-steps}

Pausade resor kan återupptas manuellt när som helst.

Så här återupptar du en resa:

1. Öppna den resa du vill återuppta.
1. Klicka på knappen **...Mer** i den övre högra delen av arbetsytan och välj **Återuppta**.




