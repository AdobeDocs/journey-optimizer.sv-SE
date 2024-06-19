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
source-git-commit: 893f7146b358da48153b1e6bc74b8f622028df76
workflow-type: tm+mt
source-wordcount: '611'
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
   >
   > Observera att fragmentstatus gradvis introduceras under flera dagar efter Journey Optimizer juni-utgåvan. Vissa användare har omedelbar åtkomst, men andra kan uppleva en fördröjning innan den blir tillgänglig i deras miljöer. Observera att fragment inte behöver vara **Live** för att användas i era resor och kampanjer.

1. När fragment-ID:t har lagts till, om du öppnar motsvarande uttrycksfragment och [redigera den](../content-management/fragments.md#edit-fragments) från gränssnittet synkroniseras ändringarna. De sprids automatiskt till alla utkast- eller direktresor/kampanjer som innehåller detta fragment-ID.

1. Klicka på **[!UICONTROL More actions]** -knapp intill ett fragment. På snabbmenyn som öppnas väljer du **[!UICONTROL View fragment]** om du vill ha mer information om det fragmentet. The **[!UICONTROL Fragment ID]** visas också och kan kopieras härifrån.

   ![](assets/expression-fragment-view.png)

1. Du kan öppna uttrycksfragmentet i ett annat fönster för att redigera dess innehåll och egenskaper, antingen med **[!UICONTROL Open fragment]** på snabbmenyn eller på **[!UICONTROL Fragment info]** fönster. [Lär dig redigera ett fragment](../content-management/fragments.md#edit-fragments)

   ![](assets/expression-fragment-open.png)

1. Sedan kan ni anpassa och validera innehållet som vanligt med hjälp av alla personaliserings- och redigeringsfunktionerna i [personaliseringsredigerare](personalization-build-expressions.md).

>[!NOTE]
>
>Om du skapar ett uttrycksfragment som innehåller flera radbrytningar och använder det i [SMS](../sms/create-sms.md#sms-content) eller [push](../push/design-push.md) så bevaras radbrytningarna. Se därför till att testa [SMS](../sms/send-sms.md) eller [push](../push/send-push.md) meddelande innan det skickas.

## Bryt arv {#break-inheritance}

När du lägger till ett fragment-ID i personaliseringsredigeraren synkroniseras ändringarna som gjorts i det ursprungliga uttrycksfragmentet.

Du kan även klistra in innehållet i ett uttrycksfragment i redigeraren. Välj **[!UICONTROL Paste fragment]** för att infoga innehållet.

![](assets/expression-fragment-paste.png)

I så fall bryts arvet från det ursprungliga fragmentet. Fragmentets innehåll kopieras till redigeraren och ändringarna synkroniseras inte längre.

Det blir ett fristående element som inte längre är länkat till det ursprungliga fragmentet. Du kan redigera det som vilket annat element som helst i koden.

