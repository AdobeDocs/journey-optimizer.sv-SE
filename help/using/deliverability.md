---
title: Körning av övervakningsmeddelande
description: Läs riktlinjer för övervakning och leverans
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
exl-id: 8f33dda7-9bd5-4293-8d0d-222205cbc7d5
source-git-commit: 0184614fb3203a1b5fee7603acd173042f223578
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 1%

---

# Hantera leverans {#manage-deliverability}

Leverans är ett mått på hur väl leveransen når mottagarnas inkorgar.

**E-postleverans** avser den uppsättning egenskaper som avgör om ett meddelande kan nå sin destination via en personlig e-postadress inom en kort tid och med den förväntade kvaliteten i fråga om innehåll och format. Dessa egenskaper kan delas in i fyra huvudkategorier: datakvalitet, meddelande och innehåll, utskick av infrastruktur och anseende. Tillsammans utgör de grunden för ett framgångsrikt program för e-postleverans.

The **leveransgrad** är antalet meddelanden som når mottagarnas inkorgar jämfört med antalet meddelanden som levererades. Det beror på flera faktorer, särskilt:

* Begränsade skräppostklagomål
* Låga studsfrekvenser
* Kvaliteten på adresserna
* Meddelandeinnehåll
* Avsändarens rykte

Optimera leveransen av [!DNL Journey Optimizer] rekommenderar vi att du använder de bästa metoderna som anges i det här avsnittet. Leveransproblem är i allmänhet kopplade till skydd mot skräppost som implementeras av Internet-leverantörer och e-postserveradministratörer.

En djupdykning i vad som är möjligt och mer information om termer, begrepp och metoder för leverans finns i [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=sv){target=&quot;_blank&quot;}.

## Minska antalet klagomål {#reduce-complaint-rate}

Internetleverantörer har vanligtvis ett framträdande sätt att rapportera ett mottaget meddelande som skräppost. Detta gör det möjligt att identifiera otillförlitliga källor. Genom att snabbt följa avanmälningsbegäranden och därmed visa att du är en tillförlitlig avsändare kan ni minska antalet klagomål. [Läs mer om hantering av avanmälan](consent.md#opt-out-management).

Som allmän regel ska du inte försöka hindra mottagare som vill avanmäla sig genom att kräva att de fyller i fält som e-postadress eller namn, till exempel. Startsidan för den sista prenumerationen bör bara ha en valideringsknapp.

Betala extra vård vid ytterligare bekräftelse: en användare kan ha två e-postadresser som omdirigeras till samma ruta (till exempel: firstname.lastname@club.com och firstname.lastname@internet-club.com). Om profilen bara kommer ihåg den första adressen och vill avbeställa prenumerationen via ett meddelande som skickas till den andra, kommer formuläret att avslå detta eftersom den krypterade identifieraren och den angivna e-postadressen inte matchar.

## Utnyttja undertryckningslistor {#suppression-lists}

[!DNL Journey Optimizer] hanterar en undertryckningslista som samlar in skräppostklagomål, hårda studsar och mjuka studsar som sker på ett konsekvent sätt.

För att skydda leveransen utesluts de mottagare vars adresser finns med i listan över undertryckningar som standard från alla framtida leveranser, eftersom det kan skada ditt sändningsanseende om du skickar till dessa kontakter.

[Läs mer om listan över inaktiveringar](suppression-list.md).

## Använd övervakningsverktyg {#monitoring-tools}

Använd funktionerna i [!DNL Journey Optimizer] för att övervaka leveransen.

The **[!UICONTROL Executions]** -fliken i meddelandelistan gör att du kan kontrollera hur leveranserna fungerar med hjälp av en uppsättning realtidsindikatorer. På den här fliken visas bland annat:
* Antalet meddelanden som har körts, skickats och levererats.
* Antalet meddelanden som har öppnats och antalet meddelanden/länkar som har klickats.

[Läs mer om övervakning av meddelandekörning](message-monitoring.md).

## Anpassa meddelandeinnehåll {#adapt-message-content}

I mindre utsträckning kan innehållet i vissa meddelanden identifieras som skräppost.

<!--The use of certain words or of exclamation points in the subject line and within the messages can be read as signs of spam.

Spammers are also known to replace text with images to stop offending text from being analyzed automatically by anti-spam filters. In response to this, a message (in HTML format) with a high proportion of images, or images as attachments, may end up being blocked.-->

Om du vill förbättra leveransgraden och se till att dina e-postmeddelanden når dina mottagare ska du följa principerna nedan när du utformar meddelandeinnehållet:

* **Avsändarens namn och adress**: Adressen måste uttryckligen identifiera avsändaren. Domänen måste ägas av och registreras hos avsändaren. Domänregistret får inte privatiseras.

<!--* **Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).
* **Personalize your email**: Personalizing the email increases the chances of your message being opened.
* **Images and text**: Respect a decent text/image ratio (for example 60% text and 40% images).-->
* **Avbeställ länk- och landningssida**: Länken för att avbryta prenumerationen är viktig. Den måste vara synlig och giltig och formuläret måste vara funktionellt.

<!--**Use tools** offered by Journey Optimizer to optimize the content of your email (delivery analysis, anti-spam analysis).-->

[Läs mer om hur du utformar e-postinnehåll](design-emails.md).

<!--
## Establish your reputation as a sender

If you recently moved to another email service provider, IP address, or email domain or subdomain, you need to establish your reputation as a sender. Otherwise, your deliveries might be blocked or moved to the spam folder of the recipients' mailbox.

To warm up your IP, you can gradually ramp up the number of your deliveries. See this [use case](building-journeys/ramp-up-deliveries-uc.md).
-->