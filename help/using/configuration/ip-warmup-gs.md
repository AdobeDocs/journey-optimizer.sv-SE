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
source-git-commit: 5e0d683bf52df4992773c6147b9e418241777e5d
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 2%

---

# Kom igång med planer för IP-värmare {#ip-warmup-gs}

Med [!DNL Journey Optimizer] kan du enkelt utföra arbetsflöden för IP-uppvärmning direkt från användargränssnittet på ett standardiserat och effektivt sätt som följer bästa praxis för optimal leverans. När e-postmeddelanden skickas via en ny plattform, är Internetleverantörer (ISP) misstänkta för IP-adresser som inte känns igen. Om stora mängder e-postmeddelanden plötsligt skickas markerar internetleverantörerna dem ofta som skräppost.

För att undvika att markeras som skräppost kan du öka volymen som skickas stegvis med funktionen för IP-värmerappning. Med det här nya alternativet på menyn **[!UICONTROL Administration]** kan du göra det enklare på ett konsoliderat sätt i stället för att skapa komplexa dagliga resor.

➡️ [Lär dig hur du skapar och kör en IP-uppvärmningsplan i den här videon](#video)

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

>[!VIDEO](https://video.tv.adobe.com/v/3453844/?learn=on&captions=swe)

>[!NOTE]
>
>Läs mer om hur du kan förbättra ditt e-postanseende med IP-uppvärmning i [Guiden &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=sv-SE) Leveranssätt med bästa praxis.
