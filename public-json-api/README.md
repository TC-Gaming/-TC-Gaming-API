#
Public Server Status JSON API

The Public Server Status JSON API gives you access to live server statuses. This API is public and **does not require a key** as this data is cached every 5 seconds.

## API Index

We currently offer the following public JSON APIs:

| API | Description | Documentation |
| :--- | :--- | :--- |
| `/status_one.json` | CityDriving One Server Status | [View Docs](#server-status-citydriving-one) |
| `/status_two.json` | CityDriving Two Server Status | [View Docs](#server-status-citydriving-two)|
| `/status_three.json` | CityDriving Three Server Status | [View Docs](#server-status-citydriving-three)|
| `/status_four.json` | CityDriving Four Server Status | [View Docs](#server-status-citydriving-four)|

## Server Status: CityDriving One

**ENDPOINT:** `/json/status_one.json`

This request indexes players by ID (inside the `players` object) and returns all currently connected clients. This example only returns one client for brevity.

**REQUEST:**
```shell
GET https://api.tc-gaming.co.uk/json/status_one.json
HTTP/1.1 200 OK
```

**RESPONSE:**
```json
{
    "server": "One",
    "time": 1490493497160,
    "players": {
        "17": {
            "siren": false,
            "med": false,
            "caution": false,
            "tow": false,
            "cop": false,
            "isChased": false,
            "isJoining": false,
            "hazard": false
        },
        ...
    }
}
```

## Server Status: CityDriving Two

**ENDPOINT:** `/json/status_two.json`

This request indexes players by ID (inside the `players` object) and returns all currently connected clients. This example only returns one client for brevity.

**REQUEST:**
```shell
GET https://api.tc-gaming.co.uk/json/status_two.json
HTTP/1.1 200 OK
```

**RESPONSE:**
```json
{
    "server": "Two",
    "time": 1490493497160,
    "players": {
        "17": {
            "siren": false,
            "med": false,
            "caution": false,
            "tow": false,
            "cop": false,
            "isChased": false,
            "isJoining": false,
            "hazard": false
        },
        ...
    }
}
```

## Server Status: CityDriving Three

**ENDPOINT:** `/json/status_three.json`

This request indexes players by ID (inside the `players` object) and returns all currently connected clients. This example only returns one client for brevity.

**REQUEST:**
```shell
GET https://api.tc-gaming.co.uk/json/status_three.json
HTTP/1.1 200 OK
```

**RESPONSE:**
```json
{
    "server": "Three",
    "time": 1490493497160,
    "players": {
        "17": {
            "siren": false,
            "med": false,
            "caution": false,
            "tow": false,
            "cop": false,
            "isChased": false,
            "isJoining": false,
            "hazard": false
        },
        ...
    }
}
```

## Server Status: CityDriving Four

**ENDPOINT:** `/json/status_four.json`

This request indexes players by ID (inside the `players` object) and returns all currently connected clients. This example only returns one client for brevity.

**REQUEST:**

```shell
GET https://api.tc-gaming.co.uk/json/status_four.json
HTTP/1.1 200 OK
```
**RESPONSE:**
```json
{
    "server": "Four",
    "time": 1490493497160,
    "players": {
        "17": {
            "siren": false,
            "med": false,
            "caution": false,
            "tow": false,
            "cop": false,
            "isChased": false,
            "isJoining": false,
            "hazard": false
        },
        ...
    }
}
```