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
version: Journey Orchestration
source-git-commit: 70653bafbbe8f1ece409e3005256d9dff035b518
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 0%

---

# Uppdatera profil {#update-profile}

>[!CONTEXTUALHELP]
>id="ajo_journey_update_profiles"
>title="Uppdatera profilaktivitet"
>abstract="Med aktiviteten Uppdatera profil kan du uppdatera en befintlig [!DNL Adobe Experience Platform]-profil med information som kommer från händelsen, en datakälla eller med ett specifikt värde."

Använd åtgärdsaktiviteten **[!UICONTROL Update Profile]** för att uppdatera en befintlig [!DNL Adobe Experience Platform]-profil med information från en händelse, en datakälla eller med ett specifikt värde.

## Viktiga begrepp {#key-concepts}

* Åtgärden **Uppdatera profil** kan bara användas i resor som har ett namnutrymme.
* Åtgärden uppdaterar bara befintliga fält, inga nya profilfält skapas.
* Du kan inte använda åtgärden **Uppdatera profil** för att generera upplevelsehändelser, till exempel ett köp.
* Precis som med andra åtgärder kan du definiera en alternativ sökväg om fel eller timeout inträffar, och du kan inte placera två åtgärder parallellt.
* Uppdateringsbegäran som skickades till [!DNL Adobe Experience Platform] är omedelbart/inom en sekund. Det tar normalt några sekunder men ibland mer utan garanti. Om en åtgärd till exempel använder&quot;fält 1&quot; som har uppdaterats av en **Uppdatera profil** -åtgärd som har placerats precis tidigare, bör du därför inte förvänta dig att&quot;fält 1&quot; kommer att uppdateras i åtgärden.
* Aktiviteten **Uppdatera profil** stöder inte XDM-fält som är definierade som uppräkningar eller föreslagna värden.
* Aktiviteten **[!UICONTROL Update profile]** uppdaterar bara [profilarkivet](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html#profile-data-store){target="_blank"}, inte datasjön.

## Val av datauppsättning {#dataset-selection}

Aktiviteten **Uppdatera profil** kräver en dedikerad datamängd för att lagra uppdateringar. Eftersom den här aktiviteten endast uppdaterar profilarkivet (inte Datalake), bör alla uppdateringar sparas i en profilaktiverad datauppsättning som är specifikt avsedd för **Uppdatera profil** -åtgärder. Om du använder en datauppsättning som används för batch- eller direktuppspelningsinmatning kommer nya inbyggda data att skriva över de ändringar som gjorts av åtgärden **Uppdatera profil**.

Aktivitetskonfigurationen **Uppdatera profil** kräver inte heller något identitetsnamnutrymme. Se därför till att den valda datauppsättningen använder samma **Identity namespace** som användes av åtgärden som startade resan som det är detta namnområde som dessa uppdateringar kommer att använda. Identitetskartan kan även användas av den valda datauppsättningen. Om du inte väljer en datauppsättning med rätt namnutrymme eller en som använder identitetskarta kommer aktiviteten Uppdatera profil att misslyckas.

## Använda profiluppdateringen

1. Designa din resa genom att börja med ett evenemang. Se [avsnittet](../building-journeys/journey.md).

1. Släpp aktiviteten **Uppdatera profil** på arbetsytan i avsnittet **Åtgärd** på paletten.

   ![Uppdatera profilaktivitet på resepaletten under Åtgärder](assets/profileupdate0.png)

1. Välj ett schema i listan.

1. Klicka på **Fält** för att markera fältet som du vill uppdatera. Endast ett fält kan markeras.

   ![Konfigurationspanelen för profiluppdatering med listrutan för fältval](assets/profileupdate2.png)

1. Välj en datauppsättning i listan.

   >[!NOTE]
   >
   >Åtgärden **Uppdatera profil** uppdaterar profildata i realtid, men uppdaterar inte datauppsättningar. Val av datauppsättning krävs eftersom profilen är en post som är relaterad till en datauppsättning.

1. Klicka på fältet **Värde** för att definiera värdet som du vill använda:

   * Med den enkla uttrycksredigeraren kan du välja ett fält från en datakälla eller från den inkommande händelsen.

     ![Fältväljare i enkelt läge för profilattributsuppdateringar](assets/profileupdate4.png)

   * Om du vill definiera ett specifikt värde eller utnyttja avancerade funktioner väljer du **Avancerat läge**.

     ![Uttrycksredigerare för avancerat läge för komplexa profiluppdateringar](assets/profileupdate3.png)

**Uppdateringsprofilen** har nu konfigurerats.

![Aktivitet för profiluppdatering under resan med fältkonfiguration](assets/profileupdate1.png)


## Använda testläget {#using-the-test-mode}

I testläge simuleras inte profiluppdateringen. Uppdateringen utförs på testprofilen.

Det är bara testprofiler som kan ta sig in på en resa i testläge. Du kan antingen skapa en ny testprofil eller omvandla en befintlig profil till en testprofil. I [!DNL Adobe Experience Platform] kan du uppdatera profilattribut via en CSV-filimport eller API-anrop. En enklare metod är att använda en **Uppdatera profil**-åtgärd och ändra testprofilens booleska fält från false till true.

Mer information om hur du omvandlar en befintlig profil till en testprofil finns i det här [avsnittet](../audience/creating-test-profiles.md#create-test-profiles-csv).
