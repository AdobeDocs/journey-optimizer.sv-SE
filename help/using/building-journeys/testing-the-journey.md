---
title: Testa resan
description: Läs om testning av resan
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 9937d9b5-df5e-4686-83ac-573c4eba983a
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 2%

---

# Testa din resa{#testing_the_journey}

Innan du kan testa din resa måste du åtgärda eventuella fel. Se [det här avsnittet](../building-journeys/troubleshooting.md#checking-for-errors-before-testing).

Du kan testa din resa innan den publiceras med testprofiler. På så sätt kan ni analysera hur individer flödar in på resan och felsöka före publicering.

Det är bara testprofiler som kan gå in på en resa i testläge. Du kan antingen skapa en ny testprofil eller omvandla en befintlig profil till en testprofil. Se detta [section](../building-journeys/creating-test-profiles.md).

Så här använder du testläget:

1. Innan du testar din resa kontrollerar du att den är giltig och att det inte finns något fel. Du kommer inte att kunna starta ett test av en resa med fel. Se [det här avsnittet](../building-journeys/troubleshooting.md#checking-for-errors-before-testing). En varningssymbol visas om det finns fel.

1. Aktivera testläget genom att klicka på **[!UICONTROL Test]** i det övre högra hörnet.

   ![](assets/journeytest1.png)

1. Använd **[!UICONTROL Wait time]** i det nedre vänstra hörnet för att definiera den tid som varje vänteaktivitet och händelsetimeout ska vara i testläge. Standardtiden är 10 sekunder för timeout för väntetider och händelser. Detta säkerställer att du får testresultaten snabbt. Den här parametern visas bara om du har släppt en eller flera vänteaktiviteter under din resa.

   ![](assets/journeytest_wait.png)

   >[!NOTE]
   >
   >När en reaktionshändelse används under en resa är väntetiden som standard och minimivärdet 40 sekunder. Se [det här avsnittet](../building-journeys/reaction-events.md).

1. Klicka **[!UICONTROL Trigger an event]** för att konfigurera och skicka händelser till resan.

   ![](assets/journeyuctest1.png)

1. Konfigurera de olika fälten. I **Profilidentifierare** anger du värdet för fältet som används för att identifiera testprofilen. Det kan till exempel vara e-postadressen. Se till att skicka händelser som rör testprofiler. Se [Aktivera händelser](#firing_events).

   ![](assets/journeyuctest1-bis.png)

1. När du har tagit emot händelserna klickar du på **[!UICONTROL Show log]** för att visa testresultatet och verifiera dem. Se [Visa loggarna](#viewing_logs).

   ![](assets/journeyuctest2.png)

1. Om något fel uppstår kan du inaktivera testläget, ändra din resa och testa den igen. När testet är klart kan du publicera din resa. Läs [den här sidan](../building-journeys/publishing-the-journey.md).

## Viktiga anteckningar {#important_notes}

* Det finns ett gränssnitt för att utlösa händelser till den testade resan, men händelser kan också skickas av tredjepartssystem som Postman.
* Endast personer som markerats som&quot;testprofiler&quot; i kundprofiltjänsten i realtid får delta i den testade resan. Se detta [section](../building-journeys/creating-test-profiles.md).
* Testläget är bara tillgängligt i utkastresor som använder ett namnutrymme. Testläget måste kontrollera om en person som deltar i resan är en testprofil eller inte och därför måste kunna nå Adobe Experience Platform.
* Det högsta antalet testprofiler som kan gå in på en resa under en testsession är 100.
* När du inaktiverar testläget töms resorna från alla som har gått in i det tidigare eller som befinner sig i det. Rapporten blir också tydligare.
* Du kan aktivera/inaktivera testläget så många gånger som behövs.
* Du kan inte ändra din resa när testläget är aktiverat. När du är i testläge kan du publicera resan direkt, du behöver inte inaktivera testläget tidigare.
* När en delning nås väljs alltid den översta grenen. Du kan ordna om placeringen av de delade grenarna om du vill att testet ska välja en annan bana.
* För att optimera prestandan och förhindra föråldrad resursanvändning kommer alla resor i testläge som inte har utlösts på en vecka att återgå till statusen Utkast.

## Aktivera händelser {#firing_events}

The **[!UICONTROL Trigger an event]** kan du konfigurera en händelse som får en person att komma in på resan.

>[!NOTE]
>
>När du utlöser en händelse i testläge genereras en verklig händelse, vilket innebär att den även kommer att drabba andra resor som lyssnar på den här händelsen.

Du måste känna till vilka profiler som är flaggade som testprofiler i Adobe Experience Platform. Testläget tillåter bara dessa profiler under resan och händelsen måste innehålla ett ID. Det förväntade ID:t beror på händelsekonfigurationen. Det kan till exempel vara ett ECID eller en e-postadress. Värdet för den här nyckeln måste läggas till i **Profilidentifierare** fält.

Om resan innehåller flera händelser använder du listrutan för att välja en händelse. Konfigurera sedan de fält som skickats och körningen av den händelse som skickats för varje händelse. Med gränssnittet kan du skicka rätt information i händelsens nyttolast och kontrollera att informationstypen är korrekt. Testläget sparar de senaste parametrarna som användes i en testsession för senare bruk.

![](assets/journeytest4.png)

Med gränssnittet kan du skicka enkla händelseparametrar. Om du vill skicka samlingar eller andra avancerade objekt i händelsen kan du klicka på **[!UICONTROL Code View]** för att se hela koden för nyttolasten och ändra den. Du kan till exempel kopiera och klistra in händelseinformation som har förberetts av en teknisk användare.

![](assets/journeytest5.png)

En teknisk användare kan också använda det här gränssnittet för att komponera händelsenyttolaster och utlösa händelser utan att behöva använda något tredjepartsverktyg.

När du klickar på **[!UICONTROL Send]** testas. Personens förlopp under resan representeras av ett visuellt flöde. Vägen blir progressivt grön allt eftersom personen rör sig över resan. Om ett fel inträffar visas en varningssymbol i motsvarande steg. Du kan placera markören på den för att visa mer information om felet och få tillgång till fullständig information (när den är tillgänglig).

![](assets/journeytest6.png)

När du väljer en annan testprofil på händelsekonfigurationsskärmen och kör testet igen rensas det visuella flödet och den nya personens sökväg visas.

När du öppnar en resa i ett test motsvarar den visade sökvägen det senaste testet som utfördes.

Det visuella flödet fungerar oavsett om händelsen aktiveras via gränssnittet eller externt (med till exempel Postman).

## Testläge för regelbaserade resor {#test-rule-based}

Testläget är även tillgängligt för resor som använder en regelbaserad händelse. Mer information om regelbaserade händelser finns i [den här sidan](../event/about-events.md).

När en händelse utlöses **Händelsekonfiguration** kan du definiera de händelseparametrar som ska godkännas i testet. Du kan visa händelse-ID-villkoret genom att klicka på verktygstipsikonen i det övre högra hörnet. Det finns också ett verktygstips bredvid varje fält som ingår i regelutvärderingen.

![](assets/jo-event8.png)

Mer information om hur du använder testläget finns i [den här sidan](../building-journeys/testing-the-journey.md).

## Testläge för affärshändelser {#test-business}

När du använder en affärshändelse (se [det här avsnittet](../event/about-events.md)) kan du i testläge utlösa en enskild testprofilentré under resan, simulera händelsen och skicka rätt profil-ID. Du måste godkänna händelseparametrarna och identifieraren för den testprofil som ska gå in på resan i testet. Du kan inte använda **[!UICONTROL Up to 100 profiles at once]** alternativ som finns för andra segmentbaserade resor. I testläge finns det inget kodläge tillgängligt för resor baserat på affärshändelser.

Observera att du inte kan ändra definitionen för affärshändelser i samma testsession när du först utlöser en affärshändelse. Du kan bara göra så att samma person eller en annan person anger resan som går genom samma eller en annan identifierare. Om du vill ändra parametrar för affärshändelser måste du stoppa och starta om testläget.

## Visa loggarna {#viewing_logs}

The **[!UICONTROL Show log]** kan du visa testresultaten. På den här sidan visas resans aktuella information i JSON-format. Med en knapp kan du kopiera hela noder. Du måste uppdatera sidan manuellt för att kunna uppdatera resans testresultat.

![](assets/journeytest3.png)

>[!NOTE]
>
>I testloggarna visas felkoden och felsvaret om ett fel uppstår vid anrop till ett tredjepartssystem (datakälla eller åtgärd).

Antalet personer (tekniskt sett kallas de instanser) som för närvarande befinner sig under resan visas. Här är användbar information som visas för varje individ:

* _ID_: Personens interna ID under resan. Detta kan användas för felsökning.
* _aktuellt steg_: det steg där personen befinner sig på resan. Vi rekommenderar att du lägger till etiketter till dina aktiviteter för att lättare kunna identifiera dem.
* _aktuellt steg_ > fas: Status för den enskilda personens resa (körning, slutförd, fel eller timeout). Mer information finns nedan.
* _aktuellt steg_ > _extraInfo_: beskrivning av felet och annan sammanhangsbaserad information.
* _aktuellt steg_ > _fetchErrors_: information om hämtning av datafel som inträffade under det här steget.
* _externalKeys_: värdet för den nyckelformel som definieras i händelsen.
* _enrichedData_: de data som resan har hämtat om resan använder datakällor.
* _transitionHistory_: en lista med steg som personen följde. För händelser visas nyttolasten.
* _actionExecutionErrors_ : information om de fel som uppstått.

Här är en persons olika status:

* _Körs_: personen för närvarande befinner sig på resan.
* _Slutförd_: personen befinner sig i slutet av resan.
* _Fel_: Personen stoppas på resan på grund av ett fel.
* _Timeout_: Personen stoppas på resan på grund av ett steg som tog för mycket tid.

När en händelse aktiveras i testläget genereras en datauppsättning automatiskt med källans namn.

Testläget skapar automatiskt en Experience Event och skickar den till Adobe Experience Platform. Källan för upplevelsehändelsen heter&quot;Journey Orchestration Test Events&quot;.

Vid flera händelser som triggas av flera resor

Det finns ett scenario när flera händelser skickas från flera resor som kommer att ha olika scheman. Kan ett schema mappas till en datauppsättning? Annars behöver vi flera datauppsättningar.

Dessa datauppsättningar skapas och namnges automatiskt om en måldatauppsättning inte ingår i upplevelsehändelsen. Därför ser vi dagens&quot;Automatiskt skapade datauppsättningar för resenärer&quot;.

Namngivningen av vår källa skapar automatiskt. Om vi har flera händelser bör vi sammanfoga och låta det vara &quot;Journey Orchestration Test Event - NAME OF SCHEMA&quot;. Detta blir automatiskt&quot;Automatiskt genererad datauppsättning för testhändelsen Journey Orchestration - SCHEMAS NAMN&quot;.