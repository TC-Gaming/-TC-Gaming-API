# User Profile API

The endpoint for the user profile API is: `/citydriving/profile`

## API Index

We currently offer the following user profile APIs:

| API | Documentation |
| :--- | :--- |
| Get a User Profile | [View Docs](#get-a-user-profile) |
| Get a User's InSim UI Options | [View Docs](#get-a-users-insim-ui-options) |

---

## Get a User Profile

Access all of a CityDriving user's profile details and statistics.

**ENDPOINT:** `/citydriving/profile/get`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `username` | _{string}_ : A Live for Speed username |

#### Optional Parameters

This API can optionally return a stats object, an array of cars and/or and array of licenses. Any combination can be requested.

| Name | Expected Value |
| :--- | :--- |
| `stats` | _{number}_ : 0 &#124; 1 |
| `cars` | _{number}_ : 0 &#124; 1 |
| `licenses` | _{number}_ : 0 &#124; 1 |

#### Example

**REQUEST:** `?key=YOUR_KEY&username=mbutcher&stats=1&cars=1&licenses=1`

This request usually returns all cars and licenses owned by a user. This example only shows one of each for brevity.

**RESPONSE:**

```shell
GET https://api.tc-gaming.co.uk/citydriving/profile/get?key=YOUR_KEY&username=mbutcher&stats=1&cars=1&licenses=1
HTTP/1.1 200 OK
```
```json
{
  "id": 17,
  "username": "mbutcher",
  "isOnline": true,
  "nickname": "^1[TC]\u00bbPete\u00ab",
  "insimAdmin": false,
  "adminLevel": 1,
  "needsCopTraining": false,
  "money": 108291,
  "hasRadarWarner": true,
  "hasLocator": true,
  "hasWinch": true,
  "dateJoined": 1198269302,
  "dateLastSeen": 1502325692,
  "countryCode": "gb",
  "flag": "\/\/cdn.boardhost.com\/flags\/gb.png",
  "stats": {
      "sent_money": 27481094,
      "received_money": 27081385,
      "earned_refunds": 10160810,
      "paid_for_renting": 54425,
      "received_fines": 156920,
      "paid_fines": 10114736,
      "paid_radar_fines": 46048,
      "driven_distance": 223936390,
      "driving_money_plus": 1323732,
      "driving_money_minus": 873890,
      "crashes": 1134,
      "chases_won_robber": 244,
      "chases_lost_robber": 169,
      "chases_won_cop": 844,
      "chases_lost_cop": 168,
      "outran_cops": 565,
      "net_value": 545150,
      "gaming_time_total": 20255991,
      "gaming_time_cop": 5678183,
      "gaming_time_civil": 14577808,
      "cop_xp": 10055,
      "robber_xp": 11032,
      "rp_xp": 94
  },
  "licenses": [
    {
      "type": "cop",
      "name": "Cop License",
      "dateIssued": 1398100100,
      "issuedBy": "mbutcher",
      "validUntil": null,
      "suspendedUntil": null,
      "revoked": false,
      "expired": false,
      "suspended": false
    },
    ...
  ],
  "cars": [
    {
      "vin": "AAAFI",
      "type": "FXO",
      "odometerKm": 20929.747,
      "condition": 22.9
    },
    ...
  ]
}
```

---

## Get a User's InSim UI Options

Access a CityDriving user's `!setopt` InSim UI options.

**ENDPOINT:** `/citydriving/profile/getopts`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `username` | _{string}_ : A Live for Speed username |

#### Example

**REQUEST:** `?key=YOUR_KEY&username=mbutcher`

This API only returns the options which have been changed from the default setting using the `!setopt` command. Numbers refer to the LFS colour code of the chat message. This example shows the default values which would not normally be returned.

**RESPONSE:** 

```shell
GET https://api.tc-gaming.co.uk/citydriving/profile/getopts?key=YOUR_KEY&username=mbutcher
HTTP/1.1 200 OK
```
```json
{
  "tccol": 5,
  "rccol": 5,
  "cccol": 5,
  "lcol": 5,
  "ccol": 6,
  "xcol": 6
  "chcol": 3,
  "pmcol": 5,
  "requestcol": 5
  "force_mouse": 0,
  "show_speedlimit": 1,
  "chase_debug": 0
}
```