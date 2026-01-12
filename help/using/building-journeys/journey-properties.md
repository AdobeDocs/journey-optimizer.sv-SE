---
solution: Journey Optimizer
product: journey optimizer
title: Definiera resans egenskaper
description: Lär dig hur du ställer in egenskaper för din resa med Adobe Journey Optimizer
feature: Journeys, Get Started
topic: Content Management
role: User
level: Intermediate
keywords: resa, konfiguration, egenskaper
exl-id: 6c21371c-6cbc-4d39-8fe6-39f1b8b13280
version: Journey Orchestration
source-git-commit: 0271dfdf9578921f48001f2bdcc0dbb15f785762
workflow-type: tm+mt
source-wordcount: '2846'
ht-degree: 0%

---

# Ange egenskaper för din resa {#jo-properties}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties"
>title="Resans egenskaper"
>abstract="I det här avsnittet visas resans egenskaper. Som standard är skrivskyddade parametrar dolda. Vilka inställningar som är tillgängliga beror på resans status, dina behörigheter och produktkonfiguration."

## Åtkomst till egenskaperna för en resa {#access-properties}

Resans egenskaper är centraliserade i rätt spår. Det här avsnittet visas som standard när du skapar en ny resa. Klicka på pennikonen bredvid resans namn för att öppna befintliga resor.

I det här avsnittet definierar du namnet på resan, lägger till en beskrivning och anger globala egenskaper för resan.

Du kan:

