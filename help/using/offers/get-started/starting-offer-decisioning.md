---
title: Kom igång med Beslutshantering
description: Kom igång med Beslutshantering. Läs mer om dess arkitektur, erbjudanden och beslut, liksom om vanliga användningsfall som gör att du kan arbeta.
feature: Offers
topic: Integrations
role: User
level: Beginner
exl-id: 659984cb-b232-47ba-9f5a-604bf97a5e92
source-git-commit: f186eeb09e9f9e0b8094baa8038ab0298b7e5148
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 45%

---

# Om beslutshantering {#about-offer-decision}

Använd [!DNL Journey Optimizer] för att leverera det bästa erbjudandet och upplevelsen till era kunder via alla kontaktytor vid rätt tidpunkt. När ni väl utformat er målgrupp kan ni inrikta er på personaliserade erbjudanden.

>[!NOTE]
>
>Om du är [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target=&quot;_blank&quot;}-användare och använder **Offer decisioning**-programtjänsten gäller även alla beslutshanteringsfunktioner som beskrivs i det här avsnittet dig.

Beslutsledningskapaciteten består av två huvudkomponenter:

* **Centralized Offer Library**, som är gränssnittet där du skapar och hanterar de olika elementen som dina erbjudanden består av, och definierar deras regler och begränsningar.
* Den **beslutsmotor för erbjudandet** som använder Adobe Experience Platform-data och kundprofiler i realtid, tillsammans med erbjudandebiblioteket, för att välja rätt tid, kunder och kanaler som erbjudandena ska levereras till.

![](../../assets/architecture.png)

Några fördelar:

* Förbättrade kampanjresultat genom att leverera personaliserade erbjudanden i flera kanaler,
* Förbättrade arbetsflöden: I stället för att skapa flera leveranser eller kampanjer kan marknadsföringsteamen förbättra arbetsflödena genom att skapa en enda leverans och variera erbjudandena i olika delar av mallen.
* Styr hur många gånger ett erbjudande visas för olika kampanjer och kunder.

