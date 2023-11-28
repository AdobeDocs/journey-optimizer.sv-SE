---
solution: Journey Optimizer
product: journey optimizer
title: Använd uttrycksfragment
description: Lär dig använda uttrycksfragment i [!DNL Journey Optimizer] Uttrycksredigerare.
feature: Personalization, Fragments
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, bibliotek, personalisering
exl-id: 74b1be18-4829-4c67-ae45-cf13278cda65
source-git-commit: 08f3fc1837a4daa1ecaa7afcd53c80381177efb0
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Utnyttja uttrycksfragment {#use-expression-fragments}

När du använder **Uttrycksredigerare** kan du använda alla uttrycksfragment som har skapats eller sparats i den aktuella sandlådan.

Lär dig hur du skapar och hanterar fragment i [det här avsnittet](../content-management/fragments.md).

➡️ [Lär dig hur du hanterar, redigerar och använder fragment i den här videon](../content-management/fragments.md#video-fragments)

## Använda ett uttrycksfragment {#use-expression-fragment}

Följ stegen nedan om du vill lägga till uttrycksfragment i ditt innehåll.

1. Öppna [Uttrycksredigerare](personalization-build-expressions.md) och väljer **[!UICONTROL Fragments]** till vänster.

   ![](assets/expression-fragments-pane.png)

   I listan visas alla uttrycksfragment som har skapats eller sparats som fragment i den aktuella sandlådan. [Läs mer](../content-management/fragments.md#create-expression-fragment)

   >[!NOTE]
   >
   >Fragment sorteras efter skapandedatum: nyligen tillagda uttrycksfragment visas först i listan.

1. Du kan också uppdatera listan.

   >[!NOTE]
   >
   >Om vissa fragment har ändrats eller lagts till medan du redigerar innehållet, uppdateras listan med de senaste ändringarna.

1. Klicka på ikonen + bredvid ett uttrycksfragment för att infoga motsvarande fragment-ID i redigeraren.

   ![](assets/expression-fragment-add.png)

   När fragment-ID:t har lagts till, om du öppnar motsvarande uttrycksfragment och [redigera den](../content-management/fragments.md#edit-fragments) från gränssnittet synkroniseras ändringarna. De sprids automatiskt till alla **[!UICONTROL Draft]** resor/kampanjer som innehåller detta fragment-ID.

   >[!NOTE]
   >
   >Ändringarna sprids inte till innehåll som används i **[!UICONTROL Live]** resor eller kampanjer.

1. Klicka på **[!UICONTROL More actions]** -knapp intill ett fragment.

1. På snabbmenyn som öppnas väljer du **[!UICONTROL View fragment]** om du vill ha mer information om det fragmentet. The **[!UICONTROL Fragment ID]** visas också och kan kopieras härifrån.

   ![](assets/expression-fragment-view.png)

1. Du kan öppna uttrycksfragmentet i ett annat fönster för att redigera dess innehåll och egenskaper, antingen med **[!UICONTROL Open fragment]** på snabbmenyn eller på **[!UICONTROL Fragment info]** fönster. [Lär dig redigera ett fragment](../content-management/fragments.md#edit-fragments)

   ![](assets/expression-fragment-open.png)

1. Sedan kan ni anpassa och validera innehållet som vanligt med hjälp av alla personaliserings- och redigeringsfunktionerna i [Uttrycksredigerare](personalization-build-expressions.md).

>[!NOTE]
>
>Om du skapar ett uttrycksfragment som innehåller flera radbrytningar och använder det i [SMS](../sms/create-sms.md#sms-content) eller [push](../push/design-push.md) så bevaras radbrytningarna. Se därför till att testa [SMS](../sms/send-sms.md) eller [push](../push/send-push.md) meddelande innan det skickas.

## Bryt arv {#break-inheritance}

När du lägger till ett fragment-ID i uttrycksredigeraren synkroniseras ändringarna som gjorts i det ursprungliga uttrycksfragmentet.

Du kan även klistra in innehållet i ett uttrycksfragment i redigeraren. Välj **[!UICONTROL Paste fragment]** för att infoga innehållet.

![](assets/expression-fragment-paste.png)

I så fall bryts arvet från det ursprungliga fragmentet. Fragmentets innehåll kopieras till redigeraren och ändringarna synkroniseras inte längre.

Det blir ett fristående element som inte längre är länkat till det ursprungliga fragmentet. Du kan redigera det som vilket annat element som helst i koden.

