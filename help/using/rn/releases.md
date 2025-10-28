---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Journey Optimizer release cycle
feature: Release Notes
description: Förstå Adobe Journey Optimizer versionscykel
source-git-commit: cef105e55f3353c616e18be84faa0ee774aeac06
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---

# Journey Optimizer release cycle {#releases}

[!DNL Adobe Journey Optimizer] uppdateras regelbundet för att leverera nya funktioner, förbättringar och korrigeringar. Den här sidan förklarar hur releasecykeln fungerar och vad varje releasefas innebär, så att du enkelt kan förstå när funktioner blir tillgängliga för din organisation.

## Löpande leveransmodell {#continuous-delivery-model}

[!DNL Adobe Journey Optimizer] arbetar på en kontinuerlig leveransmodell, vilket möjliggör en skalbar, stegvis metod för funktionsdistribution. Med den här modellen kan Adobe leverera innovationer snabbare och säkerställa kontinuerlig stabilitet och prestanda under utrullningen.

>[!NOTE]
>
> Eftersom [!DNL Adobe Journey Optimizer] använder kontinuerlig leverans kan nya funktioner visas progressivt i olika organisationer eller regioner.

Som en del av denna modell:

* Nya funktioner och förbättringar driftsätts i produktionen så fort de är klara.

* Versionsinformationen [**Versionsinformationen**](release-notes.md) uppdateras mellan månadsutgåvorna med ett avsnitt om _de senaste uppdateringarna_ som meddelar om nya funktioner och förbättringar när de introduceras, så att du hålls informerad i realtid.

## Frigör tajming och cadence {#release-timing}

[!DNL Adobe Journey Optimizer] följer vanligtvis en månadsvis publiceringsgräns, där distributioner vanligtvis sker under den sista veckan i varje månad. Månatliga versionsinformation och relaterad dokumentation publiceras på tisdagar i releaseminarien. Förhandsversionsinformation publiceras på fredag före versionsveckan.

>[!TIP]
>
> I slutet av varje kvartal kan releaser förutses och lanseras upp till två veckor före månadens slut för att anpassas till kvartalsvisa scheman eller beroende produktreleaser.

I månadsversionen introduceras de viktigaste nya funktionerna och korrigeringarna, men med kontinuerliga leveranser kan ytterligare uppdateringar distribueras mellan cyklerna när de är klara. Versionsinformationen uppdateras sedan i avsnittet _Senaste uppdateringar_ och tillgänglighetsdatumet anges. Alla ändringar som släpps under månaden sammanställs i månadsversionsinformationen på releasedatum.


## Frigör banor {#release-paths}

Funktionerna i Journey Optimizer följer olika versionsvägar beroende på deras komplexitet, beroenden och omfattning. Plattformen använder flera tillgänglighetsetiketter (Beta, begränsad tillgänglighet, allmän tillgänglighet), men alla funktioner passerar inte igenom alla.

Vanliga versionssökvägar är:

* **Direkt till GA** - Vissa nya funktioner och förbättringar går direkt till General Availability (GA).
* **LA → GA** - Vissa funktioner är först tillgängliga för en begränsad målgrupp (begränsad tillgänglighet) före allmän utrullning.
* **Beta → LA → GA** - Större eller experimentella funktioner går igenom alla faser för testning och validering.
* **Beta → GA** - Vissa stabila Beta-funktioner kan flyttas direkt till GA utan en mellanliggande LA-fas.

>[!TIP]
>
> Om du är intresserad av tidig tillgång till funktioner i Beta eller begränsad tillgänglighet kan du kontakta din Adobe-representant för att diskutera deltagaralternativen.


## Tillgänglighetsetiketter {#availability-labels}

