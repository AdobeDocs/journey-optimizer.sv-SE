---
solution: Journey Optimizer
product: journey optimizer
title: AEM Content Fragments
description: Lär dig hur du kommer åt och hanterar AEM Content Fragments
topic: Content Management
role: User
level: Beginner
exl-id: 57d7c25f-7e39-46ad-85c1-65e2c18e2686
source-git-commit: 74723337f97c8196b506ccc1ace11077710494ea
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 0%

---

# Adobe Experience Manager Content Fragments {#aem-fragments}

Genom att integrera Adobe Experience Manager as a Cloud Service med Adobe Journey Optimizer kan du nu smidigt införliva dina AEM Content Fragments i ditt Journey Optimizer-innehåll. Denna smidiga anslutning förenklar processen att komma åt och utnyttja AEM-innehåll, vilket gör det möjligt att skapa personaliserade och dynamiska kampanjer och resor.

Mer information om AEM Content Fragments finns i [Arbeta med innehållsfragment](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments-with-journey-optimizer){target="_blank"} i Experience Manager-dokumentationen.

>[!AVAILABILITY]
>
>För hälso- och sjukvårdskunder aktiveras integreringen endast när man licensierar Journey Optimizer Healthcare Shield och Adobe Experience Manager Enhanced Security-tillägg.

## Begränsningar {#limitations}

* Vi rekommenderar att du begränsar antalet användare som har tillgång till publicering av innehållsfragment för att minska risken för oavsiktliga fel.

* För flerspråkigt innehåll stöds endast det manuella flödet.

* Variationer stöds för närvarande inte.

* Korrektur för publicerade kampanjer och resor visar data från den senaste utgåvan av Experience Manager Content fragment.

## Skapa och tilldela en tagg i Experience Manager

Innan du använder ditt Content-fragment i Journey Optimizer måste du skapa en tagg speciellt för Journey Optimizer:

1. Få åtkomst till din **Experience Manager**-miljö.

1. Välj **Taggning** på menyn **Verktyg**.

   ![](assets/do-not-localize/aem_tag_1.png)

1. Klicka på **Skapa tagg**.

1. Kontrollera att ID:t följer följande syntax: `ajo-enabled:{AJO-OrgId}/{AJO-SandboxName}`.

1. Klicka på **Skapa**.

1. Definiera innehållsfragmentmodellen så som beskrivs i [Experience Manager-dokumentationen](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragment-models){target="_blank"} och tilldela den nya Journey Optimizer-taggen.

Nu kan du börja skapa och konfigurera ditt innehållsfragment för senare användning i Journey Optimizer. Läs mer i [Experience Manager-dokumentation](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/managing){target="_blank"}.

## Lägg till Experience Manager Content-fragment {#aem-add}

När du har skapat och personaliserat dina AEM Content Fragments kan du nu importera det till din kampanj eller resa för att optimera resan.

1. Skapa din [kampanj](../campaigns/create-campaign.md) eller [resa](../building-journeys/journey-gs.md).

1. Om du vill komma åt ditt AEM-innehållsfragment klickar du på ![Personalization-ikonen](assets/do-not-localize/Smock_PersonalizationField_18_N.svg) i ett textfält eller öppnar källkoden via en HTML-innehållskomponent.

   ![](assets/aem_campaign_2.png)

1. Klicka på **[!UICONTROL AEM Content Fragment]** på menyn **[!UICONTROL Open AEM CF selector]** i den vänstra rutan.

   ![](assets/aem_campaign_3.png)

1. Välj en **[!UICONTROL Content Fragment]** i den tillgängliga listan för import till ditt Journey Optimizer-innehåll.

1. Klicka på **[!UICONTROL Show filters]** för att finjustera listan med innehållsfragment.

   Som standard är filtret Innehållsfragment förinställt så att endast godkänt innehåll visas.

   ![](assets/aem_campaign_4.png)

1. När du har valt **[!UICONTROL Content Fragment]** klickar du på **[!UICONTROL Select]** för att öppna den.

   ![](assets/aem_campaign_5.png)

1. Klicka på **[!UICONTROL View fragment]** om du vill visa fragmentinformationen. Observera att om du öppnar menyn **[!UICONTROL Fragment Info]** så är redigeraren skrivskyddad.

   Välj **[!UICONTROL Preview]** på den högra menyn för att visa ditt fragment i Adobe Experience Manager.

   ![](assets/aem_campaign_7.png)

1. Klicka på ikonen ![Fler åtgärder](assets/do-not-localize/Smock_MoreSmallList_18_N.svg) för att komma åt fragmentets avancerade meny:

   * **[!UICONTROL Swap fragment]**
   * **[!UICONTROL Explore references]**
   * **[!UICONTROL Open in AEM]**

   ![](assets/aem_campaign_8.png)

1. Välj önskade fält från din **[!UICONTROL Fragment]** som ska läggas till i ditt innehåll.
   <!--
    Note that if you choose to copy the value, any future updates to the Content Fragment will not be reflected in your campaign or journey. However, using dynamic placeholders ensures real-time updates.-->

   ![](assets/aem_campaign_6.png)

1. Om du vill aktivera realtidspersonalisering måste alla platshållare som används i en **[!UICONTROL Content fragment]** uttryckligen deklareras som parametrar i fragmenthjälpposten. Du kan mappa dessa platshållare till profilattribut, sammanhangsberoende attribut, statiska strängar eller fördefinierade variabler på följande sätt:

   1. **Mappning av profil- eller kontextuella attribut**: Tilldela platshållaren till en profil eller ett sammanhangsberoende attribut, t.ex. name = profile.person.name.firstName.

   1. **Statisk strängmappning**: Tilldela ett fast strängvärde genom att placera det inom dubbla citattecken, t.ex. name = &quot;John&quot;.

   1. **Variabelmappning**: Referera till en variabel som deklarerats tidigare inom samma HTML, t.ex. name = &#39;variableName&#39;.
I det här fallet kontrollerar du att **_variableName_** har deklarerats innan du lägger till fragment-ID:t, med följande syntax:

      ```html
      {% let variableName = attribute name %} 
      ```

   I exemplet nedan mappas platshållaren **_name_** till attributet **_profile.person.name.firstName_** i fragmentet.

   ![](assets/aem_campaign_9.png){zoomable="yes"}


1. Klicka på **[!UICONTROL Save]**. Du kan nu testa och kontrollera meddelandeinnehållet enligt beskrivningen i [det här avsnittet](../content-management/preview.md).

När du har utfört dina tester och validerat innehållet kan du [skicka din kampanj](../campaigns/review-activate-campaign.md) eller [publicera din resa](../building-journeys/publish-journey.md) till din målgrupp.

Med Adobe Experience Manager kan ni identifiera de Journey Optimizer-kampanjer eller resor där ett innehållsfragment används. Läs mer i [Adobe Experience Manager-dokumentation](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/extension-content-fragment-ajo-external-references).
