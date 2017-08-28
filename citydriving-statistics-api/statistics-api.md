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
| [TC] Training Team Members | [View Docs](#training-team-members)  |
| [TC] CityDriving Members | [View Docs](#tc-citydriving-members) |
| [TC] CityDriving Admins by Level | [View Docs](#tc-citydriving-admins-by-level) |
| [TC] Racing Members | [View Docs](#tc-racing-members) |

## API-Wide Optional Parameters

All statistics API requests default to 20 rows of returned data. Certain applications may require more rows or a range of rows. For this reason all statistics API requests can utilise the `rows` and `skip` parameters. With these parameters, you can request any range of rows in the top 1000 total records.

| Name | Expected Value | Default Value |
| :--- | :--- | :--- |
| `rows` | _{integer}_ : Number of rows to request | 20 |
| `skip` | _{integer}_ : Number of rows to skip/offset | - |

#### Examples

Request first 50 records: `rows=50`  
Request records 60 to 80: `skip=60`  
Request records 100 to 200: `skip=100&rows=100`  

---

## Users Online

The users online API gives you basic details of all users who are online on a [TC] CityDriving server. To request only the users on a specific server, see: [Users Online by Server](#users-online-by-server).

**ENDPOINT:** `/citydriving/stats/online`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

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
        "id": 11969,
        "countryCode": "GB",
        "username": "Garypants",
        "nickname": "^1[TC]^7\u203aCarl\u2039",
        "money": 259473,
        "distance": 156889746,
        "trip": 34846,
        "bonus": 22,
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

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

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
        "id": 11969,
        "countryCode": "GB",
        "username": "Garypants",
        "nickname": "^1[TC]^7\u203aCarl\u2039",
        "money": 259473,
        "distance": 156889746,
        "trip": 34846,
        "bonus": 22,
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

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

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
        "id": 11969,
        "countryCode": "GB",
        "username": "Garypants",
        "nickname": "^1[TC]^7\u203aCarl\u2039",
        "money": 259473,
        "distance": 156889746,
        "trip": 34846,
        "bonus": 22,
        "lastCar": "XRT",
        "lastPosition": "^3Medical Centre^8",
        "server": "^7One"
    },
    ...
]
```

---

## Top Money

The top money API can return any range of the top 1000 users with the most money. The default range is 20.

**ENDPOINT:** `/citydriving/stats/money`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/money?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 2107,
        "countryCode": "DE",
        "username": "P V L",
        "nickname": "^7Just ^1P ^7V ^1L",       
        "money": 4671440,
        "distance": 68547122,
        "trip": 0,
        "lastCar": null,
        "lastPosition": null,
        "lastSeen": "2017-07-07 08:49:38",
        "server": null
    },
    ...
]
```

---

## Top Wealth

The top wealth API can return any range of the top 1000 users with the most money and assets (wealth). The default range is 20.

**ENDPOINT:** `/citydriving/stats/wealth`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/wealth?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 2107,
        "countryCode": "DE",
        "username": "P V L",
        "nickname": "^7Just ^1P ^7V ^1L",       
        "wealth": 5249230,
        "distance": 68547122,
        "trip": 0,
        "lastCar": null,
        "lastPosition": null,
        "lastSeen": "2017-07-07 08:49:38",
        "server": null
    },
    ...
]
```

---

## Cop Experience

The cop experience API can return any range of the top 1000 users with the highest cop experience. The default range is 20.

**ENDPOINT:** `/citydriving/stats/cop_xp`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/cop_xp?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 23210,
        "countryCode": "HU",
        "username": "sergey29",
        "nickname": "^2[GLOW]Angel[COP]",
        "xp": 483008,
        "lastSeen": "2017-08-26 20:15:17",
        "server": "^7Two"
    },
    ...
]
```

---

## Robber Experience

The robber experience API can return any range of the top 1000 users with the highest robber experience. The default range is 20.

**ENDPOINT:** `/citydriving/stats/robber_xp`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/robber_xp?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 23210,
        "countryCode": "HU",
        "username": "sergey29",
        "nickname": "^2[GLOW]Angel[COP]",
        "xp": 150961,
        "lastSeen": "2017-08-26 20:15:17",
        "server": "^7Two"
    },
    ...
]
```

---

## Roleplay Points

The roleplay points API can return any range of the top 1000 users with the highest number of roleplaying points (RP). The default range is 20.

**ENDPOINT:** `/citydriving/stats/rp`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/rp?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 24557,
        "countryCode": "NL",
        "username": "i-love-cruise",
        "nickname": "^4[CSR]^7Wouter^4[RES]",
        "rp": 37445,
        "lastSeen": "2017-08-26 12:02:10",
        "server": "^7One"
    },
    ...
]
```

---

## Last Tickets

The last tickets API can return any range of the latest 1000 issued fines. The default range is 20.

**ENDPOINT:** `/citydriving/stats/last_tickets`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one ticket for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/last_tickets?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id_cop": 28819,
        "username_cop": "tilo0803",
        "cop": "^6[COP]^7GMaker",
        "id_robber": 30589,
        "username_robber": "lord_ring",
        "robber": "^1\u2039^7Ricardo^1\u203a",
        "date": "2017-08-28 14:23:40",
        "location": "Paddock Tunnel Way, Weston Park",
        "offense": "Speeding",
        "fine": 60
    },
    ...
]
```

---

## Top Crashers

The top crashers API can return any range of the top 1000 with the most 'heavy contacts'. The default range is 20.

**ENDPOINT:** `/citydriving/stats/crashers`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/crashers?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 23210,
        "countryCode": "HU",
        "username": "sergey29",
        "nickname": "^2[GLOW]Angel[COP]",
        "crashes": 6451,
        "last seen": "2017-08-26 20:15:17",
        "server": "^7Two"
    },
    ...
]
```

