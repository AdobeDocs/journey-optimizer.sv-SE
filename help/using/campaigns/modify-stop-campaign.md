---
solution: Journey Optimizer
product: journey optimizer
title: Ändra eller stoppa en kampanj
description: Lär dig hur du ändrar, stoppar eller duplicerar live-kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: hantera kampanjer, status, schema, åtkomst, optimering
exl-id: 1b88c84e-9d92-4cc1-b9bf-27a2f1d29569
source-git-commit: 1ad534b7877f0ac6c1f50e29f41af708e83b34c9
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---

# Hantera kampanjer {#modify-stop-campaign}

När en kampanj har aktiverats kan du när som helst ändra eller stoppa den. Dessa åtgärder är endast tillgängliga för kampanjer med en återkommande körning.

Dessutom kan ni duplicera live-kampanjer (som körs en gång eller med en återkommande körning) för att skapa nya, och arkivera slutförda eller stoppade kampanjer.

## Åtkomst till kampanjer {#access}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_view"
>title="Kampanjlista och kalendervyer"
>abstract="Förutom kampanjlistan innehåller [!DNL Journey Optimizer] en kalendervy över dina kampanjer, som ger en tydlig visuell representation av deras scheman. Du kan när som helst växla mellan list- och kalendervyer med dessa knappar."

Kampanjer är tillgängliga på menyn **[!UICONTROL Campaigns]**.

Som standard visas alla kampanjer med statusvärdena **[!UICONTROL Draft]**, **[!UICONTROL Scheduled]** och **[!UICONTROL Live]** i listan. Om du vill visa stoppade, slutförda och arkiverade kampanjer måste du rensa filtret.

![](assets/create-campaign-list.png)

