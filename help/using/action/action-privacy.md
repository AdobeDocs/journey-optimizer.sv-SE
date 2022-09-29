---
solution: Journey Optimizer
title: Datastyrning
description: Datastyrning
feature: Actions
topic: Administration
role: Admin
level: Intermediate
source-git-commit: f2f55f42739509c50223d01e25fb1f16bf19a0de
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 0%

---

# Datastyrning {#restrict-fields}


>[!IMPORTANT]
>
>Användningen av etiketter och tvångsåtgärder för användning av data (DULE) är för närvarande begränsad till utvalda kunder och kommer att distribueras till alla miljöer i en framtida version.

Med styrningsramverket DULE (Data Usage Labeling and Enforcement) kan Journey Optimizer nu utnyttja Adobe Experience Platform styrningsprinciper för att förhindra att känsliga fält exporteras till tredjepartssystem via anpassade åtgärder. Om systemet identifierar ett begränsat fält i de anpassade åtgärdsparametrarna visas ett fel som hindrar dig från att publicera resan.

Med Adobe Experience Platform kan ni sätta etiketter på era fält och skapa marknadsföringsåtgärder för varje kanal. Sedan definierar ni en styrningspolicy som är kopplad till en etikett och en marknadsföringsåtgärd.

I Journey Optimizer kan du tillämpa dessa profiler på dina anpassade åtgärder för att förhindra att specifika fält exporteras till tredjepartssystem.

## Viktiga anteckningar {#important-notes}

* Datastyrning gäller endast för anpassade kundresor. Campaign Classic och Campaign Standard stöds inte.
* Styrningsprinciper tillämpas endast när en marknadsföringsåtgärd (obligatorisk eller ytterligare) har ställts in på den anpassade åtgärdsnivån.
* Attribut som är en del av en fältgrupp som använder det färdiga unionsschemat stöds inte. Dessa attribut döljs från gränssnittet. Du måste skapa en annan fältgrupp med ett annat schema.

## Definiera styrningspolicyer {#governance-policies}

Du kan använda befintliga etiketter, marknadsföringsåtgärder och policyer. Här följer de huvudsakliga konfigurationsstegen för att skapa nya:

* Lägg till en etikett och använd den på specifika fält som du inte vill ska exporteras till tredjepartssystem, till exempel en persons blodtyp.
* Definiera en marknadsföringsåtgärd för varje anpassad åtgärd från tredje part som används på dina resor.
* Skapa en styrningspolicy och koppla den till etikett- och marknadsföringsåtgärden.

Mer information om hur du hanterar principer finns i [dokumentation](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=en#consent-policy)

Låt oss ta ett exempel på det blodtypsfält som du måste märka som känsligt och begränsa dig från att exporteras till tredje part. Här är de olika stegen:

1. I den vänstra menyn, under **Integritet**, klicka **Profiler**.
   ![](assets/action-privacy0.png)
1. Välj **Etiketter** och klicka **Skapa etikett**.
   ![](assets/action-privacy1.png)
1. Definiera ett namn och ett eget namn för den här etiketten. Till exempel: _ePHI1_.
   ![](assets/action-privacy2.png)
1. I den vänstra menyn, under **Datahantering**, klicka **Scheman** och klickar på **Använd etiketter för åtkomst och datastyrning** -knappen. Välj schema och fält (blodtyp) och markera den tidigare skapade etiketten, _ePHI1_ i vårt exempel.
   ![](assets/action-privacy3.png)
1. Gå tillbaka till **Profiler** väljer du **Marknadsföringsåtgärd** och klicka **Skapa marknadsföringsåtgärd**. Vi rekommenderar att ni skapar en marknadsföringsåtgärd för varje anpassad åtgärd från tredje part som används på era resor. Låt oss till exempel skapa en _Marknadsföringsåtgärder för Slack_ som kommer att användas för din anpassade Slack-åtgärd.
   ![](assets/action-privacy4.png)
1. Välj **Bläddra** flik, klicka **Skapa princip** och markera **Datastyrningspolicy**. Välj etikett (_ePHI1_) och marknadsföringsåtgärder (_Marknadsföringsåtgärder för Slack_).
   ![](assets/action-privacy5.png)

När du ska använda din anpassade Slack-åtgärd i en resa konfigurerad med _Marknadsföringsåtgärder för Slack_, kommer den tillhörande policyn att utnyttjas.

## Konfigurera den anpassade åtgärden {#consent-custom-action}

I den vänstra menyn, under **Administration**, klicka **Konfigurationer** och markera **Åtgärder**. Öppna din anpassade Slack-åtgärd. När du konfigurerar en anpassad åtgärd kan två fält användas för datastyrning.

![](assets/action-privacy6.png)

* The **Kanal** kan du välja kanal för den här anpassade åtgärden: **E-post**, **SMS**, eller **Push-meddelande**. Den fyller i **Obligatorisk marknadsföringsåtgärd** fält med standardmarknadsföringsåtgärd för den valda kanalen. Om du väljer **övriga**, kommer inga marknadsföringsåtgärder att definieras som standard. I vårt exempel väljer vi kanalen **övriga**.

* The **Obligatorisk marknadsföringsåtgärd** gör att du kan definiera de marknadsföringsåtgärder som är kopplade till din anpassade åtgärd. Om du till exempel använder den anpassade åtgärden för att skicka e-post med en tredje part kan du välja **Målgruppsanpassning**. I vårt exempel väljer vi _Marknadsföringsåtgärder för Slack_. De styrningsprinciper som är kopplade till marknadsföringsåtgärden hämtas och utnyttjas.

De andra stegen för att konfigurera en anpassad åtgärd finns i [det här avsnittet](../action/about-custom-action-configuration.md#consent-management).

## Bygg resan {#consent-journey}

I den vänstra menyn, under **Resehantering**, klicka **Resor**. Skapa din resa och lägg till en anpassad åtgärd.  När du lägger till en anpassad åtgärd under en resa kan du hantera datastyrning med flera alternativ. Klicka på **Visa skrivskyddade fält** för att visa alla parametrar.

The **Kanal** och **Obligatorisk marknadsföringsåtgärd**, som definieras när den anpassade åtgärden konfigureras, visas längst upp på skärmen. Du kan inte ändra dessa fält.

![](assets/action-privacy7.png)

Du kan definiera en **Ytterligare marknadsföringsåtgärder** för att ange typ av anpassad åtgärd. På så sätt kan du definiera syftet med den anpassade åtgärden under den här resan. Utöver den nödvändiga marknadsföringsåtgärden, som vanligtvis är specifik för en kanal, kan ni definiera ytterligare en marknadsföringsåtgärd som är specifik för den anpassade åtgärden under den här resan. Till exempel: ett träningskommunikation, ett nyhetsbrev, ett friskvårdsmeddelande osv. Både den marknadsföringsåtgärd som krävs och den ytterligare marknadsföringsåtgärden gäller.

I vårt exempel använder vi inte någon ytterligare marknadsföringsåtgärd.

Om något av fälten är märkt _ePHI1_ (fältet för blodtyp i vårt exempel) upptäcks i åtgärdsparametrarna, ett fel visas som förhindrar dig från att publicera resan.

![](assets/action-privacy8.png)

De andra stegen för att konfigurera en anpassad åtgärd under en resa beskrivs i [det här avsnittet](../building-journeys/using-custom-actions.md).
