---
solution: Journey Optimizer
product: journey optimizer
title: Tysta timmar
description: Lär dig hur du förhindrar att kommunikation skickas under vissa perioder med regler för tysta timmar
feature: Campaigns
topic: Content Management
role: User
level: Intermediate
keywords: tysta timmar, tidsundantag, affärsregler, regeluppsättningar, schema, kampanjer
exl-id: [TO BE GENERATED]
hide: yes
hidefromtoc: yes
source-git-commit: 11bccd63afa1bf5aafcd1dff70c8193ea754d256
workflow-type: tm+mt
source-wordcount: 968
ht-degree: 0%

---

# Tysta timmar {#quiet-hours}

>[!AVAILABILITY]
>
>Regler för tysta timmar är för närvarande bara tillgängliga för en uppsättning organisationer (begränsad tillgänglighet). Om du vill bli medlem i väntelistan kontaktar du Adobe.

Med tysta timmar kan du definiera tidsbaserade undantag för e-post-, SMS-, push- och whatsApp-kanaler. De ser till att inga meddelanden skickas under särskilda tidsperioder och hjälper er att följa kundönskemål och krav på regelefterlevnad.

Du kan lägga till tysta timmar genom regeluppsättningar, som kan tilldelas enskilda åtgärder i kampanjer eller resor för exakt kontroll.

## Varför använda tysta timmar {#why-quiet-hours}

Tysta timmar hjälper er att förbättra kundupplevelsen och upprätthålla regelefterlevnaden på flera sätt:

* **Respektera kundernas önskemål**: Undvik att skicka meddelanden under obehagliga tider (t.ex. sent på kvällen eller tidig morgon), som kan påverka varumärkesanseendet och kundlojaliteten negativt.

* **Förbättra engagemanget**: Genom att skicka meddelanden när kunderna är mer benägna att se och agera på dem ökar ni effektiviteten i er kommunikation.

* **Juridisk efterlevnad**: Vissa länder och regioner förbjuder SMS-marknadsföringsmeddelanden under vissa timmar. Med tysta timmar kan du följa regler som TCPA och statsspecifika SMS-lagar.

* **Optimera timing**: Om det har gått för mycket tid sedan ett meddelande schemalagdes kanske det inte längre är relevant. Med tysta timmar kan du antingen ignorera inaktuella meddelanden eller hålla kvar dem tills en lämplig tidpunkt.

## Hur tysta timmar fungerar {#how-quiet-hours-work}

Tysta timmar implementeras genom affärsregler som ni skapar och tillämpar på era kampanjer och resor med hjälp av regeluppsättningar.

När ett meddelande är schemalagt att skickas under en lugn timperiod utför [!DNL Adobe Journey Optimizer] en av två åtgärder baserat på din konfiguration:

* **Ignorera**: Meddelandet ignoreras permanent och skickas aldrig.
* **Kö**: Meddelandet sparas och skickas automatiskt så fort den tysta timperioden är slut.

Systemet utvärderar tysta timmar baserat på mottagarens tidszon, som kan vara:

* Tidszonen som anges i kundens profil
* En härledd tidszon baserad på andra profil- och händelsedata
* En fast tidszon som du anger i regeln

>[!NOTE]
>
>Fönster före nedtryckning: Systemet börjar undertrycka kommunikationen 30 minuter innan tysta öppettider börjar och ser till att inga meddelanden levereras när den tysta perioden börjar.

## Skapa en regel för tysta timmar {#create-quiet-hours-rule}

Så här skapar du en regel för tysta timmar:

1. Navigera till **[!UICONTROL Administration]** > **[!UICONTROL Business Rules]**.

1. Skapa en ny regeluppsättning i avsnittet **[!UICONTROL Rule sets]** eller välj en befintlig regeluppsättning som du vill lägga till regeln för tysta timmar i.

1. Klicka på **[!UICONTROL Create rule]** och välj **[!UICONTROL Quiet Hours]** som regeltyp.

