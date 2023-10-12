---
solution: Journey Optimizer
product: journey optimizer
title: Kopiera en resa till en annan sandlåda
description: Lär dig kopiera en resa till en annan sandlåda
feature: Journeys
topic: Content Management
role: User, Developer
level: Intermediate
keywords: sandlåda, resa, kopia, miljö
exl-id: 8c63f2f2-5cec-4cb2-b3bf-2387eefb5002
source-git-commit: aaa9dcbfc691eac0fd9d06e905c2e1d7612d854a
workflow-type: tm+mt
source-wordcount: '834'
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
>abstract="Markera den målsandlåda som du vill kopiera resan till. Endast sandlådor i din organisation är tillgängliga."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_object_details"
>title="Objektinformation"
>abstract="Det här är resan du ska kopiera."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_dependent_objects"
>title="Beroende objekt"
>abstract="Det här är listan över associerade objekt som används under resan. I den här listan visas namn, objekttyp och internt Journey Optimizer-id."

Med Journey Optimizer kan du kopiera en hel resa från en sandlåda till en annan. Du kan t.ex. kopiera en resa från sandlådemiljön på scenen till produktionssandlådan. Förutom själva resan kopierar Journey Optimizer även de flesta av de objekt som resan är beroende av: målgrupper, ytor (t.ex. förinställningar), scheman, händelser och åtgärder. Mer information om kopierade objekt finns i [section](#limitations).

>[!CAUTION]
>
>Vi garanterar inte att alla länkade element kopieras till målsandlådan. Vi rekommenderar att du gör en grundlig kontroll innan du publicerar resan. På så sätt kan du identifiera eventuella saknade objekt.

De kopierade objekten i målsandlådan är unika och det finns ingen risk för att befintliga element skrivs över. Både resan och alla meddelanden under resan överförs i utkastläge. På så sätt kan du utföra en grundlig validering innan den publiceras i målsandlådan. Kopieringsprocessen kopierar bara metadata om resan och objekten i den resan. Inga profil- eller datauppsättningsdata kopieras som en del av den här processen.

Så här kopierar du en resa till en annan sandlåda:

1. Klicka på **[!UICONTROL Journeys]**. Listan över resor visas.

2. Sök efter den resa du vill kopiera och klicka på **Fler åtgärder** ikon (de tre punkterna bredvid resans namn) och klicka på **Kopiera till sandlåda**.

   ![](assets/copy-sandbox1.png)

   The **Kopiera till sandlåda** visas.

   ![](assets/copy-sandbox2.png)

3. Välj **Målsandlåda** i listrutan. Endast sandlådor i din organisation är tillgängliga.

4. Granska **Beroende objekt** -avsnitt. Det här är listan över associerade objekt som används under resan. I den här listan visas namn, objekttyp och internt Journey Optimizer-id.

5. Klicka på **Kopiera** i det övre högra hörnet för att börja kopiera resan till målsandlådan.

   ![](assets/copy-sandbox3.png)

   Kopieringsprocessen börjar och förloppet för varje enskilt objekt visas. Kopieringsprocessen varierar beroende på hur komplicerad resan är och hur många objekt som behöver kopieras. Om ett fel påträffas visas ett meddelande för det relaterade objektet.

   ![](assets/copy-sandbox4.png)

6. När kopieringen är klar klickar du **Stäng**.

7. Få åtkomst till målsandlådan och kontrollera alla kopierade objekt noggrant.

## Kopiera processer och begränsningar {#limitations}

Alla länkade element kanske inte kopieras till målsandlådan. Adobe rekommenderar starkt att du gör en grundlig kontroll. Identifiera eventuella saknade objekt och skapa dem manuellt innan resan publiceras.

Följande objekt kopieras:

* Målgrupp

  En målgrupp kan bara kopieras en gång från en sandlåda till en annan. När en målgrupp har kopierats går den inte att redigera i målsandlådan.

* Schema

  Scheman som används under den här resan kopieras.

* Meddelande

  De kanalåtgärder som används under resan. Fält som används för personalisering i meddelandet kontrolleras inte för fullständighet. Innehållsblock kopieras inte.

* Resa - arbetsytedetaljer

  Beteckningen av resan på arbetsytan, inklusive objekt i resan, t.ex. villkor, åtgärder, händelser, läsning av målgrupper osv. Hoppaktiviteten tas inte med i kopian.

* Händelse

  Händelserna och händelseinformationen som används under resan kopieras.

* Åtgärd

  De åtgärder och åtgärdsdetaljer som används under resan kopieras.

Ytor (t.ex. förinställningar) kopieras inte över. Systemet väljer automatiskt den närmaste matchningen i målsandlådan baserat på meddelandetyp och ytnamn. Om det inte finns några ytor i målsandlådan misslyckas kopieringen av ytan. Det innebär att meddelandekopian också kommer att misslyckas eftersom ett meddelande kräver att en yta är tillgänglig för konfiguration. I det här fallet måste minst en yta skapas för den högra kanalen i meddelandet för att kopian ska fungera.

För scheman, sammanfogningsprinciper och målgrupper refereras endast de objekten till andra gången de kopieras. De behandlas som objekt som redan finns och kommer att kopieras igen. Det innebär att dessa objekt bara kan kopieras en gång.

Det tar fem minuter innan Adobe Journey Optimizer kan referera till scheman, kopplingsprofiler och målgrupper utan att ett fel visas på arbetsytan. Vänta i fem minuter så kommer dessa referenser att vara tillgängliga.
