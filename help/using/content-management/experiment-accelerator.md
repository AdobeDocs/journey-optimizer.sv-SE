---
solution: Journey Optimizer
product: journey optimizer
title: Experimentation Accelerator
description: Förbättra er förmåga att utföra experiment effektivt och generera insikter
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: innehåll, experimentera, multipelt, målgrupp, behandling
hide: true
hidefromtoc: true
source-git-commit: e4d5631701c5c270af7aec931f6b98a567b4ed29
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 0%

---

# Kom igång med Experimentation Accelerator {#content-experiment}

>[!BEGINSHADEBOX]

* **[Kom igång med Experimentation Accelerator](experiment-accelerator.md)**
* [Fliken Experiment](experiment-accelerator-monitor.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
> Experimentation Accelerator är för närvarande i betaversion och funktionerna lanseras stegvis.

**Experimentation Accelerator** är ett kraftfullt verktyg som har utformats för att effektivisera och förbättra experimenteringsprocessen. Genom att integrera med Adobe Target och Adobe Journey Optimizer utgör programmet en central plattform för att hantera, analysera och optimera experiment. Med hjälp av AI-baserade insikter och adaptiv testning kan ni med Experimentation Accelerator fatta datadrivna beslut, förbättra marknadsföringsstrategier och få mätbara resultat.

Några viktiga fördelar:

* **Snabbare experimenterande**: Kör adaptiva, alltid-på-tester med modeller som justeras över tid.

* **Enhetlig plattform**: Hantera alla experiment från Adobe Target och Journey Optimizer på ett och samma ställe.

* **AI-styrda insikter**: Hitta viktiga resultat, prestandadrivrutiner och nya möjligheter automatiskt.

* **Smartare målgruppsanpassning**: Använd beteendes- och innehållsdata för att prioritera effektiva experiment.

* **KPI-övervakning**: Spåra mätvärden som lyft, intäkter och förtroende mellan experiment.

* **Smidig Collaboration**: Dela enkelt resultat och hantera teamroller med aviseringar i realtid.

När du har [skapat och konfigurerat ditt experiment](content-experiment.md) och skickat dina kampanjer eller resor till dina profiler, kan du få tillgång till **[!UICONTROL Experimentation Accelerator]** och fördjupa dig i hur ditt experiment fungerar.

Så här kommer du åt **[!UICONTROL Experimentation Accelerator]**:

* Välj **[!UICONTROL Experimentation Accelerator]** i listrutan **[!UICONTROL Experimentation]** på den vänstra menyn.

* Du kan också välja **[!UICONTROL Experimentation Accelerator]** i Apps-väljaren.

Observera att användare som bara har en Target-licens bara kan komma åt den via Apps-väljaren.

<!--
<table style="table-layout:fixed"><tr style="border: 0;">
<td><img alt="Overview" href="experiment-accelerator-overview.md" src="assets/do-not-localize/experiments-2.jpeg">
<div align="center"><p><strong><a href="experiment-accelerator-overview.md">Overview</a></strong></p></div></td>
<td><img alt="Experiments" href="experiment-accelerator-monitor.md" src="assets/do-not-localize/experiment-overview.jpeg">
<div align="center"><p><strong><a href="experiment-accelerator-monitor.md">Experiments</a></strong></p></div></td>
<td><img alt="Metrics" href="experiment-accelerator-metrics.md" src="assets/do-not-localize/experiment-metrics.png">
<div align="center"><p><strong><a href="experiment-accelerator-metrics.md">Metrics</a></strong></p></div></td>
</tr></table>
-->

## Vad är A/B-testning?

A/B-testning är en process där två eller flera versioner av något jämförs för att avgöra vilken som fungerar bäst i förhållande till ett definierat mål.

Deltagare tilldelas slumpmässigt till en version, en så kallad variant, och deras beteende spåras. Resultatet visar om en version är statistiskt bättre än de andra.

## Nyckelterminologi

| Villkor | Definition |
|-|-|
| Kontroll | Den ursprungliga versionen som används som baslinje för jämförelse. |
| Variant eller behandling | En ny version har skapats för att testa mot kontrollen. |
| Hypotes | En förutsägelse om vilka ändringar som ger ett bättre resultat och varför. |
| Samplingsstorlek | Antalet individer eller sessioner som ingår i testet. |
| Statistisk signifikans | Ett mått på tillförsikt att resultaten inte beror på en slumpmässig chans. |
| Lyft | Den procentuella förbättringen eller minskningen av en variant jämfört med kontrollen. |
| Primärt mått | Det viktigaste måttet som används för att avgöra om testet lyckades. |
| Sekundära mått | Stödjande mätvärden som ger ytterligare insikter eller hjälper till att övervaka oönskade effekter. |
| Konfidensintervall | Det uppskattade intervall inom vilket den verkliga effekten sannolikt kommer att falla. |
| Segment | En specifik del av målgruppen som analyserats oberoende av varandra (t.ex. nya användare, mobilbesökare). |

## Bästa tillvägagångssätt för att köra experiment

* **Börja med en tydlig hypotes**

  En stark hypotes innefattar vad du håller på att ändra, vad du förväntar dig att hända och varför.
Exempel: _Vi tror att X-ändringar kommer att öka med Y på grund av Z._

* **Definiera ett meningsfullt framgångsmått**

  Välj ett mätvärde som passar in i de bredare målen. Undvik&quot;ovanlighetsmått&quot; som ser bra ut men inte avspeglar den verkliga effekten.

* **Testa en ändring i taget (när det är möjligt)**

  Genom att isolera variabler blir det enklare att tolka resultaten korrekt. Om du testar flera ändringar samtidigt kanske du inte vet vad som orsakade effekten.

* **Låt testet köras tillräckligt länge**

  För tidiga slutsatser kan vara vilseledande. Vänta på en statistiskt signifikant samplingsstorlek innan du agerar.

* **Var medveten om externa faktorer**

  Säsongalitet, semester och andra förändringar i din miljö kan förvränga resultatet. Dokumentera allt som kan påverka beteendet under testet.

* **Använd detaljerad segmentering**

  Genom att dela upp resultaten efter målgruppssegment kan du hitta dolda mönster men undvika att övertolka små provstorlekar.

* **Dokumentera och dela aviseringar**

  Se tydligt vad som har testats, varför och vad du lärt dig. Detta bygger upp institutionskunskaper och förhindrar upprepade misstag.

## Vanliga mått

| Mått | Vad det innebär | När ska användas |
|-|-|-|
| Konverteringsgrad | Procentandelen användare som slutfört en önskad åtgärd | Användbar för att spåra framgångar i en målstyrd upplevelse |
| Klickfrekvens (CTR) | Procentandelen användare som klickar på ett visst element | Anger hur övertygande upplevelsen är |
| Hastighet | Hur stor interaktion användarna har med upplevelsen | Bra för att mäta intresse eller uppmärksamhet |
| Studsfrekvens | Procentandel användare som snabbt lämnar utan att vidta åtgärder | Kan ge en dålig eller förvirrande upplevelse |
| Tid på sidan | Hur mycket tid användarna lägger på en viss del av upplevelsen | Kan spegla intressenivå eller komplexitet |
| Intäkter per besökare | Genomsnittlig intäkt per användare | Används ofta i handelsinriktade experiment |
| Bevarandefrekvens | Procentandelen användare som återgår eller förblir engagerade över tiden | Användbar för långsiktiga värdebedömningar |

## Vad är ett bra experiment?

Ett bra experiment ger inte bara en vinst, det ger en tydlig och åtgärdbar inlärning.
Här kan du söka efter:

&amp;check; **Statistisk konfidens**: Det är osannolikt att skillnaden mellan varianter beror på en chans.
&amp;check; **Justering med mål**: Det primära måttet visar meningsfulla framsteg mot ett affärsmål.
&amp;check; **Sekundär effekt**: Inga signifikanta negativa biverkningar på relaterade mått.
&amp;check; **Scalability**: Resultatet kan informera framtida beslut eller vara generaliserat till andra områden.
&amp;check; **Clarity**: Orsaken till resultatet är relativt isolerad och förstådd.

Experimentation handlar inte bara om att hitta den&quot;bästa&quot; versionen, utan också om att bygga upp kunskap genom testning och iteration. När det är klart avslöjar experiment insikter som driver smartare beslut, bättre användarupplevelser och förbättrade resultat.

>[!BEGINSHADEBOX]

**Exempel:**

* **Företag**: Hotellkedja
* **Hypotes**: Om vi använder ett mer brådskande språk på hemsidan leder det till fler bokningar.
   * **Kontroll**: Ursprunglig version
   * **Variant**: En ny version med en brådskande fråga har lagts till
   * **Primärt mått**: Bokningsfrekvens
   * **Sekundära mått**: Studsfrekvens, tid på plats
* **Resultat**: Varianten gav en 14-procentig ökning av bokningsfrekvensen, utan någon negativ ändring av andra mätvärden.
* **Åtgärd**: Överväg att rulla ut varianten och köra uppföljningsförsök för att testa liknande metoder inom andra områden.

>[!ENDSHADEBOX]
