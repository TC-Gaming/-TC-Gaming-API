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

### Example

**REQUEST:** `?key=YOUR_KEY&vin=aaaab`

**RESPONSE:**

```text
GET https://api.tc-gaming.co.uk/citydriving/carinfo?key=YOUR_KEY&vin=aaaab
HTTP/1.1 200 OK
```

```javascript
[
    {
        "id": 1,
        "vin": "AAAAB",
        "owner": "chucknorris",
        "nickname": "^7*^1\u2039^7:Chuck\u203a",
        "idOwner": 4,
        "type": "XFG",
        "dateBuilt": 1325267211,
        "datePurchase": 1325267211,
        "odometerKm": 7819.045,
        "isOnMarket": false,
        "numPreowners": 1,
        "isWrecked": false,
        "marketPrice": 0,
        "condition": 67.1463,
        "wear": 32.8437,
        "damage": 0
    }
]
```

