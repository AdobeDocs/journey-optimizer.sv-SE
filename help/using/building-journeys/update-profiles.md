---
solution: Journey Optimizer
product: journey optimizer
title: Uppdatera profil
description: Lär dig hur du använder aktiviteten Uppdatera profil under en resa
feature: Journeys, Profiles, Activities
topic: Content Management
role: User
level: Intermediate
keywords: profil, uppdatering, resa, aktivitet
exl-id: 8b2b2d1e-9bd1-439d-a15e-acdbab387c4b
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 0%

---

# Uppdatera profil {#update-profile}

>[!CONTEXTUALHELP]
>id="ajo_journey_update_profiles"
>title="Uppdatera profilaktivitet"
>abstract="Med aktiviteten Uppdatera profil kan du uppdatera en befintlig Adobe Experience Platform-profil med information som kommer från händelsen, en datakälla eller med ett specifikt värde."

Använd **[!UICONTROL Update Profile]** Åtgärdsaktivitet för att uppdatera en befintlig Adobe Experience Platform-profil med information från en händelse, en datakälla eller med ett specifikt värde.

## Rekommendationer

* The **Uppdatera profil** -åtgärden kan bara användas i resor som har ett namnutrymme.
* Åtgärden uppdaterar bara befintliga fält, inga nya profilfält skapas.
* Du kan inte använda **Uppdatera profil** åtgärd för att generera upplevelsehändelser, till exempel ett köp.
* Precis som med andra åtgärder kan du definiera en alternativ sökväg om fel eller timeout inträffar, och du kan inte placera två åtgärder parallellt.
* Uppdateringsbegäran som skickas till Adobe Experience Platform är omedelbart/inom en sekund. Det tar normalt några sekunder men ibland mer utan garanti. Detta resulterar exempelvis i att en åtgärd använder &quot;fält 1&quot; som har uppdaterats av en **Uppdatera profil** åtgärd som placerats precis tidigare, du bör inte förvänta dig att &quot;fält 1&quot; uppdateras i åtgärden.
* The **Uppdatera profil** aktiviteten stöder inte XDM-fält som är definierade som en uppräkning.
* The **[!UICONTROL Update profile]** endast aktiviteten uppdaterar [Profilarkiv](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html#profile-data-store){target="_blank"}, inte Data Lake.
* När du väljer en datauppsättning i **[!UICONTROL Update profile]** är det tillrådligt att använda en som inte styrs av dataöverföringsflöden. För **Uppdatera profil** uppdateringarna lagras bara i [Profilarkiv](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html#profile-data-store){target="_blank"}, finns det risk för att sådana ändringar skrivs över med ett dataöverföringsflöde.

  Dessutom kan du **Uppdatera profil** aktivitetskonfigurationen kräver inget identitetsnamnutrymme. Se därför till att den valda datauppsättningen använder samma ID-namnutrymme som användes av åtgärden som startade resan som det är detta namnområde som dessa uppdateringar kommer att använda. Identitetskartan kan även användas av den valda datauppsättningen. Om du inte väljer en datauppsättning med rätt namnutrymme eller en som använder identitetskarta orsakar detta **Uppdatera profil** aktivitet som ska misslyckas.



## Använda profiluppdateringen

1. Designa din resa genom att börja med ett evenemang. Se det här [section](../building-journeys/journey.md).

1. I **Åtgärd** väljer du **Uppdatera profil** till arbetsytan.

   ![](assets/profileupdate0.png)

1. Välj ett schema i listan.

1. Klicka på **Fält** för att markera det fält som du vill uppdatera. Endast ett fält kan markeras.

   ![](assets/profileupdate2.png)

1. Välj en datauppsättning i listan.

   >[!NOTE]
   >
   >The **Uppdatera profil** uppdaterar profildata i realtid, men uppdaterar inte datauppsättningar. Val av datauppsättning krävs eftersom profilen är en post som är relaterad till en datauppsättning.

1. Klicka på **Värde** fält för att definiera det värde som du vill använda:

   * Med den enkla uttrycksredigeraren kan du välja ett fält från en datakälla eller från den inkommande händelsen.

     ![](assets/profileupdate4.png)

   * Om du vill definiera ett specifikt värde eller använda avancerade funktioner klickar du på **Avancerat läge**.

     ![](assets/profileupdate3.png)

The **Uppdatera profil** är nu konfigurerat.

![](assets/profileupdate1.png)


## Använda testläget {#using-the-test-mode}

I testläge simuleras inte profiluppdateringen. Uppdateringen utförs på testprofilen.

Det är bara testprofiler som kan ta sig in på en resa i testläge. Du kan antingen skapa en ny testprofil eller omvandla en befintlig profil till en testprofil. I Adobe Experience Platform kan du uppdatera profilattribut via csv-filimport eller API-anrop. En enklare metod är att använda en **Uppdatera profil** Åtgärdsaktivitet och ändra testprofilens booleska fält från false till true.

Mer information om hur du omvandlar en befintlig profil till en testprofil finns i [section](../audience/creating-test-profiles.md#create-test-profiles-csv).
