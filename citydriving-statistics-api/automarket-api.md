# AutoMarket API

The endpoint for the AutoMarket API is: `/citydriving/market`

| API | Documentation |
| :--- | :--- |
| Get Current Listings | [View Docs](#get-current-listings) |

## Get Current Listings

The AutoMarket API returns all available cars on the [CityDriving AutoMarket](https://world.city-driving.co.uk/?page=market) or all available cars of a certain type.

**ENDPOINT:** `/citydriving/market/getlist`

#### Mandatory Parameters

Calling this API with no optional parameters will return all available cars on the AutoMarket.

| Name | Expected Value |
| :--- | :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

This API can optionally return listings of a certain type of car. To do so, add a `type` key with a three digit LFS car code (See the [LFS Manual](https://en.lfsmanual.net/wiki/Cars) for abbreviations). 

| Name | Expected Value |
| :--- | :--- | :--- |
| `type` | _{string}_ :  LFS car code eg. UF1 |

#### Examples

**REQUEST:** `?key=YOUR_KEY&type=uf1`

This example request will return all available UF1s on the market. This example only returns one car for brevity.

**RESPONSE:**
```shell
GET https://api.tc-gaming.co.uk/citydriving/market/getlist?key=YOUR_KEY&type=uf1
HTTP/1.1 200 OK
```
```json
[
    {
        "vin": "AAEXW",
        "type": "UF1",
        "dateBuilt": "1332041585",
        "datePurchase": "1332041585",
        "onMarketSince": "1501386141",
        "condition": "71.9",
        "daysOnMarket": "23",
        "pre_owner_nickname": "alsulaiti"
    },
    ...
]
```