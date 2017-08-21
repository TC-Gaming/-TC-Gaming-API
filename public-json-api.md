# Public Server Status JSON API

The Public Server Status JSON API gives you access to live server statuses. This API is public and **does not require a key** as this data is cached every 5 seconds.

## API Index

We currently offer the following public JSON APIs:

| API | Description | Documentation |
| :--- | :--- | :--- |
| `/status_one.json` | CityDriving One Server Status | [View Docs](#server-status:-citydriving-one) |
| `/status_two.json` | CityDriving Two Server Status | [View Docs](#)|
| `/status_three.json` | CityDriving Three Server Status | [View Docs](#)|
| `/status_four.json` | CityDriving Four Server Status | [View Docs](#)|

## Server Status: CityDriving One

ENDPOINT: /json/status_one.json

Responses

This request indexes players by ID and returns all connected clients. This example only returns one client for brevity.

REQUEST: ?key=...

GET https://api.tc-gaming.co.uk/json/status_one.json
HTTP/1.1 200 OK
{
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
  }
},
"server": "One"
}