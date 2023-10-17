---
solution: Journey Optimizer
product: journey optimizer
title: Delegera en underdomän
description: Lär dig delegera dina underdomäner.
feature: Subdomains
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, delegering, domän, DNS
exl-id: 8021f66e-7725-475b-8722-e6f8d74c9023
source-git-commit: c4b8a74541a3fb9fea054bd1145592d75c62b165
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 4%

---

# Delegera en underdomän {#delegate-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomainname"
>title="Delegering av underdomän"
>abstract="Med Journey Optimizer kan du delegera dina underdomäner till Adobe. Du kan delegera en underdomän helt till Adobe, vilket är den rekommenderade metoden. Du kan också skapa en underdomän med CNAME för att peka på poster som är specifika för Adobe, men på det här sättet måste du behålla och hantera DNS-poster på egen hand."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/delegate-subdomains/about-subdomain-delegation.html#subdomain-delegation-methods" text="Konfigurationsmetoder för underdomäner"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomainname_header"
>title="Delegering av underdomän"
>abstract="För att börja skicka e-post delegerar du din underdomän till Adobe. När du är klar konfigureras DNS-poster, inkorgar, avsändare, svar och studsadresser åt dig."

Domännamnsdelegering är en metod som gör att ägaren av ett domännamn (tekniskt: en DNS-zon) kan delegera en underavdelning av den (tekniskt: en DNS-zon under den, som kan kallas en underzon) till en annan enhet. Om du hanterar zonen&quot;example.com&quot; kan du som kund delegera underzonen&quot;marketing.example.com&quot; till Adobe. Läs mer på [delegering av underdomän](about-subdomain-delegation.md)

>[!NOTE]
>
>Som standard [!DNL Journey Optimizer] Med licensavtalet kan du delegera upp till 10 underdomäner. Kontakta Adobe om du vill öka begränsningen.

Du kan delegera en underdomän helt eller skapa en underdomän med CNAME för att peka mot Adobe-specifika poster.

>[!CAUTION]
>
>Den fullständiga underdomänsdelegeringen rekommenderas. Läs mer om skillnaderna mellan [konfigurationsmetoder för underdomäner](about-subdomain-delegation.md#subdomain-delegation-methods).
>
>Underdomänskonfigurationen är gemensam för alla miljöer. Därför kommer alla ändringar av en underdomän också att påverka produktionssandlådorna.

## Fullständig delegering av underdomäner {#full-subdomain-delegation}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_dns"
>title="Generera matchande DNS-poster"
>abstract="Om du vill delegera en ny underdomän till Adobe måste du kopiera och klistra in Adobe-namnserverinformationen som visas i Journey Optimizer-gränssnittet i din värdlösning för domäner för att generera matchande DNS-poster. Om du vill delegera en underdomän med CNAME måste du också kopiera och klistra in valideringsposten för SSL CDN-URL. När kontrollerna är klara kan underdomänen användas för att leverera meddelanden."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/delegate-subdomains/delegate-subdomain.html#cname-subdomain-delegation" text="CNAME-delegering av underdomän"

[!DNL Journey Optimizer] kan du delegera dina underdomäner till Adobe direkt från produktgränssnittet. På så sätt kan Adobe leverera meddelanden som en hanterad tjänst genom att kontrollera och underhålla alla aspekter av DNS som krävs för att leverera, återge och spåra e-postkampanjer.

Du kan förlita dig på att Adobe upprätthåller den DNS-infrastruktur som krävs för att uppfylla branschstandardkraven för leverans för e-postmarknadsföringsavsändardomäner, samtidigt som du fortsätter att underhålla och kontrollera DNS för dina interna e-postdomäner.

Följ stegen nedan om du vill delegera en ny underdomän till Adobe helt:

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Subdomains]** menyn och klicka sedan på **[!UICONTROL Set up subdomain]**.

   ![](assets/subdomain-delegate.png)

1. Välj **[!UICONTROL Fully delegated]** från **[!UICONTROL Set up method]** -avsnitt.

   ![](assets/subdomain-method-full.png)

1. Ange namnet på den underdomän som ska delegeras.

   ![](assets/subdomain-name.png)

   >[!CAUTION]
   >
   >Det är inte tillåtet att delegera en ogiltig underdomän till Adobe. Se till att du anger en giltig underdomän som ägs av din organisation, till exempel marketing.yourcompany.com.

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

1. Listan med poster som ska placeras på dina DNS-servrar visas. Kopiera de här posterna, antingen en efter en eller genom att hämta en CSV-fil, och navigera sedan till din värdlösning för domänen för att generera matchande DNS-poster.

