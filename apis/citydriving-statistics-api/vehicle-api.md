# Vehicle API

The endpoint for the vehicle API is: `/citydriving/carinfo`

## API Index

We currently offer the following statistics APIs:

| API | Documentation |
| :--- | :--- |
| Car Information | [View Docs](vehicle-api.md#car-information) |

## Car Information

The car information API lets you query the Vehicle ID Numbers \(VINs\) of all cars that have ever been built. You can use this API to retrieve more in-depth information about the cars from the [User Profile API](user-profile-api.md).

**ENDPOINT:** `/citydriving/carinfo`

### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `vin` | _{string}_ : 5 letter Vehicle ID Number eg. AAAAB |

### Optional Parameters <a id="optional-parameters"></a>

You can optionally request to see an array of previous owners and/or an array of upgrades on that car.

| Name | Expected Value |
| :--- | :--- |
| `preowners` | _{number}_ : 0 \| 1 |
| `upgrades` | _{number}_ : 0 \| 1 |

### Example

**REQUEST:** `?key=YOUR_KEY&vin=aaaab&preowners=1&upgrades=1`

**RESPONSE:**

```text
GET https://api.tc-gaming.co.uk/citydriving/carinfo?key=YOUR_KEY&vin=aaaab&preowners=1&upgrades=1
HTTP/1.1 200 OK
```

```javascript
{
  "id": 42389,
  "vin": "ACKSJ",
  "owner": "chucknorris",
  "nickname": "^7*^1\u2039^7:Chuck\u203a",
  "idOwner": 4,
  "type": "RB4",
  "dateBuilt": 1509119202,
  "datePurchase": 0,
  "odometerKm": 1885.525,
  "isOnMarket": false,
  "numPreowners": 0,
  "isWrecked": false,
  "marketPrice": 0,
  "condition": 86.2358,
  "wear": 13.7343,
  "damage": 0.0199,
  "preOwners": [
    {
      "buyer": "chucknorris",
      "buyerId": "4",
      "datePurchase": 1509119202,
      "odometerKm": 0
    },
    ...
  ],
  "upgrades": [
    {
      "id": 113172,
      "type": "ramp",
      "condition": 0.9988,
      "value": 2497
    },
    {
      "id": 113171,
      "type": "winch",
      "condition": 0.999,
      "value": 4995
    },
    {
      "id": 113110,
      "type": "radar_warner",
      "condition": 1,
      "value": 2500
    }
  ]
}
```

