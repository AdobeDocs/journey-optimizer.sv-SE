---
solution: Journey Optimizer
product: journey optimizer
title: Vanliga frågor och svar
description: Vanliga frågor om Live-aktivitet
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '1603'
ht-degree: 0%

---

# Vanliga frågor och svar {#mobile-live-faq}

>[!BEGINSHADEBOX]

* [Kom igång med Live-aktivitet](get-started-mobile-live.md)
* [Konfiguration av aktiv aktivitet](mobile-live-configuration.md)
* [Live Activity-integrering med Adobe Experience Platform Mobile SDK](mobile-live-configuration-sdk.md)
* [Skapa en Live-aktivitet](create-mobile-live.md)
* **[Frågor och svar](mobile-live-faq.md)**
* [Rapport om aktiv aktivitetskampanj](../reports/campaign-global-report-cja-activity.md)

>[!ENDSHADEBOX]

## Allmänna frågor

+++Vad är skillnaden mellan en Live-aktivitet och ett push-meddelande?

Live Activity ger permanenta uppdateringar i realtid på Lock Screen och Dynamic Island utan att användarna behöver låsa upp enheten. Push-meddelanden är tillfälliga varningar som försvinner när de har stängts. Live-aktiviteter förblir synliga och kan uppdateras flera gånger tills de avslutas explicit.

+++

+++Hur många aktiviteter kan vara aktiva samtidigt?

En iOS-app kan köra flera Live-aktiviteter samtidigt, inklusive flera som använder samma `ActivityAttributes`-typ.

Det finns ingen hård gräns för hur många Live-aktiviteter av en viss attributtyp som utvecklare kan använda. Du kan starta så många appar som din applogik kräver, till exempel en per pågående leverans eller resa. IOS har dock en systemnivåbegränsning för hur många Live-aktiviteter som kan vara aktiva eller synliga samtidigt.

I praktiken:

* iOS har vanligtvis stöd för upp till fem samtidiga aktiviteter per app.

* Om du överskrider det här antalet kan systemet sluta visa vissa aktiviteter eller avsluta äldre aktiviteter för att spara resurser.

* Varje Live-aktivitet har en unik `Activity.id` som gör att du kan uppdatera eller avsluta den individuellt.

+++

+++Måste användarna ha appen öppen för att få uppdateringar av Live Activity?

Nej. Live-aktiviteter kan startas, uppdateras och avslutas på fjärrbasis även när appen är helt stängd, vilket är en av de viktigaste fördelarna med funktionen.

+++

+++Vilka iOS-versioner stöder Live Activity?

* iOS 16.1+: Grundläggande stöd för Live Activity
* iOS 17.2+: Funktioner som går att starta (fjärrstarta utan att öppna appen)
* iOS 18+: Stöd för TV-kanaler för målgruppsbaserade liveaktiviteter
+++

+++Hur länge kan en liveaktivitet förbli aktiv?

Apple begränsar Live-aktiviteter till **8 timmar med aktiva uppdateringar**. Efter det avslutar systemet automatiskt aktiviteten, men den kan vara synlig i ett statiskt tillstånd i upp till **12 timmar till** innan den tas bort. Du kan också avsluta en Live-aktivitet tidigare genom att ange en `dismissalDate` eller genom att anropa `activity.end()` explicit i din app.

+++

### Utvecklarfrågor

+++Behöver jag skapa ett separat widgettillägg för Live-aktiviteter?

Ja. Live-aktiviteter visas via WidgetKit, så du måste skapa ett widgettillägg i Xcode-projektet och implementera `ActivityConfiguration`.
[Läs mer om widgetkonfigurationen](mobile-live-configuration-sdk.md)

+++

+++Kan jag använda samma `LiveActivityAttributes`-klass för både lokala aktiviteter och fjärraktiviteter i Live?

Ja. Samma attributklass fungerar för både lokalt startade och fjärrstartade (push-to-start) Live-aktiviteter. Du måste registrera den hos `Messaging.registerLiveActivity()`.

+++

+++Vad händer om jag skickar en uppdatering för en Live-aktivitet som inte finns?

Om du skickar en update- eller end-händelse för en `liveActivityID` eller `channelID` som inte finns, kommer begäran att misslyckas tyst på enheten. Se alltid till att du håller reda på vilka Live-aktiviteter som är aktiva för varje användare.

+++

+++Kan jag testa Live-aktiviteter i iOS-simulatorn?

Ja, du kan testa både igång-aktiviteter och direktaktiviteter på fjärrbasis i iOS-simulatorn.

