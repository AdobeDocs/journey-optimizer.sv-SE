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
source-git-commit: 67032a4bcbfd56552d783f3ef78593375bfcc378
workflow-type: tm+mt
source-wordcount: '1560'
ht-degree: 0%

---

# Ange egenskaper för din resa {#jo-properties}

>[!CONTEXTUALHELP]
>id="ajo_journey_properties"
>title="Resans egenskaper"
>abstract="I det här avsnittet visas resans egenskaper. Som standard är skrivskyddade parametrar dolda. Vilka inställningar som är tillgängliga beror på resans status, på dina behörigheter och din produktkonfiguration."

>[!CONTEXTUALHELP]
>id="ajo_journey_exit_criterias"
>title="Kriterier för avresa"
>abstract="I det här avsnittet visas alternativen för avslutningskriterier. Du kan skapa en eller flera regler för avslutningskriterier för din resa."

Resetillgångarna är centraliserade till rätt spår under resan. Det här avsnittet visas som standard när du skapar en ny resa. Klicka på pennikonen bredvid resans namn för att komma åt dess egenskaper för befintliga resor.


Använd det här avsnittet för att ange namnet på resan, lägga till en beskrivning och:

* hantera [inträde och återinträde](#entrance),
* välj start och slut [datum](#dates),
* hantera [åtkomst till data](#manage-access),
* definiera [varaktighet för timeout](#timeout) i reseverksamhet (endast för administratörer),
* välj resa och profil [tidszoner](#timezone)
* Tilldela enhetliga Adobe Experience Platform-taggar till din resa för att enkelt klassificera dem och förbättra sökningen från kampanjlistan. [Lär dig hur du arbetar med taggar](../start/search-filter-categorize.md#tags)

![](assets/journey32.png)

>[!NOTE]
>
>För direktresor visar den här skärmen endast publiceringsdatumet och namnet på den användare som publicerade resan.

The **Kopiera teknisk information** Med kan du kopiera teknisk information om den resa som supportteamet kan använda för att felsöka. Följande information kopieras: `JourneyVersion UID`, `OrgID`, `orgName`, `sandboxName`, `lastDeployedBy`, `lastDeployedAt`.


## Ingång och återinträde {#entrance}

Som standard tillåter nya resor återinträde. Du kan avmarkera **Tillåt återinträde** om du vill erbjuda en engångspresentation när en person går in i en affär.

När **Tillåt återinträde** är aktiverat, **Vänteperiod för återinträde** -fältet visas. I det här fältet kan du definiera väntetiden innan du tillåter en profil att gå in på resan igen med en enda resa (med början från en händelse eller en målgruppskvalifikation). Detta förhindrar att resor utlöses felaktigt flera gånger för samma händelse. Som standard är fältet inställt på 5 minuter. Maximala längden är 29 dagar.

Läs mer om hantering av profilentré och återinträde på marknaden i [det här avsnittet](entry-management.md).

## Hantera åtkomst {#manage-access}

Om du vill tilldela etiketter för anpassad eller grundläggande dataanvändning till resan klickar du på **[!UICONTROL Manage access]** -knappen. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

![](assets/journeys-manage-access.png)

## Tidszoner för resa och profil {#timezone}

Tidszonen definieras på resenivå. Du kan ange en fast tidszon eller använda Adobe Experience Platform-profiler för att definiera resetidszonen. Om en tidszon definieras i Adobe Experience Platform-profilen kan den hämtas under resan.

Mer information om hantering av tidszoner finns i [den här sidan](../building-journeys/timezone-management.md).

## Start- och slutdatum {#dates}

Du kan definiera en **Startdatum**. Om du inte har angett någon sådan kommer den att definieras automatiskt vid publiceringstidpunkten.

Du kan också lägga till en **Slutdatum**. Detta gör att profiler kan avslutas automatiskt när datumet nås. Om inget slutdatum anges kan profilerna behållas tills [tidsgräns för global resa](#global_timeout) (som i allmänhet är 91 dagar och reducerat till 7 dagar med tilläggserbjudande till hälso- och sjukvårdsskölden). Det enda undantaget är återkommande läsningar på målgruppsresor med **Tvinga återinträde vid upprepning** som slutar vid startdatumet för nästa förekomst.

## Timeout {#timeout}

### Tidsgräns eller fel i reseaktiviteter {#timeout_and_error}

När du redigerar en åtgärd eller villkorsaktivitet kan du definiera en alternativ sökväg om ett fel eller en timeout inträffar. Om bearbetningen av aktiviteten som förhör ett tredjepartssystem överskrider tidsgränsen som anges i **[!UICONTROL Timeout or error]** för resans egenskaper väljs den andra vägen för att utföra en eventuell reservåtgärd.

Giltiga värden är mellan 1 och 30 sekunder.

Vi rekommenderar att du definierar en mycket kort **[!UICONTROL Timeout or error]** om resan är tidskänslig (exempel: reagera på en persons realtidsplats) eftersom du inte kan fördröja åtgärden i mer än några sekunder. Om resan är mindre tidskänslig kan du använda ett längre värde för att ge mer tid till det system som anropas för att skicka ett giltigt svar.

Journeys använder också en global tidsgräns enligt informationen nedan.

### Tidsgräns för global resa {#global_timeout}

Förutom [timeout](#timeout_and_error) som används i reseaktiviteter används en timeout för den globala resan. Den visas inte i gränssnittet och kan inte ändras.

Den här globala tidsgränsen stoppar de enskilda personernas framsteg under resan **91 dagar** efter att de gått in. Den här tidsgränsen reduceras till **7 dagar** med tilläggserbjudande för hälso- och sjukvårdssköld. Det innebär att en persons resa inte kan vara längre än 91 dagar (eller 7 dagar). Efter denna timeout-period tas personens data bort. Individer som fortfarande flyter i resan i slutet av timeoutperioden kommer att stoppas och de kommer inte att beaktas vid rapporteringen. Du kan därför se fler människor komma in på resan än att gå ut.

>[!NOTE]
>
>Resor reagerar inte direkt på förfrågningar om avanmälan, åtkomst eller radering av sekretess. Den globala tidsgränsen säkerställer dock att individer aldrig stannar mer än 91 dagar på någon resa.

På grund av den 91-dagars tidsgränsen för resan kan vi inte säkerställa att återinträdesspärren fungerar mer än 91 dagar när resan inte tillåts. Eftersom vi tar bort all information om personer som tagit sig in på resan 91 dagar efter ankomsten, kan vi inte veta vem som tagit sig in tidigare, mer än 91 dagar sedan.

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
      <p>Profilen kommer att ha en TTL på 91 dagar (7 dagar för HIPAA), vilket motsvarar den tid då resan ursprungligen publicerades.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil som redan har registrerat en resa när TTL-tillägget startas?</p>
    </td>
    <td>
      <p>Profilen behåller en TTL på 91 dagar (7 dagar för HIPAA) enligt den ursprungliga publiceringstiden för resan.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil i en tidigare version som publiceras om efter att TTL-tillägget startats?</p>
    </td>
    <td>
      <p>Profilen behåller en TTL på 91 dagar (7 dagar för HIPAA), i linje med den ursprungliga reseversionens publiceringstid.</p>
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
      <p>Profilen kommer att ha en TTL på 91 dagar (7 dagar för HIPAA), vilket överensstämmer med den ursprungliga publiceringstiden. För återkommande resor med tvingad återinträde kommer TTL-värdet att matcha upprepningsperioden.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil som körs genom en resa när TTL-tillägget startas?</p>
    </td>
    <td>
      <p>Profilen behåller en TTL på 91 dagar (7 dagar för HIPAA) enligt den ursprungliga publiceringstiden för resan. För återkommande resor med tvingad återinträde kommer TTL-värdet att matcha upprepningsperioden.</p>
    </td>
  </tr>
  <tr style="border: 1;">
    <td>
      <p>Vad händer med en profil som körs i en tidigare version som publiceras om efter att tillägget TTL har startats?</p>
    </td>
    <td>
      <p>Profilen behåller en TTL på 91 dagar (7 dagar för HIPPA), i linje med den ursprungliga reseversionens publiceringstid. För återkommande resor med tvingad återinträde kommer TTL-värdet att matcha upprepningsperioden.</p>
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

Resan använder sammanfogningsprinciper när profildata hämtas från Adobe Experience Platform. Beroende på resetyp används olika kopplingsprofiler:

* På läs målgrupps- eller målgruppsklassificeringsresor: målgruppspolicyn används
* Vid Unitary-händelseresor: standardprincipen för sammanslagning används
* Vid affärsevenemangsresor: sammanfogningspolicyn från målgruppen i följande Läs målgruppsaktivitet används

Resan kommer att respektera den sammanslagningspolicy som används under hela resan. Om flera målgrupper används i en resa (t.ex. i&quot;inAudience&quot;-funktioner), vilket skapar inkonsekvenser med den sammanfogningspolicy som används under resan, uppstår därför ett fel och publiceringen blockeras. Men om en inkonsekvent målgrupp används i meddelandepersonalisering visas ingen varning trots inkonsekvensen. Därför rekommenderar vi att du kontrollerar vilken sammanfogningspolicy som är kopplad till målgruppen när den här målgruppen används i meddelandepersonalisering.

Mer information om kopplingsregler finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/en/docs/experience-platform/profile/merge-policies/overview){target="_blank"}.
