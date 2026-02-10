---
solution: Journey Optimizer
title: Begränsa genomströmning med externa datakällor och anpassade åtgärder
description: Begränsa genomströmning med externa datakällor och anpassade åtgärder
feature: Journeys, Use Cases, Custom Actions, Data Sources
topic: Content Management
role: Developer
level: Experienced
keywords: resa, datakällor, begränsning, genomströmning, anpassade åtgärder
exl-id: 45d6bb82-88ea-4510-a023-a75a82cc6f7b
version: Journey Orchestration
source-git-commit: 70653bafbbe8f1ece409e3005256d9dff035b518
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 0%

---

# Användningsfall: begränsa dataflöde med externa datakällor och anpassade åtgärder{#limit-throughput}

Använd det här användningsexemplet för att begränsa hanteringen av resor när externa system måste hantera ett begränsat antal förfrågningar per sekund.

## Beskrivning av användningsfallet

I [!DNL Adobe Journey Optimizer] kan användare skicka API-anrop till externa system via anpassade åtgärder och datakällor.

Detta kan göras med:

* **Datakällor**: om du vill samla in information från externa system och använda den i kundresan, till exempel för att få väderinformation om profilstaden och få ett dedikerat kundressflöde baserat på detta.

* **Anpassade åtgärder**: om du vill skicka information till externa system, till exempel för att skicka e-post via en extern lösning med Journey Optimizer orkestreringsfunktioner tillsammans med profilinformation, målgruppsdata och resekontext.

>[!NOTE]
>
>Eftersom svaren nu stöds bör du använda anpassade åtgärder i stället för datakällor för externa datakällor som användningsfall. Mer information om svar finns i [avsnittet](../action/action-response.md)

Om du arbetar med externa datakällor eller anpassade åtgärder kanske du vill skydda dina externa system genom att begränsa resans genomströmning: upp till 5 000 instanser/sekund för enastående resor och upp till 20 000 instanser/sekund för målgruppsinställda. Läs mer om resefrekvenser och dataflöde i [det här avsnittet](entry-management.md#journey-processing-rate).

För anpassade åtgärder finns begränsningsfunktioner på produktnivå. Se den här [sidan](../configuration/external-systems.md#capping).

För externa datakällor kan du definiera en begränsning på slutpunktsnivå för att undvika att överbelasta dessa externa system med hjälp av Journey Optimizer API:er för begränsning. Alla återstående begäranden efter att gränsen har nåtts kommer dock att tas bort. I det här avsnittet hittar du tillfälliga lösningar som du kan använda för att optimera dataflödet.

Mer information om hur du integrerar med externa system finns på [sidan](../configuration/external-systems.md).

## Implementering

För **målgruppsinlösta resor** kan du definiera läsfrekvensen för din Läs målgrupp-aktivitet som påverkar resans genomströmning. [Läs mer](../building-journeys/read-audience.md)

>[!NOTE]
>
> Det här är det maximala antalet profiler som kan komma in på resan per sekund. Denna avgift gäller endast denna aktivitet och inga andra delar av resan. [Läs mer](../building-journeys/read-audience.md)


![Begränsa genomströmningskonfigurationspanelen med inställningar för hastighetsbegränsning](assets/limit-throughput-1.png)

Du kan ändra det här värdet från 500 till 20 000 instanser per sekund. Om du behöver gå under 500/s kan du även lägga till villkor för&quot;procentuell delning&quot; med vänteaktiviteter för att dela upp din resa i flera grenar och få dem att köras vid en viss tidpunkt.

![Resa med begränsad genomströmningsaktivitet som styr leveransfrekvensen för meddelanden](assets/limit-throughput-2.png)

Låt oss ta ett exempel på en **målgruppsinställd resa** som arbetar med en population av **10 000 profiler** och skickar data till ett externt system som stöder **100 förfrågningar/sekund**.

1. Du kan definiera din läspublik för att läsa profiler med ett genomflöde på 500 profiler/sekund, vilket innebär att det tar 20 sekunder att läsa alla dina profiler. På andra sidan kommer du att läsa 500 av dem, på andra 2 500 till osv.

1. Du kan sedan lägga till en procentuell delning av villkorsaktivitet med en delning på 20 % som har 100 profiler i varje gren vid varje sekund.

1. Efter det lägger du till väntningsaktiviteter med en viss timer i varje gren. Här har vi konfigurerat en 30-sekunders väntan på var och en. Varje sekund kommer 100 profiler att flöda in i varje gren.

   * På förgrening 1 väntar de i 30 sekunder, vilket innebär att:
      * den andra 1, kommer 100 profiler att vänta på den andra 31
      * på andra 2, kommer 100 profiler att vänta på andra 32, osv.

   * På gren 2 väntar de i 60 sekunder, vilket innebär att:
      * På andra 1 väntar 100 profiler på andra 61 (1&#39;01&#39;)
      * På andra 2 väntar 100 profiler på andra 62 (1&#39;02&#39;) osv.

   * Eftersom vi vet att maximalt 20 sekunder förväntas läsa alla profiler, kommer det inte att finnas någon överlappning mellan varje gren. 20 är den sista där profiler kommer att flöda in i villkoret. Mellan 31:a och 51:a sekund behandlas alla profiler i gren 1. Mellan andra 61 (1&#39;01&#39;) och andra 81 (1&#39;21&#39;), kommer alla profiler i gren 2 att bearbetas osv.

   * Du kan också lägga till en sjätte gren med färre än 100 profiler per gren, särskilt om det externa systemet bara stöder 100 begäranden/sekund.

>[!IMPORTANT]
>
>Precis som med andra lösningar bör du testa lösningen noggrant innan du går till produktion för att vara säker på att den fungerar som du vill.

Som extra skydd kan du också använda funktionen för att hämta innehåll.

>[!NOTE]
>
>Till skillnad från Kapning, som skyddar en slutpunkt genom att vara global till alla resor i en sandlåda, fungerar den här lösningen bara på resenivå. Det innebär att om flera resor körs parallellt och har samma slutpunkt som mål, måste du ta hänsyn till detta när du utformar din resa. Den här lösningen passar därför inte för alla användningsområden.
