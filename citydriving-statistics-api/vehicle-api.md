# Vehicle API

The endpoint for the vehicle API is: `/citydriving/carinfo`

## API Index

We currently offer the following statistics APIs:

| API | Documentation |
| :--- | :--- |
| Car Information | [View Docs](#car-information) | 

---

## Car Information

The car information API lets you query the Vehicle ID Numbers (VINs) of all cars that have ever been built. You can use this API to retrieve more in-depth information about the cars from the [User Profile API](user-profile-api.md).

**ENDPOINT:** `/citydriving/carinfo`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `vin` | _{string}_ : 5 letter Vehicle ID Number eg. AAAAB |

#### Example

**REQUEST:** `?key=YOUR_KEY&vin=aaaab`

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/carinfo?key=YOUR_KEY&vin=aaaab
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 1,
        "vin": "AAAAB",
        "owner": "chucknorris",
        "type": "XFG",
        "dateBuilt": 1325267211,
        "datePurchase": 1325267211,
        "distanceKm": 7186.055,
        "isOnMarket": false,
        "numPreOwners": 1,
        "isWrecked": 0,
        "marketPrice": 0,
        "condition": 72.2
    }
]
```
