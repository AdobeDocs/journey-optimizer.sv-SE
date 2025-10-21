---
title: Exempel på Personalization-mallar
description: Exempel på Journey Optimizer Personalization
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 832b0bfa-ec74-4b1d-ad85-d4e4ea2f8863
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---

# E-post om förskrivningar av hälsoplaner {#plan-prescription}

En profil innehåller hälsoplaner och varje plan innehåller recept. Förskrivningarna har olika lägen, t.ex.&quot;ready&quot; (klar),&quot;revy&quot; eller&quot;hämtad&quot;.

I det här fallet vill vi skicka ett e-postmeddelande till varje profil, inklusive alla recept som är klara att hämtas eller återkallas. Klicka på varje flik nedan för mer information om syntaxen som ska användas för att implementera det här användningsexemplet.

>[!BEGINTABS]

>[!TAB Återgivet meddelande]

<p>Hej John Doe,</p>
<p>Här är de recept som antingen är klara för upphämtning eller har återkallats:</p>

**Hälsoplan A**

<ul>

<li>
      <strong>Förskrifts-ID:</strong> pres1<br>
      <strong>Namn:</strong> Medication A<br>
      <strong>Läge:</strong> klart
   </li>

<li>
      <strong>Förskrifts-ID:</strong> pres2<br>
      <strong>Namn:</strong> Medication B<br>
      <strong>Tillstånd:</strong> återkallelse
   </li>

</ul>

**Hälsoplan B**

<ul>

<li>
      <strong>Förskrifts-ID:</strong> pres4<br>
      <strong>Namn:</strong> Medication D<br>
      <strong>Läge:</strong> klart
   </li>

</ul>

>[!TAB HTML-mall]

```html
<p>Hi {{profile.person.firstName}} {{profile.person.lastName}},</p>
<p>Here are the prescriptions that are either ready for pick up or have been recalled:</p>
{{#each profile.plans as |plan|}}
<h3>{{plan.name}}</h3>
<ul>
   {{#each plan.prescriptions as |prescription|}}
   {%#if prescription.state = "ready" or prescription.state = "recall"%}
   <li>
      <strong>Prescription ID:</strong> {{prescription.prescription_id}}<br>
      <strong>Name:</strong> {{prescription.name}}<br>
      <strong>State:</strong> {{prescription.state}}
   </li>
   {%/if%}
   {{/each}}
</ul>
{{/each}}
```

>[!TAB Profildata]

```javascript
{
  "profile": {
    "person": {
      "firstName": "John",
      "lastName": "Doe"
    },
    "plans": [
      {
        "planId": "plan1",
        "name": "Health Plan A",
        "prescriptions": [
          {
            "prescription_id": "pres1",
            "name": "Medication A",
            "state": "ready"
          },
          {
            "prescription_id": "pres2",
            "name": "Medication B",
            "state": "recall"
          }
        ]
      },
      {
        "planId": "plan2",
        "name": "Health Plan B",
        "prescriptions": [
          {
            "prescription_id": "pres3",
            "name": "Medication C",
            "state": "picked up"
          },
          {
            "prescription_id": "pres4",
            "name": "Medication D",
            "state": "ready"
          }
        ]
      }
    ]
  }
}
```

>[!ENDTABS]
