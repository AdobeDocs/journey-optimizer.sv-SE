---
title: Kopiera en resa till en annan sandlåda
description: Lär dig hur du kopierar en resa till en annan sandlåda
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 4d211b9a0087526fe81d7b989195f21ceab42865
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Kopiera en resa till en annan sandlåda {#copy-to-sandbox}

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_main"
>title="Kopiera en resa till en annan sandlåda"
>abstract="Med Journey Optimizer kan du kopiera en hel resa från en sandlåda till en annan. Du kan t.ex. kopiera en resa från sandlådemiljön Stage till produktionssandlådan. Förutom själva resan kopierar Journey Optimizer också merparten av de objekt som resan är beroende av."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_sandbox_details"
>title="Sandlådeinformation"
>abstract="Markera den målsandlåda som du vill kopiera resan till. Endast sandlådor i din IMS-organisation är tillgängliga."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_object_details"
>title="Objektinformation"
>abstract="Det här är resan du ska kopiera."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_dependent_objects"
>title="Beroende objekt"
>abstract="Det här är listan över associerade objekt som används under resan. I den här listan visas namn, objekttyp och internt Journey Optimizer-id."

Med Journey Optimizer kan du kopiera en hel resa från en sandlåda till en annan. Du kan t.ex. kopiera en resa från sandlådemiljön på scenen till produktionssandlådan. Förutom själva resan kopierar Journey Optimizer även de flesta av de objekt som resan är beroende av: meddelanden, segment, förinställningar, scheman, händelser och åtgärder. Se [begränsningar](../event/about-events.md)

>[!CAUTION]
>
>Vi garanterar inte att alla länkade element kopieras till målsandlådan. Vi rekommenderar att du gör en grundlig kontroll innan du publicerar resan. Detta gör att du kan identifiera eventuella saknade objekt.

De kopierade objekten i målsandlådan är unika och det finns ingen risk för att befintliga element skrivs över. Både resan och alla meddelanden under resan överförs i utkastläge. På så sätt kan du utföra en grundlig validering innan den publiceras i målsandlådan. Kopieringsprocessen kopierar bara metadata om resan och objekten i den resan. Inga profil- eller datauppsättningsdata kopieras som en del av den här processen.

Så här kopierar du en resa till en annan sandlåda:

1. Klicka på **[!UICONTROL Journeys]**. Listan över resor visas.

2. Sök efter den resa du vill kopiera och klicka på **Fler åtgärder** ikon (de tre punkterna bredvid resans namn) och klicka på **Kopiera till sandlåda**.

   ![](assets/copy-sandbox1.png)

   The **Kopiera till sandlåda** visas.

   ![](assets/copy-sandbox2.png)

3. Välj **Målsandlåda** i listrutan. Endast sandlådor i din IMS-organisation är tillgängliga.

4. Granska **Beroende objekt** -avsnitt. Det här är listan över associerade objekt som används under resan. I den här listan visas namn, objekttyp och internt Journey Optimizer-id.

5. Klicka på **Kopiera** i det övre högra hörnet för att börja kopiera resan till målsandlådan.

   ![](assets/copy-sandbox3.png)

   Kopieringsprocessen börjar och förloppet för varje enskilt objekt visas. Kopieringsprocessen varierar beroende på hur komplicerad resan är och hur många objekt som behöver kopieras. Om ett fel påträffas visas ett meddelande för det relaterade objektet.

   ![](assets/copy-sandbox4.png)

6. När kopieringen är klar klickar du på **Stäng**.

7. Få åtkomst till målsandlådan och kontrollera alla kopierade objekt noggrant.

## Kopiera processer och begränsningar {#limitations}

Vi garanterar inte att alla länkade element kopieras till målsandlådan. Vi rekommenderar att du gör en grundlig kontroll. Identifiera eventuella saknade objekt och skapa dem manuellt innan resan publiceras.

Följande objekt kopieras:

* Segment

   Ett segment kan bara kopieras en gång från en sandlåda till en annan. Efterföljande begäranden om att kopiera segmentet misslyckas. När ett segment har kopierats går det inte att redigera det i målsandlådan.

* Schema

   Scheman som används under den här resan kopieras.

* Meddelande

   Det eller de fysiska meddelanden som används i resan (antingen e-post eller push-meddelanden). Fält som används för personalisering i meddelandet kontrolleras inte för fullständighet. Innehållsblock kopieras inte.

* Resa - arbetsytedetaljer

   Återgivningen av resan på arbetsytan, inklusive objekt i resan, t.ex. villkor, åtgärder, händelser, läs segment osv. Hoppaktiviteten tas inte med i kopian.

* Händelse

   Händelserna och händelseinformationen som används under resan kopieras.

* Åtgärd

   De åtgärder och åtgärdsdetaljer som används under resan kopieras.

Förinställningar kopieras inte över. Systemet väljer automatiskt närmaste matchning i målsandlådan baserat på meddelandetyp och förinställningsnamn. Om det inte finns några förinställningar i målsandlådan misslyckas kopieringen av förinställningen. Det innebär att meddelandekopian inte fungerar eftersom ett meddelande kräver en förinställning för att kunna konfigureras. I det här fallet måste minst en förinställning skapas för den högra kanalen i meddelandet för att kopian ska fungera.

