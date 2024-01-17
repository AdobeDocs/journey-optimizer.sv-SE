---
solution: Journey Optimizer
product: journey optimizer
title: Testa din resa
description: Lär dig testa din resa
feature: Journeys, Test Profiles
topic: Content Management
role: User
level: Intermediate
keywords: test, resa, kontroll, fel, felsökning
exl-id: 9937d9b5-df5e-4686-83ac-573c4eba983a
source-git-commit: ac83b44ca24b26edfbf70a2781e1ed7dede318d4
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 1%

---

# Testa din resa{#testing_the_journey}

>[!CONTEXTUALHELP]
>id="ajo_journey_test"
>title="Testa din resa"
>abstract="Använd testprofiler för att testa resan innan du publicerar den. På så sätt kan ni analysera hur individer flödar in på resan och felsöka före publicering."

Använd testprofiler för att testa resan innan du publicerar den. I det här läget kan du testa din resa och identifiera problem med testprofiler.

Det är bara testprofiler som kan ta sig in på en resa i testläge. Du kan antingen skapa nya testprofiler eller omvandla befintliga profiler till testprofiler. Läs mer om testprofiler i [det här avsnittet](../audience/creating-test-profiles.md).

>[!NOTE]
>
>Innan du testar din resa måste du åtgärda eventuella fel. Lär dig kontrollera fel innan du testar i [det här avsnittet](../building-journeys/troubleshooting.md#checking-for-errors-before-testing).

Så här använder du testläget:

1. Aktivera testläget genom att aktivera **[!UICONTROL Test]** i det övre högra hörnet.

   ![](assets/journeytest1.png)

1. Om resan har minst en **Vänta** aktivitet, ange **[!UICONTROL Wait time]** parameter för att definiera den tid som varje vänteaktivitet och händelsetimeout ska vara i testläge. Standardtiden är 10 sekunder för timeout för väntetider och händelser. Detta säkerställer att du får testresultaten snabbt.

   ![](assets/journeytest_wait.png)

   >[!NOTE]
   >
   >När en reaktionshändelse med en tidsgräns används i en resa är väntetiden som standard och det lägsta värdet 40 sekunder. Se [det här avsnittet](../building-journeys/reaction-events.md).

1. Använd **[!UICONTROL Trigger an event]** för att konfigurera och skicka händelser till resan.

   ![](assets/journeyuctest1.png)

1. Konfigurera de olika fälten. I **Profilidentifierare** anger du värdet för fältet som används för att identifiera testprofilen. Det kan till exempel vara e-postadressen. Se till att skicka händelser som rör testprofiler. Se [det här avsnittet](#firing_events).

   ![](assets/journeyuctest1-bis.png)

1. När du har tagit emot händelserna klickar du på **[!UICONTROL Show log]** för att visa testresultatet och verifiera dem. Se [det här avsnittet](#viewing_logs).

   ![](assets/journeyuctest2.png)

1. Om något fel uppstår kan du inaktivera testläget, ändra din resa och testa den igen. När testerna är klara kan du publicera din resa. Läs [den här sidan](../building-journeys/publishing-the-journey.md).

## Viktiga anteckningar {#important_notes}

* I testläge kan du utlösa händelser med hjälp av gränssnittet. Det går inte att skicka händelser från externa system med ett API.
* Endast personer som markerats som&quot;testprofiler&quot; i kundprofiltjänsten i realtid får delta i den testade resan. Se detta [section](../audience/creating-test-profiles.md).
* Testläget är bara tillgängligt i utkastresor som använder ett namnutrymme. Testläget måste kontrollera om en person som deltar i resan är en testprofil eller inte och därför måste kunna nå Adobe Experience Platform.
* Det högsta antalet testprofiler som kan gå in på en resa under en testsession är 100.
* När du inaktiverar testläget töms resorna från alla som har gått in i det tidigare eller som befinner sig i det. Rapporten blir också tydligare.
* Du kan aktivera/inaktivera testläget så många gånger som behövs.
* Du kan inte ändra din resa när testläget är aktiverat. När du är i testläge kan du publicera resan direkt, du behöver inte inaktivera testläget tidigare.
* När en delning nås väljs alltid den översta grenen. Du kan ordna om placeringen av de delade grenarna om du vill att testet ska välja en annan bana.
* För att optimera prestanda och förhindra föråldrad resursanvändning kommer alla resor i testläge som inte har utlösts på en vecka att växla tillbaka till **Utkast** status.
* Händelser som utlöses av testläget lagras i dedikerade datauppsättningar. Dessa datauppsättningar har följande etiketter: `JOtestmode - <schema of your event>`

## Utlös dina händelser {#firing_events}

>[!CONTEXTUALHELP]
>id="ajo_journey_test_configuration"
>title="Konfigurera testläget"
>abstract="Om resan innehåller flera händelser använder du listrutan för att välja en händelse. Konfigurera sedan de fält som skickats och körningen av den händelse som skickats för varje händelse."

Använd **[!UICONTROL Trigger an event]** för att konfigurera en händelse som får en person att komma in på resan.

>[!NOTE]
>
>När du utlöser en händelse i testläge genereras en verklig händelse, vilket innebär att den även kommer att drabba andra resor som lyssnar på den här händelsen.

Du måste känna till vilka profiler som är flaggade som testprofiler i Adobe Experience Platform. Testläget tillåter bara dessa profiler under resan och händelsen måste innehålla ett ID. Det förväntade ID:t beror på händelsekonfigurationen. Det kan till exempel vara ett ECID eller en e-postadress. Värdet för den här nyckeln måste läggas till i **Profilidentifierare** fält.

Om resan innehåller flera händelser använder du listrutan för att välja en händelse. Konfigurera sedan de fält som skickats och körningen av den händelse som skickats för varje händelse. Gränssnittet hjälper dig att skicka rätt information i händelsens nyttolast och kontrollera att informationstypen är korrekt. Testläget sparar de senaste parametrarna som användes i en testsession för senare bruk.

![](assets/journeytest4.png)

Med gränssnittet kan du skicka enkla händelseparametrar. Om du vill skicka samlingar eller andra avancerade objekt i händelsen kan du klicka på **[!UICONTROL Code View]** för att se hela koden för nyttolasten och ändra den. Du kan till exempel kopiera och klistra in händelseinformation som har förberetts av en teknisk användare.

![](assets/journeytest5.png)

En teknisk användare kan också använda det här gränssnittet för att komponera händelsenyttolaster och utlösa händelser utan att behöva använda något tredjepartsverktyg.

När du klickar **[!UICONTROL Send]** testas. Personens förlopp under resan representeras av ett visuellt flöde. Vägen blir progressivt grön allt eftersom personen rör sig över resan. Om ett fel inträffar visas en varningssymbol i motsvarande steg. Du kan placera markören på den för att visa mer information om felet och få tillgång till fullständig information (när den är tillgänglig).

![](assets/journeytest6.png)

När du väljer en annan testprofil på händelsekonfigurationsskärmen och kör testet igen rensas det visuella flödet och den nya personens sökväg visas.

När du öppnar en resa i ett test motsvarar den visade sökvägen det senaste testet som utfördes.

## Testläge för regelbaserade resor {#test-rule-based}

Testläget är även tillgängligt för resor som använder en regelbaserad händelse. Mer information om regelbaserade händelser finns i [den här sidan](../event/about-events.md).

När en händelse utlöses **Händelsekonfiguration** kan du definiera de händelseparametrar som ska godkännas i testet. Du kan visa händelse-ID-villkoret genom att klicka på verktygstipsikonen i det övre högra hörnet. Det finns också ett verktygstips bredvid varje fält som ingår i regelutvärderingen.

![](assets/jo-event8.png)

## Testläge för affärshändelser {#test-business}

När en [affärshändelse](../event/about-events.md)använder du testläget för att utlösa en enskild testprofilentré under resan, simulera händelsen och skicka rätt profil-ID. Du måste godkänna händelseparametrarna och identifieraren för den testprofil som ska gå in på resan i testet. I testläge finns det inget kodläge tillgängligt för resor baserat på affärshändelser.

Observera att du inte kan ändra definitionen för affärshändelser i samma testsession när du först utlöser en affärshändelse. Du kan bara göra så att samma person eller en annan person anger resan som går genom samma eller en annan identifierare. Om du vill ändra parametrar för affärshändelser måste du stoppa och starta om testläget.

## Visa loggar {#viewing_logs}

>[!CONTEXTUALHELP]
>id="ajo_journey_test_logs"
>title="Loggar för testläge"
>abstract="Knappen Visa logg visar testresultat i JSON-format. Dessa resultat visar antalet individer under resan och deras status."

The **[!UICONTROL Show log]** kan du visa testresultaten. På den här sidan visas resans aktuella information i JSON-format. Med en knapp kan du kopiera hela noder. Du måste uppdatera sidan manuellt för att uppdatera resans testresultat.

![](assets/journeytest3.png)


>[!NOTE]
>
>I testloggarna visas felkoden och felsvaret om ett fel uppstår vid anrop till ett tredjepartssystem (datakälla eller åtgärd).

Antalet personer (tekniskt sett kallas de förekomster) som för närvarande befinner sig under resan visas. Här är användbar information som visas för varje individ:

* _ID_: personens interna ID under resan. Detta kan användas i felsökningssyfte.
* _aktuellt steg_: det steg där personen befinner sig på resan. Vi rekommenderar att du lägger till etiketter till dina aktiviteter för att lättare kunna identifiera dem.
* _aktuellt steg_ > fas: statusen för personens resa (körning, avslutad, fel eller timeout). Mer information finns nedan.
* _aktuellt steg_ > _extraInfo_: beskrivning av felet och annan sammanhangsberoende information.
* _aktuellt steg_ > _hämtningsfel_: information om hämtning av datafel som inträffade under det här steget.
* _externalKeys_: värdet för den nyckelformel som definieras i händelsen.
* _enrichedData_: de data som resan har hämtat om resan använder datakällor.
* _transitionHistory_: en lista med steg som den enskilda personen följde. För händelser visas nyttolasten.
* _actionExecutionErrors_ : information om de fel som uppstod.

Här är en persons olika status:

* _Körs_: den enskilda personen befinner sig för närvarande på resan.
* _Slutförd_: personen är i slutet av resan.
* _Fel_: personen stoppas på resan på grund av ett fel.
* _Timeout_: personen stoppas på resan på grund av ett steg som tog för mycket tid.

När en händelse aktiveras i testläget genereras en datauppsättning automatiskt med källans namn.

Testläget skapar automatiskt en Experience Event och skickar den till Adobe Experience Platform. Källan för upplevelsehändelsen heter&quot;Journey Orchestration Test Events&quot;.