1. Konfigurera inställningarna för tysta timmar:

   * **Regelnamn**: Ge regeln ett beskrivande namn.

   * **Tidsperiod**: Definiera när tysta timmar ska gälla:
      * **Timmar på dagen**: Ange specifika timmar (t.ex. 8:00 till 8:00 AM)
      * **Dagar i veckan**: Välj specifika dagar (t.ex. helger)
      * **Anpassade datum**: Välj specifika kalenderdatum (t.ex. helgdagar)

   * **Tidszon**: Välj hur du vill bestämma tidszonen:
      * **Användarens lokala tidszon**: Använd tidszonen från varje mottagares profil
      * **Specifik tidszon**: Använd en fast tidszon (t.ex. Eastern, Central)

   * **Åtgärd**: Välj vad som ska hända med meddelanden under tysta timmar:
      * **Ignorera**: Meddelanden ignoreras permanent
      * **Kö**: Meddelanden sparas och skickas när tysta timmar slutar

1. Klicka på **[!UICONTROL Save]** för att skapa regeln.

## Använd tysta timmar på kampanjer och resor {#apply-quiet-hours}

När ni har skapat en regel för tysta timmar måste ni tillämpa den på era kampanjer eller resor:

1. Öppna kampanjen eller resan där du vill lägga in tysta timmar.

1. Navigera till den åtgärd (Email, SMS, Push eller WhatsApp) som du vill styra.

1. Leta reda på avsnittet **[!UICONTROL Rule set]** i åtgärdskonfigurationen.

1. Välj den regeluppsättning som innehåller din tysta timregel.

1. Spara ändringarna.

Regeln för tysta timmar gäller nu för den specifika åtgärden. Alla meddelanden som skickas via den här åtgärden respekterar konfigurationen för tysta timmar.

>[!NOTE]
>
>Regler för tysta timmar gäller för både schemalagd och händelseutlösta meddelanden. Kontrollera att regeluppsättningen är korrekt konfigurerad för att hantera ditt användningsfall.

## Tidszonshändelser {#timezone-considerations}

När du använder alternativet **Användarens lokala tidszon** söker [!DNL Adobe Journey Optimizer] efter tidszonsinformation i följande ordning:

1. **Profilens tidszonsattribut**: Tidszonen anges uttryckligen i kundens profil
2. **Inledd tidszon**: En tidszon som beräknas baserat på andra profildata och beteendesignaler

Om inget av det finns tillgängligt kanske systemet inte använder tysta timmar korrekt. Se till att era kundprofiler innehåller tidszonsinformation för optimala resultat.

När du använder en **specifik tidszon** får (eller tar inte emot) alla mottagare meddelanden baserat på den enskilda tidszonen, oavsett var de befinner sig.

## Skyddsritningar och begränsningar {#guardrails-limitations}

Tänk på följande när du använder tysta timmar:

* **Aktiveringstid**: Det kan ta upp till 20 minuter innan en regel eller regeluppsättning aktiveras fullständigt. Planera därefter när du skapar eller ändrar regler.

* **Fördröjning för kampanjaktivering**: Vänta minst 10 minuter innan du aktiverar en resa eller skickar en kampanj för att säkerställa att reglerna tillämpas korrekt.

* **Regeluppsättningsgränser**: För närvarande kan du ha upp till tre aktiva regeluppsättningar för kanaldomänen och 5 för resedomänen.

* **Meddelandefrisläppningsfrekvens**: När tysta sluttider och köade meddelanden släpps skickas de med en hastighet av upp till 5 000 meddelanden per sekund per organisation.

* **Stöds inte i**: Regler för tysta timmar är för närvarande inte tillgängliga för kampanjsamordning.

* **Torr körning**: Regler för tysta timmar utvärderas inte under körning av torra körningar.

## Rapportering {#reporting}

Ni kan spåra hur tysta timmar påverkar era kampanjer och resor med standardrapporteringsfunktionerna:

* **Heltidsrapport**: Avsnittet Exkluderade orsaker visar mängden kunder som inte fick kommunikation på grund av regler för tysta timmar, tillsammans med det specifika regeluppsättningsnamnet.

* **Live-rapport**: (Om tillgängligt) Visar realtidsstatistik för profiler som väntar på grund av tysta timmar eller ignoreras på grund av tysta timmar.

## Nästa steg {#next-steps}

När reglerna för tysta timmar har konfigurerats och tillämpats kan du:

* Granska kampanjen eller resan för att säkerställa att reglerna är korrekt kopplade
* Aktivera kampanj eller resa
* Övervaka effekten av tysta timmar i dina rapporter

