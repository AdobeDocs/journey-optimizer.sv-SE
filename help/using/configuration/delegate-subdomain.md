---
title: Delegera underdomäner
description: Lär dig hur du delegerar dina underdomäner
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 8021f66e-7725-475b-8722-e6f8d74c9023
source-git-commit: a174944bb8efcb67d758d4fe215674c1b8bbee13
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 5%

---

# Delegera en underdomän

Delegering av domännamn är en metod som tillåter ägaren av ett domännamn (tekniskt: en DNS-zon) för att delegera en indelning av den (tekniskt: en DNS-zon under den, som kan kallas en underzon) till en annan entitet. Om du hanterar zonen&quot;example.com&quot; kan du som kund delegera underzonen&quot;marketing.example.com&quot; till Adobe.

Genom att delegera en underdomän för användning med [!DNL Journey Optimizer], kan klienter förlita sig på att Adobe upprätthåller den DNS-infrastruktur som krävs för att uppfylla branschstandardkraven för leverans för avsändardomäner för e-postmarknadsföring, samtidigt som de behåller och kontrollerar DNS för sina interna e-postdomäner.

[!DNL Journey Optimizer] kan du delegera dina underdomäner till Adobe direkt från produktgränssnittet. På så sätt kan Adobe leverera meddelanden som en hanterad tjänst genom att kontrollera och underhålla alla aspekter av DNS som krävs för att leverera, återge och spåra e-postkampanjer.

>[!NOTE]
>
>Som standard [!DNL Journey Optimizer] Med licensavtalet kan du delegera upp till 10 underdomäner. Kontakta Adobe om du vill öka begränsningen.
>
>Journey Optimizer stöder för närvarande inte användning av CNAME för delegering av underdomäner.

Följ stegen nedan om du vill delegera en ny underdomän:

1. Öppna **[!UICONTROL Channels]** / **[!UICONTROL Subdomains]** menyn och klicka sedan på **[!UICONTROL Delegate subdomain]**.

   ![](../assets/subdomain-delegate.png)

1. Ange namnet på den underdomän som ska delegeras.

   ![](../assets/subdomain-name.png)

   >[!CAUTION]
   >
   >Det är inte tillåtet att delegera en ogiltig underdomän till Adobe. Se till att du anger en giltig underdomän som ägs av din organisation, till exempel marketing.dincompany.com.
   >
   >Observera att underdomäner på flera nivåer, som email.marketing.your.com, inte stöds för närvarande.

1. Listan med poster som ska placeras på dina DNS-servrar visas. Kopiera de här posterna, antingen en efter en eller genom att hämta en CSV-fil, och navigera sedan till din värdlösning för domänen för att generera matchande DNS-poster.

1. Kontrollera att alla DNS-poster har skapats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan &quot;Jag bekräftar ...&quot; och klickar sedan på **[!UICONTROL Submit]**.

   ![](../assets/subdomain-submit.png)

   >[!NOTE]
   >
   >Du kan skapa posterna och skicka konfigurationen för underdomänen senare med **[!UICONTROL Save as draft]** -knappen. Du kan sedan återuppta delegeringen av underdomäner genom att öppna den från listan över underdomäner.

1. När underdomänsdelegeringen har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](access-subdomains.md).

   ![](../assets/subdomain-processing.png)

   Innan du kan använda den underdomänen för att skicka meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 3 timmar. Läs mer i [det här avsnittet](#subdomain-validation).

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att leverera meddelanden.

   <!-- later on, users will be notified in Pulse -->

   ![](../assets/subdomain-notification.png)

## Underdomänvalidering {#subdomain-validation}

Kontrollerna och åtgärderna nedan utförs tills underdomänen har verifierats och kan användas för att skicka meddelanden.

>[!NOTE]
>
>Dessa steg utförs av Adobe och kan ta upp till 3 timmar.

1. **Förvalidera**: Adobe kontrollerar om underdomänen har delegerats till Adobe DNS (NS-post, SOA-post, zoninställningar, ägarskapspost). Om steget före valideringen misslyckas returneras ett fel tillsammans med motsvarande orsak, annars går Adobe vidare till nästa steg.

1. **Konfigurera DNS för domänen**:

   * **MX-post**: Post för eXchange-post för e-postserver som bearbetar inkommande e-post som skickas till underdomänen.
   * **SPF-post**: Post för Sender Policy Framework - Visar IP-adresser för e-postservrar som kan skicka e-post från underdomänen.
   * **DKIM-post**: DomainKeys Identified Mail-standardpost - Använder kryptering med offentlig-privat nyckel för att autentisera meddelandet för att undvika förfalskning.
   * **A**: Standard-IP-mappning.

1. **Skapa spårnings- och spegeladresser**: om domänen är email.example.com, blir spårnings-/spegeldomänen data.email.example.com. Den skyddas genom att SSL-certifikatet installeras.

1. **Tillhandahåll CDN CloudFront**: om CDN inte redan är inställt, tillhandahåller Adobe det för imbern.

1. **Skapa CDN-domän**: Om domänen är email.example.com blir CDN-domänen cdn.email.example.com.

1. **Skapa och bifoga CDN SSL-certifikat**: Adobe skapar CDN-certifikatet för CDN-domänen och kopplar certifikatet till CDN-domänen.

1. **Skapa vanlig DNS**: Om det här är den första underdomänen som du delegerar, skapar Adobe den framåtriktade DNS som krävs för att skapa PTR-poster - en för varje IP-adress.

1. **Skapa PTR-post**: PTR-posten, som också kallas omvänd DNS-post, krävs av Internet-leverantörer så att de inte markerar e-postmeddelanden som skräppost. Gmail rekommenderar också att du har PTR-poster för varje IP. Adobe skapar PTR-poster endast när du delegerar den första underdomänen, en för varje IP-adress, alla IP-adresser som pekar på den första underdomänen. Om IP-adressen till exempel är *192.1.2.1* och underdomänen är *email.example.com* blir PTR-posten: *192.1.2.1 PTR r1.email.example.com*. Du kan uppdatera PTR-posten efteråt för att peka på den nya delegerade domänen.