* **Lokal**: Detta inkluderar att skapa, uppdatera och avsluta Live-aktiviteter direkt från din app med **ActivityKit API:er**.

* **Fjärr**: Om du vill fjärrtesta Live Activity-funktionen integrerar du vårt Messaging SDK i din app och använder de körnings-API:er som tillhandahålls för att skicka fjärstart, uppdatering och slut till testenheten eller iOS-simulatorn. Liknar hur push-meddelanden kan testas för närvarande med Adobe SDK-integrering.

+++

+++Hur hanterar jag uppdateringar när appen finns i bakgrunden?

SDK hanterar detta automatiskt. När Live Activity har registrerats får den uppdateringar även när appen avslutas. Inga ytterligare bakgrundslägen krävs.
+++

+++Vad är skillnaden mellan `liveActivityID` och `channelID`?

* `liveActivityID`: Används för enskilda (enhetsspecifika) aktiva aktiviteter som riktar sig till specifika användare. Varje ID representerar en unik Live Activity-instans.
* `channelID`: Används för livesändning som skickas till målgrupper. Alla användare i publiken får samma uppdateringar i samma kanal.
+++

+++Kan jag anpassa Dynamic Island-utseendet separat från låsskärmen?

Ja. `ActivityConfiguration` har separata stängningar för Lock Screen-innehåll och Dynamic Island-innehåll (expanderat, kompakt och minimalt), och varje design är separat.
+++

+++Måste jag lagra push-tokens manuellt?

Nej. När du registrerar en Live Activity-typ med `Messaging.registerLiveActivity()`, samlar SDK automatiskt in och hanterar push-tokens åt dig.
+++

### Marknadsföringsfrågor

+++Kan jag personalisera Live Activity-innehåll för varje användare i en utsändningskampanj?

Sändningskampanjer skickar samma innehåll till alla användare i publiken. För personaliserat innehåll ska ni använda enhetliga (transaktionsbaserade) kampanjer riktade till enskilda användare.
+++

+++Hur vet jag om min Live Activity levererades utan problem?

[Övervaka kampanjanalysen](../reports/campaign-global-report-cja-activity.md) i Adobe Journey Optimizer. Ni kan spåra leveransfrekvenser, fel och engagemangsmått. Överväg också att implementera anpassade analyshändelser i appen.
+++

+++Kan jag schemalägga live-aktiviteter i förväg?

API-anropet utlöser den aktiva aktiviteten omedelbart. Du kan dock schemalägga dina API-anrop via dina backend-system eller använda Journey Optimizer orchestration-funktioner för att ordna dem på rätt sätt.
+++

+++Vad händer om jag skickar en start-händelse för en liveaktivitet som redan finns?

När du fjärrstartar liveaktiviteter via Adobe körnings-API:er:

* Du kan inkludera ett `x-request-id`-huvud i din begäran. Det bör helst finnas en 1:1-relation mellan varje `liveActivityID` och dess motsvarande `x-request-id`. Detta garanterar att om flera begäranden görs med samma kombination av `x-request-id` och `liveActivityID`, kommer endast en Live-aktivitet att startas på enheten och dubblettbegäranden kommer att ignoreras.

* Om rubriken `x-request-id` utelämnas behandlas varje begäran separat, vilket kan leda till att flera Live-aktiviteter skapas med samma `liveActivityID`. I sådana fall kan framtida uppdateringar misslyckas eller gälla endast en av de aktiva instanserna.

* Värdet `x-request-id` får inte återanvändas i olika `liveActivityIDs` i separata API-begäranden.

+++

+++Kan jag testa olika Live Activity-upplevelser?

Ja. Skapa flera kampanjer med olika innehållsstrukturer och testa vilka som fungerar bättre med Adobe Journey Optimizer experimentella funktioner. Se till att appen har stöd för alla innehållslägesvarianter.

+++

+++Hur ofta ska jag uppdatera en liveaktivitet?

Uppdatera endast när meningsfull information ändras eftersom för ofta förekommande uppdateringar kan tömma batteriet och minska kvaliteten på användarupplevelsen. För realtidsscenarier, som leveransspårning, är vanligtvis 30-60 sekunder godtagbara. Om innehållet förändras långsammare, t.ex. sportresultat, kan du bara uppdatera för viktiga event.

+++

+++Kan jag inrikta mig på användare baserat på om de har Live-aktiviteter aktiverat eller inte?

Du måste arbeta med ditt utvecklingsteam för att spåra och skicka inställningen till Adobe Experience Platform som ett användarattribut och sedan segmentera utifrån det attributet.

+++

### API-frågor

