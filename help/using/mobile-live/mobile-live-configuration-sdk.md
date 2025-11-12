---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera aktivitetskanalen Live
description: Lär dig hur du konfigurerar din integrering med Adobe Experience Platform Mobile SDK
feature: Channel Configuration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# Live Activity-integrering med Adobe Experience Platform Mobile SDK {#mobile-live-config-sdk}

>[!BEGINSHADEBOX]

* [Kom igång med Live-aktivitet](get-started-mobile-live.md)
* [Konfiguration av aktiv aktivitet](mobile-live-configuration.md)
* **[Live Activity-integrering med Adobe Experience Platform Mobile SDK](mobile-live-configuration-sdk.md)**
* [Skapa en Live-aktivitet](create-mobile-live.md)
* [Vanliga frågor och svar](mobile-live-faq.md)
* [Rapport om aktiv aktivitetskampanj](../reports/campaign-global-report-cja-activity.md)


>[!ENDSHADEBOX]

Adobe Experience Platform Mobile SDK har inbyggt stöd för Apple Live-aktiviteter. På så sätt kan appen visa dynamiska uppdateringar i realtid direkt på låsskärmen och Dynamic Island utan att öppna appen.

1. [Importera nödvändiga moduler](#import)

   Importera följande moduler: **[!DNL AEPMessaging]**, **[!DNL AEPMessagingLiveActivity]**, **[!DNL ActivityKit]**.

1. [Definiera attribut](#attributes)

   Följ `LiveActivityAttributes`, ta med `LiveActivityData` och ett `ContentState`-attribut.

1. [Registrera Live-aktiviteter](#register)

   Använd `Messaging.registerLiveActivity()` efter SDK-initiering.

1. [Skapa widgetkonfiguration](#widget)

   Implementera `ActivityConfiguration` för både Lock Screen och Dynamic Island.

1. [Starta en Live-aktivitet lokalt (valfritt)](#local)

   Live-aktiviteter kan initieras via Journey Optimizer eller lokalt i programkoden.

1. [Lägg till stöd för felsökning (valfritt)](#debug)

   Implementera `LiveActivityAssuranceDebuggable` för Assurance.

Kontrollera att följande minimiversioner är installerade för att säkerställa korrekt konfiguration och kompatibilitet.

>[!BEGINSHADEBOX]

**Förutsättningar:**

* **iOS:**
   * **iOS16.1 eller senare**: Grundläggande funktioner för Live-aktivitet
   * **iOS 17.2+**: Stöd för push-to-start
   * **iOS 18+**: Stöd för sändningskanaler
* **Xcode:** 14.0 eller senare
* **Swift:** 5.7 eller senare
* **Beroenden:** AEPCore, AEPMessaging, AEPMessagingLiveActivity, ActivityKit

>[!ENDSHADEBOX]

## Steg 1: Importera nödvändiga moduler {#import}

För att komma igång måste du först importera följande moduler: **[!DNL AEPMessaging]**, **[!DNL AEPMessagingLiveActivity]**, **[!DNL ActivityKit]**.

```swift
import AEPMessaging
import AEPMessagingLiveActivity
import ActivityKit
```

## Steg 2: Definiera aktivitetsattribut {#attributes}

Skapa en struktur som följer protokollet `LiveActivityAttributes`. Detta definierar både statiska data och läget för dynamiskt innehåll för din Live-aktivitet.

Nyckelkomponenterna är:

* **`liveActivityData`** (krävs) som innehåller Adobe Experience Platform-specifika data.
   * För enskilda användare: Använd `LiveActivityData(liveActivityID: "unique-id")`
   * För sändning: Använd `LiveActivityData(channelID: "channel-id")`

* Statiska attribut, anpassade egenskaper som är specifika för ditt användningsfall, t.ex. `restaurantName`.

* **`ContentState`** som definierar dynamiska data som kan uppdateras under Live-aktivitetens livscykel. Den måste överensstämma med `Codable` och `Hashable`.

* `LiveActivityOrigin`-uppräkningen anger om en aktivitet initierades lokalt i appen eller via fjärråtkomst via ett push-to-start-meddelande, som stöds i iOS 17.2 och senare. Med det här värdet kan SDK skilja mellan lokalt initierade och fjärraktiverade Live-aktiviteter under datainsamling.

**Exempel**

```swift
@available(iOS 16.1, *)
struct FoodDeliveryLiveActivityAttributes: LiveActivityAttributes {
    // Mandatory: AEP Integration Data
    var liveActivityData: LiveActivityData
    
    // Static Attributes: Custom properties that do not change
    var restaurantName: String
    
    // Dynamic Content State: Data that can be updated
    struct ContentState: Codable, Hashable {
        var orderStatus: String
    }
}
```

```swift
@available(iOS 16.1, *)
public struct LiveActivityData: Codable {
    /// Unique identifier for broadcast Live activity channels
    public let channelID: String?
     
    /// Unique identifier for individual Live activities
    public let liveActivityID: String?
     
    /// Indicates local vs remote creation
    public let origin: LiveActivityOrigin?
     
    // Initializers
    public init(channelID: String)        // For broadcast Live activities
    public init(liveActivityID: String)   // For individual Live activities
}
```

Du kan även registrera flera Live-aktivitetstyper för din app:

```swift
if #available(iOS 16.1, *) {
    Messaging.registerLiveActivity(AirplaneTrackingAttributes.self)
    Messaging.registerLiveActivity(FoodDeliveryLiveActivityAttributes.self)
    Messaging.registerLiveActivity(GameScoreLiveActivityAttributes.self)
}
```

## Steg 3: Registrera Live-aktiviteter {#register}

Registrera dina Live-aktivitetstyper i din `AppDelegate` efter SDK-initiering, vilket gör att du kan:

* Aktiverar automatisk push-to-start-tokensamling (iOS 17.2+)
* Samlar in token för Live-aktivitetsuppdatering automatiskt
* Möjliggör livscykelhantering och händelsespårning

**Exempel på en live-aktivitet för matleveranser:**

```swift
if #available(iOS 16.1, *) {
    Messaging.registerLiveActivity(FoodDeliveryLiveActivityAttributes.self)
}
```

## Steg 4: Skapa Live-aktivitetswidgetar {#widgets}

Live-aktiviteter visas via widgetar, du måste skapa ett widgetpaket och en konfiguration:

**Exempel på en live-aktivitet för matleveranser:**

```swift
@main
struct FoodDeliveryWidgetBundle: WidgetBundle {
    var body: some Widget {
        FoodDeliveryLiveActivityWidget()
    }
}

@available(iOS 16.1, *)
struct FoodDeliveryLiveActivityWidget: Widget {
    var body: some WidgetConfiguration {
        ActivityConfiguration(for: FoodDeliveryLiveActivityAttributes.self) { context in
            // Lock Screen UI
            VStack {
                Text("Order from \(context.attributes.restaurantName)")
                Text("Status: \(context.state.orderStatus)") // possible status may include "Ordered", "Order accepted", "Preparing", "On the Way","Delivered"
            }
        } dynamicIsland: { context in
            // Dynamic Island UI
            DynamicIsland {
                // Expanded UI
            } compactLeading: {
                // Compact leading UI
            } compactTrailing: {
                // Compact trailing UI
            } minimal: {
                // Minimal UI
            }
        }
    }
}
```

## Steg 5: Starta en Live-aktivitet lokalt (valfritt) {#local}

Journey Optimizer kan fjärrstarta Live-aktiviteter, men du kan också starta dem lokalt:

**Exempel på en live-aktivitet för matleveranser:**

```swift
let attributes = FoodDeliveryLiveActivityAttributes(
    liveActivityData: LiveActivityData(liveActivityID: "order123"),
    restaurantName: "Pizza Palace"
)

let contentState = FoodDeliveryLiveActivityAttributes.ContentState(
    orderStatus: "Ordered"
)

let activity = try Activity<FoodDeliveryLiveActivityAttributes>.request(
    attributes: attributes,
    contentState: contentState,
    pushType: .token
)
```

## Steg 6: Lägg till stöd för felsökning (valfritt) {#debug}

Om det behövs kan du felsöka Live-aktivitetsscheman i Adobe Assurance:

**Exempel på en live-aktivitet för matleveranser:**

```swift
@available(iOS 16.1, *)
extension FoodDeliveryLiveActivityAttributes: LiveActivityAssuranceDebuggable {
    static func getDebugInfo() -> (attributes: FoodDeliveryLiveActivityAttributes, state: ContentState) {
        return (
            FoodDeliveryLiveActivityAttributes(
                liveActivityData: LiveActivityData(liveActivityID: "debug-order-123"),
                restaurantName: "Debug Restaurant"
            ),
            ContentState(orderStatus: "Ordered")
        )
    }
}
```