Du kan också filtrera listan baserat på kampanjtyp och kanal, eller de taggar som har tilldelats kampanjerna när de skapas. [Lär dig hur du tilldelar taggar till en kampanj](create-campaign.md#create)

## Kampanjkalender {#calendar}

Förutom kampanjlistan innehåller [!DNL Journey Optimizer] en kalendervy över dina kampanjer, som ger en tydlig visuell representation av deras scheman.

>[!AVAILABILITY]
>
>Kalendervyn är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Använd [det här formuläret](https://forms.cloud.microsoft/r/FC49afuJVi){target=”_blank”} om du vill begära åtkomst.
>
>Den här funktionen är under aktiv utveckling. Vi välkomnar dina indata och begäranden med knappen **[!UICONTROL Beta Feedback]** på den övre menyn.

I kalendern visas alla kampanjer som är schemalagda för den aktuella veckan. Använd pilknapparna ovanför kalendern för att navigera mellan veckor.

![kalendervy som visar aktiva kampanjer](assets/campaigns-timeline.png)

Hur kampanjer presenteras:

* Som standard visar kalenderrutnätet alla aktiva och schemalagda kampanjer för den valda veckan. Ytterligare filteralternativ kan visa slutförda, stoppade och avslutade aktiveringar eller aktiveringar av en viss typ eller kanal.
* Utkastkampanjer visas inte.
* Kampanjer som sträcker sig över flera dagar visas högst upp i kalenderrutnätet.
* Om ingen starttid anges används den närmaste manuella aktiveringstiden för att placera den i kalendern.
* Kampanjer visas som 1-timmars tidsintervall, men detta återspeglar inte den faktiska tiden för sändning eller slutförande.

Om du vill ha mer information om en kampanj klickar du på det synliga blocket för att öppna detaljer om den.

Om du vill visa information om en viss kampanj väljer du den i listan. En informationsruta öppnas med olika information om kampanjen, t.ex. typ, åtkomst till rapporter eller taggar som har tilldelats.

![kampanjlista med informationsrutan öppnad](assets/campaign-rail.png)

## Kampanjstatus och larm {#statuses}

Kampanjer kan ha flera statusvärden:

* **[!UICONTROL Draft]**: Kampanjen redigeras, den har inte aktiverats.
* **[!UICONTROL Activating]**: Kampanjen aktiveras.
* **[!UICONTROL Processing]** *(endast e-postkampanjer)*: Målgruppsexporten är klar, kampanjen publiceras.
* **[!UICONTROL Live]**: Kampanjen har aktiverats.
* **[!UICONTROL Scheduled]**: Kampanjen är konfigurerad att aktiveras ett visst startdatum.
* **[!UICONTROL Stopped]**: Kampanjen har stoppats manuellt. Du kan inte aktivera eller återanvända den längre. [Lär dig stoppa en kampanj](modify-stop-campaign.md#stop)
* **[!UICONTROL Completed]**: Kampanjen är slutförd. Den här statusen tilldelas automatiskt 3 dagar efter att en kampanj har aktiverats, eller vid kampanjens slutdatum om den har en återkommande körning.
* **[!UICONTROL Archived]**: Kampanjen har arkiverats. [Lär dig arkivera kampanjer](modify-stop-campaign.md#archive)

>[!NOTE]
>
>Ikonen Öppna utkast till version bredvid statusen **[!UICONTROL Live]** eller **[!UICONTROL Scheduled]** anger att en ny version av kampanjen har skapats och inte har aktiverats än. [Läs mer](modify-stop-campaign.md#modify).

När ett fel inträffar inom en av era kampanjer visas en varningsikon bredvid kampanjens status. Klicka på den för att visa information om varningen. Dessa varningar kan inträffa i olika situationer, t.ex. när kampanjmeddelandet inte har publicerats eller om den valda konfigurationen är felaktig.

![](assets/campaign-alerts.png)

## Ändra en återkommande kampanj {#modify}

Så här ändrar du och skapar en ny version av en återkommande kampanj:

1. Öppna kampanjen och klicka sedan på knappen **[!UICONTROL Modify campaign]**.

1. En ny version av kampanjen skapas. Du kan kontrollera live-versionen genom att klicka på **[!UICONTROL Open live version]**.

   ![](assets/create-campaign-draft.png)

   I kampanjlistan visas aktiverade kampanjer med en pågående utkastversion med en specifik ikon i kolumnen **[!UICONTROL Status]**. Klicka på den här ikonen för att öppna utkastet till kampanjversionen.

   ![](assets/create-campaign-edit-list.png)

1. När ändringarna är klara kan du aktivera den nya versionen av kampanjen (se [Granska och aktivera en kampanj](create-campaign.md#review-activate)).

   >[!IMPORTANT]
   >
   >När du aktiverar utkastet ersätts kampanjens liveversion.

## Stoppa en återkommande kampanj {#stop}

Om du vill stoppa en återkommande kampanj öppnar du den och klickar sedan på knappen **[!UICONTROL Stop campaign]**.

![](assets/create-campaign-stop.png)

>[!IMPORTANT]
>
>Att stoppa en kampanj kommer inte att stoppa en pågående sändning, men det kommer att stoppa en schemalagd sändning eller nästa förekomst om sändning redan pågår.

<!-- inbound campaign (inapp): can stop and resume -->

## Duplicera en kampanj {#duplicate}

Du kan duplicera en livekampanj och skapa en ny. Det gör du genom att öppna kampanjen och sedan klicka på **[!UICONTROL Duplicate]**.

![](assets/create-campaign-duplicate.png)

## Arkivera en kampanj {#archive}

Med tiden växer listan över kampanjer och blir så småningom svårare att hitta färdiga och stoppade kampanjer.

För att förhindra detta kan ni arkivera slutförda och stoppade kampanjer som ni inte längre behöver. Om du vill göra det klickar du på ellipsknappen och väljer **[!UICONTROL Archive]**.

![](assets/create-campaign-archive.png)

Arkiverade kampanjer kan sedan hämtas med det dedikerade filtret i listan. [Lär dig hur du får åtkomst till kampanjer](get-started-with-campaigns.md#access)
