---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med planer för IP-värmare
description: Lär dig hur du implementerar en IP-värmeringsplan
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP, leverans
exl-id: 393f051d-b86d-4b4f-b564-7a9ae3a5d4b8
source-git-commit: 5dd6ebadd7b8c7490cb10496282697ce32ff3693
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Kom igång med planer för IP-värmare {#ip-warmup-gs}

Med [!DNL Journey Optimizer] kan du enkelt utföra arbetsflöden för IP-uppvärmning direkt från användargränssnittet på ett standardiserat och effektivt sätt som följer bästa praxis för optimal leverans. När e-postmeddelanden skickas via en ny plattform, är Internetleverantörer (ISP) misstänkta för IP-adresser som inte känns igen. Om stora mängder e-postmeddelanden plötsligt skickas markerar internetleverantörerna dem ofta som skräppost.

För att undvika att markeras som skräppost kan du öka volymen som skickas stegvis med funktionen för IP-värmerappning. Med det här nya alternativet på menyn **[!UICONTROL Administration]** kan du automatisera volymhanteringen och förenkla uppvärmningsprocessen utan att behöva göra komplicerade kundresekonfigurationer.

>[!NOTE]
>
>Innan du implementerar din IP-värmeplan bör du lära dig mer om grundläggande leveransfunktioner, anseende och bästa praxis i den här [IP-leveransguiden](ip-warmup-deliverability-guide.md).

➡️ [Lär dig hur du skapar och kör en IP-värmeringsplan i den här videon](#video)

>[!AVAILABILITY]
>
>Den här funktionen kan bara aktiveras i sandlådor av produktionstyp.

<!--
Benefits

* Standardization on Campaign which will be easy for practitioners too > why?

* No more pain of creating queries, audiences and testing those as system will create the audiences. 

* Ease of excluding domains and changing the plan with help of simple toggles to exclude OR by editing numbers inline or create new phases or reupload plan if drastic change. No more pain of editing audience definitions, journey conditions

* There is an expectation that with this, it will ease around 30% of effort and will be much better experience for consultant/partner/practitioner - right from planning to execution to reporting
-->

De viktigaste stegen för att implementera en plan för IP-uppvärmning är följande:

1. Du måste först skapa en eller flera kampanjer med alternativet IP-värmare aktiverat. [Läs mer](ip-warmup-campaign.md)

1. Skapa en IP-värmeringsplan i [!DNL Journey Optimizer] och överför Excel-bladet som har förberetts med din leveranskonsult. [Läs mer](ip-warmup-plan.md)

1. Välj en kampanj för varje fas i planen och aktivera motsvarande körningar. [Läs mer](ip-warmup-execution.md)

## Instruktionsvideo {#video}

Lär dig hur du skapar och kör en IP-värmeringsplan.

>[!VIDEO](https://video.tv.adobe.com/v/3432637/?learn=on)

>[!NOTE]
>
>Läs mer om hur du kan förbättra ditt e-postanseende med IP-uppvärmning i [Guiden &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html) Leveranssätt med bästa praxis.

## Ytterligare resurser {#additional-resources}

Utforska de här praktiska blogginläggen för mer ingående vägledning om IP-värmare:

* [Adobe Journey Optimizer Deliverability Guide: Från Zero Reputation till Inbox Hero](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/adobe-journey-optimizer-deliverability-guide-from-zero/ba-p/761950) - Omfattande guide som täcker viktiga aspekter av anseende, värmeringskalendrar, övervakning och felsökning av bästa praxis.

* [Förstå hur du konfigurerar IP-värmerappningen](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/ajo-ip-warmup-understanding-how-to-set-up-the-ip-warmup/ba-p/761949) - Lär dig grunderna i hur du konfigurerar IP-värmeringsplaner och metodtips för en lyckad implementering.

* [Avancerade funktioner i IP-uppvärmningsplaner](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/advanced-features-in-ajo-ip-warm-up-plans-granular-controls-for/ba-p/761958) - Upptäck avancerade funktioner och detaljerade kontroller för att optimera din strategi för IP-uppvärmning.

* [Felsökning av IP-uppvärmning](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/ajo-ip-warm-up-troubleshooting-audience-delays-and-smart-retry/ba-p/761952) - Hitta lösningar på vanliga problem, som fördröjningar av målgrupper och läs om smarta återförsöksmekanismer.
