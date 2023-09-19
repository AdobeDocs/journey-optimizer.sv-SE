---
title: Kom igång med Experience Decision
description: Läs mer om Experience Decision
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 9b7280c33ce8238b54f7fd1865545f865ffb72ed
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 1%

---

# Kom igång med Experience Decision {#get-started-experience-decisioning}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* **[Kom igång med Experience Decision](gs-experience-decisioning.md)**
* Hantera dina beslutsobjekt
   * [Konfigurera objektkatalogen](catalogs.md)
   * [Skapa beslutsobjekt](items.md)
   * [Hantera artikelsamlingar](collections.md)
* Konfigurera val av objekt
   * [Skapa beslutsregler](rules.md)
   * [Skapa rangordningsmetoder](ranking.md)
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

## Vad är Experience Decision? {#about}

>[!AVAILABILITY]
>
>Funktionen för upplevelsebeslut är för närvarande endast tillgänglig som betaversion för utvalda användare. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.

Experience Decision förenklar personaliseringen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas beslutsposter och en sofistikerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person.

Dessa beslutsobjekt integreras smidigt i ett stort antal inkommande ytor via den nya kodbaserade upplevelsekanalen, som nu är tillgänglig inom Journey Optimizer-kampanjer.

**Begränsningar:**

* Beslutspolicyer kan endast användas i kodbaserade upplevelsekampanjer.
* För närvarande är frekvensbegränsning inte tillgängligt i Experience Decision.

## Viktiga steg i Experience Decision {#steps}

De viktigaste stegen för Experience Decision är följande:

1. **Konfigurera anpassade attribut**: Anpassa beslutsobjektets katalog efter dina specifika krav genom att ställa in anpassade attribut i katalogschemat.

1. **Skapa beslutsobjekt** för att visa för er målgrupp.

1. **Ordna med samlingar**: Använd samlingar för att kategorisera beslutsobjekt baserat på attributbaserade regler. Införliva samlingar i era urvalsstrategier för att avgöra vilken samling av beslutsobjekt som ska övervägas.

1. **Skapa beslutsregler**: Beslutsregler används i beslutsposter och/eller urvalsstrategier för att fastställa till vilka en beslutspost kan visas.

1. **Implementera rangordningsmetoder**: Skapa rangordningsmetoder och tillämpa dem i beslutsstrategier för att fastställa prioritetsordningen för val av beslutsposter.

1. **Skapa urvalsstrategier**: Bygg upp urvalsstrategier som utnyttjar samlingar, beslutsregler och rangordningsmetoder för att identifiera de beslutsobjekt som är lämpliga att visa för profiler.

1. **Bädda in en beslutsprincip i din kodbaserade kampanj**: Beslutspolicyn kombinerar flera urvalsstrategier för att fastställa vilka beslutsfrågor som ska visas för den avsedda målgruppen.

<!--## Glossary-->
