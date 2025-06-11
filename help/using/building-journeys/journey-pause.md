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
source-git-commit: 2d7067782d6adc7fe5c458a575729d2293af2aaf
workflow-type: tm+mt
source-wordcount: '1196'
ht-degree: 0%

---

# Pausa en resa {#journey-pause}

>[!CONTEXTUALHELP]
>id="ajo_journey_pause"
>title="Pausa din resa"
>abstract="Pausa en live-resa för att förhindra att nya profiler kommer in. Välj om du vill ta bort profiler som finns på resan eller behålla dem på plats. Om de behålls kommer de att återuppta körningen vid nästa åtgärdsaktivitet när resan har startats om. Perfekt för uppdateringar eller nödstopp utan att förlora några framsteg."

Du kan pausa dina resor, utföra alla ändringar som behövs och återuppta dem igen när som helst.<!--You can choose whether the journey is resumed at the end of the pause period, or whether it stops completely. --> Under pausen kan du [använda globala filter](#journey-global-filters) för att exkludera profiler baserat på deras attribut. Resan återupptas automatiskt i slutet av pausperioden. Du kan även [återuppta det manuellt](#journey-resume-steps).

>[!AVAILABILITY]
>
>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.


## Viktiga fördelar {#journey-dry-run-benefits}

Pausa och återuppta resor ger resenärerna större kontroll och flexibilitet genom att tillåta att direktresor tillfälligt avbryts utan att störa kundupplevelsen. När det är pausat skickas ingen kommunikation och profilerna förblir i ett uppehåll tills resan återupptas.

Denna funktion minskar risken för att skicka oavsiktliga meddelanden vid fel eller uppdateringar (t.ex. ändring av meddelandeinnehåll), stöder säkrare resehantering och ökar administratörens förtroende. Synligheten till pausade resor och deras status direkt i användargränssnittet ökar insynen och flexibiliteten ytterligare.

>[!CAUTION]
>
>Behörigheter att pausa och återuppta resor är begränsade till användare med högnivåbehörighet **[!DNL Publish journeys]**. Läs mer om hur du hanterar [!DNL Journey Optimizer] användares åtkomsträttigheter i [det här avsnittet](../administration/permissions-overview.md).

## Skyddsutkast och rekommendationer

* En reseversion kan pausas i högst 14 dagar.
* Pausade resor beaktas i alla affärsregler, på samma sätt som om de var levande.
* Profiler tas bort under en pausad resa när de når en åtgärdsaktivitet. Om de stannar på en väntetid under den tid som en resa pausas och avslutar som väntar efter att den har återupptagits, fortsätter resan och tas inte bort.
* Även efter pausen kommer dessa händelser att räknas in i antalet resthändelser per sekund, efter vilken strypningen görs för att skapa en enhet.
* Profiler som hade passerat resan men ignorerats under pausen räknas fortfarande som profiler som kan användas.
* När profiler hålls i en pausad resa uppdateras profilattributen vid återupptagningstid
* Villkor körs fortfarande i pausade resor, så om en resa har pausats på grund av problem med datakvaliteten kan alla villkor som föregår en åtgärdsnod utvärderas med felaktiga data.
* För inkrementell målgruppsbaserad läsning beaktas den pausade längden. Om en daglig resa till exempel pausades den andra och återupptogs den 5:e i månaden, kommer körningen den 6:e att ta alla profiler som är kvalificerade från den 1:e till den 6:e. Detta gäller inte för målgruppskompetens eller händelsebaserade resor (om en målgruppskompetens eller ett evenemang tas emot under en paus ignoreras dessa händelser).
* Pausade resor räknas in i kvoten för direktresor.
* Den globala tidsgränsen för resan gäller fortfarande för pausade resor. Om en profil till exempel har besökt en resa i 90 dagar och resan har pausats, kommer den här profilen fortfarande att avsluta resan den 91:e dagen.
* Om profiler hålls på en resa och den här resan automatiskt återupptas efter några dagar, fortsätter profilerna resan och släpps inte. Om du vill släppa dem måste du stoppa resan.
  <!--* There is a guardrail (at an org level) on the max number of profiles that can be held in paused journeys. This guardrail is per org, and is visible in the journey inventory on a new bar (only visible when there are paused journeys).-->

## Pausa en resa {#journey-pause-steps}

Du kan pausa alla **Live**-resor.

Så här pausar du din resa:

1. Öppna den resa du vill pausa.
1. Klicka på knappen **...Mer** i den övre högra delen av arbetsytan och välj **Paus**.

   ![Pausa resan](assets/pause-journey-button.png){width="80%" align="left"}

1. Välj hur du vill hantera profiler som för närvarande är på resan.

   ![Pausa alternativ för resa](assets/pause-confirm.png){width="50%" align="left"}

   Du kan:

   * **Håll** profiler - Profilerna väntar på att resan ska återupptas
   * **Ignorera** profiler - Profiler exkluderas från resan på nästa åtgärdsnod

1. Bekräfta genom att klicka på knappen **Paus**.

I listan över dina resor kan du pausa en eller flera **Live**-resor. Om du vill pausa en grupp resor (_masspaus_) markerar du dem i listan och klickar på knappen **Paus** i det blå fältet längst ned på skärmen. Knappen **Paus** är bara tillgänglig när **Live**-resor har valts.

![Pausa två direktresor i grupp från det nedre fältet](assets/bulk-pause-journeys.png){width="80%" align="left"}


## Så här återupptar du en pausad resa {#journey-resume-steps}

>[!CONTEXTUALHELP]
>id="ajo_journey_pause"
>title="Återuppta resan"
>abstract="Återuppta en pausad resa så att nya profiler kan komma in igen. Om profiler väntade under pausen fortsätter de sin resa. Perfekt för säker återstart av resor efter uppdateringar eller pauser."

Pausade resor återupptas automatiskt vid slutet av den maximala pausperioden på 14 dagar. De kan när som helst återupptas manuellt. Om du återupptar en pausad resa kan nya profiler komma in igen. Om profiler väntade under pausen fortsätter de sin resa. Perfekt för säker återstart av resor efter uppdateringar eller pauser.

Så här återupptar du en pausad resa och börjar lyssna på resehändelser igen:

1. Öppna den resa du vill återuppta.
1. Klicka på knappen **...Mer** i den övre högra delen av arbetsytan och välj **Återuppta**.

   Resan växlar till statusen **Återupptar**. Övergången från statusen **Återupptar** till **Live** kan ta en stund: alla profiler måste återupptas för att resan ska bli **Live** igen.

1. Bekräfta genom att klicka på knappen **Återuppta**.


I listan över dina resor kan du återuppta en eller flera **Pausade** resor. Om du vill återuppta en grupp av resor (_massåteruppta_) markerar du dem och klickar på knappen **Återuppta** i det blå fältet längst ned på skärmen. Observera att knappen **Återuppta** endast är tillgänglig när **Pausade** resor har valts.


## Tillämpa ett globalt filter på profiler i en pausad resa  {#journey-global-filters}

När en resa pausas kan du använda ett globalt filter baserat på profilattribut. Det här filtret gör att profiler som matchar det definierade uttrycket utesluts vid återupptagningstid. Profiler som matchar de villkor som för närvarande finns under resan kommer att avsluta den och nya profiler som försöker komma in kommer att blockeras.

Om du t.ex. vill utesluta alla franska kunder från marknadsföringsmaterial till Frankrike gör du så här:

1. Bläddra till den pausade resa som du vill ändra.

1. Klicka på ikonen **Avsluta villkor och globalt filter** .

   ![Lägg till ett globalt filter för en pausad resa](assets/add-global-filter.png){width="50%" align="left"}

1. Definiera ett filter baserat på profilattribut i inställningarna för **Avsluta villkor och globalt filter**.

1. Ange uttrycket för att exkludera profiler där landattributet är lika med Frankrike.

   ![Lägg till ett globalt filter för en pausad resa](assets/add-country-filter.png){width="50%" align="left"}

1. Spara filtret och klicka på knappen **Uppdatera resa** för att tillämpa ändringarna.

1. [Fortsätt resan](#journey-resume-steps).

   Vid CV kommer alla profiler med landattributet inställt på Frankrike automatiskt att uteslutas från resan. Alla nya profiler med landattributet inställt på Frankrike som försöker ta sig in på resan kommer att blockeras.

Observera att uteslutning av profiler för närvarande på resan och för nya profiler endast sker när de når en åtgärdsnod.

>[!CAUTION]
>
>* Du kan bara ange **ett** globalt filter per resa.
>
>* Du kan bara skapa, uppdatera eller ta bort ett globalt filter på **Pausade** resor.