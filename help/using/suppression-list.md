---
title: Undertryckningslista
description: Lär dig vad suppressionslistan är, dess syfte och vad som ingår i den.
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
source-git-commit: ea2bb0c2956781138a0c7f2d0babfd91070dd351
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 2%

---

# Undertryckningslista {#suppression-list}

En inaktiveringslista består av e-postadresser som du vill utesluta från leveranser, eftersom det kan skada ditt sändningsrykte och din leveransfrekvens om du skickar till dessa kontakter.

Supprestionslistan [!DNL Journey Optimizer] hanteras på din egen miljönivå.

Den samlar in e-postadresser och domäner som inte används i alla e-postmeddelanden i en enda klientmiljö, vilket är specifikt för ett IMS-organisations-ID som är kopplat till ett sandbox-ID.

<!--It gathers spam complaints, hard bounces, and soft bounces that occur consistently.-->

## Varför en lista över inaktiveringar? {#why-suppression-list}

För att kontrollera de e-postmeddelanden som tas emot av deras inkorgsägare och se till att de bara får de som de vill ha, har Internet-leverantörer (ISP) och kommersiella skräppostfilter sina egna algoritmer för att spåra e-postavsändarens allmänna anseende baserat på IP-adresserna och de avsändande domänerna de använder.

Om du inte tar emot synpunkter (t.ex. skräppost, studsar) Med tanke på detta kommer de att sätta ditt rykte på en lägre nivå. Supprestionslistan hjälper dig att följa Internet-leverantörernas feedback.

Mottagare vars e-postadresser inte visas exkluderas automatiskt från meddelandeleveransen. Detta snabbar upp leveranserna eftersom felfrekvensen avsevärt påverkar leveranshastigheten.

## Vad finns på listan över spärrar? {#what-s-on-suppression-list}

E-postadresser läggs till i listan över inaktiveringar enligt följande:

* Alla **pappershögarna** och **skräppostklagomål** skickar automatiskt motsvarande e-postadresser till listan över spärrade adresser efter en enstaka förekomst.

* **Mjuka** <!--and temporary **ignored** errors--> markeringar skickar inte omedelbart en e-postadress till listan över inaktiveringar, men de ökar en felräknare. Flera [försök](configuration/retries.md) utförs sedan, och när felräknaren når tröskelvärdet läggs adressen till i listan.

* Du kan även [**manuellt** lägga till en adress eller en domän](configuration/manage-suppression-list.md#add-addresses-and-domains) i listan över inaktiveringar.

Läs mer om hårda studsar och mjuka studsar i [det här avsnittet](#delivery-failures).

>[!NOTE]
>
>Det går inte att skicka adresser för att avbryta prenumerationen till listan över inaktiveringar eftersom de inte får e-post från [!DNL Journey Optimizer]. Deras val hanteras på Experience Platform-nivå. Läs mer om [avanmälan](../using/consent.md).
<!--Email addresses of recipients who **unsubscribe** from your sendings are NOT sent to the suppression list. Confirmed by eng.: "Subscribe and Unsubscribe are handled by the Consent/Subscription service. A user that opts out will not make it to the suppression list – we won’t send them emails."-->

För varje adress, den grundläggande orsaken till inaktiveringen och undertryckningskategorin (mjuk, hård, osv.) visas i listan. Läs mer om hur du får åtkomst till och hanterar listan över inaktiveringar i [det här avsnittet](configuration/manage-suppression-list.md).

<!--Once a message is sent, the message logs allow you to view the delivery status for each recipient and the associated failure type and reason. [Learn more about monitoring message execution](monitoring.md). NO ACCESS TO LOGS YET-->

>[!NOTE]
>
>Profilerna med **[!UICONTROL Suppressed]**-status exkluderas under meddelandesändningsprocessen. Samtidigt som **reseservrapporterna** visar dessa profiler som om de har flyttats genom resan ([Läs segment](building-journeys/read-segment.md) och [Meddelande](building-journeys/journeys-message.md)-aktiviteter), kommer **e-postrapporterna** inte att inkludera dem i **[!UICONTROL Sent]**-måtten eftersom de filtreras ut innan e-postmeddelandet skickas.
>
>Läs mer i [Live-rapporten](reports/live-report.md) och [Global Report](reports/global-report.md). Om du vill ta reda på orsaken till alla undantagsfall kan du använda [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html).

### Leveransfel {#delivery-failures}

Det finns två typer av fel när en leverans misslyckas:

* **Hård studs**. Ett hårt studsande indikerar en ogiltig e-postadress (dvs. en e-postadress som inte finns). Detta innebär ett studsmeddelande från den mottagande e-postservern som uttryckligen anger att adressen är ogiltig.
* **Mjuk studsa**. Detta är ett tillfälligt e-poststuds som inträffade för en giltig e-postadress.
<!--* **Ignored**. This is an email bounce that occurred for a valid email address but is known to be temporary, such as a failed connection attempt, a temporary Spam-related issue (email reputation), or a temporary technical issue.-->

Ett **hårt studsande** lägger automatiskt till e-postadressen i listan över spärrade adresser.

Ett **mjukt studsande** <!--or an **ignored** error--> som inträffar för många gånger skickar även e-postadressen till listan efter flera försök. [Läs mer om återförsök](configuration/retries.md)

Om du fortsätter att skicka till de här adresserna kan det påverka leveransfrekvensen, eftersom den talar om för Internet-leverantörer att du kanske inte följer god praxis för underhåll av e-postadresslistor och därför kanske inte är en betrodd avsändare.

### Skräppost {#spam-complaints}

Supprestionslistan samlar in e-postadresser som markerar ditt meddelande som skräppost. Om någon till exempel skriver till en kundtjänst och begär att aldrig få e-post igen från dig, kommer personens e-postadress att undertryckas i din instans och du kommer inte att kunna leverera till den adressen längre.

Om du skickar till mottagarna efter att de skickat in ett skräppostklagomål kan det få stor effekt på ditt sändningsrykte, eftersom det informerar Internet-leverantörer om att du kan skicka oönskade e-postmeddelanden och kanske inte lyssnar på dina mottagare.

Detta kan leda till att din IP-adress eller sändande domän blockeras, vilket kan undvikas om dessa adresser finns med i listan över spärrade adresser.

<!--### Unsubscriptions {#unsubscriptions}

Every email sent to recipients must include an unsubscribe link. Upon clicking this link, if a recipient confirms [opting out](consent.md), the corresponding email address is immediately sent to the suppression list. This user must not receive communication from your brand until subscribed again.
NOT TRUE > "Subscribe and Unsubscribe are handled by the Consent/Subscription service. A user that opts out will not make it to the suppression list – we won’t send them emails."-->

<!--MOVED to Configuration/Retries section

The threshold is set at three errors:
* For the same delivery, at the third attempt, the address is suppressed.
* If there are different deliveries and two errors occur at least 24 hours apart, the error counter is incremented upon each error and the address is also suppressed at the third attempt.
When a delivery is successful after a retry, the error counter of the address is reinitialized.

### Retries {#retries}

If a message fails due to a temporary bounce of the **Ignored** type, retries will be performed for **3.5 days** from the time the message was added to the email queue.

The minimum delay between retries and the maximum number of retries to be performed are ///managed by the Enhanced MTA/// based on how well an IP is performing, both historically and currently at a given domain.

After 3.5 days, any message in the retry queue will be removed from the queue and sent back as a bounce.-->
