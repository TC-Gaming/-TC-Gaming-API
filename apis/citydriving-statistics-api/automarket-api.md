# AutoMarket API

The endpoint for the AutoMarket API is: `/citydriving/market`

## API Index

We currently offer the following AutoMarket APIs:

| API | Documentation |
| :--- | :--- |
| Get Current Listings | [View Docs](automarket-api.md#get-current-listings) |

## Get Current Listings

The AutoMarket API returns all available cars on the [CityDriving AutoMarket](https://world.city-driving.co.uk/?page=market) or all available cars of a certain type.

**ENDPOINT:** `/citydriving/market/getlist`

### Mandatory Parameters

Calling this API with no optional parameters will return all available cars on the AutoMarket.

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

### Optional Parameters

This API can optionally return listings of a certain type of car. To do so, add a `type` key with a three digit LFS car code \(See the [LFS Manual](https://en.lfsmanual.net/wiki/Cars) for abbreviations\). You can also optionally view the array of upgrades.

| Name | Expected Value |
| :--- | :--- |
| `type` | _{string}_ :  LFS car code eg. UF1 |
| `upgrades` | _{number}_ : 0 \| 1 |

### Examples

**REQUEST:** `?key=YOUR_KEY&type=uf1&upgrades=1`

This example request will return all available UF1s on the market. This example only returns one car for brevity.

**RESPONSE:**

```text
GET https://api.tc-gaming.co.uk/citydriving/market/getlist?key=YOUR_KEY&type=uf1&upgrades=1
HTTP/1.1 200 OK
```

```javascript
[
  {
    "vin": "AAJCX",
    "type": "UF1",
    "dateBuilt": 1345988079,
    "datePurchase": 1345988079,
    "onMarketSince": 1542888779,
    "condition": 98.5628,
    "wear": 1.4372,
    "damage": 0,
    "daysOnMarket": 31,
    "pre_owner_nickname": "^4k3nny^13000",
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
  },
  ...
]
```

