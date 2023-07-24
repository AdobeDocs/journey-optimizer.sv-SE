---
solution: Journey Optimizer
product: journey optimizer
title: Hantera avanmälan
description: Lär dig hur du hanterar avanmälan och sekretess
feature: Journeys
topic: Content Management
role: User
level: Intermediate
source-git-commit: 58223b4b6e6e2ef5b7fc23c5b475e74ad72d0d13
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Implementera medgivande för avanmälan för personalisering {#cpes-opt-out}


## Uttrycksredigeraren

Uttrycksredigeraren när bilder, text, ämnesrad (segment i kampanjer) personaliseras - användargränssnitt och Headless

Personaliseringsredigeraren utför inga kontroller eller kontroller av godkännande eftersom den inte deltar i leveransen av meddelandeåtgärder. Personaliseringsredigeraren följer de rättighetsbaserade åtkomstkontrolletiketter som tillhandahålls av den enhetliga profiltjänsten för att tillåta/neka att olika fält används för personalisering. Förhandsgranskning och rendering av meddelanden maskerar identifierade fält med känslig information.

I AJO Campaigns kan reglerna för samtycke verkställas på två platser. Kunderna kan inkludera definitioner av medgivandepolicyer som en del av målgruppen eller segmentskapandet för att säkerställa att målgruppen som valts för kampanjen redan har filtrerat bort profiler som inte matchar medgivandekriterierna. För det andra kommer meddelandekörningstjänsten att utföra en allmän samtyckeskontroll på kanalnivå för att säkerställa att profilerna har valt att ta emot marknadsföringskommunikation på den specifika kanalen. Själva AJO Campaign-objektet utför för närvarande inga ytterligare efterlevnadskontroller av principen för samtycke.

AJO Campaign och personalisering för manuell indrivning av samtycke:

En användares anmälningsstatus och personaliseringsönskemål bör ingå i målgruppsreglerna och -definitionen före aktivering i en Journey Optimizer Campaign. En marknadsföringsanvändare i Adobe Experience Platform kan lägga till en samtyckeskontroll till sin målgrupp genom att skapa en ny målgruppskomposition eller genom att definiera ett nytt segment med regelbyggaren.

Om du använder målgruppshanteraren kan du dela upp målgruppen med hjälp av profilattribut. När du har valt vilka medgivandeattribut du vill kontrollera kan du spara målgrupperna för aktivering i en kampanj. Tänk på att om ni skapar en målgrupp som inte har gett sitt medgivande till personalisering och sedan väljer den här målgruppen för aktivering i en kampanj, kommer personaliseringsverktygen fortfarande att vara tillgängliga. Det är marknadsföringsanvändaren som måste förstå att om de arbetar med en målgrupp som inte ska ta emot personalisering, ska de inte använda personaliseringsverktyg.

Så här skapar du en delad målgrupp i målgruppssammansättning:

1. Välj den ursprungliga målgruppen.

1. Klicka på plusikonen för att skapa en delad publik.

1. I delningsegenskaperna väljer du&quot;attribute split&quot; som typ.

1. I attributfältet klickar du på pennikonen för att öppna attributmarkeringsfönstret.

1. Ange ett värde i rutan om du vill söka efter attributet för godkännande av personalisering (observera att det här är attributets sökvägsprofil.consents.personalize.content.val

1. Välj det här attributet.

1. I Sökväg 1 - välj en etikett som hjälper dig att definiera den icke-personliga målgruppen.

1. Välj lämpligt värde i den här listan: https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html?lang=en#choice-values

   I det här fallet ska vi använda ett&quot;n&quot; för att ange att NEJ är avanmälan för personalisering

   Du kan skapa en separat bana för andra alternativvärden eller välja att ta bort återstående banor och aktivera&quot;andra profiler&quot;, som skulle innehålla alla andra profiler som inte hade det valda värdet&quot;n&quot;.

1. När du är klar klickar du i rutan där det står &quot;Spara publik&quot;. Ett nytt egenskapsfönster öppnas där du kan välja vilket namn du vill använda för de härledda målgrupperna.

1. Publicera publikens komposition när du är klar.

Om du använder segmentregelbyggaren för att skapa en målgrupp kan du välja alternativ för personalisering och samtycke som exkluderingsparametrar i målgruppsdefinitionen. Genom att lägga till i exkluderingsparametrarna kan du skapa ett enda målgruppssegment med profiler där personer som inte har gett sitt samtycke filtreras bort.
