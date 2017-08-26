# Statistics API

The endpoint for the statistics API is: `/citydriving/stats`

## API Index

We currently offer the following statistics APIs:

| API | Documentation |
| :--- | :--- |
| Users Online | [View Docs](#users-online) |
| Users Online by Server | [View Docs](#users-online-by-server) |
| Top Distance | [View Docs](#top-distance) |
| Top Money | [View Docs](#top-money) |
| Top Wealth | [View Docs](#top-wealth) |
| Cop Experience | [View Docs](#cop-experience) |
| Robber Experience | [View Docs](#robber-experience) |
| Roleplay Points | [View Docs](#roleplay-points) |
| Last Tickets | [View Docs](#last-tickets) |
| Top Crashers | [View Docs](#top-crashers) |
| Newest Players | [View Docs](#newest-players) |
| Badges & Licenses | [View Docs](#badges-licenses) |
| Training Team Members | [View Docs](#training-team-members)  |
| [TC] CityDriving Members | [View Docs](#citydriving-members) |
| [TC] CityDriving Admins by Level | [View Docs](#citydriving-admins-by-level) |
| [TC] Racing Members | [View Docs](#racing-members) |

## API-Wide Optional Parameters

All statistics API requests default to 20 rows. Certain applications may require more rows or a range of rows. For this reason all statistics API requests can utilise the `range` and `skip` parameters.

| Name | Expected Value | Default Value |
| :--- | :--- | :--- |
| `rows` | _{integer}_ : Number of rows to request | 20 |
| `skip` | _{integer}_ : Number of rows to skip/offset | - |

---

## Users Online

The users online API gives you basic details of all users who are online on a [TC] CityDriving server. To request only the users on a specific server, see: [Users Online by Server](#users-online-by-server).

**ENDPOINT:** `/citydriving/stats/online`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Example

**REQUEST:** `?key=YOUR_KEY`

This request usually returns all connected users on all CityDriving servers. This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/online?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": "11969",
        "countryCode": "GB",
        "username": "Garypants",
        "nickname": "^1[TC]^7\u203aCarl\u2039",
        "money": "259473",
        "distance": "156889746",
        "trip": "34846",
        "bonus": "22",
        "lastCar": "XRT",
        "lastPosition": "^3Medical Centre^8",
        "server": "^7One"
    },
    ...
]
```

---

## Users Online by Server

The users online by server API gives you a breakdown of online users by server.

**ENDPOINT:** `/citydriving/stats/live`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `server` | _{string}_: one &#124; two &#124; three &#124; four |

#### Example

**REQUEST:** `?key=YOUR_KEY`

This request usually returns all connected users on a given CityDriving server. This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/live?key=YOUR_KEY&server=two
HTTP/1.1 200 OK
```
```json
[
    {
        "id": "11969",
        "countryCode": "GB",
        "username": "Garypants",
        "nickname": "^1[TC]^7\u203aCarl\u2039",
        "money": "259473",
        "distance": "156889746",
        "trip": "34846",
        "bonus": "22",
        "lastCar": "XRT",
        "lastPosition": "^3Medical Centre^8",
        "server": "^7Two"
    },
    ...
]
```

---

## Top Distance

The top distance API can return any range of the top 1000 users with the highest total driven distance. The default range is 20.

**ENDPOINT:** `/citydriving/stats/distance`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Example

**REQUEST:** `?key=YOUR_KEY`

This request usually returns all connected users on all CityDriving servers. This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/online?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": "11969",
        "countryCode": "GB",
        "username": "Garypants",
        "nickname": "^1[TC]^7\u203aCarl\u2039",
        "money": "259473",
        "distance": "156889746",
        "trip": "34846",
        "bonus": "22",
        "lastCar": "XRT",
        "lastPosition": "^3Medical Centre^8",
        "server": "^7One"
    },
    ...
]
```

## Top Money
## Top Wealth
## Cop Experience
## Robber Experience
## Roleplay Points
## Last Tickets
## Top Crashers
## Newest Players
## Badges & Licenses
## Training Team Members
## [TC] CityDriving Members
## [TC] CityDrivings Admins by Level
## [TC] Racing Members