+++Vad är skillnaden mellan `timestamp` och `dismissal-date`?

* `timestamp`: Den aktuella epoktiden när händelsen inträffar, som krävs för alla händelser.
* `dismissal-date`: En framtida epok när den aktiva aktiviteten automatiskt ska stängas, vilket bara krävs för sluthändelser.

+++

+++Måste jag skicka alla `attributes` fält i varje uppdateringsanrop?

Ja, baserat på klassen `LiveActivityAttribute`.

* Alla fält från attributobjektet, inklusive `liveActivityData`, ska inkluderas i varje anrop för start, uppdatering eller slut.
* Endast fälten `content-state` representerar de ändringar som faktiskt ändras dynamiskt i en aktiv aktivitet som körs.
* Inkludera även ett varningsobjekt, så att push-funktionen hanteras som ett meddelande som är synligt för användaren, inte som en tyst bakgrund. Krävs endast för&quot;start&quot;-fall och är annars valfritt.

+++

+++Vilket format ska epoktidsstämplar ha?

Använd Unix-epok-tid på **sekunder**, inte millisekunder. Till exempel: `1759937682`

+++

+++Kan jag använda samma `requestId` för flera API-anrop?

Nej. Varje API-begäran ska ha en unik `requestId` för att säkerställa sekretess och korrekt spårning. Använd UUID:n eller liknande unika identifierare.

+++

+++Vilken autentisering krävs för det Headless API?

Se [API-dokumentationen för utlösta kampanjer](https://developer.adobe.com/journey-optimizer-apis/references/messaging/) för autentiseringskrav, inklusive OAuth-token och API-nycklar.

+++

+++Vad händer om mitt API-anrop misslyckas?

Implementera återförsökslogik med exponentiella bakgrunder. Kontrollera API-svaret för felkoder och meddelanden för att diagnostisera problem. Vanliga fel kan vara ogiltiga kampanj-ID:n, felformaterade nyttolaster eller autentiseringsproblem.

+++

+++Kan jag skicka live-aktivitetsuppdateringar från mina egna backend-servrar?

Ja, det är det avsedda beteendet. Din backend anropar Adobe Journey Optimizer Headless API för att aktivera Live Activity-händelser när din affärslogik kräver det.

+++

+++Behöver jag en annan kampanj för start-, uppdaterings- och sluthändelser?

Nej. Du kan använda samma kampanj och ändra fältet `event` i nyttolasten. Vissa organisationer föredrar dock separata kampanjer för bättre analysspårning.

+++

### Felsökningsfrågor

+++Min Live-aktivitet startar men uppdateras inte. Vad kunde vara problemet?

Vanliga orsaker:

* `liveActivityID` eller `channelID` matchar inte mellan start- och uppdateringsanrop.
* `content-state` fält matchar inte din `ContentState`-struktur.
* Den aktiva aktiviteten har redan avslutats.
* Problem med nätverksanslutningen på enheten.

+++

+++Fältet `attributes-type` känns inte igen. Vad ska jag kolla?

* Kontrollera att klassnamnet matchar **exakt** (skiftlägeskänsligt) med Swift-strukturnamnet
* Kontrollera att strukturen är korrekt definierad och registrerad
* Kontrollera om det finns stavfel i JSON-nyttolasten
* Bekräfta att den installerade programversionen har implementeringen av Live Activity

+++

+++Användarna ser bara uppdateringen av Live Activity och inte varningsmeddelandet. Är detta ett känt problem?

Nej. Fältet `alert` är valfritt och kan inaktiveras av iOS under vissa förhållanden, till exempel Stör inte. Live-aktiviteter kan uppdateras tyst, vilket ofta är tänkt. Varningsfältet är obligatoriskt för att skicka fjärrstarter, annars behandlas det som ett tyst bakgrundsmeddelande.

+++

+++Kan jag ta bort eller rensa alla Live-aktiviteter för en användare?

Du måste skicka en&quot;end&quot;-händelse för varje aktiv Live-aktivitet. Spåra vilka live-aktiviteter som är aktiva för varje användare i dina system så att du kan rensa upp dem på rätt sätt.

+++

+++Min widget visar&quot;Inga data&quot; trots att jag har skickat en uppdatering. Vad kunde vara problemet?

* Kontrollera att widgetimplementeringen har åtkomst till `context.state` och `context.attributes`.
* Kontrollera att standardvärden eller fellägen hanteras i widgetens gränssnitt.
* Använd protokollet `LiveActivityAssuranceDebuggable` för att felsöka schemat.
* Testa med Adobe Assurance för att se om data tas emot.
+++