* Tilldela enhetliga Adobe Experience Platform-taggar till resan, så att du enkelt kan klassificera dem och förbättra sökningen från kampanjlistan. [Lär dig arbeta med taggar](../start/search-filter-categorize.md#tags)
* Välj resemätningar. [Lär dig hur du konfigurerar och spårar dina resemått](success-metrics.md)
* Hantera [inträde och återinträde](#entrance). Hanteringen av profilentréer beror på typen av resa. Information finns på [den här sidan](entry-management.md)
* Hantera [åtkomst till data](#manage-access)
* Välj resan och profilen [tidszoner](#timezone)
* Välj anpassade [start- och slutdatum](#dates)
* Definiera en [timeout-varaktighet](#timeout) i reseaktiviteter (endast för Admin-användare)
* Övervaka konflikter och prioritera dina resor med [konflikthanteringsverktyg](#conflict)

![Konfigurationsfönstret för reseegenskaper med allmänna inställningar och avancerade alternativ](assets/new-journey-properties.png){width="80%"}{zoomable="yes"}

>[!NOTE]
>
>För direktresor visar den här skärmen endast publiceringsdatumet och namnet på den användare som publicerade resan.

Med alternativet **Kopiera teknisk information** kan du kopiera teknisk information om den resa som supportteamet kan använda för att felsöka. Följande information kopieras: `JourneyVersion UID`, `OrgID`, `orgName`, `sandboxName`, `lastDeployedBy`, `lastDeployedAt`.

Läs mer om tekniska fält som rör en resa för en viss profil och hur du använder dem [på den här sidan](expression/journey-properties.md).

## Ingång och återinträde {#entrance}

Profilinmatningsläget definieras på resenivån i den högra konfigurationsrutan. Inställningarna beskrivs nedan.

Hanteringen av profilentréer beror på typen av resa. Läs mer om hantering av profilinträde och återinträde på [den här sidan](entry-management.md). Läs mer om hastighetsbearbetning av resor och hur profiler flödar genom resor i [det här avsnittet](entry-management.md#journey-processing-rate).

### Tillåt återinträde  {#allow-reentrance}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_entrance"
>title="Tillåt återinträde"
>abstract="Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet **Tillåt återinträde** till exempel om du vill erbjuda en engångspresentation när en person går in i en affär."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/entry-management" text="Profilingångshantering"

Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet **Tillåt återinträde** för engångsresor, till exempel om du vill erbjuda en engångsgåva när en person går till en affär.

### Vänteperiod för återinträde  {#reentrance-wait}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_re-entrance_wait"
>title="Vänteperiod för återinträde"
>abstract="Ställ in väntetiden innan du tillåter att en profil går in på resan igen med enhetsresor. Detta förhindrar att användarna kommer in på resan igen under en viss tid. Maximal varaktighet: 90 dagar."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/entry-management" text="Profilingångshantering"

När alternativet **Tillåt återinträde** är aktiverat visas fältet **Återkommande vänteperiod**. I det här fältet kan du definiera väntetiden innan du tillåter en profil att gå in på resan igen med en enda resa (med början från en händelse eller en målgruppskvalifikation). Detta förhindrar att resor utlöses felaktigt flera gånger för samma händelse. Som standard är fältet inställt på 5 minuter. Maximala längden är 90 dagar.

## Hantera åtkomst {#manage-access}

Du kan begränsa åtkomsten till en resa baserat på åtkomstetiketter.

Om du vill tilldela anpassade etiketter för dataanvändning till resan klickar du på ikonen **[!UICONTROL Manage access labels]** och väljer en eller flera etiketter.

[Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

## Tidszoner för resa och profil {#timezone}

Tidszonen definieras på resenivå. Du kan ange en fast tidszon eller använda Adobe Experience Platform-profiler för att definiera resetidszonen. Om en tidszon definieras i Adobe Experience Platform-profilen kan den hämtas under resan.

[Läs mer om hantering av tidszoner](../building-journeys/timezone-management.md)

## Start- och slutdatum {#dates}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_start_date"
>title="Startdatum"
>abstract="Välj det datum då profiler kan börja registrera resan. Om inget startdatum har angetts används transportens publiceringsdatum som standard."

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_end_date"
>title="Slutdatum"
>abstract="Ange datumet då resan slutar. På detta datum avslutas resan automatiskt av aktiva profiler och inga nya tävlingsbidrag tillåts."

Som standard kan profiler ta sig in på din resa så snart den har publicerats, och de kan stanna tills tidsgränsen för den [globala resan](#global_timeout) nås. Det enda undantaget är återkommande läsmålgruppsresor med **Tvinga återinträde vid upprepning** aktiverat, som slutar vid startdatumet för nästa förekomst.

Om det behövs kan du definiera ett anpassat **startdatum** och **slutdatum**. Detta gör att profilerna kan gå in på din resa ett visst datum och avsluta automatiskt när slutdatumet nås.

## Timeout {#timeout}

### Tidsgräns för reseaktiviteter {#timeout_and_error}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties_timeout"
>title="Timeout eller fel"
>abstract="Ange hur länge resan ska försöka utföra en åtgärd eller utvärdera ett villkor innan det behandlas som timeout. Rekommenderade värden är mellan 1 och 30 sekunder."

När du redigerar en åtgärd eller villkorsaktivitet kan du definiera en alternativ sökväg om ett fel eller en timeout inträffar. Om bearbetningen av aktiviteten som förhör ett tredjepartssystem överskrider tidsgränsen som anges i fältet **[!UICONTROL Timeout or error]** för resans egenskaper, väljs den andra sökvägen för att utföra en eventuell reservåtgärd.

Rekommenderade värden är mellan 1 och 30 sekunder.

Vi rekommenderar att du definierar ett mycket kort **[!UICONTROL Timeout or error]**-värde om din resa är tidskänslig (exempel: reagerar på en persons realtidsplats) eftersom du inte kan fördröja åtgärden i mer än några sekunder. Om resan är mindre tidskänslig kan du använda ett längre värde för att ge mer tid till det system som anropas för att skicka ett giltigt svar.

Journeys använder också en global tidsgräns enligt informationen nedan.

### Tidsgräns för global resa {#global_timeout}

Utöver den [timeout](#timeout_and_error) som används i reseaktiviteter används en timeout för den globala resan. Den visas inte i gränssnittet och kan inte ändras.

Den här globala tidsgränsen avbryter förloppet för personer på resan **91 dagar** efter att de har gått in. Det innebär att en persons resa inte kan vara längre än 91 dagar. Efter denna timeout-period tas personens data bort. Individer som fortfarande flyter i resan i slutet av timeoutperioden kommer att stoppas och de kommer inte att beaktas vid rapporteringen. Du kan därför se fler människor komma in på resan än att gå ut.

>[!NOTE]
>
>Den exakta definitionen av när en resa betraktas som&quot;avslutad&quot; varierar beroende på resetyp. [Se detaljerade villkor](end-journey.md#journey-finished-definition).

På grund av den 91-dagars tidsgränsen för resor, när återinträde inte tillåts, kan vi inte säkerställa att återinträdesspärren fungerar mer än 91 dagar. Eftersom vi tar bort all information om personer som tagit sig in på resan 91 dagar efter ankomsten, kan vi inte veta vem som tagit sig in tidigare, mer än 91 dagar sedan.

En enskild person kan bara förlägga en vänteaktivitet om han eller hon har tillräckligt med tid kvar på resan för att slutföra väntetiden innan tidsgränsen på 91 dagar för en resa är slut. Läs [den här sidan](../building-journeys/wait-activity.md).

#### TTL (Time-to-Live) och datalagring - frågor och svar {#timeout-faq}

Från och med Adobe Journey Optimizer-versionen från juni 2024 har den globala tidsgränsen för resan flyttats från 30 till 91 dagar. Effekter listas i Frågor och svar nedan:

**För Unitary Journeys**

<table style="table-layout:auto">
  <tr style="border: 1;">
    <td>
      <p>Vad händer med den resa som publiceras efter att TTL-tillägget lanserats?</p>
    </td>
    <td>
      <p>Profiler som kommer in på den nya resan får automatiskt en TTL på 91 dagar.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil som går in på en resa som publicerades innan TTL-tillägget startades?</p>
    </td>
    <td>
      <p>Profilen kommer att ha en TTL på 30 dagar (7 dagar för HIPAA), vilket motsvarar den tid då resan ursprungligen publicerades.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil som redan har registrerat en resa när TTL-tillägget startas?</p>
    </td>
    <td>
      <p>Profilen behåller en TTL på 30 dagar (7 dagar för HIPAA) enligt den ursprungliga publiceringstiden för resan.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil i en tidigare version som publiceras om efter att TTL-tillägget startats?</p>
    </td>
    <td>
      <p>Profilen behåller en TTL på 30 dagar (7 dagar för HIPAA), i linje med den ursprungliga reseversionens publiceringstid.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en ny profil som anger en återpublicerad reseversion efter att TTL-tillägget har startats?</p>
    </td>
    <td>
      <p>Profilen kommer att ha en TTL på 91 dagar, vilket matchar TTL-värdet för den nypublicerade reseversionen.</p>
    </td>
  </tr>
</table>

**För segmentutlösarresor**

<table style="table-layout:auto">
  <tr style="border: 1;">
    <td>
      <p>Vad händer med nya engångsresor som publiceras efter tillägget för TTL?</p>
    </td>
    <td>
      <p>Profiler som kommer in på den nya resan kommer att ha en TTL på 91 dagar automatiskt.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med nya återkommande resor utan tvingad återinträde som publiceras efter tillägget för TTL?</p>
    </td>
    <td>
      <p>Profiler som kommer in på den nya resan kommer att ha en TTL på 91 dagar automatiskt.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med nya återkommande resor med tvingad återinträde som publiceras efter tillägget för TTL?</p>
    </td>
    <td>
      <p>Profiler som går in på den nya resan kommer att ha en TTL som motsvarar upprepningsperioden. Om resan till exempel körs dagligen är TTL 1 dag.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil som går in på en resa som publicerades innan TTL-tillägget startades?</p>
    </td>
    <td>
      <p>Profilen kommer att ha en TTL på 30 dagar (7 dagar för HIPAA), vilket överensstämmer med den ursprungliga publiceringstiden. För återkommande resor med tvingad återinträde kommer TTL-värdet att matcha upprepningsperioden.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil som körs genom en resa när TTL-tillägget startas?</p>
    </td>
    <td>
      <p>Profilen behåller en TTL på 30 dagar (7 dagar för HIPAA) enligt den ursprungliga publiceringstiden för resan. För återkommande resor med tvingad återinträde kommer TTL-värdet att matcha upprepningsperioden.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil som körs i en tidigare version som publiceras om efter att tillägget TTL har startats?</p>
    </td>
    <td>
      <p>Profilen behåller en TTL på 30 dagar (7 dagar för HIPPA), i linje med den ursprungliga reseversionens publiceringstid. För återkommande resor med tvingad återinträde kommer TTL-värdet att matcha upprepningsperioden.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en ny profil som anger en återpublicerad reseversion efter att TTL-tillägget har startats?</p>
    </td>
    <td>
      <p>Profilen kommer att ha en TTL på 91 dagar, vilket matchar TTL-värdet för den nypublicerade reseversionen. För återkommande resor med tvingad återinträde kommer TTL-värdet att matcha upprepningsperioden.</p>
    </td>
  </tr>
</table>

## Sammanfoga profiler {#merge-policies}

Adobe Journey Optimizer använder sammanfogningsprinciper när profildata hämtas från Adobe Experience Platform. Beroende på resetyp används olika kopplingsprofiler:

* På läs målgrupps- eller målgruppsklassificeringsresor: målgruppspolicyn används
* Vid Unitary-händelseresor: standardprincipen för sammanslagning används
* Vid affärsevenemangsresor: sammanfogningspolicyn från målgruppen i följande Läs målgruppsaktivitet används

Adobe Journey Optimizer tillämpar den kopplingsregel som används under hela kundresan. Om flera målgrupper används i en resa (till exempel med in [`inAudience`-funktioner](functions/functioninaudience.md)) skapas därför inkonsekvenser med den sammanfogningsprincip som används för resan. Ett fel genereras och publikationen blockeras. Men om en inkonsekvent målgrupp används i meddelandepersonalisering visas ingen varning trots inkonsekvensen. Därför rekommenderar vi att du kontrollerar vilken sammanfogningspolicy som är kopplad till målgruppen när den här målgruppen används i meddelandepersonalisering.

Mer information om sammanfogningsprinciper finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/merge-policies/overview){target="_blank"}.

>[!NOTE]
>
>När en princip för målgruppssammanfogning uppdateras måste en aktiv resa som refererar till den målgruppen publiceras på nytt (eller dupliceras). Genom att ändra sammanslagningspolicyn på ett effektivt sätt skapas en&quot;ny&quot; målgrupp som den pågående resan inte har tillgång till, vilket säkerställer att alla data är enhetliga.

## Avslutningskriterier {#exit-criteria}

>[!CONTEXTUALHELP]
>id="ajo_journey_exit_criterias"
>title="Avslutningskriterier"
>abstract="I det här avsnittet visas alternativen för avslutningskriterier. Du kan skapa en eller flera regler och filter för utförselvillkor för din resa."

### Villkor för avresa {#exit-criteria-desc}

Genom att lägga till kriterier för att avsluta resan gör du så att profilerna avslutas så snart en händelse inträffar (t.ex. köp) eller så kvalificerar de sig för en viss målgrupp. Detta förhindrar användaren från att få ut mer information från resan.

Du kanske vill ta bort profiler från en resa när de inte längre uppfyller resans syfte. Detta kan uppnås med **globala avslutningskriterier**, som är nära kopplade till målhantering.

>[!TIP]
>
>Söker du praktisk vägledning med exempel från verkligheten? Se vår [omfattande guide till kriterier för resa in- och utträde](entry-exit-criteria-guide.md), som omfattar fullständiga användningsfall med både in- och utresekonfigurationer, bästa praxis och optimeringsstrategier.

**Exempel på användning**

En marknadsförare har en marknadsföringsresa som har en serie kommunikationer. Alla dessa meddelanden syftar till att få kunden att göra ett inköp. Så snart köpet är klart bör kunden inte få resten av meddelandena i serien. Genom att definiera ett avslutningskriterium tas alla profiler som har gjort ett köp bort från resan.

#### Konfiguration och användning {#exit-criteria-config}

Avslutskriterier ställs in på resenivå. En resa kan ha flera exitkriterier. Om du har angett flera avslutsvillkor utförs utvärderingen uppifrån och ned med en `OR`-logik. Om du har avslutningskriterier A och avslutningskriterier B utvärderas det därför som A **OR** B. Kriterierna utvärderas under varje steg av resan.

Följ de här stegen för att **skapa** och avsluta villkor:

1. Öppna din resa.

1. Klicka på ikonen ![Visa avslutningsvillkor](assets/do-not-localize/Smock_UserCheckedOut_18_N.svg) **[!UICONTROL Show Exit Criteria]** i det övre högra avsnittet på arbetsytan.

1. Välj **[!UICONTROL Add exit criteria]**.

1. Ange en **etikett** och välj om ditt avslutsvillkor är baserat på en **händelse** eller en **publik**.

   * För avslutningskriterier som baseras på en händelse, t.ex. nedladdning av en app eller tillägg av en produkt i en kundvagn, väljer du endast en enhetshändelse.
   * Välj en målgrupp för avslutningskriterier som baseras på en målgrupp, t.ex. en målgrupp som kontrollerar om en kund har köpt under de senaste 24 timmarna. Obs! Det kan ta upp till 10 minuter innan avslutningskriterierna används för att bli effektiva.

Du kan lägga till flera avslutningskriterier.

![Panelen Avsluta villkor som visar målgruppsvillkor för avslut](assets/exitcriteria-sample.png){width="40%" align="left"}


### Profilattributsbaserade avslutningskriterier {#profile-exit-criteria}

Profilattributsbaserade villkor för utträde ger dig större kontroll över pausade resor genom att du kan definiera regler som automatiskt tar bort specifika profiler innan resan återupptas. Du kan ange avslutningsvillkor baserat på profilattribut, t.ex. plats, status eller inställningar, för att säkerställa att endast relevanta profiler fortsätter under resan efter att den har återupptagits.

Du kan till exempel [pausa en resa](journey-pause.md), lägga till ett avslutningsvillkor för att ta bort alla profiler som finns i Frankrike och återuppta resan i vetskap om att profilerna kommer att uteslutas i nästa steg. Denna logik gäller både profiler som redan är på resan och alla nya profiler som kvalificerar sig efter att resan har återupptagits.

Den här funktionen fungerar tillsammans med funktionerna Paus/Återuppta, vilket gör att du kan hantera resorna på ett säkrare och flexiblare sätt. Det minimerar manuella ingrepp, minskar risken för att skicka irrelevant eller icke-kompatibel kommunikation och ser till att kundens kundresa hålls i linje med aktuella affärskrav.

Läs det här avsnittet för att lära dig hur du [använder villkor för att avsluta profilattribut på pausade resor](journey-pause.md#journey-pause-sample).

### Skyddsritningar och begränsningar {#exit-criteria-guardrails}

Följande skyddsutkast och begränsningar gäller för funktionen [Villkor för avslut från resa](#exit-criteria-desc):

* Utgångskriterier definieras endast i utkastläge
* Samstämmighet mellan händelser och händelsebaserade kriterier för utträde på resan

Följande skyddsutkast gäller när du använder funktionen [Profilattributsbaserade avslutningsvillkor](#profile-exit-criteria):

* **Utgångsvillkor gäller på åtgärdsnivå**\
  Utgångsvillkoren för profilattribut utvärderas endast i steg om åtgärder. Till skillnad från andra typer av avslutningskriterier gäller de inte globalt under hela resan.\
  Om du återupptar en resa och vissa profiler uppfyller avslutningsvillkoret, kommer de profilerna att uteslutas vid nästa åtgärdsnod.\
  Nya profiler som kommer in på resan efter återupptagandet utvärderas och utesluts vid den första åtgärdsnoden, om de uppfyller villkoret.

* **En profilbaserad avslutsregel per resa**\
  Du kan bara definiera ett avslutande villkor för profilattribut per resa. Denna begränsning bidrar till att bibehålla klarheten och undviker konflikter i reselogiken.

* **Endast tillgänglig på pausade resor**\
  Du kan bara lägga till eller redigera slutvillkor för profilattribut när resan pausas.

   * I ett **utkast** visas alternativet *Profilattribut* inaktiverat (skrivskyddat), medan alternativen *Händelse* och *målgrupp* fortfarande är aktiva.
   * I en **pausad resa** går det att redigera alternativet *Profilattribut* och alternativen *Händelse* och *målgrupp* blir skrivskyddade.

### Relaterade ämnen {#exit-criteria-related}

* [Guide för in- och utträdeskriterier för resor](entry-exit-criteria-guide.md) - Fullständig guide med verkliga exempel och bästa praxis
* [Profilingångshantering](entry-management.md) - Konfigurera hur profiler anger resor
* [Hur resorna slutar](end-journey.md) - Förstå naturligt slutförande av resan
* [Pausa en resa med villkor för utträde av profilattribut](journey-pause.md#journey-exit-criteria) - Använd villkor för utträde när du pausar resor

## Reseschema {#schedule}

Avsnittet **[!UICONTROL Schedule]** är bara tillgängligt när en **[!UICONTROL Read Audience]**-aktivitet har släppts på arbetsytan. Det gör att du kan definiera ett specifikt datum/tid och en viss frekvens som resan ska köras med. [Lär dig schemalägga en läsarresa](../building-journeys/read-audience.md)

## Konflikthantering {#conflict}

Avsnittet **[!UICONTROL Conflict management]** i resans egenskaper gör att du kan övervaka konflikter och prioritera dina resor. Du kan:

* Använd en **regeluppsättning** för att exkludera den här resan till en del av målgruppen baserat på appningsregler. [Lär dig arbeta med regeluppsättningar](../conflict-prioritization/rule-sets.md)

* Tilldela en **prioritetspoäng** till resan, från 0 till 100. Ett högre tal anger en högre prioritet. Prioritetsvärdet som infogas här ärvs av alla inkommande åtgärder (till exempel i appen) som ingår i den här resan. [lär dig hur du arbetar med prioriteringspoäng](../conflict-prioritization/priority-scores.md)

  I situationer där samma konfiguration för inkommande kanal används i andra kampanjer eller resor visas den inkommande åtgärden med högsta prioritet för mottagaren. Om flera resor eller kampanjer har samma poäng väljs det element som senast ändrades.

* **Visa konflikter** med andra resor, kampanjer eller kanalkonfigurationer. Om du vill identifiera överlappning för målgrupper, start- och slutdatum, kanalkonfiguration, kanal eller regeluppsättning kan du visa potentiella konflikter här. [Lär dig identifiera potentiella konflikter under resan](../conflict-prioritization/conflicts.md)