---

## Newest Players

The newest players API can return any range of the newest 1000 players. The default range is 20.

**ENDPOINT:** `/citydriving/stats/new_players`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/new_players?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 30900,
        "countryCode": "BR",
        "username": "viniciussantos",
        "nickname": "^4\u3029^7Ran^1dom",
        "money": 4093,
        "distance": 4050,
        "dateJoined": "2017-08-26 14:47:12"
    },
    ...
]
```

---

## Badges & Licenses

Get all users who have a certain license. The default range is 20.

**ENDPOINT:** `/citydriving/stats/badge`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `badge` | _{string}_ : Badge Name (See list of values below) |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### List of Badges & Licenses

These are the most common values for `badge`.

| Name | Value Code |
| :--- | :--- |
| COP | `cop` |
| TOW | `tow` |
| MED/RES | `med` |
| SUPER | `super` |
| [TC] CityDriving Admin | `tc` |
| [TC] Trainer | `tct` |
| [GLOW] Member | `glow` |
| [CSR] Member | `csr` |
| 6Speed Member | `6s` |
| [RDSR] Member | `rdsr` |
| SO Member | `so` |

#### Example

**REQUEST:** `?key=YOUR_KEY&badge=cop`

This example lists COP badges and only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/badge?key=YOUR_KEY&badge=cop
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 4,
        "countrycode": "DE",
        "username": "chucknorris",
        "nickname": "^7\u2039Chuck\u203a",
        "money": 1385061,
        "distance": 222851975,
        "last seen": "2017-08-26 23:21:59",
        "server": "^7One"
    },
    ...
]
```

---

## [TC] Training Team Members

Get a list of training team members. The default range is 20 so you may need to use a higher value for the `rows` parameter.

**ENDPOINT:** `/citydriving/stats/trainer_level`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Trainer Levels

The levels key refers to a trainer's basic rank within the team:

| Rank | Level |
| :--- | :--- |
| Leader | 1 |
| Trainer | 2 |
| Assistant | 3 | 
| Civillian Assistant | 4 |

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/trainer_level?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 487,
        "countrycode": "GB",
        "username": "Degats",
        "last_seen": "2017-08-25 23:16:39",
        "trainer_level": 1
    },
    ...
]
```

---

## [TC] CityDriving Members

Get a list of [TC] CityDriving admins. The default range is 20 so you may need to use a higher value for the `rows` parameter.

**ENDPOINT:** `/citydriving/stats/tcmembers`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/tcmembers?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 17,
        "countryCode": "GB",
        "username": "mbutcher",
        "nickname": "^1[TC]\u00bbPete\u00ab",
        "money": 108291,
        "distance": 223936390,
        "trip": 0,
        "lastCar": "No car",
        "lastPosition": "spectating",
        "lastSeen": "2017-08-10 02:41:32",
        "server": "^7One"
    },
    ...
]
```

---

## [TC] CityDrivings Admins by Level

Get a list of [TC] CityDriving admins by their admin level. The default range is 20 so you may need to use a higher value for the `rows` parameter.

**ENDPOINT:** `/citydriving/stats/admins`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |
| `level` | _{string}_ : Admin Level (See list of values below) |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Admin Levels

The levels key refers to an admin's basic rank within the team. Use the following levels as values for the `level` parameter:

| Rank | Level |
| :--- | :--- |
| Leader/Server Control/Chief Constable/CCiT | 1 |
| Inspector/Supervisor | 2 |
| Constable | 3 | 
| Constable in Probation | 4 |
| Recruit | 5 |

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/admins?key=YOUR_KEY&level=1
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 17,
        "countryCode": "GB",
        "username": "mbutcher",
        "nickname": "^1[TC]\u00bbPete\u00ab",
        "money": 108291,
        "distance": 223936390,
        "trip": 0,
        "lastCar": "No car",
        "lastPosition": "spectating",
        "lastSeen": "2017-08-10 02:41:32",
        "server": "^7One"
    },
    ...
]
```

---

## [TC] Racing Members

Get a list of [TC] Racing members. The default range is 20 so you may need to use a higher value for the `rows` parameter.

**ENDPOINT:** `/citydriving/stats/tcrmembers`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

#### Optional Parameters

See [API-Wide Optional Parameters](#api-wide-optional-parameters).

#### Admin Levels

The levels key refers to an admin's basic rank within the team.

| Rank | Level |
| :--- | :--- |
| [TC] Team Leader/[TC] Racing Manager | 1 |
| [TC] Racing Driver | 2 |

#### Example

**REQUEST:** `?key=YOUR_KEY`

This example only shows one user for brevity.

**RESPONSE:** 
```shell
GET https://api.tc-gaming.co.uk/citydriving/stats/tcrmember?key=YOUR_KEY
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 17,
        "countrycode": "GB",
        "username": "mbutcher",
        "last_seen": "2017-08-10 02:41:32",
        "admin_level": 1
    },
    ...
]
```