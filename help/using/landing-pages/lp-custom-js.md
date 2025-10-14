---
solution: Journey Optimizer
product: journey optimizer
title: Använda anpassad JavaScript på en landningssida
description: Lär dig hur du utformar innehållet på en landningssida i Journey Optimizer
feature: Landing Pages
topic: Content Management
role: Developer
level: Experienced
keywords: landning, landningssida, javascript, kod
exl-id: 2a7ebead-5f09-4ea5-8f00-8b5625963290
source-git-commit: 8579acfa881f29ef3947f6597dc11d4c740c3d68
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 1%

---

# Använda anpassad JavaScript på en landningssida {#lp-custom-js}

Du kan definiera innehållet på landningssidan med anpassade JavaScript. Om du till exempel behöver utföra avancerad formatering eller om du vill lägga till anpassade beteenden på dina landningssidor, kan du skapa egna kontroller och köra dem i [!DNL Journey Optimizer].

## Infoga JavaScript-kod på en landningssida

Om du vill infoga anpassad JavaScript i startsidans innehåll kan du antingen göra följande:

* Importera befintligt HTML-innehåll när du börjar skapa ditt innehåll och markera filen som innehåller din anpassade JavaScript-kod. Lär dig hur du importerar innehåll [&#x200B; i det här avsnittet](../email/existing-content.md).

* Utforma landningssidan från grunden eller från en sparad mall. Dra och släpp innehållskomponenten **[!UICONTROL HTML]** på arbetsytan och visa källkoden för att lägga till JavaScript i komponenten. Lär dig hur du använder komponenten HTML i [det här avsnittet](../email/content-components.md#HTML). <!--You can also simply switch the whole landing page content to code view and enter or paste your JavaScript code.-->

  ![](assets/lp_designer-html-component.png)

* Ange eller klistra in JavaScript-kod direkt i innehållsdesignern. Lär dig hur du kodar ditt eget innehåll [i det här avsnittet](../email/code-content.md).

>[!NOTE]
>
>För närvarande kan du inte visa JavaScript i aktion när [förhandsgranskar landningssidan](create-lp.md#test-landing-page).

För att landningssidan ska visas korrekt använder du följande syntax enligt beskrivningen i avsnitten nedan.

## Kodinitiering

Om du vill initiera din JavaScript-kod måste du använda händelsen `lpRuntimeReady`. Den här händelsen utlöses när biblioteket har initierats. Återanropet körs med objektet `lpRuntime` för att visa biblioteksmetoden och krokarna.

`LpRuntime` står för&quot;Landing page Runtime&quot;. Det här objektet är huvudidentifieraren för biblioteket. Den visar kopplingar, formuläröverföringsmetoder och andra verktygsmetoder som kan användas i anpassade JavaScript.

**Exempel:**

```
if(window.lpRuntime){
    init(window.lpRuntime);
}else{
    window.addEventListener('lpRuntimeReady',function(e){
        init(e.detail);
    });
}
 
function init(lpRuntime){
    // Enter custom JavaScript here using methods from lpRuntime.
}
```

## Hookar

Med kopplingar kan du bifoga en metod under formulärskickningens livscykel. Du kan till exempel använda kopplingar för att utföra någon formulärvalidering innan formuläret skickas.

Här är de krokar du kan använda:

| Namn | Beskrivning |
|--- |--- |
| addBeforeSubmitHook | Anpassad krok som ska anropas innan formuläret skickas. Returnerar true om du vill fortsätta skicka, annars returneras false om du vill blockera överföringen. |
| addOnFailureHook | Anpassad krok som ska anropas vid misslyckad formuläröverföring. |
| addOnSuccessHook | Anpassad krok som anropas när formuläret skickas. |

**Exempel:**

```
//LpRuntime hooks
lpRuntime.hooks.addBeforeSubmitHook(function(){
    // Add your validation logic here.
});
```

## Skräddarsy formulärinlämning

De metoder som anges nedan används för att skicka anpassade formulär.

>[!NOTE]
>
>Eftersom formuläröverföringen hanteras av anpassad JavaScript måste standardöverföringen inaktiveras uttryckligen genom att den globala variabeln `disableDefaultFormSubmission` anges till `true`.

| Namn | Beskrivning |
|--- |--- |
| submitForm | Den här metoden skickar formuläret och hanterar flödet efter överföringen. |
| submitFormPartial | Den här metoden skickar även formuläret, men hoppar över flödet efter inskickandet. Om du till exempel har konfigurerat omdirigering till slutförd sidskickning kommer denna omdirigering inte att ske om formuläret skickas delvis. |

**Exempel:**

```
//LpRuntime methods
window.disableDefaultFormSubmission = true        // Flag to disable the default submission flow.
 
lpRuntime.submitForm(formSubmissionData);         // This will trigger the default form submission handling like redirecting to error or success page.
  
lpRuntime.submitFormPartial(formSubmissionData,{   // This will not trigger the default submission handling.
    beforeSubmit : callback,
    onFailure : failureCallback,                   // Custom onFailureCallback - will be used in partial submission of form.
    onSuccess : successCallback                    // Custom onSuccessCallback - will be used in partial submission of form.
})
```

## Verktygsfunktion

| Namn | Beskrivning |
|--- |--- |
| getFormData | Den här metoden kan användas för att hämta `formData` i form av ett JSON-objekt. Det här objektet kan skickas till `submitForm` för att skicka formulär. |

**Exempel:**

```
let formData = lpRuntime.getFormData();                           // Method to generate formdata
 
lpRuntime.submitForm(formData);
```

## Användningsfall

### Användningsfall 1: Lägga till validering före inlämning av formulär

```
<html>
<body>
// Enter HTML body here.
  
<script>
        if(window.lpRuntime){
          console.log('got runtime',lpRuntime);
          init(window.lpRuntime);
        }else{
          window.addEventListener('lpRuntimeReady',function(e){
            init(window.lpRuntime);
          });
        }
        
  
      // Here validate the function is checking if the checkbox is selected. This method should return true if you want form submission.
      function validateForm(){
        return document.querySelector('.spectrum-Checkbox-input').checked;
      }    
  
      function init(lpRuntime){
          lpRuntime.hooks.addBeforeSubmitHook(function(){
              return validateForm(); // This method should return true if you want to proceed with submission.
          })
      }
  
</script>  
  
</body>
</html>
```

### Användningsfall 2: Delvis inskickande av formulär

Du har till exempel ett formulär med flera kryssrutor på sidan. När du markerar en kryssruta vill du att dessa data ska sparas i backend-objektet utan att användaren behöver vänta på att han/hon ska klicka på skicka-knappen.

```
<html>
<body>
    <form>
        <input type='checkbox' value="1" name="name1"/>
        <input type='checkbox' value="2" name="name2"/>
        <input type='checkbox' value="3" name="name3"/>
        <input type='checkbox' value="4" name="name4"/>
    </form>
  
<script>
      window.disableDefaultFormSubmission=true;
 
      window.addEventListener('lpRuntimeReady',function(e){        
        init(e.detail)
      }
 
     function init(lpRuntime){
        window.getElementByTagName('input').addEventListener('change',function(e){
            let formData = lpRuntime.getFormData();
            lpRuntime.submitFormPartial(formData);
        })
      }
    </script>
  
</body>
</html>
```

### Användningsfall 3: Anpassade analystaggar

Med JavaScript kan du lägga till avlyssnare för indatafält och koppla en anpassad anropsutlösare för analys.

```
<html>
<body>
    <form>
        <input type='checkbox' value="1" name="name1"/>
        <input type='checkbox' value="2" name="name2"/>
        <input type='checkbox' value="3" name="name3"/>
        <input type='checkbox' value="4" name="name4"/>
    </form>
  
<script>
      window.disableDefaultFormSubmission=false;  
 
      window.addEventListener('lpRuntimeReady',function(e){        
        init(e.detail)
      }
 
     function init(lpRuntime){
         window.getElementByTagName('input').addEventListener('change',function(e){
            //trigger analytics events
        })
      }
        
    </script>
  
</body>
</html>
```

### Användningsfall 4: Dynamisk blankett

```
<html>
<body>
    <form>
        <input type='checkbox' value="1" name="name1"/>
        <div class="hiddenInput hidden">
            <input type='text' name="name2"/>
        </div>
    </form>
  
<script>
      window.disableDefaultFormSubmission=false;     
 
      window.addEventListener('lpRuntimeReady',function(e){        
        init(e.detail)
      }
 
      function init(lpRuntime){
        window.getElementByTagName('input').addEventListener('change',function(e){
            document.querySelector('.hiddenInput').toggleClass('hidden');
        })
      }
        
    </script>
  
</body>
</html>
```
