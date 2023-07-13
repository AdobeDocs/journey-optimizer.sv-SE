---
solution: Journey Optimizer
product: journey optimizer
title: Lägg till ett meddelande i en resa
description: Lär dig hur du lägger till ett meddelande under en resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: resa, meddelande, push, sms, e-post, i appen
exl-id: 4db07a9e-c3dd-4873-8bd9-ac34c860694c
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# E-post, i appen, push, SMS{#add-a-message-in-a-journey}

[!DNL Journey Optimizer] innehåller inbyggda meddelandefunktioner. Du kan enkelt lägga till en push-funktion, ett SMS-meddelande, en aktivitet i appen eller ett e-postmeddelande under resan och definiera inställningar och innehåll. Sedan utförs den och skickas i samband med resan.

Du kan också ange specifika åtgärder för att skicka meddelanden till dig:

* Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. Läs mer om detta [section](../action/action.md).

* Om du arbetar med Campaign och Journey Optimizer, se följande avsnitt:

   * [[!DNL Journey Optimizer] och Campaign Classic v7/Campaign v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] och Campaign Standard](../action/acs-action.md)

Följ stegen nedan om du vill lägga till ett meddelande under en resa:

1. Påbörja resan med en [Händelse](general-events.md) eller en [Läs målgrupp](read-audience.md) aktivitet.

1. Från **Åtgärder** dra och släpp en **e-post**, en **I appen**, en **SMS** eller en **Push** till arbetsytan.

1. Konfigurera aktiviteten. Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sidor:

   <table style="table-layout:fixed">
   <tr style="border: 0;">
   <td>
   <a href="../email/create-email.md">
   <img alt="Lead" src="../assets/do-not-localize/email.jpg">
   </a>
   <div><a href="../email/create-email.md"><strong>Skapa e-postmeddelanden</strong>
   </div>
   <p>
   </td>
   <td>
   <a href="../in-app/create-in-app.md">
   <img alt="Lead" src="../assets/do-not-localize/in-app.jpg">
   </a>
   <div><a href="../in-app/create-in-app.md"><strong>Skapa meddelanden i appen</strong>
   </div>
   <p>
   </td>
   <td>
   <a href="../push/create-push.md">
   <img alt="Sällan" src="../assets/do-not-localize/push.jpg">
   </a>
   <div>
   <a href="../push/create-push.md"><strong>Skapa push-meddelanden<strong></a>
   </div>
   <p>
   </td>
   <td>
   <a href="../sms/create-sms.md">
   <img alt="Validering" src="../assets/do-not-localize/sms.jpg">
   </a>
   <div>
   <a href="../sms/create-sms.md"><strong>Skapa SMS-meddelanden</strong></a>
   </div>
   <p>
   </td>
   </tr>
   </table>

## Uppdatera liveinnehåll{#update-live-content}

Du kan uppdatera innehållet i ett meddelande (e-post, i appen, push, SMS) under en direktresa.

Det gör du genom att öppna din liveresa, välja meddelandeaktivitet och klicka på **Redigera innehåll**.

![](assets/add-a-message2.png)

Du kan dock inte ändra de attribut som används i personaliseringen, vare sig det är profilattribut eller kontextuella data (från händelse- eller reseegenskaper).

Om du har ändrat sammanhangsberoende data visas följande felmeddelande: ERR_AUTHORING_JOURNEYVERSION_201

Om du har ändrat profilattribut visas följande felmeddelande: ERR_AUTHORING_JOURNEYVERSION_202

Observera att för aktiviteten i appen kan ändringar göras i innehållet medan resan pågår, men utlösare i appen kan inte ändras.

## Sändningsoptimering{#send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_disabled"
>title="Om Tidsoptimering för Skickat"
>abstract="Adobe Journey Optimizer funktion för optimering av sändningstid, som bygger på Adobe AI-tjänster, kan förutsäga den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser."

### Om optimering vid sändning {#about-send-time}

Adobe Journey Optimizer funktion för optimering av sändningstid, som bygger på Adobe AI-tjänster, kan förutsäga den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser. Använd vår maskininlärningsmodell för att schemalägga personliga sändningstider för varje användare så att de kan utöka öppnings- och klickfrekvensen för dina meddelanden.

Modellen för optimering av sändningstid (Send-Time Optimization) innehåller information om dina Adobe Journey Optimizer-data och tittar på användarnivå som är öppen (för e-post och push) och klickar (för e-post) för att avgöra när kunderna är mest benägna att interagera med dina meddelanden. För optimering av sändningstid krävs minst en månads meddelandespårningsdata för att kunna ge välgrundade rekommendationer. För varje användare väljer systemet automatiskt den bästa tiden med följande poäng:

* Den bästa timmen varje dag i veckan för att maximera engagemanget
* Den bästa veckodagen för att maximera engagemanget
* Den bästa timmen på den bästa veckodagen för att maximera engagemanget

Modellen varierar oavsett om du talar om poängsättning eller utbildning. Utbildningen genomförs varje vecka, inledningsvis och därefter varje kvartal. Poängen är en gång i veckan och därefter en gång i månaden.

* Utbildning - utveckling av den algoritm som används för att göra poängen
* Poäng - poängsättning för enskilda profiler baserat på den tränade modellen

Den här informationen lagras med användarens profil och hänvisas till vid körning av resan för att tala om för Adobe Journey Optimizer när meddelandet ska skickas.

>[!CAUTION]
>
>Den här funktionen är inte kompatibel med sprängningsläge.

### Aktivera optimering av sändningstid{#activate-send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_email"
>title="Aktivera optimering av sändningstid"
>abstract="Välj om du vill optimera e-postöppningen eller skicka e-postklick genom att välja lämplig alternativknapp. Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för Skicka i nästa alternativ."

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_push"
>title="Aktivera optimering av sändningstid"
>abstract="Standardinställningen för push-meddelanden är öppningsalternativet, eftersom klickningar inte gäller för push-meddelanden. Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för Skicka i nästa alternativ."

Aktivera optimering av sändningstid för ett e-postmeddelande eller push-meddelande genom att välja **Sändningsoptimering** växla från aktivitetsparametrarna.

![](../building-journeys/assets/jo-message5.png)

För e-postmeddelanden väljer du om du vill optimera e-postöppningar eller e-postklick genom att välja lämplig alternativknapp. Standardinställningen för push-meddelanden är öppningsalternativet, eftersom klickningar inte gäller för push-meddelanden.

Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för **Skicka inom nästa** alternativ. Om du väljer&quot;sex timmar&quot; som värde, [!DNL Journey Optimizer] kontrollerar varje användarprofil och väljer den optimala sändningstiden inom sex timmar från körningstiden för resan.

**Vad händer om den optimala tiden är utanför fönstret?**

Låt oss ta ett exempel med följande inställningar:

* Optimera med klick
* Åtgärden ska börja kl. 10.00
* Fönstret är 3 timmar

En profil kan ha en optimal öppningstid som ligger utanför fönstret. John är till exempel bäst öppen vid klick vid 17:00.

På profilnivå finns poäng för varje timme i veckan. I det här exemplet skickas e-postmeddelandet alltid i fönstret. Vid körning kontrollerar systemet listan över bakgrundsmusik i det fönstret (3-timmarsfönster med början kl. 10.00). Systemet jämför sedan poängen för 10, 11 och 10 och väljer den högsta. E-postmeddelandet skickas då.