| **Etikett** | **Syfte** | **Tillgänglighet** | **Nyckelanteckningar** |
|------------|-------------|------------------|----------------|
| **Beta** | Tidig testning och insamling av feedback. | Begränsat till utvalda kunder eller organisationer som deltar i Adobe Beta-program. | - Ej avsedd för produktion.<br>- Funktioner eller design kan ändras före GA.<br>- Feedback hjälper till att förfina den slutliga implementeringen. |
| **Begränsad tillgänglighet (LA)** | Kontrollerad utrullning för validering och övervakning. | Endast aktiverat för vissa kunder eller miljöer (till exempel utvecklingssandlådor). | - Produktionsklar och fullt stödd.<br> - Används för att validera prestanda och skalbarhet före den allmänna versionen.<br>- Åtkomst kräver Adobe-godkännande. |
| **Allmän tillgänglighet (GA)** | Omfattande funktionalitet som stöds. | Aktiveras som standard för alla berättigade organisationer. | - Produktionsklar och fullt stödd.<br> - Licensiering eller berättiganden kan gälla.<br> - Kan rulla ut progressivt mellan regioner. |


## utrullning och tillgänglighet {#rollout}

Även efter ett GA-meddelande kan lanseringen ske gradvis i olika organisationer eller regioner. Om en ny funktion inte visas omedelbart i din miljö är den vanligtvis tillgänglig inom några dagar efter att den släppts.

Denna gradvisa driftsättning gör att Adobe kan övervaka stabilitet, prestanda och användarupplevelse innan driftsättningen är klar.


## Håll dig informerad {#staying-informed}

Så här håller du dig uppdaterad:

* Granska den [**senaste versionsinformationen**](release-notes.md) för nya och uppdaterade funktioner.
* Kontrollera avsnittet **_Senaste uppdateringar_** mellan månadsutgåvor för realtidsdistributioner.
* Övervaka **Förhandsversionsinformation** (om den är tillgänglig) om du vill se en förhandsvisning av kommande funktioner.
* Kontakta din Adobe-representant för Beta eller begränsad tillgänglighet eller information om behörighet.

Du kan prenumerera på **e-postmeddelanden och produktmeddelanden** för Journey Optimizer produktreleaser. Så här prenumererar du:

1. Navigera till **Adobe Experience Cloud-inställningar**
1. Under **Notifications** hittar du **Journey Optimizer**
1. Aktivera **nya utgåvor** I appen och e-postmeddelanden

![](assets/do-not-localize/pulse-notif.png){width="70%" align="left"}

## Vanliga frågor {#faq}

Nedan finns Frågor och svar om Adobe Journey Optimizer releasecykel.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ställa din fråga eller kontakta [Adobe Journey Optimizer Community](https://experienceleaguecommunities.adobe.com/t5/adobe-journey-optimizer/ct-p/journey-optimizer?profile.language=en){target="_blank"}.

+++ När planeras Adobe Journey Optimizer-releaser?

[!DNL Adobe Journey Optimizer] släpper vanligtvis uppdateringar under den sista veckan i varje månad. I slutet av varje kvartal kan releasen vara avancerad i upp till två veckor för att passa in i uppdateringar som omfattar flera lösningar eller plattformar.

+++

+++ Varför visas inte en ny funktion direkt efter att den har annonserats?

Vissa GA-funktioner lanseras stegvis för att säkerställa plattformsstabilitet och prestanda. Om du inte ser någon funktion direkt visas den när distributionen är klar för din region eller organisation.

+++

+++ Vad är skillnaden mellan Beta, Limited Availability och GA?

* **Beta**: Tidig testfas, begränsad åtkomst, feedbackbaserad.
* **Begränsad tillgänglighet (LA)**: Kontrollerad utrullning för slutlig validering.
* **Allmän tillgänglighet (GA)**: Fullständig version för alla berättigade kunder.

+++

+++ Går alla funktioner igenom Beta och Begränsad tillgänglighet?

Nej. Vissa funktioner släpps direkt till GA eller endast till LA, beroende på deras art och beredskap. Versionsvägen är anpassad efter varje möjlighet att balansera flexibilitet, kvalitet och stabilitet.

+++

+++ Hur kan jag delta i Beta eller begränsade tillgänglighetsprogram?

Du får åtkomst via inbjudan eller förfrågan via din Adobe-representant. Deltagande hjälper till att utforma funktionsdesign och säkerställer att dina användningsfall beaktas i den slutliga versionen.

+++

+++ Hur ofta uppdateras versionsinformationen?

Versionsinformationen uppdateras kontinuerligt. Efter månatliga releaser uppdateras avsnittet _Senaste uppdateringar_ när nya funktioner eller förbättringar publiceras.

+++
