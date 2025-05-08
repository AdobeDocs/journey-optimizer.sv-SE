---
title: Rankningsmetoder
description: Lär dig hur du arbetar med rangordningsmetoder
feature: Decisioning, Ranking
topic: Integrations
role: User
level: Intermediate
exl-id: c1d69bc9-4486-4037-b218-f4f704b2ba9c
source-git-commit: 4839c3c70dcc524da5f3cc394d5573ce5755ea64
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 0%

---

# Rankningsmetoder {#rankings}

Med rangordningsmetoder kan du rangordna objekt som ska visas för en viss profil. När en rangordningsmetod har skapats kan du tilldela den till en urvalsstrategi för att definiera vilka objekt som ska väljas först.

Det finns två sorteringsmetoder:

* **Med formler** kan du definiera regler som avgör vilket objekt som ska presenteras först, i stället för att ta hänsyn till objektets prioritetspoäng.

* **AI-modeller** gör att du kan använda tränade modellsystem som utnyttjar flera datapunkter för att avgöra vilket objekt som ska presenteras först.

## Skapa rangordningsmetoder {#create}

Så här skapar du en rangordningsmetod:

1. Navigera till menyn **[!UICONTROL Strategy setup]** och välj sedan menyn **[!UICONTROL Formulas]** eller **[!UICONTROL AI models]** beroende på vilken typ av rankning du vill använda.

1. Klicka på knappen **[!UICONTROL Create formula]** eller **[!UICONTROL Create AI model]** i skärmens övre högra hörn.

   ![](assets/ranking-create.png)

1. Konfigurera formeln eller AI-modellen så att den passar dina behov och spara den sedan.

   Detaljerad information om hur du skapar rankningsformler och AI-modeller finns i dokumentationen för beslutshantering:

   * [Rankningsformler](exd-ranking-formulas.md)
   * [AI-modeller](../offers/ranking/ai-models.md)

   >[!NOTE]
   >
   >Inkapslingsdjupet i en rankningsformel är begränsat till 30 nivåer. Detta mäts genom att räkna de `)` avslutande parenteserna i PQL-strängen. En regelsträng kan vara upp till 8 kB för UTF-8-kodade tecken. Detta motsvarar 8 000 ASCII-tecken (1 byte vardera), eller 2 000-4 000 icke-ASCII-tecken (2-4 byte vardera). [Läs mer om hur du bestämmer dig för skyddsprofiler och begränsningar](gs-experience-decisioning.md#guardrails)

En beslutspolicy stöder upp till 10 urvalsstrategier och beslutsposter tillsammans. [Läs mer om hur du bestämmer dig för skyddsprofiler och begränsningar](gs-experience-decisioning.md#guardrails)

+++ Optimera modeller på anpassade [!DNL Customer Journey Analytics]-mått

>[!NOTE]
>
>Den här funktionen är bara tillgänglig för [!DNL Customer Journey Analytics]-kunder med administratörsbehörighet.
>
>Innan du börjar bör du kontrollera att du har integrerat Journey Optimizer med Customer Journey Analytics för att exportera Journey Optimizer-datauppsättningar till standarddatavyer. [Lär dig utnyttja [!DNL Journey Optmizer] data i [!DNL Customer Journey Analytics]](../reports/cja-ajo.md)

Personaliserade optimeringsmodeller är en typ av AI-modell som gör att ni kan definiera affärsmål och använda kunddata för att utbilda affärsorienterade modeller för att leverera personaliserade erbjudanden och maximera nyckeltal. Detaljerad information om hur du skapar en anpassad AI-modell finns i [dokumentationen för beslutshantering](../offers/ranking/personalized-optimization-model.md).

Som standard använder personaliserade optimeringsmodeller **erbjudandeklick** som optimeringsmått. Om du arbetar med [!DNL Customer Journey Analytics] kan du med [!DNL Decisioning] utnyttja dina egna anpassade mått för att optimera din modell.

Det gör du genom att gå till skärmen för att skapa en anpassad AI-modell och expandera listrutan **[!UICONTROL Conversion event]**. Alla mätvärden från din standardvy för [!DNL Customer Journey Analytics] [data](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views){target="_blank"} visas i listan. Välj det mätvärde som du vill optimera modellen på och slutför sedan skapandet av AI-modellen som vanligt.

![](assets/ai-ranking-custom-metrics.png)

>[!NOTE]
>
>Som standard använder måtten i [!DNL Customer Journey Analytics] en attribueringsmodell med&quot;sista handen&quot;, som tilldelar 100 % av krediten till kontaktytan som inträffar senast före konverteringen.
>
>Även om det går att ändra attribueringsmodellen är inte alla attribueringsmodeller idealiska för optimering av AI-modeller. Vi rekommenderar att du väljer en attribueringsmodell som är anpassad efter dina optimeringsmål för att säkerställa att modellen är korrekt och fungerar korrekt.
>
>Mer information om tillgängliga attribueringsmodeller och riktlinjer för hur de används finns i [[!DNL Customer Journey Analytics] dokumentationen](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/attribution){target="_blank"}

+++

## Utnyttja attribut för beslutsunderlag i formler {#items}

Rankningsformler uttrycks i **PQL-syntax** och kan utnyttja olika attribut, t.ex. profilattribut, [kontextdata](context-data.md) och attribut relaterade till dina beslutsobjekt.

>[!NOTE]
>
>Mer information om hur du använder PQL-syntaxen finns i [dedikerad dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html)

Om du vill använda attribut som hör till dina beslutsobjekt i formler måste du följa syntaxen nedan i din rankningsreceptas kod. Expandera varje avsnitt för mer information:

++ + utnyttja standardattribut för beslutsunderlag

![](assets/formula-attribute.png)

+++

+++utnyttja anpassade attribut för beslutsobjekt

![](assets/formula-attribute-custom.png)

+++
