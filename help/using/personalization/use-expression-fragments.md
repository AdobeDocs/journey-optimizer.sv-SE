---
solution: Journey Optimizer
product: journey optimizer
title: Använd uttrycksfragment
description: Lär dig använda uttrycksfragment i [!DNL Journey Optimizer] personaliseringsredigerare.
feature: Personalization, Fragments
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, bibliotek, personalisering
exl-id: 74b1be18-4829-4c67-ae45-cf13278cda65
source-git-commit: e6924928e03d494817a2368b33997029ca2eca1c
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 0%

---

# Utnyttja uttrycksfragment {#use-expression-fragments}

När du använder **personaliseringsredigerare** kan du använda alla uttrycksfragment som har skapats eller sparats i den aktuella sandlådan.

Ett fragment är en återanvändbar komponent som kan refereras till i [!DNL Journey Optimizer] kampanjer och resor. Med den här funktionen kan man skapa flera anpassade innehållsblock som kan användas av marknadsföringsanvändare för att snabbt sammanställa innehåll i en förbättrad designprocess. [Lär dig skapa och hantera fragment](../content-management/fragments.md).

➡️ [Lär dig hur du hanterar, redigerar och använder fragment i den här videon](../content-management/fragments.md#video-fragments)

## Använda ett uttrycksfragment {#use-expression-fragment}

Följ stegen nedan om du vill lägga till uttrycksfragment i ditt innehåll.

>[!NOTE]
>
>Du kan lägga till upp till 30 fragment i en viss leverans. Fragment kan bara kapslas upp till 1 nivå.

1. Öppna [personaliseringsredigerare](personalization-build-expressions.md) och väljer **[!UICONTROL Fragments]** till vänster.

   I listan visas alla uttrycksfragment som har skapats eller sparats som fragment i den aktuella sandlådan. De sorteras efter skapandedatum: nyligen tillagda uttrycksfragment visas först i listan. [Läs mer](../content-management/fragments.md#create-expression-fragment)

   ![](assets/expression-fragments-pane.png)

   Du kan även uppdatera den här listan.

   >[!NOTE]
   >
   >Om vissa fragment har ändrats eller lagts till medan du redigerar innehållet, uppdateras listan med de senaste ändringarna.

1. Klicka på ikonen + bredvid ett uttrycksfragment för att infoga motsvarande fragment-ID i redigeraren.

   ![](assets/expression-fragment-add.png)

   >[!CAUTION]
   >
   >Du kan lägga till valfritt **Utkast** eller **Live** till ert innehåll. Du kan dock inte aktivera din resa eller kampanj om ett fragment med statusen Utkast används i det. Vid en resa eller kampanjpublicering kommer utkastsfragment att visa ett fel och du måste godkänna dem för att kunna publicera.

1. När fragment-ID:t har lagts till, om du öppnar motsvarande uttrycksfragment och [redigera den](../content-management/fragments.md#edit-fragments) från gränssnittet synkroniseras ändringarna. De sprids automatiskt till alla utkast- eller direktresor/kampanjer som innehåller detta fragment-ID.

1. Klicka på **[!UICONTROL More actions]** -knapp intill ett fragment. På snabbmenyn som öppnas väljer du **[!UICONTROL View fragment]** om du vill ha mer information om det fragmentet. The **[!UICONTROL Fragment ID]** visas också och kan kopieras härifrån.

   ![](assets/expression-fragment-view.png)

1. Du kan öppna uttrycksfragmentet i ett annat fönster för att redigera dess innehåll och egenskaper, antingen med **[!UICONTROL Open fragment]** på snabbmenyn eller på **[!UICONTROL Fragment info]** fönster. [Lär dig redigera ett fragment](../content-management/fragments.md#edit-fragments)

   ![](assets/expression-fragment-open.png)

1. Sedan kan ni anpassa och validera innehållet som vanligt med hjälp av alla personaliserings- och redigeringsfunktionerna i [personaliseringsredigerare](personalization-build-expressions.md).

>[!NOTE]
>
>Om du skapar ett uttrycksfragment som innehåller flera radbrytningar och använder det i [SMS](../sms/create-sms.md#sms-content) eller [push](../push/design-push.md) så bevaras radbrytningarna. Se därför till att testa [SMS](../sms/send-sms.md) eller [push](../push/send-push.md) meddelande innan det skickas.

## Anpassa redigerbara fält {#customize-fields}

Om vissa delar av ett uttrycksfragment har gjorts redigerbara med hjälp av variabler, kan du åsidosätta deras standardvärden med en viss syntax. [Lär dig hur du anpassar fragment](../content-management/customizable-fragments.md)

Följ de här stegen för att anpassa fälten:

1. Infoga fragmentet i koden från **Fragment** -menyn.

1. Använd `<fieldId>="<value>"` koden i slutet av syntaxen för att åsidosätta variabelns standardvärde.

   I exemplet nedan åsidosätter vi värdet för en variabel vars ID är &quot;sport&quot; med &quot;yoga&quot;-värdet. Då visas&quot;yoga&quot; i fragmentinnehållet överallt där variabeln&quot;sport&quot; refereras.

   ![](../content-management/assets/fragment-expression-use.png)

Ett exempel som visar hur du lägger till redigerbara fält i ett uttrycksfragment och åsidosätter deras värden när du skapar ett e-postmeddelande finns i [det här avsnittet](../content-management/customizable-fragments.md#example).

## Bryt arv {#break-inheritance}

När du lägger till ett fragment-ID i personaliseringsredigeraren synkroniseras ändringarna som gjorts i det ursprungliga uttrycksfragmentet.

Du kan även klistra in innehållet i ett uttrycksfragment i redigeraren. Välj **[!UICONTROL Paste fragment]** för att infoga innehållet.

![](assets/expression-fragment-paste.png)

I så fall bryts arvet från det ursprungliga fragmentet. Fragmentets innehåll kopieras till redigeraren och ändringarna synkroniseras inte längre.

Det blir ett fristående element som inte längre är länkat till det ursprungliga fragmentet. Du kan redigera det som vilket annat element som helst i koden.

