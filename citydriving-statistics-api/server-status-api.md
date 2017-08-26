# Server Status API

The endpoint for the server status API is: `/citydriving/live`

## API Index

We currently offer the following server status APIs:

| API | Documentation |
| :--- | :--- |
| Server Status Overview | [View Docs](#server-status-overview) |

---

## Server Status Overview

The server status overview gives details such as online status, track code, track name and the number of allowed and connected guests.

**ENDPOINT:** `/citydriving/live/status`

#### Mandatory Parameters

| Name | Expected Value |
| :--- | :--- | :--- |
| `key` | _{string}_ : API Key |
| `server` | _{string}_ : all &#124; one &#124; two &#124; three &#124; events &#124; training |

#### Example

**REQUEST:** `?key=YOUR_KEY&server=all`

This example request will return the status of all servers.

**RESPONSE:**
```shell
GET https://api.tc-gaming.co.uk/citydriving/live/status?key=YOUR_KEY&server=all
HTTP/1.1 200 OK
```
```json
{
  "one": {
    "online": true,
    "track": "KY3X",
    "guests": 40,
    "maxGuests": 40,
    "trackName": "Kyoto"
  },
  "two": {
    "online": true,
    "track": "KY3X",
    "guests": 38,
    "maxGuests": 40,
    "trackName": "Kyoto"
  },
  "three": {
    "online": true,
    "track": "BL1X",
    "guests": 7,
    "maxGuests": 40,
    "trackName": "Blackwood"
  },
  "events": {
    "online": true,
    "track": "RO1X",
    "guests": 0,
    "maxGuests": 47,
    "trackName": "Corby"
  },
  "training": {
    "online": true,
    "track": "AS5X",
    "guests": 0,
    "maxGuests": 32,
    "trackName": "Montana"
  }
}
```