---
title: Skapa och hantera godkännandepolicyer
description: Lär dig hur du skapar och hanterar godkännandepolicyer.
role: User
level: Beginner
feature: Approval
exl-id: e518cb3c-f361-43a4-b9a5-ec070c612e75
source-git-commit: 4ce83c9cd3f70462c977db6e872a7ac51ea0e006
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Skapa och hantera godkännandepolicyer {#approval-policies}

>[!CONTEXTUALHELP]
>id="ajo_approval_policy_request_approval"
>title="Begär godkännande"
>abstract="Begär godkännande"

>[!CONTEXTUALHELP]
>id="ajo_approval_policy_request_change"
>title="Begär ändring"
>abstract="Begär ändring"

>[!NOTE]
>
>Om du vill skapa godkännandeprinciper måste du ha system- eller produktadministratörsbehörighet i Adobe Experience Platform. [Läs mer](https://experienceleague.adobe.com/sv/docs/experience-platform/access-control/home)

Med godkännandeprinciper kan administratörer upprätta en valideringsprocess för resor och kampanjer. Det här systemet anger specifika villkor som avgör om en resa eller kampanj kräver godkännande. Dessa profiler kan variera i komplexitet. De kan helt enkelt kräva att alla kampanjer granskas av en viss användare eller ett visst team, eller fastställa kriterier baserat på vem som skapade kampanjen.

Du kan rikta in godkännandepolicyer med hjälp av flexibla kriterier som taggar, kampanj-/resenamn, kanaltyper eller begärandeinformation. Du kan till exempel kräva godkännande för alla objekt som är taggade med&quot;hög risk&quot; eller för alla kampanjer som matchar ett visst namnmönster.

## Skapa godkännandepolicyer {#create-policies}

>[!CONTEXTUALHELP]
>id="ajo_permissions_approval_policy"
>title="Ny godkännandeprincip"
>abstract="På den här skärmen anger du namnet och väljer sammanhang för godkännandeprincipen, skapar sedan villkoren för att avgöra vem som kan initiera godkännandebegäran och vem som kan validera den."

>[!CONTEXTUALHELP]
>id="ajo_approval_policy_self_approval"
>title="Blockera självgodkännande"
>abstract="Aktivera det här alternativet om du vill hindra användare från att godkänna egna godkännandebegäranden, även när de tillhör en användargrupp eller roll som har utsetts till granskare."

Så här skapar du en godkännandeprincip:

1. Gå till **[!UICONTROL Administration]** och sedan [!DNL Journey Optimizer] från menyn **[!UICONTROL Permissions]** i **[!UICONTROL Policies]**.

   ![Skapa knapp för godkännandeprincip på menyn Behörigheter](assets/policy_create_1.png)

1. Klicka på **[!UICONTROL Create]** på fliken **[!UICONTROL Approval Policy]**, välj **[!UICONTROL Approval Policy]** och klicka på **[!UICONTROL Confirm]**.

1. Ange **[!UICONTROL Name]** och **[!UICONTROL Description]** som princip.

1. Välj om profilen ska gälla för **[!UICONTROL Journeys]** eller **[!UICONTROL Campaigns]**.

1. Aktivera **[!UICONTROL Block self-approval]** för att förhindra att användare som skapar en resa/kampanj godkänner sina egna objekt.

   ![](assets/policy_create_2.png)

Du kan nu förfina villkoren för att ange vem som kan initiera godkännandebegäran och vem som kan validera den.

## Ange villkor för godkännandeprofiler {#conditions}

Godkännandepolicyer erbjuder flexibla alternativ för målinriktning som passar era styrningsbehov. Du kan skapa godkännandeprofiler baserat på olika kriterier, bland annat:

* **Kampanj-/resenamn**: Målspecifika objekt efter namn
* **Taggar**: Använd principer för alla kampanjer eller resor med en viss tagg
* **Kanaltyper**: Kräv godkännande för specifika åtgärder (e-post, SMS, push osv.)
* **Kampanjtyper**: Ange andra regler för [Åtgärd jämfört med API-utlösta kampanjer](../campaigns/get-started-with-campaigns.md#campaign-types)
* **Beställare**: Definiera principer baserat på vem som skapar kampanjen eller resan

Följ de här stegen för att definiera villkoren som är kopplade till en godkännandeprincip:

1. Få åtkomst till din **[!UICONTROL Approval policy]**.

1. Klicka på **[!UICONTROL If]** på menyn **[!UICONTROL Add condition]** för att definiera vilket objekt eller vilken användare som ska utlösa en godkännandebegäran.

1. Välj lämplig **[!UICONTROL Category]**, **[!UICONTROL Matching Rule]** och **[!UICONTROL Options]**.

   Exempel:&quot;if Action match any Direct Mail&quot; eller&quot;If Requestor User name match John Doe.&quot;

   ![Gränssnitt för villkorsbyggare för godkännandeprincip](assets/policy_condition_1.png)

   +++ Läs mer om tillgängliga kategorier och alternativ
   <table>
    <tr>
      <th>Kategori</th>
      <th>Alternativ</th>
    </tr>
    <tr>
      <td rowspan="3">Kampanjtyp</td>
      <td>Schemalagd (marknadsföring)</td>
    </tr>
    <tr>
    <td>API-utlöst (marknadsföring)</td>
    </tr>
    <tr>
    <td>API-utlöst (Transactional)</td>
    </tr>
    <tr>
    <td rowspan="8">Åtgärd</td>
    <td>I appen</td>
    </tr>
    <tr>
    <td>Push-meddelande</td>
   </tr>
    <tr>
    <td>SMS</td>
    </tr>
    <tr>
    <td>E-post</td>
    </tr>
    <tr>
    <td>Direktmeddelande</td>
    </tr>
    <tr>
    <td>Webb</td>
    </tr>
    <tr>
    <td>Kodbaserad</td>
    </tr>
    <tr>
    <td>Innehållskort</td>
    </tr>
    <tr>
    <td>Taggar</td>
    <td>Namnet på taggen som används för att ordna era målgrupper. </td>
    </tr>
    <tr>
    <td>Objektnamn</td>
    <td>Objektets namn.</td>
    </tr>
    <tr>
    <td>Användarnamn för begärande</td>
    <td>Den utsedda begärarens namn och e-postadress</td>
    </tr>
    <tr>
    <td>Användargrupp för begärande</td>
    <td>Namn på användargruppen med utsedda beställare</td>
    </tr>
    </table>

1. Om du vill lägga till fler villkor klickar du på **[!UICONTROL Add condition]** för att definiera ytterligare regler och väljer antingen **[!UICONTROL And]** eller **[!UICONTROL Or]** för att ange hur villkoren ska anslutas.

1. Klicka på **[!UICONTROL Then, send approval request to]** på menyn **[!UICONTROL Add condition]** för att definiera vilken användare som kan godkänna godkännandebegäran.

1. I listrutan **[!UICONTROL Category]** väljer du om du vill välja en användargrupp eller en enskild användare.

1. Välj sedan den specifika användargruppen eller användaren i listrutan **[!UICONTROL Option]**.

   Den valda användaren eller användargruppen ansvarar för att validera godkännandebegäran.

   ![Gränssnitt för mottagarval för godkännandebegäran](assets/policy_condition_2.png)

1. Om du vill lägga till fler villkor klickar du på **[!UICONTROL Add condition]** för att definiera ytterligare regler och väljer antingen **[!UICONTROL And]** eller **[!UICONTROL Or]** för att ange hur villkoren ska anslutas.

1. Klicka på **[!UICONTROL Save]** när din princip är fullständigt konfigurerad.

Du kan nu aktivera din godkännandeprincip för att tillämpa den.

## Aktivera och hantera godkännandepolicyer {#activate-policies}

Om du vill tillämpa din godkännandeprincip måste du aktivera den. Gör så här:

1. Få åtkomst till din **[!UICONTROL Approval policy]**.

1. Klicka sedan på **[!UICONTROL Activate]** för att använda de konfigurerade villkoren i din miljö.

   >[!NOTE]
   >
   >När du har aktiverat profiler kan de inte redigeras. Om du vill ändra villkoren måste du först inaktivera principen.

   ![Aktivera principknapp för godkännande](assets/policy_activate_1.png)

1. Öppna de avancerade alternativen på menyn **[!UICONTROL Policy]** till **[!UICONTROL Edit]**, **[!UICONTROL Deactivate]** eller **[!UICONTROL Duplicate]** profilen efter behov.

   ![Alternativ för hantering av godkännandeprincip](assets/policy_activate_2.png)
