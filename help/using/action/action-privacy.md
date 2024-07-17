---
solution: Journey Optimizer
product: journey optimizer
title: Datastyrning
description: Definiera en styrningspolicy som är kopplad till en etikett och en marknadsföringsåtgärd
feature: Journeys, Actions, Custom Actions, Privacy
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: data, styrning, DULE, etiketter, märkning, plattform, policy
exl-id: be3efd3b-35d5-4cf7-9015-29d1e305355d
source-git-commit: f8d62a702824bcfca4221c857acf1d1294427543
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 0%

---

# Datastyrning {#restrict-fields}


>[!IMPORTANT]
>
>Användningen av etiketter och tvångsåtgärder för användning av data (DULE) är för närvarande begränsad till utvalda kunder och kommer att distribueras till alla miljöer i en framtida version.

Med styrningsramverket DULE (Data Usage Labeling and Enforcement) kan Journey Optimizer nu utnyttja Adobe Experience Platform styrningsprinciper för att förhindra att känsliga fält exporteras till tredjepartssystem via anpassade åtgärder. Om systemet identifierar ett begränsat fält i de anpassade åtgärdsparametrarna visas ett fel som hindrar dig från att publicera resan.

Med Adobe Experience Platform kan ni sätta etiketter på era fält och skapa marknadsföringsåtgärder för varje kanal. Sedan definierar ni en styrningspolicy som är kopplad till en etikett och en marknadsföringsåtgärd.

I Journey Optimizer kan du tillämpa dessa profiler på dina anpassade åtgärder för att förhindra att specifika fält exporteras till tredjepartssystem.

Mer information om ramverket för datastyrning och hur du arbetar med etiketter och policyer finns i Adobe Experience Platform-dokumentationen:

* [Översikt över tjänsten Datastyrning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html)
* [Översikt över etiketter för dataanvändning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html)
* [Dataanvändningsprinciper](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html)

## Viktiga anteckningar {#important-notes}

* Datastyrning gäller endast för anpassade kundresor. Kampanjåtgärder v7/v8 och Campaign Standard stöds inte.
* Styrningspolicyer gäller endast när en marknadsföringsåtgärd (obligatorisk eller ytterligare) har ställts in på den anpassade åtgärdsnivån.

## Definiera styrningspolicyer {#governance-policies}

Du kan använda befintliga etiketter, marknadsföringsåtgärder och policyer. Här följer de huvudsakliga konfigurationsstegen för att skapa nya:

* Lägg till en etikett och använd den på specifika fält som du inte vill ska exporteras till tredjepartssystem, till exempel en persons blodtyp.
* Definiera en marknadsföringsåtgärd för varje anpassad åtgärd från tredje part som används på dina resor.
* Skapa en styrningspolicy och koppla den till etikett- och marknadsföringsåtgärden.

Mer information om hur du hanterar principer finns i [dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#consent-policy)

Låt oss ta ett exempel på det blodtypsfält som du måste märka som känsligt och begränsa dig från att exporteras till tredje part. Här är de olika stegen:

1. Klicka på **Profiler** under **Integritet** på den vänstra menyn.
1. Välj fliken **Etiketter** och klicka på **Skapa etikett**.
   ![](assets/action-privacy1.png)
1. Definiera ett namn och ett eget namn för den här etiketten. Exempel: _ePHI1_.
1. Klicka på **Scheman** under **Datahantering** på den vänstra menyn och klicka sedan på knappen **Använd åtkomst- och datastyrningsetiketter** . Markera ditt schema och fält (blodtyp) och markera den etikett som skapats tidigare, _ePHI1_ i vårt exempel.
   ![](assets/action-privacy3.png)
1. Gå tillbaka till menyn **Profiler**, välj fliken **Marknadsföringsåtgärd** och klicka på **Skapa marknadsföringsåtgärd**. Vi rekommenderar att ni skapar en marknadsföringsåtgärd för varje anpassad åtgärd från tredje part som används på era resor. Låt oss till exempel skapa en _Slack-marknadsföringsåtgärd_ som ska användas för din anpassade Slack-åtgärd.
   ![](assets/action-privacy4.png)
1. Välj fliken **Bläddra**, klicka på **Skapa princip** och välj **Datastyrningsprincip**. Markera etiketten (_ePHI1_) och marknadsföringsåtgärden (_Slack marknadsföringsåtgärd_).
   ![](assets/action-privacy5.png)

När du ska använda din anpassade Slack-åtgärd som konfigurerats med _Slack marknadsföringsåtgärden_ på en resa, kommer den associerade principen att utnyttjas.

## Konfigurera den anpassade åtgärden {#consent-custom-action}

Klicka på **Konfigurationer** under **Administration** på den vänstra menyn och välj **Åtgärder**. Öppna din anpassade Slack-åtgärd. När du konfigurerar en anpassad åtgärd kan två fält användas för datastyrning.

![](assets/action-privacy6.png)

* I fältet **Kanal** kan du välja kanal som är relaterad till den här anpassade åtgärden: **E-post**, **SMS** eller **Push-meddelande**. Det kommer att förifylla fältet **Obligatorisk marknadsföringsåtgärd** med standardmarknadsföringsåtgärden för den valda kanalen. Om du väljer **other** definieras ingen marknadsföringsåtgärd som standard. I vårt exempel väljer vi kanalen **other**.

* Med den **obligatoriska marknadsföringsåtgärden** kan du definiera marknadsföringsåtgärden som är relaterad till din anpassade åtgärd. Om du till exempel använder den anpassade åtgärden för att skicka e-post med en tredje part kan du välja **E-postmarknadsföring**. I vårt exempel väljer vi marknadsföringsåtgärden _Slack_. De styrningsprinciper som är kopplade till marknadsföringsåtgärden hämtas och utnyttjas.

De andra stegen för att konfigurera en anpassad åtgärd beskrivs i [det här avsnittet](../action/about-custom-action-configuration.md#consent-management).

## Bygg resan {#consent-journey}

Klicka på **Resor** på den vänstra menyn under **Resehantering**. Skapa din resa och lägg till en anpassad åtgärd.  När du lägger till en anpassad åtgärd under en resa kan du hantera datastyrning med flera alternativ. Klicka på **Visa skrivskyddade fält** om du vill visa alla parametrar.

Marknadsföringsåtgärden **Kanal** och **Obligatorisk**, som definieras när den anpassade åtgärden konfigureras, visas längst upp på skärmen. Du kan inte ändra dessa fält.

![](assets/action-privacy7.png)

Du kan definiera en **ytterligare marknadsföringsåtgärd** för att ange typen av anpassad åtgärd. På så sätt kan du definiera syftet med den anpassade åtgärden under den här resan. Utöver den nödvändiga marknadsföringsåtgärden, som vanligtvis är specifik för en kanal, kan ni definiera ytterligare en marknadsföringsåtgärd som är specifik för den anpassade åtgärden under den här resan. Exempel: en träningskommunikation, ett nyhetsbrev, ett friskvårdsmeddelande osv. Både den marknadsföringsåtgärd som krävs och den ytterligare marknadsföringsåtgärden gäller.

I vårt exempel använder vi inte någon ytterligare marknadsföringsåtgärd.

Om ett av fälten med etiketten _ePHI1_ (blodet i vårt exempel) identifieras i åtgärdsparametrarna visas ett fel som förhindrar dig från att publicera resan.

![](assets/action-privacy8.png)

De andra stegen för att konfigurera en anpassad åtgärd under en resa beskrivs i [det här avsnittet](../building-journeys/using-custom-actions.md).
