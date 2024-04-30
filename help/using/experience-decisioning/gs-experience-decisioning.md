---
title: Kom igång med Experience Decision
description: Läs mer om Experience Decision
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 4c57dbf9-b2a4-42da-8aa3-5a1b3a475a32
source-git-commit: f71795c99157ce43f5250aaf10eb0b97f235b454
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Kom igång med Experience Decision {#get-started-experience-decisioning}

>[!BEGINSHADEBOX &quot;Det du hittar i den här handboken&quot;]

* **[Kom igång med Experience Decision](gs-experience-decisioning.md)**
* Hantera dina beslutsposter: [Konfigurera objektkatalogen](catalogs.md) - [Skapa beslutsobjekt](items.md) - [Hantera artikelsamlingar](collections.md)
* Konfigurera objektmarkering: [Skapa beslutsregler](rules.md) - [Skapa rangordningsmetoder](ranking.md)
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

## Vad är Experience Decision? {#about}

>[!AVAILABILITY]
>
>Funktionen för upplevelsebeslut är för närvarande endast tillgänglig som betaversion för utvalda användare. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.
>
>Beslutspolicyer kan endast användas i kodbaserade upplevelsekampanjer.

Experience Decision förenklar personaliseringen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas beslutsposter och en sofistikerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person.

Dessa beslutsobjekt integreras smidigt i ett stort antal inkommande ytor via den nya kodbaserade upplevelsekanalen, som nu är tillgänglig inom Journey Optimizer-kampanjer.

## Viktiga steg i Experience Decision {#steps}

De viktigaste stegen för Experience Decision är följande:

1. **Tilldela rätt behörigheter**. Besluten är endast tillgängliga för användare som har tillgång till ett Experience Decision-relaterat **[!UICONTROL role]** som beslutsfattare. Om du inte kan komma åt beslut måste din behörighet utökas.

   +++Lär dig hur du tilldelar rollen Beslutsledare

   1. Tilldela en roll till en användare i [!DNL Permissions] -produkt, navigera till **[!UICONTROL Roles]** och välj Beslutshanterare.

      ![](assets/decision_permission_1.png)

   1. Klicka på **[!UICONTROL Add user]** på fliken **[!UICONTROL Users]**.

      ![](assets/decision_permission_2.png)

   1. Ange användarens namn eller e-postadress eller välj användaren i listan och klicka på **[!UICONTROL Save]**.

      Om användaren inte har skapats tidigare, se [Lägga till användardokumentation](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users).

      ![](assets/decision_permission_3.png)

   Användaren bör sedan få ett e-postmeddelande som omdirigeras till din instans.

+++

1. **Konfigurera anpassade attribut**: Anpassa beslutsobjektets katalog efter dina specifika krav genom att ställa in anpassade attribut i katalogschemat.

1. **Skapa beslutsobjekt** för att visa för er målgrupp.

1. **Ordna med samlingar**: Använd samlingar för att kategorisera beslutsobjekt baserat på attributbaserade regler. Införliva samlingar i era urvalsstrategier för att avgöra vilken samling av beslutsobjekt som ska övervägas.

1. **Skapa beslutsregler**: Beslutsregler används i beslutsposter och/eller urvalsstrategier för att fastställa till vilka en beslutspost kan visas.

1. **Implementera rangordningsmetoder**: Skapa rangordningsmetoder och tillämpa dem i beslutsstrategier för att fastställa prioritetsordningen för val av beslutsposter.

1. **Skapa urvalsstrategier**: Bygg upp urvalsstrategier som utnyttjar samlingar, beslutsregler och rangordningsmetoder för att identifiera de beslutsobjekt som är lämpliga att visa för profiler.

1. **Bädda in en beslutsprincip i din kodbaserade kampanj**: Beslutspolicyn kombinerar flera urvalsstrategier för att fastställa vilka beslutsfrågor som ska visas för den avsedda målgruppen.
