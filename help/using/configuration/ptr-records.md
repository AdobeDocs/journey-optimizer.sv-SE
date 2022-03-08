---
title: PTR-poster
description: Lär dig hantera PTR-poster
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 4c930792-0677-4ad5-a46c-8d40fc3c4d3a
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 0%

---

# PTR-poster {#ptr-records}

## Om PTR-poster {#about-ptr-records}

En pekarpost (PTR) är en typ av DNS-post (Domain Name System) som tillhandahåller det domännamn som är länkat till en IP-adress.

Med PTR-poster kan e-postservrar som tar emot e-post kontrollera e-postservrarnas äkthet genom att identifiera om deras IP-adresser motsvarar de namn som servrarna ansluter till.

## Få åtkomst till dina underdomäners PTR-poster {#access-ptr-records}

En gång [en underdomän har delegerats](delegate-subdomain.md) i Adobe Journey Optimizer skapas en PTR-post automatiskt och kopplas till den här underdomänen. Du kommer åt den via **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** > **[!UICONTROL PTR records]** -menyn.

![](assets/ptr-records.png)

I listan visas de PTR-poster som genererats för varje delegerad underdomän med syntaxen nedan:

* &quot;r&quot; för register,
* &quot;xx&quot; för de två sista siffrorna i IP-adressen,
* underdomännamn.

Du kan öppna en PTR-post från listan för att visa det associerade underdomännamnet och IP-adressen.

## Redigera en PTR-post {#edit-ptr-record}

Du kan ändra en PTR-post om du vill redigera den underdomän som är associerad med en IP-adress.

>[!NOTE]
>
>Du kan inte ändra **[!UICONTROL IP]** och **[!UICONTROL PTR record]** fält.

### Fullt delegerade underdomäner {#fully-delegated-subdomains}

Redigera en PTR-post med en underdomän som är [helt delegerad](delegate-subdomain.md#full-subdomain-delegation) till Adobe följer du stegen nedan.

1. Öppna en PTR-post genom att klicka på dess namn i listan.

   ![](assets/ptr-record-select.png)

1. Välj en underdomän [helt delegerad](delegate-subdomain.md#full-subdomain-delegation) till Adobe från listan.

   ![](assets/ptr-record-subdomain.png)

1. Klicka **[!UICONTROL Save]** för att bekräfta dina ändringar.

### Delegerade underdomäner med CNAME-metoden {#edit-ptr-subdomains-cname}

Så här redigerar du en PTR-post med en underdomän som har delegerats till Adobe med [CNAME-metod](delegate-subdomain.md#cname-subdomain-delegation)följer du stegen nedan.

1. Öppna en PTR-post genom att klicka på dess namn i listan.

   ![](assets/ptr-record-select-cname.png)

1. Markera en underdomän som delegerats till Adobe med [CNAME-metod](delegate-subdomain.md#cname-subdomain-delegation) från listan.

   ![](assets/ptr-record-subdomain-cname.png)

1. Du måste skapa en ny framåtriktad DNS-post på din värdplattform. Det gör du genom att kopiera posten som genererats av Adobe. När du är klar markerar du rutan &quot;Jag bekräftar..&quot;.

   ![](assets/ptr-record-subdomain-confirm.png)

   >[!NOTE]
   >
   >Om du får det här meddelandet: &quot;Skapa en vanlig DNS först och försök sedan igen&quot;, följ stegen nedan:
   >   * Kontrollera DNS-providern om den vidarebefordrade DNS-posten har skapats.
   >   * Poster i hela DNS kanske inte synkroniseras omedelbart. Vänta några minuter och försök igen.


1. Klicka **[!UICONTROL Save]** för att bekräfta dina ändringar.

## Kontrollera uppdateringsinformation för PTR-post {#check-ptr-record-update}

A **[!UICONTROL Processing]** visas bredvid namnet på PTR-posten i listan.

![](assets/ptr-record-updating.png)

Om du vill kontrollera uppdateringsinformationen för PTR-posten klickar du på **[!UICONTROL Updating]** eller **[!UICONTROL Recent updates]** ikon.

![](assets/ptr-record-recent-update.png)

Du kan se information som uppdateringsstatus och begärda ändringar.

![](assets/ptr-record-updates.png)

## Uppdateringsstatus för PTR-post {#ptr-record-update-statuses}

En PTR-postuppdatering kan ha följande status:

* ![](assets/do-not-localize/ptr-record-processing.png) **[!UICONTROL Processing]**: Uppdateringen av PTR-posten har skickats och genomgår en verifieringsprocess.
* ![](assets/do-not-localize/ptr-record-success.png) **[!UICONTROL Success]**: Den uppdaterade PTR-posten har verifierats och den nya underdomänen är nu associerad med IP-adressen.
* ![](assets/do-not-localize/ptr-record-failed.png) **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under PTR-postuppdateringsverifieringen.

### Bearbetar {#processing}

Flera leveranskontroller kommer att utföras för att verifiera att den nya underdomänen som ska associeras med IP-adressen är giltig. <!--The processing time is around **48h-72h**, and can take up to **7-10 days**.-->

>[!NOTE]
>
>Du kan inte ändra en PTR-post medan uppdateringen pågår. Du kan fortfarande klicka på namnet, men **[!UICONTROL Subdomain]** fältet är nedtonat. Ändringarna visas inte förrän uppdateringen har slutförts.

Under valideringsprocessen är den gamla underdomänen fortfarande kopplad till IP-adressen.

### Lyckades {#success}

När valideringsprocessen har slutförts kopplas den nya underdomänen automatiskt till IP-adressen.

### Misslyckades {#failes}

Om valideringsprocessen misslyckas visas den äldre PTR-posten. Den giltiga underdomänen som tidigare var associerad med IP-adressen ändras inte.

Följande typer av uppdateringsfel är möjliga:
* Det gick inte att skapa en ny framåtriktad DNS för PTR-posten
* Det gick inte att uppdatera posten
* Det gick inte att ta in tillhörigheterna igen

När uppdateringen misslyckas blir PTR-posten redigerbar igen. Du kan klicka på dess namn och uppdatera underdomänen igen.
