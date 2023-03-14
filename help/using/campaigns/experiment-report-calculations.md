---
title: Statistiska beräkningar som används i experimentrapporten
description: Läs mer om statistiska beräkningar som används vid körning av experimentrapporter
feature: A/B Testing
topic: Content Management
role: User
level: Experienced
hide: true
hidefromtoc: true
badge: label="Beta" type="Informative"
source-git-commit: 160e4ce03d3be975157c30fbe511875a85b00551
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 0%

---

# Statistiska beräkningar i experimentrapporten {#experiment-report-calculations}

>[!BEGINSHADEBOX]

Vad du hittar i den här dokumentationen:

* [Kom igång med innehållsexperiment](get-started-experiment.md)
* [Skapa ett innehållsexperiment](content-experiment.md)
* [Förstå statistiska beräkningar](experiment-calculations.md)
* [Konfigurera experimentrapporter](reporting-configuration.md)
* **[Statistiska beräkningar i experimentrapporten](experiment-report-calculations.md)**

>[!ENDSHADEBOX]

På den här sidan visas detaljerade statistiska beräkningar som används i rapporten Experimentation för Campaigns i Adobe Journey Optimizer.

Observera att den här sidan är avsedd för tekniska användare.

## Konverteringsgrad

konverteringsgraden eller **medelvärde**, μ<sub>ν</sub> för varje behandling `ν` i en studie definieras som förhållandet mellan summan av mätvärdet och antalet profiler som tilldelats det mätvärdet, N<sub>ν</sub>:

![](assets/statistical_1.png){width="125" align="center"}

Här, Y<sub>iν</sub> är värdet för det objektiva måttet för varje profil `i`, som har tilldelats en viss variant *ν*. När det objektiva måttet är ett&quot;unikt&quot; mått, dvs. antalet profiler som utför en viss åtgärd, visas det som en konverteringsgrad och formateras som en procentandel. När mätvärdet är ett värde för antal eller totalt värde (t.ex. när e-post öppnas, intäkter), visas medelvärdet för uppskattningen för mätvärdet som Antal per profil eller Värde per profil.

Vid behov används samplingens standardavvikelse med uttrycket:

![](assets/statistical_2.png){width="225" align="center"}

## Lyft {#lift}

Lyften mellan en variant  *ν* och kontrollvarianten  *ν<sub>0</sub>* är det relativa deltavärdet i konverteringsgraden, definierat som beräkningen nedan där de enskilda konverteringssatserna är enligt definitionen ovan. Detta visas som ett procenttal.

![](assets/statistical_3.png){width="125" align="center"}

</br>

## Giltiga konfidensintervall för enskilda behandlingar

På panelen Journey Experimentation visas &quot;närsomhelst giltiga&quot; konfidensintervall (konfidenssekvenser) för enskilda behandlingar i ett experiment.

