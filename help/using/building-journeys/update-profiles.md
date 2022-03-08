---
title: Uppdatera profil
description: Lär dig hur du använder aktiviteten Uppdatera profil under en resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 8b2b2d1e-9bd1-439d-a15e-acdbab387c4b
source-git-commit: 68407db81224e9c2b6930c800e57b65e081781fe
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Uppdatera profil {#update-profile}

The **[!UICONTROL Update Profile]** kan du uppdatera en befintlig Adobe Experience Platform-profil med information från händelsen, en datakälla eller med ett specifikt värde.

## Viktiga anteckningar

* The **Uppdatera profil** kan bara användas i resor som börjar med en händelse som har ett namnutrymme.
* Åtgärden uppdaterar bara befintliga fält, inga nya profilfält skapas.
* Du kan inte använda **Uppdatera profil** åtgärd för att generera upplevelsehändelser, till exempel ett köp.
* Precis som med andra åtgärder kan du definiera en alternativ sökväg om fel eller timeout inträffar, och du kan inte placera två åtgärder parallellt.
* Uppdateringsbegäran som skickas till Platform kommer snabbt men inte omedelbart/inom en sekund. Det tar normalt några sekunder men ibland mer utan garanti. Om en åtgärd till exempel använder&quot;fält 1&quot; som har uppdaterats av en åtgärd av typen Uppdatera profil som har placerats precis tidigare, bör du därför inte förvänta dig att&quot;fält 1&quot; kommer att uppdateras i åtgärden.

## Använda testläget {#using-the-test-mode}

I testläge simuleras inte profiluppdateringen. Uppdateringen utförs på testprofilen.

Det är bara testprofiler som kan gå in på en resa i testläge. Du kan antingen skapa en ny testprofil eller omvandla en befintlig profil till en testprofil. I Adobe Experience Platform kan du uppdatera profilattribut via csv-filimport eller API-anrop. En enklare metod är att använda en **Uppdatera profil** Åtgärdsaktivitet och ändra testprofilens booleska fält från false till true.

Mer information om hur du omvandlar en befintlig profil till en testprofil finns i [section](../building-journeys/creating-test-profiles.md#create-test-profiles-csv).

## Använda profiluppdateringen

1. Designa din resa genom att börja med ett evenemang. Se det här [section](../building-journeys/journey.md).

1. I **Åtgärd** väljer du **Uppdatera profil** till arbetsytan.

   ![](../assets/profileupdate0.png)

1. Välj ett schema i listan.

1. Klicka på **Fält** för att markera det fält som du vill uppdatera. Endast ett fält kan markeras.

   ![](../assets/profileupdate2.png)

1. Välj en datauppsättning i listan.

   >[!NOTE]
   >
   >The **Uppdatera profil** uppdaterar profildata i realtid, men uppdaterar inte datauppsättningar. Val av datauppsättning krävs eftersom profilen är en post som är relaterad till en datauppsättning.

1. Klicka på **Värde** fält för att definiera värdet som du vill använda:

   * Med den enkla uttrycksredigeraren kan du välja ett fält från en datakälla eller från den inkommande händelsen.

      ![](../assets/profileupdate4.png)

   * Om du vill definiera ett specifikt värde eller använda avancerade funktioner klickar du på **Avancerat läge**.

      ![](../assets/profileupdate3.png)

The **Uppdatera profil** har konfigurerats.

![](../assets/profileupdate1.png)
