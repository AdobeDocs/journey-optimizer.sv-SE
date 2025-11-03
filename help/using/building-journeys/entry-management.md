---
solution: Journey Optimizer
product: journey optimizer
title: Profilhantering
description: Lär dig hantera profilpost
feature: Journeys, Profiles
role: User
level: Intermediate
keywords: återinträde, resa, profil, återkommande
exl-id: 8874377c-6594-4a5a-9197-ba5b28258c02
version: Journey Orchestration
source-git-commit: 5eddbb1f9ab53f1666ccd8518785677018e10f6f
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 0%

---


# Profilingångshantering {#entry-management}

Hanteringen av profilentréer beror på typen av resa.

## Resetyper {#types-of-journeys}

Med Adobe Journey Optimizer kan du skapa följande typer av resor:

* **Unitary event**-resor: Dessa resor börjar med en Unitary-händelse. När händelsen tas emot kommer den associerade profilen in i resan. [Läs mer](#entry-unitary)

* **Affärshändelse** resor: Resorna börjar med en Business-händelse som omedelbart följs av en **Läs målgruppsaktivitet**. När evenemanget tas emot går profiler som tillhör målgruppen in på resan. En instans av den här resan skapas för varje profil. [Läs mer](#entry-business)

* **Läs målgrupper** resor: De här resorna börjar med en **Läs målgrupp**-aktivitet. När resan är genomförd kommer profiler som tillhör målgruppen in på resan. En instans av den här resan skapas för varje profil. Resorna kan vara återkommande eller &quot;engångsvisa&quot;. [Läs mer](#entry-read-audience)

* **Målgruppskvalificering** resor: dessa resor börjar med en Audience-kvalificeringshändelse. Dessa resor lyssnar på ingångar och utgångar för profiler i målgrupper. När detta händer kommer den associerade profilen in på resan. [Läs mer](#entry-unitary)

I alla resetyper kan en profil inte finnas flera gånger i samma resa, samtidigt, för alla aktiva [versioner av resan](publishing-the-journey.md#journey-versions-journey-versions). Om du vill kontrollera att en person befinner sig på en resa används profilidentiteten som en nyckel. Systemet tillåter inte att samma nyckel, till exempel nyckeln `CRMID=3224`, finns på olika platser under samma resa.

## Bearbetningsgrad för resor {#journey-processing-rate}

Bearbetningshastigheten för resan påverkas av flera faktorer som avgör hur profiler flödar genom en resa:

### Ingångstakt för profil {#profile-entrance-rate}

Hur profiler anger resor och hur ofta de förväntas tillkomma beror på den första aktiviteten som används:

* **Läs målgrupper** resor (batchscenario, där du anger en målgrupp med profiler som mål och utlöser en resa för den fullständiga målgruppen): det högsta antalet är 20 000 TPS (transaktioner per sekund), vilket är den kvot som är tillgänglig på **sandlådenivå**. Om du har flera resor som körs samtidigt på den sandlådan kanske 20 000 TPS inte är möjligt. Använd det här maxvärdet som bästa scenario.

* **Målgruppskvalificering** resor (enställigt scenario, där du vill utlösa en resa när en profil kvalificerar eller diskvalificerar för en målgrupp): det högsta antalet är 5 000 TPS. Observera att detta är en delad gräns med resor som börjar med händelser och som också delas över resor på **organisationsnivå**.

* **Enhetlig händelse** resor (enställigt scenario, där du vill utlösa en resa när en händelse skickas från en profil): samma som ovan, båda delar samma gräns på 5 000 TPS. Mer information om händelseflöde för resan finns i [det här avsnittet](../event/about-events.md#event-thoughput).

* **Affärshändelse** - resor (som egentligen är ett enastående till gruppscenario eftersom en affärshändelse alltid följs av en läsare): affärshändelser räknas också in i kvoten på 5 000 TPS, men aktiviteten Läs målgrupp direkt efter har samma gräns som resor som börjar med en läsare (20 000 TPS).

### Evenemang och målgruppskvalifikationer inom resor {#events-inside-journeys}

Efter ingången kan du använda **Unitary-aktiviteter** eller **Audience-kvalificeringsaktiviteter** inuti resan. En profil kan delta i någon av de fyra typer av resor som beskrivs ovan och vänta på att en händelse ska skickas ut eller vänta tills profilen kvalificerar sig för en målgrupp. Dessa Unitary Events- och Audience-kvalifikationer kommer att räknas in i den kvot som beskrivs ovan. Om du till exempel påbörjar en resa med en läsare (med högst 20 000 TPS) och har en händelse direkt efter, kommer den här händelsen att ha högst 5 000 TPS.

### Påverkan av väntande aktiviteter {#wait-activities-impact}

**Vänta**-aktiviteter på resor kan också påverka hur många profiler som följer en resa vid en viss tidpunkt. Vanligtvis baseras en Wait-aktivitet på en relativ tid (t.ex.: avsluta 2 timmar efter att vänta, så alla profiler inte avslutas samtidigt). Om en fast tid definieras för den vänteaktiviteten kan flera profiler avsluta den resan samtidigt. Detta rekommenderas inte. Stora volymer kan sedan ses och TPS:en kan från och med nu överstiga 20 000 TPS.

### Åtgärdsaktiviteter {#action-activities-impact}

Slutligen kan **åtgärd**-aktiviteter (interna kanaler som e-post, SMS, push osv., utgående eller inkommande, Anpassade åtgärder, Hoppar som skickar profiler till andra resor, Uppdatera profiler som skickar data till den enhetliga profiltjänsten osv.) påverkas av profilinläsningen från resor men kan även påverka bearbetningsfrekvensen. En anpassad åtgärd som till exempel har en extern slutpunkt med hög svarstid som mål kommer att göra resebearbetningen långsammare.

För anpassade åtgärder är standardinställningen 300 000 anrop per minut, vilket kan ändras med en anpassad fästprincip. Läs mer om anpassad åtgärdsbegränsning i [det här avsnittet](../configuration/external-systems.md#capping).

## Unitär event- och målgruppskompetens{#entry-unitary}

I **Unitary event**- och **Audience-kvalificering**-resor kan du aktivera eller inaktivera återinträde:

* Om återinträde är aktiverat kan en profil påbörja en resa flera gånger, men kan inte göra det förrän han har avslutat hela den tidigare instansen av resan.

* Om återinträde är inaktiverat kan en profil inte ange flera gånger samma resa inom den globala resetidsgränsen. Se [avsnittet](../building-journeys/journey-properties.md#global_timeout).

Som standard tillåter resor återinträde. När alternativet **Tillåt återinträde** är aktiverat visas fältet **Återkommande vänteperiod**. Det gör att du kan definiera väntetiden innan du tillåter att en profil går in på resan igen. Detta förhindrar att resor utlöses felaktigt flera gånger för samma händelse. Som standard är fältet inställt på 5 minuter. Maximala längden är 91 dagar ([global timeout](journey-properties.md#global_timeout)).

<!--
When a journey ends, its status is **[!UICONTROL Closed]**. New individuals can no longer enter the journey. Persons already in the journey automatically exit the journey. 
-->

![](assets/journey-re-entrance.png)

Efter återinträdesperioden kan profilerna återkomma till resan. För att undvika detta och helt inaktivera återinträde för dessa profiler kan du lägga till ett villkor som testar om profilen redan har angetts eller inte, med hjälp av profil- eller målgruppsdata.

<!--
Due to the 30-day journey timeout, when journey reentrance is not allowed, we cannot make sure the reentrance blocking will work more than 91 days. Indeed, as we remove all information about persons who entered the journey 91 days after they enter, we cannot know the person entered previously, more than 91 days ago. -->

## Affärsresor {#entry-business}

<!--
Business events follow reentrance rules in the same way as for unitary events. If a journey allows reentrance, the next business event will be processed.
-->

Aktivera motsvarande alternativ i avsnittet **i resans egenskaper om du vill tillåta flera körningar av affärshändelser i** Affärsresor **[!UICONTROL Execution]**.

![](assets/business-entry.png)

När det gäller affärshändelser återanvänds målgruppsdata som hämtas vid den första exekveringen under en timmes tid för en viss resa.

En profil kan finnas flera gånger på samma resa, samtidigt, men i samband med olika affärshändelser.

Mer information finns i [avsnittet](../event/about-creating-business.md)

## Läs målgruppsresor {#entry-read-audience}

**Läsande målgrupp** resor kan vara återkommande eller&quot;engångsbruk&quot;:

* För icke-återkommande/engångsresor: profilen anges endast en gång under resan.

* För återkommande resor: Som standard anges resan för varje återkommande resa i alla profiler som tillhör målgruppen. De måste slutföra resan innan de kan komma in igen vid ett annat tillfälle.

Det finns flera alternativ för återkommande målgruppsresor för läsning. Mer information finns i avsnittet [Använda en målgrupp i en resa](../building-journeys/read-audience.md).

<!--
After 91 days, a Read audience journey switches to the **Finished** status. This behavior is set for 91 days only (i.e. journey timeout default value) as all information about profiles who entered the journey is removed 91 days after they entered. Persons still in the journey automatically are impacted. They exit the journey after the 30 day timeout. 
-->
