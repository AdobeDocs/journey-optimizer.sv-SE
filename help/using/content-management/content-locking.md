---
solution: Journey Optimizer
product: journey optimizer
title: Lås innehåll i e-postmallar
description: Lär dig hur du låser innehåll i e-postmallar.
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: 38aaa3005e72a8300cef0e28a6fecd9f5d06c1f1
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 0%

---

# Lås innehåll i e-postmallar {#lock-content-email-templates}

>[!CONTEXTUALHELP]
>id="ajo_locking_governance"
>title="Styrning"
>abstract="Aktivera styrning om du vill låsa innehållet i mallen, antingen genom att låsa hela mallen eller specifika strukturer och komponenter. På så sätt kan ni förhindra oavsiktliga redigeringar och borttagningar, vilket ger er bättre kontroll över mallanpassning och förbättrar effektiviteten och tillförlitligheten i era e-postkampanjer."

>[!CONTEXTUALHELP]
>id="ajo_locking_mode"
>title="Läge"
>abstract="Välj önskat låsläge för mallen. **Med innehållslås** kan du låsa specifika avsnitt av innehåll i mallen. Med **Skrivskyddad** kan du låsa hela innehållet i mallen och förhindra ändringar."

>[!CONTEXTUALHELP]
>id="ajo_locking_content_addition"
>title="Aktivera tillägg av innehåll"
>abstract="Växla till det här alternativet om du vill definiera ytterligare hur användare kan interagera med mallen. Välj **Tillåt struktur- och innehållstillägg** om du vill tillåta användare att lägga till strukturer mellan befintliga strukturer och lägga till innehållskomponenter eller fragment inom redigerbara strukturer. **Med** kan du lägga till innehållskomponenter eller fragment i redigerbara strukturer utan att kunna lägga till eller duplicera strukturer."

>[!CONTEXTUALHELP]
>id="ajo_email_locking_activated"
>title="Styrning har aktiverats"
>abstract="Lås innehåll aktiveras och kan förhindra att du gör ändringar."

>[!CONTEXTUALHELP]
>id="ajo_email_locking_read_only"
>title="Skrivskyddad"
>abstract="Det här innehållet är skrivskyddat och kan inte ändras."

Med Journey Optimizer kan du låsa innehåll i e-postmallar, antingen genom att låsa hela mallen eller specifika strukturer och komponenter. Detta gör att du kan förhindra oavsiktliga redigeringar eller borttagningar, vilket ger dig större kontroll över mallanpassningen och förbättrar effektiviteten och tillförlitligheten i dina e-postkampanjer.

>[!AVAILABILITY]
>
>Användare med behörighet att skapa innehållsmallar kan aktivera innehållslåsning.

Låsning av innehåll kan tillämpas antingen på **strukturnivå** eller på **komponentnivå**. Här är de huvudprinciper som gäller på struktur- och komponentnivå vid låsning av innehåll i mallen.

* När en struktur är låst:

   * Allt innehåll i strukturen är också låst som standard.
   * Inget innehåll kan läggas till i strukturen.
   * Som standard kan du inte ta bort strukturen. Du kan åsidosätta den här begränsningen genom att aktivera alternativet&quot;Tillåt borttagning&quot;.
   * Enskilda innehållskomponenter i den låsta strukturen kan anges som redigerbara.

* När en struktur är redigerbar (strukturen är inte låst):

   * Enskilda innehållskomponenter kan låsas inuti den strukturen.
   * Som standard kan du inte ta bort en komponent om den är låst eller om&quot;Endast redigerbart innehållslås&quot; är markerat. Du kan åsidosätta den här begränsningen genom att aktivera alternativet&quot;Tillåt borttagning&quot;.

## Lås en e-postmall {#define}

### Aktivera låsning av innehåll {#enable}

Du kan aktivera innehållslås för en e-postmall direkt i e-postmallen Designer, oavsett om du skapar en ny mall eller redigerar en befintlig mall. Följ de här stegen:

