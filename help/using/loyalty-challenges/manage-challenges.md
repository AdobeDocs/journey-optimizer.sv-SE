---
solution: Journey Optimizer
product: journey optimizer
title: Hantera lojalitetsutmaningar
description: Lär dig hantera, övervaka och optimera lojalitetsutmaningar i Adobe Journey Optimizer.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
source-git-commit: 7b075996eebd03f0aa812da3ece9cfebef8c65fc
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---


# Hantera utmaningar {#manage-challenges}

>[!CONTEXTUALHELP]
>id="ajo_loyalty_manage_challenges"
>title="Hantera lojalitetsutmaningar"
>abstract="När ni har skapat och publicerat lojalitetsutmaningar kan ni visa, redigera, övervaka och optimera dem för att säkerställa att de ger önskat resultat för ert lojalitetsprogram."

När ni har skapat och publicerat lojalitetsutmaningar kan ni visa, redigera, övervaka och optimera dem för att säkerställa att de ger önskat resultat för ert lojalitetsprogram.

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](gs-loyalty-challenges.md) - snabböversikt och nästa steg
* [Förstå lojalitetsutmaningar](get-started.md) - Funktioner, arbetsflöde, förutsättningar
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* **Hantera utmaningar** ◀ }︎ **Du är här** - Redigera, övervaka, optimera

>[!ENDSHADEBOX]

## Utmaningens livscykel {#challenge-lifecycle}

Utmaningarna rör sig mellan olika statusar:

* **Utkast**: Skapas eller redigeras
* **Schemalagd**: Publicerad, aktiveras på startdatumet
* **Live**: Aktiv och kunder kan delta
* **Slutförd**: Slutdatum eller mål har uppfyllts
* **Stoppad**: Manuellt stoppad före slutförande
* **Arkiverad**: Har arkiverats i organisationssyfte

## Redigera utmaningar {#edit-challenges}

Du kan redigera utmaningar beroende på deras aktuella status:

* **Utmaningar**: Fullständig redigering
* **Schemalagda/dynamiska utmaningar**: Begränsad redigering (innehållsuppdateringar, datumtillägg)

För ändringar som kräver större ändringar, duplicera utmaningen och skapa en ny version.

## Duplicerade utmaningar {#duplicate-challenges}

Duplicera utmaningarna med:
* Kör om framgångsrika utmaningar för nya tidsperioder
* Skapa varianter för olika målgrupper
* Uppdatera uppgiftskrav eller belöningar
* Återaktivera stoppade eller slutförda problem

## Bildskärmsprestanda {#monitor-performance}

Spåra utmaningsprestanda genom:

* **Deltagandestatistik**: Registrering, aktiva deltagare
* **Resultatmått**: Slutförandefrekvens, genomsnittlig slutförandetid
* **Belöningsmått**: Totalt antal distribuerade belöningar, belöningar per typ
* **Interaktionsstatistik**: Intryck av innehållskort, meddelandeleverans

Få åtkomst till prestandadata på fliken Prestanda för utmaningar och de automatiskt genererade reserapporterna.

## Bästa praxis {#best-practices}

### Skapa problem

* Börja enkelt för din första utmaning
* Testa grundligt före publicering till produktion
* Försäkra er om tydlig kommunikation om krav och belöningar
* Ställ in realistisk timing så att kunderna kan klara av utmaningar

### Förvaltning och övervakning

* Kontrollera hur utmaningen fungerar regelbundet (minst en gång i veckan för utmaningar live)
* Använd beskrivande namn som anger syfte, målgrupp eller tidsperiod
* Använd konsekventa taggar för organisationen
* Arkivera slutförda utmaningar för att hålla lagret hanterbart

## Felsökning {#troubleshooting}

Vanliga problem och lösningar:

* **Utmaningen visas inte för kunderna**: Verifiera status, målgruppsbehörighet, konfiguration av innehållskort
* **Låga deltagandefrekvenser**: Granska innehållssynlighet, meddelandeklarhet, uppgiftsgenomförbarhet
* **Aktiviteter som inte utlöser**: Kontrollera dataöverföring, händelseattribut, rätt målgrupp
* **Utmärkelser som inte allokerar**: Bekräfta konfigurationen och den externa systemanslutningen

## Nästa steg {#next-steps}

* [Skapa utmaningar](create-challenges.md) - Bygg nya lojalitetsutmaningar
* [Förstå lojalitetsutmaningar](get-started.md) - Granska funktioner och funktioner