➡️ [Titta på de här självstudiekurserna](#tutorial-videos) för mer information om Beslutshantering.

## Om erbjudanden och beslut {#offers-offer-activities}

Ett **erbjudande** består av innehåll, berättiganderegler och begränsningar som definierar villkoren som gäller när det presenteras för dina kunder.

Det skapas med **Erbjudandebiblioteket** som innehåller en central erbjudandekatalog där du kan koppla berättiganderegler och begränsningar till flera innehållsdelar för att skapa och publicera erbjudanden (se [Användargränssnitt för erbjudandebibliotek](../get-started/user-interface.md)).

![](../../assets/offer_structure.png)

När erbjudandebiblioteket har berikats med erbjudanden kan du integrera dina erbjudanden i **beslut** (tidigare kallat&quot;erbjudandeaktiviteter&quot;).

Besluten är behållare för dina erbjudanden som utnyttjar beslutsmotorn för erbjudanden för att välja det bästa erbjudandet som ska levereras beroende på leveransmålet.

## Vanliga användningsfall

Beslutshanteringsfunktionerna och integrationen med Adobe Experience Platform gör att ni kan ta upp ett antal olika användningsfall som hjälper er att öka kundernas engagemang och konverteringar.

* Visa erbjudanden på webbplatsens hemsida som matchar besökskundens intressen, baserat på data från Adobe Experience Platform.

   ![](../../assets/website.png)

* Om kunderna går nära en av era butiker skickar du push-meddelanden som påminner dem om tillgängliga erbjudanden enligt deras attribut (lojalitetsnivå, kön, tidigare köp ...).

   ![](../../assets/push_sample.png)

* Beslutshanteringen hjälper er också att förbättra kundernas upplevelse när ni kontaktar supportteamet. Med API:er för beslutshantering kan du i kundtjänstagentportalen visa information om kundens inlösta och nästa bästa erbjudanden.

   ![](../../assets/do-not-localize/call-center.png)

## Bevilja åtkomst till beslutsledning {#granting-acess-to-decision-management}

Behörigheter att komma åt och använda offera decisioningen hanteras med [Adobe Admin Console](https://helpx.adobe.com/enterprise/managing/user-guide.html){target=&quot;_blank&quot;}.

Om du vill ge åtkomst till beslutshanteringsfunktionen måste du skapa en **[!UICONTROL Product profile]** och tilldela användarna motsvarande behörigheter. Läs mer om hur du hanterar [!DNL Journey Optimizer] användare och behörigheter i [det här avsnittet](../../administration/permissions.md).

Behörigheterna som är specifika för Beslutshantering listas i [det här avsnittet](../../administration/high-low-permissions.md#decisions-permissions).

## Ordlista {#glossary}

Nedan finns en lista över de viktigaste koncept du kommer att arbeta med när du använder Beslutshantering.

* **Begränsning** eller **antal begränsningar**: en begränsning för att definiera hur många gånger ett erbjudande presenteras. Det finns två typer av begränsningar. Hur många gånger ett erbjudande kan föreslås för den kombinerade målgruppen, även kallat ”Total begränsning” och hur många gånger ett erbjudande kan föreslås för samma slutanvändare, även kallat ”Profilbegränsning”.

* **Samlingar**: samlingar är underuppsättningar av erbjudanden som baseras på fördefinierade villkor som definieras av en marknadsförare såsom erbjudandets kategori.

* **Beslut**  (tidigare kallat erbjudandeverksamhet): Ett beslut innehåller den logik som ligger till grund för valet av ett erbjudande.

* **Beslutsregel**: beslutsregler är begränsningar som läggs till på ett personaliserat erbjudande och tillämpas på en profil för att fastställa berättigande.

* **Berättigat erbjudande**: ett berättigat erbjudande uppfyller de krav som anges ovan och kan konsekvent erbjudas till en profil.

* **Beslutshantering**: Gör att ni kan skapa och leverera personaliserade erbjudandeupplevelser för slutanvändare i alla kanaler och i alla tillämpningar med hjälp av logiska funktioner och beslutsregler.

* **Reserverbjudanden**: ett reserverbjudande är erbjudandet som visas när en slutanvändare inte är berättigad till något av de personaliserade erbjudandena i samlingen.

* **Erbjudande**: ett erbjudande är ett marknadsföringsmeddelande som kan ha kopplade regler som fastställer vem som kan se erbjudandet.

* **Erbjudandebibliotek**: Erbjudandebiblioteket är ett centralt bibliotek som används för att hantera personaliserade erbjudanden och reserverbjudanden, beslutsregler och beslut.

* **Personaliserade erbjudanden**: ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på berättiganderegler och -begränsningar.

* **Placeringar**: en placering är den plats och/eller det sammanhang där ett erbjudande visas för en slutanvändare.

* **Prioritet**: prioritet används för att rangordna erbjudanden som uppfyller alla begränsningar såsom berättigande, kalender och begränsningar.

* **Representationer**: en representation är information som används av en kanal, såsom plats eller språk, för att visa ett erbjudande.


## Självstudievideor {#tutorial-videos}

>[!NOTE]
>
>Dessa videofilmer gäller för den programtjänst för Offer decisioning som är byggd på Adobe Experience Platform och är inte specifika för [!DNL Adobe Journey Optimizer]. De ger dock allmän vägledning om hur beslutshantering kan användas inom ramen för [!DNL Journey Optimizer].

### Vad är beslutshantering? {#what-is-offer-decisioning}

I videon nedan ges en introduktion till nyckelfunktioner, arkitektur och användningsfall för beslutshantering:

>[!VIDEO](https://video.tv.adobe.com/v/326961?quality=12&learn=on)

### Definiera och hantera erbjudanden {#use-offer-decisioning}

I videon nedan visas hur du använder Beslutshantering för att definiera och hantera dina erbjudanden och utnyttja kunddata i realtid.

>[!VIDEO](https://video.tv.adobe.com/v/326841?quality=12&learn=on)