1. Öppna eller skapa en e-postmall och gå till redigeringsskärmen i e-post-Designer.

1. Aktivera alternativet **[!UICONTROL Governance]** i rutan **[!UICONTROL Body]** till höger.

1. Välj önskat låsläge för mallen i listrutan **[!UICONTROL Mode]**:

   * **[!UICONTROL Content locking]**: Lås specifika innehållsavsnitt i mallen. Som standard går det att redigera alla strukturer och komponenter. Du kan sedan selektivt låsa enskilda element.
   * **[!UICONTROL Read only]**: Lås hela innehållet i mallen och förhindra ändringar.

   ![](assets/template-lock-enable.png)

1. Om du har valt läget **[!UICONTROL Content locking]** kan du ytterligare definiera hur användare kan interagera med mallen. Växla på alternativet **[!UICONTROL Enable content edition]** och välj något av följande:

   * **[!UICONTROL Allow structure & content addition]**: Användare kan lägga till strukturer mellan befintliga strukturer och lägga till innehållskomponenter eller fragment inom redigerbara strukturer.

   * **[!UICONTROL Allow content addition only]**: Användare kan lägga till innehållskomponenter eller fragment i redigerbara strukturer, men de kan inte lägga till eller duplicera strukturer.

1. När du har valt låsläget kan du definiera vilka strukturer och/eller komponenter som ska låsas om du har valt **[!UICONTROL Content locking]**-läget:

   * [Lär dig låsa strukturer](#lock-structures)
   * [Lär dig låsa komponenter](#lock-components)

   Om du valde läget **[!UICONTROL Read only]** kan du fortsätta med att slutföra och spara mallen som vanligt.

Du kan när som helst justera **[!UICONTROL Governance]**-inställningarna när du utformar mallen genom att välja malltexten. Du gör detta genom att klicka på länken **[!UICONTROL Body]** i navigeringslisten högst upp i det högra fönstret.

![](assets/template-lock-body.png)

### Lås strukturer {#lock-structures}

>[!CONTEXTUALHELP]
>id="ajo_locking_structure"
>title="Låsning av innehåll i strukturen"
>abstract="Om du vill låsa strukturen i mallen väljer du **Låst** i listrutan **Lås typ**. Som standard kan användare inte ta bort låsta strukturer. Du kan åsidosätta den här begränsningen genom att aktivera alternativet **[!UICONTROL Allow delete]**."

Så här låser du en struktur i mallen:

1. Välj den struktur som du vill låsa.

1. Välj **[!UICONTROL Locked]** i listrutan **[!UICONTROL Lock type]**.

   ![](assets/template-lock-structure.png)

   >[!NOTE]
   >
   >Som standard kan användare inte ta bort låsta strukturer. Du kan åsidosätta den här begränsningen genom att aktivera alternativet **[!UICONTROL Allow delete]**.

När du har låst en struktur kan inga ytterligare innehållskomponenter eller fragment dupliceras eller läggas till inuti den. Alla komponenter i en låst struktur är också låsta som standard. Så här gör du en komponent redigerbar i en låst struktur:

1. Markera den komponent som du vill låsa upp.

1. Växla på alternativet **[!UICONTROL Use specific locking]**.

1. Välj **[!UICONTROL Editable]** i listrutan **[!UICONTROL Lock type]**. Välj **[!UICONTROL Editable content only]** om du vill tillåta redigering av innehåll när du låser format. [Lär dig att låsa komponenter](#lock-components)

   ![](assets/template-lock-editable-component.png)

### Lås komponenter {#lock-components}

>[!CONTEXTUALHELP]
>id="ajo_locking_component"
>title="Använda specifik låsning i komponent"
>abstract="Om du vill låsa komponenten i mallen aktiverar du alternativet **Använd specifik låsning**. I listrutan **[!UICONTROL Lock type]** väljer du önskat låsalternativ: **Endast redigerbart innehållslås** gör att du kan låsa komponentens format men tillåter innehållsredigering, medan **Låst** helt låser både komponentens innehåll och stilar."

Så här låser du en specifik komponent i en struktur:

1. Markera komponenten och aktivera alternativet **[!UICONTROL Use specific locking]** i den högra rutan.

1. Välj önskat låsalternativ i listrutan **[!UICONTROL Lock type]**:

   ![](assets/template-lock-component.png)

   * **[!UICONTROL Editable content lock only]**: Lås komponentens format men tillåter innehållsredigering.
   * **[!UICONTROL Locked]**: Lås både komponentens innehåll och format fullständigt.

   >[!NOTE]
   >
   >Låstypen **[!UICONTROL Editable]** gör att användare kan redigera en komponent, även i en låst struktur. [Lär dig att låsa strukturer](#lock-structures)

1. Som standard kan användare inte ta bort låsta komponenter. Du kan aktivera borttagning genom att aktivera alternativet **[!UICONTROL Allow delete]**.

### Identifiera låst innehåll {#identify}

Använd **[!UICONTROL Navigation tree]** på den vänstra menyn för att enkelt identifiera låsta strukturer och komponenter i mallen. Den här menyn innehåller en visuell översikt över alla mallelement. Låsta objekt markeras med en låsikon och redigerbara objekt med en pennikon.

I exemplet nedan är styrning aktiverat för mallbrödtexten. *Struktur 2* är låst med *komponent 1* redigerbar, medan *struktur 3* är helt låst.

![](assets/template-lock-navigation.png)

## Använda mallar med låst innehåll {#use}

>[!CONTEXTUALHELP]
>id="ajo_email_editable_areas"
>title="Markera redigerbara områden"
>abstract="Beroende på vilken typ av låsning som används på mallen kan du utföra olika åtgärder på mallens strukturer och komponenter. Om du snabbt vill identifiera alla redigerbara områden i mallen aktiverar du alternativet **[!UICONTROL Highlight editable areas]**."

När du använder en mall med låst innehåll visas meddelandet **[!UICONTROL Governance enabled]** i den högra rutan.

Beroende på vilken typ av låsning som används för mallen kan du utföra olika åtgärder för mallens strukturer och komponenter. Om du snabbt vill identifiera alla redigerbara områden i mallen aktiverar du alternativet **[!UICONTROL Highlight editable areas]**.

I mallen nedan är till exempel alla områden redigerbara, förutom den översta bilden som har låsts, vilket innebär att du inte kan redigera eller ta bort den.

![](assets/template-lock-highlight.png)

Detaljerad information om olika typer av låsning som kan användas finns i följande avsnitt:

* [Lås strukturer](#lock-structures)
* [Lås komponenter](#lock-components)

Här är några exempel på e-postutgåvan och den tillhörande konfigurationen för låsning av innehåll som har konfigurerats:


| Typ av låsning av innehåll | Mallkonfiguration | E-postversion |
| ------- | ------- | ------- |
| Skrivskyddad innehållsmall | ![](assets/locking-sample-read-only-conf.png){zoomable="yes"} | ![](assets/locking-sample-read-only.png){zoomable="yes"} |
| Det går att redigera allt innehåll, men användarna kan inte lägga till någon struktur eller komponent | ![](assets/locking-sample-no-addition-conf.png){zoomable="yes"} | ![](assets/locking-sample-no-addition.png){zoomable="yes"} |
| Låst struktur som inte kan tas bort | ![](assets/locking-sample-structure-locked-conf.png){zoomable="yes"} | ![](assets/locking-sample-structure-locked.png){zoomable="yes"} |
| Komponent med låsta format som inte kan tas bort. Användarna kan bara ändra innehållet. | ![](assets/locking-sample-content-only-conf.png){zoomable="yes"} | ![](assets/locking-sample-content-only.png){zoomable="yes"} |
| Redigerbar komponent i en låst struktur. | ![](assets/locking-sample-editable-component-conf.png){zoomable="yes"} | ![](assets/locking-sample-editable-component.png){zoomable="yes"} |
