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
hide: true
hidefromtoc: true
exl-id: 393f051d-b86d-4b4f-b564-7a9ae3a5d4b8
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 2%

---

# Kom igång med planer för IP-värmare {#ip-warmup-gs}

<!--
>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_plan"
>title="Define your IP warmup plan"
>abstract="You can perform IP warmup workflows directly from the Journey Optimizer interface in a standardized and efficient way that follows the best practices for optimal deliverability."
-->

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* **[Kom igång med IP-värmare](ip-warmup-gs.md)**
* [Skapa IP-värmningskampanjer](ip-warmup-campaign.md)
* [Skapa en IP-värmeringsplan](ip-warmup-plan.md)
* [Kör IP-värmerappen](ip-warmup-execution.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>IP-värmerfunktionen är för närvarande endast tillgänglig som betaversion för utvalda användare. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.

Med [!DNL Journey Optimizer]kan du enkelt utföra arbetsflöden för IP-värmare direkt från användargränssnittet på ett standardiserat och effektivt sätt som följer bästa praxis för optimal leverans.

>[!CAUTION]
>
>Den här funktionen gäller endast för e-postkanalen.

När e-postmeddelanden skickas via en ny plattform, är Internetleverantörer (ISP) misstänkta för IP-adresser som inte känns igen. Om stora mängder e-postmeddelanden plötsligt skickas markerar internetleverantörerna dem ofta som skräppost.

För att undvika att markeras som skräppost kan du öka volymen som skickas stegvis med funktionen för IP-värmerappning. Det här nya alternativet i **[!UICONTROL Administration]** gör det enklare att göra det på ett konsoliderat sätt i stället för att skapa komplexa dagliga resor. Detta bör säkerställa en smidig utveckling av startfasen och göra det möjligt att minska den totala frekvensen av ogiltiga adresser.

>[!NOTE]
>
>Lär dig mer om hur du kan förbättra ditt e-postanseende med IP-uppvärmning i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html).

<!--
Benefits

* Standardization on Campaign which will be easy for practitioners too > why?

* No more pain of creating queries, audiences and testing those as system will create the audiences. 

* Ease of excluding domains and changing the plan with help of simple toggles to exclude OR by editing numbers inline or create new phases or reupload plan if drastic change. No more pain of editing audience definitions, journey conditions

* There is an expectation that with this, it will ease around 30% of effort and will be much better experience for consultant/partner/practitioner - right from planning to execution to reporting
-->

De viktigaste stegen för att implementera en plan för IP-uppvärmning är följande:

1. Du måste först skapa en eller flera kampanjer med alternativet IP-värmare aktiverat. [Läs mer](ip-warmup-campaign.md)

1. Skapa en IP-värmeringsplan i [!DNL Journey Optimizer] och ladda upp Excel-bladet som har tagits fram av er återförsäljare. [Läs mer](ip-warmup-plan.md)

1. Välj en kampanj för varje fas i planen och aktivera motsvarande körningar. [Läs mer](ip-warmup-execution.md)
