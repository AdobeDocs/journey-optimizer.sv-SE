---
solution: Journey Optimizer
product: journey optimizer
title: Undertryckningslista
description: Lär dig hur du använder listan över inaktiveringar är
feature: Deliverability
topic: Content Management
role: Admin
level: Intermediate, Experienced
exl-id: a4653378-b70f-454c-a446-ab4a14d2580a
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 2%

---

# Undertryckningslista {#suppression-list}

En undertryckningslista består av adresser och domäner som du vill utesluta från leveranser, eftersom det kan skada ditt sändningsrykte och din leveransfrekvens om du skickar till dessa kontakter.

Suppressionslistan [!DNL Journey Optimizer] hanteras på din egen miljönivå, dvs. för en given sandlåda.

Den samlar in e-postadresser och domäner som inte används i alla e-postmeddelanden i en enda klientmiljö, vilket är specifikt för ett organisations-ID som är kopplat till ett sandbox-ID.

>[!NOTE]
>
>Adobe håller en uppdaterad lista över kända dåliga adresser som har visat sig vara skadliga för engagemanget och utskickets anseende och ser till att e-post inte skickas till dem. Listan hanteras i en global undertryckningslista som är gemensam för alla Adobe-kunder. Adresserna och domännamnen som finns i den globala undertryckningslistan är dolda. Endast antalet uteslutna mottagare anges i leveransrapporterna.

Dessutom kan du använda Journey Optimizer **Suppression REST API** för att styra dina utgående meddelanden med hjälp av suppression och tillåtelselista. [Lär dig hur du arbetar med Suppression REST API](https://developer.adobe.com/journey-optimizer-apis/references/suppression/){target="_blank"}

## Varför en lista över inaktiveringar? {#why-suppression-list}

För att kontrollera de e-postmeddelanden som tas emot av deras inkorgsägare och se till att de bara får de som de vill ha, har Internet-leverantörer (ISP) och kommersiella skräppostfilter sina egna algoritmer för att spåra e-postavsändarens allmänna anseende baserat på IP-adresserna och de avsändande domänerna de använder.

Om du inte tar hänsyn till deras synpunkter (t.ex. skräppost, studsar osv.) kommer de att minska ditt rykte. Supprestionslistan hjälper dig att följa Internet-leverantörernas feedback.

Mottagare vars e-postadresser inte visas exkluderas automatiskt från meddelandeleveransen. Detta snabbar upp leveranserna eftersom felfrekvensen avsevärt påverkar leveranshastigheten.

## Vad finns på listan över spärrar? {#what-s-on-suppression-list}

Adresser läggs till i listan över undertryckningar enligt följande:

* Alla **hårda studsar** och **skräppostklagomål** skickar automatiskt motsvarande adresser till listan över spärrade adresser efter en enstaka förekomst. Läs mer om skräppostklagomål i [det här avsnittet](#spam-complaints).

* **Mjuka studsar** skickar inte omedelbart en adress till listan över inaktiveringar, men de ökar en felräknare. Flera [försök](../configuration/retries.md) utförs sedan, och när felräknaren når tröskelvärdet läggs adressen till i listan.

* Du kan också [**manuellt** lägga till en adress eller en domän &#x200B;](../configuration/manage-suppression-list.md#add-addresses-and-domains) i listan över inaktiveringar.

Läs mer om hårda studsar och mjuka studsar i [det här avsnittet](#delivery-failures).

>[!NOTE]
>
>Det går inte att skicka adresser för att avbryta prenumerationen till listan över inaktiveringar eftersom de inte får e-post från [!DNL Journey Optimizer]. Deras val hanteras på Experience Platform-nivå. Läs mer om [avanmälan](../privacy/opt-out.md).

För varje adress visas den grundläggande orsaken till inaktiveringen och undertryckningskategorin (mjuk, hård, osv.) i undertryckningslistan. Läs mer om hur du får åtkomst till och hanterar listan över inaktiveringar i [det här avsnittet](../configuration/manage-suppression-list.md).

>[!NOTE]
>
>Profilerna med statusen **[!UICONTROL Suppressed]** har uteslutits under meddelandeöverföringsprocessen. Det innebär att även om **reserapporterna** visar att de här profilerna har flyttats genom resan ([Läs målgrupp](../building-journeys/read-audience.md) och [meddelandeaktiviteter](../building-journeys/journeys-message.md)) så inkluderas de inte i **e-postrapporterna** i **[!UICONTROL Sent]**-måtten eftersom de filtreras ut innan e-postmeddelanden skickas.
>
>Läs mer om [Live-rapporten](../reports/live-report.md) och [Customer Journey Analytics-rapporten](../reports/report-gs-cja.md). Om du vill ta reda på orsaken till alla undantagsfall kan du använda [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=sv-SE){target="_blank"}.

### Leveransfel {#delivery-failures}

Det finns två typer av fel när en leverans misslyckas:

* **Hårt studs**. Ett hårt studsande indikerar en ogiltig e-postadress (dvs. en e-postadress som inte finns). Detta innebär ett studsmeddelande från den mottagande e-postservern som uttryckligen anger att adressen är ogiltig.
* **Mjukt studs**. Detta är ett tillfälligt e-poststuds som inträffade för en giltig e-postadress.

Ett **hårt studsande** lägger automatiskt till e-postadressen i listan över utelämnanden.

En **mjuk studsa** <!--or an **ignored** error--> som inträffar för många gånger skickar även e-postadressen till utelämningslistan efter flera försök. [Läs mer om återförsök](../configuration/retries.md)

Om du fortsätter att skicka till de här adresserna kan det påverka leveransfrekvensen, eftersom den talar om för Internet-leverantörer att du kanske inte följer god praxis för underhåll av e-postadresslistor och därför kanske inte är en betrodd avsändare.

### Skräppost {#spam-complaints}

Supprestionslistan samlar in e-postadresser som markerar ditt meddelande som skräppost. Om någon till exempel skriver till en kundtjänst och begär att aldrig få e-post igen från dig, kommer personens e-postadress att undertryckas i din instans och du kommer inte att kunna leverera till den adressen längre.

Om du skickar till mottagarna efter att de skickat in ett skräppostklagomål kan det få stor effekt på ditt sändningsrykte, eftersom det informerar Internet-leverantörer om att du kan skicka oönskade e-postmeddelanden och kanske inte lyssnar på dina mottagare.

Detta kan leda till att din IP-adress eller sändande domän blockeras, vilket kan undvikas om dessa adresser finns med i listan över spärrade adresser.

Vissa Internet-leverantörer erbjuder en FBL-loop (feedback loop) som gör att e-postavsändaren automatiskt kan meddelas när den användare som tar emot ett e-postmeddelande väljer att markera det som skräppost. [Läs mer](deliverability.md#feedback-loops)
