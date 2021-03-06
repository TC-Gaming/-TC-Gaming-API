# User Profile API

The endpoint for the user profile API is: `/citydriving/profile`

## API Index

We currently offer the following user profile APIs:

| API | Documentation |
| :--- | :--- |
| Get a User Profile | [View Docs](user-profile-api.md#get-a-user-profile) |
| Get a User's InSim UI Options | [View Docs](user-profile-api.md#get-a-users-insim-ui-options) |

## Get a User Profile

Access all of a CityDriving user's profile details and statistics.

**ENDPOINT:** `/citydriving/profile/get`

### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `username` | _{string}_ : A Live for Speed username |

### Optional Parameters

This API can optionally return a stats object, an array of cars \(with or without their upgrades\), an array of licences and/or and array of properties. Any combination can be requested.

| Name | Expected Value |
| :--- | :--- |
| `stats` | _{number}_ : 0 \| 1 |
| `cars` | _{number}_ : 0 \| 1 |
| `licenses` | _{number}_ : 0 \| 1 |
| `upgrades` | _{number}_ : 0 \| 1 |
| `properties` | _{number}_ : 0 \| 1 |

### Example

**REQUEST:** 

```text
?key=YOUR_KEY&username=chucknorris&stats=1&cars=1&licenses=1&upgrades=1&properties=1
```

This request usually returns all cars, licenses, properties and upgrades owned by a user. This example only shows one of each type for brevity.

**RESPONSE:**

```text
GET https://api.tc-gaming.co.uk/citydriving/profile/get?key=YOUR_KEY&username=chucknorris&stats=1&cars=1&licenses=1&upgrades=1&properties=1
HTTP/1.1 200 OK
```

```javascript
{
  "id": 4,
  "username": "chucknorris",
  "isOnline": true,
  "nickname": "^7\u2039Chuck\u203a",
  "insimAdmin": true,
  "adminLevel": 1,
  "needsCopTraining": false,
  "money": 1586937,
  "dateJoined": 1198268290,
  "dateLastSeen": 1504975483,
  "countryCode": "de",
  "flag": "\/\/cdn.boardhost.com\/flags\/de.png",
  "stats": {
    "sent_money": 423932,
    "received_money": 783590,
    "earned_refunds": 13960,
    "paid_for_renting": 41843,
    "received_fines": 1360,
    "paid_fines": 134403,
    "paid_radar_fines": 8326,
    "driven_distance": 223310815.7382,
    "driving_money_plus": 1644846,
    "driving_money_minus": 153715,
    "paid_donation": 965,
    "received_donation": 187,
    "paid_compensation": 270,
    "received_compensation": 620,
    "crashes": 1178,
    "chases_won_robber": 18,
    "chases_lost_robber": 88,
    "chases_won_cop": 5,
    "chases_lost_cop": 15,
    "outran_cops": 28,
    "net_value": 1863810,
    "gaming_time_total": 30899940,
    "gaming_time_cop": 166878,
    "gaming_time_civil": 30733062,
    "gaming_time_tow": 2124,
    "gaming_time_chasing": 179,
    "gaming_time_chased": 486,
    "driven_distance_cop": 3206.2881,
    "driven_distance_civil": 425272.3399,
    "driven_distance_tow": 2595.9957,
    "driven_distance_offroad": 115153.1259,
    "driven_distance_chasing": 3187.3062,
    "driven_distance_chased": 14601.36,
    "driven_distance_sos": 2246.9407,
    "cop_xp": 48,
    "robber_xp": 1427,
    "rp_xp": 6356,
    "gumball_distance": 0,
    "gumball_time": 0,
    "winch_used": 1,
    "ramps_placed": 1,
    "sos_called": 4,
    "sos_responded": 1
  },
  "licenses": [
    {
      "type": "admin",
      "name": "Server Administrator",
      "dateIssued": 1395919556,
      "issuedBy": 0,
      "validUntil": 0,
      "suspendedUntil": 0,
      "revoked": false,
      "expired": false,
      "suspended": false
    },
    ...
  ],
  "properties": [
    {
      "id": 13,
      "type": "garage",
      "condition": 1,
      "value": 0
    },
    {
      "id": 11,
      "type": "locator",
      "condition": 1,
      "value": 10000
    },
    ...
  ],
  "cars": [
    {
      "vin": "AAAAB",
      "type": "XFG",
      "odometerKm": 7819.045,
      "condition": 67.1463,
      "wear": 32.8437,
      "damage": 0,
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
}
```

## Get a User's InSim UI Options

Access a CityDriving user's `!setopt` InSim UI options.

**ENDPOINT:** `/citydriving/profile/getopts`

### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `username` | _{string}_ : A Live for Speed username |

### Example

**REQUEST:** `?key=YOUR_KEY&username=mbutcher`

This API only returns the options which have been changed from the default setting using the `!setopt` command. Numbers refer to the LFS colour code of the chat message. This example shows the default values which would not normally be returned.

**RESPONSE:**

```text
GET https://api.tc-gaming.co.uk/citydriving/profile/getopts?key=YOUR_KEY&username=mbutcher
HTTP/1.1 200 OK
```

```javascript
{
"chase_debug": "0",
"force_mouse": "0",
"hidead": "7817d923f3307c27bc5b02cbcd8c748d",
"loccol": "7",
"locsize": "5",
"money": "session",
"mph": "0",
"pri_mrt_civ": "ACUFU",
"pri_uf1_civ": "ACTUJ",
"pri_uf1_cop": "ACTUJ",
"pri_uf1_med": "ACTUJ",
"pri_uf1_res": "ACTUJ",
"spawn_location": "cruise",
"theme": "chucks"
}
```