1. Kontrollera att alla DNS-poster har skapats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan &quot;Jag bekräftar ...&quot; och klickar sedan på **[!UICONTROL Submit]**.

   ![](assets/subdomain-submit.png)

   >[!NOTE]
   >
   >Du kan skapa posterna och skicka konfigurationen för underdomänen senare med **[!UICONTROL Save as draft]** -knappen. Du kan sedan återuppta delegeringen av underdomäner genom att öppna den från listan över underdomäner.

1. När den fullständiga underdomänsdelegeringen har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](about-subdomain-delegation.md#access-delegated-subdomains).

   ![](assets/subdomain-processing.png)

   Innan du kan använda den underdomänen för att skicka meddelanden måste du vänta tills Adobe utför de kontroller som krävs, vilket kan ta upp till 3 timmar. Läs mer i [det här avsnittet](#subdomain-validation).

   >[!NOTE]
   >
   >Eventuella poster som saknas, det vill säga poster som ännu inte har skapats i din värdlösning, listas i listan.

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att leverera meddelanden.

   >[!NOTE]
   >
   >Underdomänen markeras som **[!UICONTROL Failed]** om du inte skapar valideringsposten i din värdlösning.

När en underdomän har delegerats till Adobe i [!DNL Journey Optimizer]skapas en PTR-post automatiskt och kopplas till den här underdomänen. [Läs mer](ptr-records.md)

>[!CAUTION]
>
>Parallell körning av underdomäner stöds för närvarande inte i [!DNL Journey Optimizer]. Om du försöker skicka en underdomän för delegering när en annan har **[!UICONTROL Processing]** får du ett felmeddelande.

## CNAME-delegering av underdomän {#cname-subdomain-delegation}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_dns_cname"
>title="Generera matchande DNS- och valideringsposter"
>abstract="Om du vill delegera en underdomän med CNAME måste du kopiera och klistra in informationen om Adobe-namnservern och den SSL CDN URL-valideringspost som visas i Journey Optimizer-gränssnittet i värdplattformen. När kontrollerna är klara kan underdomänen användas för att leverera meddelanden."

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_cdn_cname"
>title="Kopiera valideringsposten"
>abstract="Adobe genererar en valideringspost. Du måste skapa motsvarande post på värdplattformen för CDN URL-validering."

Om du har domänspecifika begränsningsprinciper och du vill att Adobe endast ska ha partiell kontroll över DNS, kan du välja att utföra alla DNS-relaterade aktiviteter på din sida.

Med CNAME-delegering av underdomäner kan du skapa en underdomän och använda CNAME för att peka mot Adobe-specifika poster. Med den här konfigurationen delar både du och Adobe ansvaret för att underhålla DNS för att konfigurera miljön för att skicka, återge och spåra e-postmeddelanden.

>[!CAUTION]
>
>CNAME-metoden rekommenderas om organisationens principer begränsar den fullständiga delegeringsmetoden för underdomäner. På det här sättet måste du behålla och hantera DNS-poster på egen hand. Adobe kan inte hjälpa till med att ändra, underhålla eller hantera DNS för en underdomän som konfigurerats via CNAME-metoden.

➡️ [Lär dig hur du skapar en underdomän med CNAME för att peka på Adobe-specifika poster i den här videon](#video)

Följ stegen nedan för att delegera en underdomän med CNAME:

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Subdomains]** menyn och klicka sedan på **[!UICONTROL Set up subdomain]**.

1. Välj **[!UICONTROL CNAME set up]** -metod.

   ![](assets/subdomain-method-cname.png)

1. Ange namnet på den underdomän som ska delegeras.

   >[!CAUTION]
   >
   >Det är inte tillåtet att delegera en ogiltig underdomän till Adobe. Se till att du anger en giltig underdomän som ägs av din organisation, till exempel marketing.yourcompany.com.

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

1. Listan med poster som ska placeras på dina DNS-servrar visas. Kopiera de här posterna, antingen en efter en eller genom att hämta en CSV-fil, och navigera sedan till din värdlösning för domänen för att generera matchande DNS-poster.

1. Kontrollera att alla DNS-poster har skapats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan &quot;Jag bekräftar ...&quot;.

   ![](assets/subdomain-create-dns-confirm.png)

   >[!NOTE]
   >
   >Du kan skapa posterna senare med **[!UICONTROL Save as draft]** -knappen. Du kan sedan återuppta delegeringen av underdomäner i det här skedet genom att öppna den från listan över underdomäner.

1. Vänta tills Adobe verifierar att dessa poster genereras utan fel i värdlösningen. Den här processen kan ta upp till 2 minuter.

   >[!NOTE]
   >
   >Eventuella poster som saknas, det vill säga poster som ännu inte har skapats i din värdlösning, listas i listan.

1. Adobe genererar en SSL CDN URL-valideringspost. Kopiera den här valideringsposten till din värdplattform. Om du har skapat den här posten på din värdlösning, markerar du kryssrutan &quot;Jag bekräftar..&quot; och klickar sedan på **[!UICONTROL Submit]**.

   <!--![](assets/subdomain-cdn-url-validation.png)-->

   >[!NOTE]
   >
   >Du kan också skapa valideringsposten och skicka underdomänskonfigurationen senare med **[!UICONTROL Save as draft]** -knappen. Du kan sedan återuppta delegeringen av underdomäner genom att öppna den från listan över underdomäner.

1. När delegeringen av CNAME-underdomänen har skickats visas underdomänen i listan med **[!UICONTROL Processing]** status. Mer information om underdomänernas status finns i [det här avsnittet](about-subdomain-delegation.md#access-delegated-subdomains).

   ![](assets/subdomain-cname-processing.png)

   Innan du kan använda den underdomänen för att skicka meddelanden måste du vänta tills Adobe utför de nödvändiga kontrollerna, som normalt tar 2 till 3 timmar. Läs mer i [det här avsnittet](#subdomain-validation).

1. När kontrollerna är slutförda<!--i.e Adobe validates the record you created and installs it-->, får underdomänen **[!UICONTROL Success]** status. Den är klar att användas för att leverera meddelanden.

   >[!NOTE]
   >
   >Underdomänen markeras som **[!UICONTROL Failed]** om du inte skapar valideringsposten i din värdlösning.

När du validerar posten och installerar certifikatet skapar Adobe automatiskt PTR-posten för CNAME-underdomänen. [Läs mer](ptr-records.md)

>[!CAUTION]
>
>Parallell körning av underdomäner stöds för närvarande inte i [!DNL Journey Optimizer]. Om du försöker skicka en underdomän för delegering när en annan har **[!UICONTROL Processing]** får du ett felmeddelande.

## Underdomänvalidering {#subdomain-validation}

Kontrollerna och åtgärderna nedan utförs tills underdomänen har verifierats och kan användas för att skicka meddelanden.

>[!NOTE]
>
>Dessa steg utförs av Adobe och kan ta upp till 3 timmar.

1. **Förvalidera**: Adobe kontrollerar om underdomänen har delegerats till Adobe DNS (NS-post, SOA-post, zoninställningar, ägarskapspost). Om steget före valideringen misslyckas returneras ett fel tillsammans med motsvarande orsak, annars går Adobe vidare till nästa steg.

1. **Konfigurera DNS för domänen**:

   * **MX-post**: E-postpost för eXchange - Post för e-postserver som bearbetar inkommande e-post som skickas till underdomänen.
   * **SPF-post**: Post för Sender Policy Framework - Visar IP-adresser för e-postservrar som kan skicka e-post från underdomänen.
   * **DKIM-post**: DomainKeys Identified Mail-standardpost - Använder kryptering med offentlig-privat nyckel för att autentisera meddelandet för att undvika förfalskning.
   * **A**: Standardmappning av IP.
   * **CNAME**: Ett kanoniskt namn eller en CNAME-post är en typ av DNS-post som mappar ett aliasnamn till ett sant eller kanoniskt domännamn.

1. **Skapa spårnings- och spegeladresser**: Om domänen är email.example.com blir spårnings-/spegeldomänen data.email.example.com. Den skyddas genom att SSL-certifikatet installeras.

1. **Tillhandahåll CDN CloudFront**: Om CDN inte redan är installerat, tillhandahåller Adobe det för din organisations-ID.

1. **Skapa CDN-domän**: Om domänen är email.example.com blir CDN-domänen cdn.email.example.com.

1. **Skapa och bifoga CDN SSL-certifikat**: Adobe skapar CDN-certifikatet för CDN-domänen och kopplar certifikatet till CDN-domänen.

1. **Skapa vanlig DNS**: Om det här är den första underdomänen som du delegerar skapar Adobe den framåtriktade DNS som krävs för att skapa PTR-poster - en för varje IP-adress.

1. **Skapa PTR-post**: PTR-posten, som också kallas omvänd DNS-post, krävs av Internet-leverantörer så att de inte markerar e-postmeddelanden som skräppost. Gmail rekommenderar också att du har PTR-poster för varje IP. Adobe skapar PTR-poster endast när du delegerar en underdomän för första gången, en för varje IP-adress, alla IP-adresser som pekar på den underdomänen. Om till exempel IP är *192.1.2.1* och underdomänen är *email.example.com* blir PTR-posten: *192.1.2.1 PTR r1.email.example.com*. Du kan uppdatera PTR-posten efteråt för att peka på den nya delegerade domänen. [Läs mer om PTR-poster](ptr-records.md)

## Instruktionsvideo{#video}

Lär dig hur du skapar en underdomän med CNAME för att peka på Adobe-specifika poster.

>[!VIDEO](https://video.tv.adobe.com/v/339484?quality=12)