Konfidenssekvensen för en enskild variant `ν` är en central del i den statistiska metod som används av Adobe. Du hittar definitionen i [den här sidan](https://doi.org/10.48550/arXiv.2103.06476) (återges från [Waudiby-Smith et al.]).

Om du är intresserad av att uppskatta en målparameter `ψ` exempelvis konverteringsgraden för en variant i en expert, kan dikotomin mellan en sekvens av&quot;fast tid&quot; konfidensintervall (CI) och en tidsenhetlig konfidenssekvens (CS) sammanfattas enligt följande:

![](assets/statistical_4.png){width="500" align="center"}

För ett regelbundet konfidensintervall garanterar sannolikhetsgarantin att målparametern ligger inom intervallet Ċ<sub>n</sub> är endast giltigt till ett fast värde av `n` (där `n` är antalet prov). Omvänt för en tillförlitlig sekvens garanteras vi att alla värden i samplingsstorleken alltid/ `t`är &quot;true&quot; för parametern i intresse inom gränserna.

Detta har några viktiga konsekvenser som är mycket viktiga för onlinetestning:

* CS kan uppdateras när nya data blir tillgängliga.
* Experimenten kan övervakas kontinuerligt, stoppas eller fortsätta.
* Type-I-felet kontrolleras vid alla stopptider, inklusive databeroende tider.

Adobe använder asymptotisk konfidenssekvens, som för en enskild variant med medelskattning `μ` har formen:

![](assets/statistical_5.png){width="300" align="center"}

Var:

* `N` är antalet enheter för varianten.
* `σ` är en uppskattning av standardavvikelsen (definierad ovan).
* `α` är den önskade nivån av typ I-fel (eller sannolikhet för feltäckning). Den här inställningen är alltid 0,05.
* ρ<sup>2</sup> är en konstant som justerar den samplingsstorlek där CS är tätast. Adobe har valt ρ<sup>2</sup> = 10<sup>-2.8</sup>, vilket är lämpligt för de typer av konverteringsgrader som förekommer i online-experiment.

## Förtroende {#confidence}

Den konfidensgrad som används av Adobe är en&quot; alltid giltig&quot; konfidensgrad, som erhålls genom att invertera konfidenssekvensen för den genomsnittliga behandlingseffekten.

För att vara exakt, i två samplingar *t* test för skillnaden i medelvärde mellan två varianter, det finns en 1:1-mappning mellan *p*-värde för detta test och konfidensintervallet för skillnaden i medel. I analogi med detta kan en *p*-värde kan erhållas genom att invertera (när som helst giltig) konfidenssekvensen för den genomsnittliga uppskattningen av behandlingseffekten:

![](assets/statistical_6.png){width="200" align="center"}

Här, *E* är en förväntan. Den uppskattade faktor som används är en IPW-skattare (Inverse Propensity WWT). Consider N = N<sub>0</sub> +N<sub>1</sub> enheter, varianttilldelningar för varje enhet `i` märkt med A<sub>i</sub>=0,1 om enheten är tilldelad till variant `ν`=0,1. Om användarna har tilldelats en fast sannolikhet (benägenhet) π<sub>0</sub>, (1-π<sub>0</sub>) och deras resultatmått är Y<sub>i</sub>blir IPW-uppskattaren för den genomsnittliga behandlingseffekten:

![](assets/statistical_12.png){width="400" align="center"}

Observera att *f* är influensfunktionen, Waudiby-Smith et al. visade att tävlingssekvensen för den här uppskattaren är:

![](assets/statistical_7.png){width="500" align="center"}

Ersätta sannolikhet för tilldelning med dess empiriska uppskattningar: π<sub>0</sub> = N<sub>0</sub>/N, avvikelsetermen kan uttryckas som ett enskilt sampel, medelvärde för μ<sub>0,1</sub> och uppskattningar av standardavvikelser, σ<sub>0,1</sub> as:

![](assets/statistical_8.png){width="500" align="center"}

härnäst bör du komma ihåg att för en regelbunden hypotesprovning med provningsvärdet z = (μ)<sub>A</sub>-μ<sub>0</sub>/σ<sub>p</sub>) finns det en korrespondens mellan `p`-värden och konfidensintervall:

![](assets/statistical_9.png){width="500" align="center"}

där `Φ` är den kumulativa fördelningen av standardnormalvärdena. För alla tidpunkter `p`-värden, med tanke på konfidenssekvensen för den genomsnittliga behandlingseffekt som definieras ovan, kan vi invertera detta förhållande:

![](assets/statistical_10.png){width="600" align="center"}

Slutligen **när som helst, giltig säkerhet** är:

![](assets/statistical_11.png){width="200" align="center"}

## Förklaring av en expert till slutsats

För en expert med två armar visas ett meddelande på panelen Experimentation i Journey Optimizer om att en Experiment är **slående** när ett giltigt konfidensintervall överstiger 95 % (dvs. när som helst giltigt `p`-value är under 5 %).

När det finns fler än två varianter används Bonferonni-korrigeringen för att kontrollera den familjeselva felfrekvensen. För ett experiment med `K` behandlingar och en enstaka baseline (kontrollbehandling) finns `K-1` oberoende hypotesstest. Korrigeringen av Bonferonni innebär att vi avvisar den nollhypotes som kontrollen och en given variant har samma medel, om `p`-value (defined above) är under ett tröskelvärde på `α/(K-1)`.

## Högpresterande arm

När ett försök har förklarats slutgiltigt visas den arm som har bäst prestanda. Detta är armen med bästa prestanda (högsta medelvärde eller konverteringsgrad), bland uppsättningen som innehåller kontrollen och alla armar som har en `p`-värde som är under Bonferonni-tröskeln.
