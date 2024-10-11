---
title: Skapa och hantera godkännandepolicyer
description: Lär dig hur du skapar och hanterar godkännandepolicyer.
role: User
level: Beginner
feature: Approval
badge: label="Begränsad tillgänglighet" type="Informative"
source-git-commit: cd46b3346e284958e6f3f9fa641b548f68672000
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---


# Skapa och hantera godkännandepolicyer {#approval-policies}

>[!AVAILABILITY]
>
> Godkännandepolicyer är för närvarande bara tillgängliga för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

Med godkännandeprinciper kan administratörer upprätta en valideringsprocess för resor och kampanjer. Det här systemet anger specifika villkor som avgör om en resa eller kampanj kräver godkännande. Dessa profiler kan variera i komplexitet, från att kräva att alla kampanjer granskas av en viss användare eller team, till att fastställa kriterier baserade på vem som skapade kampanjen.

## Skapa godkännandepolicyer {#create-policies}

1. Gå till **[!UICONTROL Permissions]** och sedan **[!UICONTROL Policies]** från menyn **[!UICONTROL Administration]** i Journey Optimizer.

   ![](assets/policy_create_1.png)

1. Klicka på **[!UICONTROL Create]** på fliken **[!UICONTROL Approval Policy]**, välj **[!UICONTROL Approval Policy]** och klicka på **[!UICONTROL Confirm]**.

1. Ange **[!UICONTROL Name]** och **[!UICONTROL Description]** som princip.

1. Välj om profilen ska gälla för **[!UICONTROL Journeys]** eller **[!UICONTROL Campaigns]**.

   ![](assets/policy_create_2.png)

Du kan nu förfina villkoren för att ange vem som ska initiera godkännandebegäran och vem som ska validera den.

## Ange villkor för godkännandeprofiler {#conditions}

1. Få åtkomst till din **[!UICONTROL Approval policy]**.

1. Klicka på **[!UICONTROL Add condition]** på menyn **[!UICONTROL If]** för att definiera vilket objekt eller vilken användare som ska utlösa en godkännandebegäran.

1. Välj lämplig **[!UICONTROL Category]**, **[!UICONTROL Matching Rule]** och **[!UICONTROL Options]**.

   Exempel:&quot;if Action match any Direct Mail&quot; eller&quot;If Requestor User name match John Do.&quot;

   ![](assets/policy_condition_1.png)

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
    <td>Användarnamn för begärande</td>
    <td>Namn och e-postadress för den som gjort begäran</td>
    </tr>
    <tr>
    <td>Användargrupp för begärande</td>
    <td>Namn på användargruppen med designade beställare</td>
    </tr>
    </table>


1. Om du vill lägga till fler villkor klickar du på **[!UICONTROL Add condition]** för att definiera ytterligare regler och väljer antingen **[!UICONTROL And]** eller **[!UICONTROL Or]** för att ange hur villkoren ska anslutas.

1. Klicka på **[!UICONTROL Add condition]** på menyn **[!UICONTROL Then, send approval request to]** för att definiera vilken användare som kan godkänna godkännandebegäran.

1. I listrutan **[!UICONTROL Category]** väljer du om du vill välja en användargrupp eller en enskild användare.

1. Välj sedan den specifika användargruppen eller användaren i listrutan **[!UICONTROL Option]**.

   Den valda användaren eller användargruppen ansvarar för att validera godkännandebegäran.

   ![](assets/policy_condition_2.png)

1. Om du vill lägga till fler villkor klickar du på **[!UICONTROL Add condition]** för att definiera ytterligare regler och väljer antingen **[!UICONTROL And]** eller **[!UICONTROL Or]** för att ange hur villkoren ska anslutas.

1. Klicka på **[!UICONTROL Save]** när din princip är fullständigt konfigurerad.

Du kan nu aktivera din godkännandeprincip för att tillämpa den.

## Aktivera och hantera godkännandepolicyer {#activate-policies}

1. Få åtkomst till din **[!UICONTROL Approval policy]**.

1. Klicka sedan på **[!UICONTROL Activate]** för att använda de konfigurerade villkoren i din miljö.

   >[!NOTE]
   >
   >När du har aktiverat profiler kan de inte redigeras. Om du vill ändra villkoren måste du först inaktivera principen.

   ![](assets/policy_activate_1.png)

1. Öppna de avancerade alternativen på menyn **[!UICONTROL Policy]** till **[!UICONTROL Edit]**, **[!UICONTROL Deactivate]** eller **[!UICONTROL Duplicate]** profilen efter behov.

   ![](assets/policy_activate_2.png)

