---
title: Kom igång med Experience Decision
description: Läs mer om Experience Decision
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
badge: label="Begränsad tillgänglighet"
exl-id: 4c57dbf9-b2a4-42da-8aa3-5a1b3a475a32
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# Kom igång med Experience Decision {#get-started-experience-decisioning}

>[!AVAILABILITY]
>
>Experience Decision är för närvarande bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.
>
>För tillfället är funktionen inte tillgänglig för kunder som har köpt Adobe **Hälsovårdssköld** och **Sköld för skydd av privatlivet och säkerheten** tilläggserbjudanden.

## Vad är Experience Decision? {#about}

Experience Decision förenklar personaliseringen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas beslutsposter och en sofistikerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person.

Dessa beslutsobjekt integreras smidigt i ett stort antal inkommande ytor via den nya kodbaserade upplevelsekanalen, som nu är tillgänglig inom Journey Optimizer-kampanjer. Policy för Experience Decision-beslut är endast tillgängliga för kodbaserade upplevelsekampanjer.

## Viktiga steg i Experience Decision {#steps}

De viktigaste stegen för Experience Decision är följande:

1. **Tilldela rätt behörigheter**. Experience Decision är bara tillgängligt för användare som har tillgång till ett Experience Decision-relaterat **[!UICONTROL role]** som beslutsfattare. Om du inte kan komma åt Experience Decision måste du utöka din behörighet.

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

1. **Konfigurera anpassade attribut**: Anpassa objektkatalogen efter dina specifika behov genom att ställa in anpassade attribut i katalogschemat.

1. **Skapa beslutsobjekt** för att visa för er målgrupp.

1. **Ordna med samlingar**: Använd samlingar för att kategorisera beslutsobjekt baserat på attributbaserade regler. Införliva samlingar i era urvalsstrategier för att avgöra vilken samling av beslutsobjekt som ska övervägas.

1. **Skapa beslutsregler**: Beslutsregler används i beslutsposter och/eller urvalsstrategier för att fastställa till vilka en beslutspost kan visas.

1. **Implementera rangordningsmetoder**: Skapa rangordningsmetoder och tillämpa dem i beslutsstrategier för att fastställa prioritetsordningen för val av beslutsposter.

1. **Skapa urvalsstrategier**: Bygg upp urvalsstrategier som utnyttjar samlingar, beslutsregler och rangordningsmetoder för att identifiera de beslutsobjekt som är lämpliga att visa för profiler.

1. **Bädda in en beslutsprincip i din kodbaserade kampanj**: Beslutspolicyn kombinerar flera urvalsstrategier för att fastställa vilka beslutsfrågor som ska visas för den avsedda målgruppen.
