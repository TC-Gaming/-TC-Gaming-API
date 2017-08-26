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
  "isOnline": false,
  "nickname": "^1[TC]\u00bbPete\u00ab",
  "insimAdmin": false,
  "adminLevel": 1,
  "needsCopTraining": false,
  "money": 109169,
  "hasRadarWarner": true,
  "hasLocator": true,
  "hasWinch": true,
  "dateJoined": 1198269302,
  "dateLastSeen": 1490382337,
  "countryCode": "gb",
  "flag": "\/\/cdn.boardhost.com\/flags\/gb.png",
  "stats": {
    "sentMoney": 26671545,
    "receivedMoney": 26278208,
    "earnedRefunds": 10160810,
    "paidForRenting": 54425,
    "receivedFines": 153576,
    "paidFines": 10110559,
    "paidRadarFines": 43888,
    "drivenDistance": 216882511,
    "timeAsCop": 5631516,
    "timeAsRobber": 14071504,
    "earnedByDriving": 1252259,
    "lostByDriving": 787973,
    "chasesWonAsRobber": 236,
    "chasesLostAsRobber": 159,
    "chasesWonAsCop": 823,
    "chasesLostAsCop": 158,
    "copXp": 8267,
    "robberXp": 8352,
    "civilianXp": 0,
    "towXp": 0,
    "medXp": 94,
    "outranCops": 542,
    "netValue": 563068,
    "gumballDistance": null,
    "gumballTime": null
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