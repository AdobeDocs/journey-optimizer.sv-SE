---
solution: Journey Optimizer
product: journey optimizer
title: Hoppa från en resa till en annan
description: Hoppa från en resa till en annan
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: hopp, aktivitet, resa, dela, dela upp
exl-id: 46d8950b-8b02-4160-89b4-1c492533c0e2
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 2%

---

# Hoppa från en resa till en annan {#jump}

>[!CONTEXTUALHELP]
>id="ajo_journey_jump"
>title="Hoppaktivitet"
>abstract="Med en hoppåtgärd kan ni föra människor från en resa till en annan. Med den här funktionen kan du förenkla utformningen av mycket komplexa resor och skapa resor baserat på gemensamma och återanvändbara resemönster."

The **[!UICONTROL Jump]** kan ni med hjälp av en viss aktivitet föra individer från en resa till en annan. Med den här funktionen kan du:

* förenkla utformningen av mycket komplexa resor genom att dela upp dem i flera.
* bygga resor baserat på gemensamma och återanvändbara resemönster

Lägg bara till en **[!UICONTROL Jump]** och välj en målresa. När personen kommer in i **[!UICONTROL Jump]** skickas en intern händelse till den första händelsen i målresan. Om **[!UICONTROL Jump]** åtgärden lyckas, den enskilda personen fortsätter att göra framsteg på resan. Beteendet liknar andra åtgärder.

I målresan utlöses den första händelsen internt av **[!UICONTROL Jump]** aktiviteten kommer att få den enskilda resan att flyta.

## Livscykel

Säg att du har lagt till en **[!UICONTROL Jump]** verksamhet på resa A till resa B. Resa A är **ursprunglig resa** och resa B, **målresa**.
Här är de olika stegen i körningsprocessen:

**Resa A** aktiveras från en extern händelse:

1. Resa A får en extern händelse som rör en individ.
1. Personen når **[!UICONTROL Jump]** steg.
1. Personen flyttas till resa B och fortsätter till nästa steg i resa A, efter **[!UICONTROL Jump]** steg.

Under resa B utlöses den första händelsen internt via **[!UICONTROL Jump]** verksamhet från resa A:

1. Resan B fick en intern händelse från resa A.
1. Personen börjar flyta i resa B.

>[!NOTE]
>
>Resa B kan också utlösas via en extern händelse.

## God praxis och begränsningar

### Redigering

* The **[!UICONTROL Jump]** aktiviteten är bara tillgänglig på resor som använder ett namnutrymme.
* Du kan bara hoppa till en resa som använder samma namnutrymme som ursprungsresan.
* Du kan inte hoppa till en resa som börjar med en **Målgruppskvalifikation** händelse eller **Läs målgrupp**.
* Du kan inte ha en **[!UICONTROL Jump]** aktivitet och **Målgruppskvalifikation** händelse eller **Läs målgrupp** på samma resa.
* Du kan inkludera så många **[!UICONTROL Jump]** aktiviteter som ni behöver på en resa. Efter **[!UICONTROL Jump]** kan du lägga till alla aktiviteter som behövs.
* Du kan ha så många hoppnivåer som behövs. Till exempel hoppar resa A till resa B, som hoppar till resa C och så vidare.
* Målresan kan även omfatta så många **[!UICONTROL Jump]** aktiviteter efter behov.
* Loopmönster stöds inte. Det finns inget sätt att länka samman två eller flera resor som skulle skapa en oändlig slinga. The **[!UICONTROL Jump]** aktivitetskonfigurationsskärmen förhindrar dig från att göra detta.

### Körning

* När **[!UICONTROL Jump]** aktiviteten körs, den senaste versionen av målresan aktiveras.
* Som vanligt kan en unik individ bara vara närvarande en gång under samma resa. Om den person som har åsamkats från ursprungsresan redan befinner sig på målresan, kommer personen alltså inte att ta sig in på målresan. Inga fel rapporteras på **[!UICONTROL Jump]** aktivitet eftersom detta är ett normalt beteende.

## Konfigurera hoppaktiviteten

1. Designa **ursprunglig resa**.

   ![](assets/jump1.png)

1. Lägg till en **[!UICONTROL Jump]** aktivitet, från **[!UICONTROL ACTIONS]** kategori. Lägg till en etikett och en beskrivning.

   ![](assets/jump2.png)

1. Klicka inuti **Målresa** fält.
I listan visas alla reseversioner som är utkast, live eller i testläge. Resor som använder ett annat namnutrymme eller som börjar med ett **Målgruppskvalifikation** -händelsen är inte tillgänglig. Målresor som skulle skapa ett slingmönster filtreras också bort.

   ![](assets/jump3.png)

   >[!NOTE]
   >
   >Du kan klicka på **Öppna målresa** -ikonen till höger för att öppna målresan på en ny flik.

1. Välj den målresa som du vill hoppa till.
The **Första händelsen** fältet är förifyllt med namnet på målresans första händelse. Om målresan innehåller flera händelser **[!UICONTROL Jump]** tillåts bara för den första händelsen.

   ![](assets/jump4.png)

1. The **Åtgärdsparametrar** -avsnittet visar alla fält för målhändelsen. På samma sätt som för andra typer av åtgärder mappar du varje fält med fält från ursprungshändelsen eller datakällan. Den här informationen skickas till målresan vid körning.
1. Lägg till nästa aktiviteter för att slutföra din ursprungliga resa.

   ![](assets/jump5.png)


   >[!NOTE]
   >
   >Personens identitet mappas automatiskt. Den här informationen visas inte i gränssnittet.

Dina **[!UICONTROL Jump]** aktiviteten har konfigurerats. Så snart resan är live eller i testläge når individerna **[!UICONTROL Jump]** steget flyttas från till målresan.

När en **[!UICONTROL Jump]** -aktiviteten konfigureras under en resa, en **[!UICONTROL Jump]** Inmatningsikonen läggs automatiskt till i början av målresan. Detta hjälper er att identifiera att resan kan utlösas externt men även internt från en **[!UICONTROL Jump]** aktivitet.

![](assets/jump7.png)

## Felsökning

Fel uppstår om:
* målresan inte längre existerar
* målresan är utkast, avslutad eller stoppad
* om den första händelsen i målresan har ändrats och mappningen är bruten

![](assets/jump6.png)
