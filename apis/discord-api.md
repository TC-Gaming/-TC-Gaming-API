# Discord API

The endpoint for the Discord API is: `/discord_status`

## API Index

We currently offer the following Discord APIs:

| API | Documentation |
| :--- | :--- |
| Discord Status API | [View Docs](discord-api.md#discord-status-api) |

## Discord Status API

This Discord API gives you access to all users who are currently on the \[TC\] Gaming public Discord server.

**ENDPOINT:** `/discord_status`

## Mandatory Parameters

| Name | Expected Value |
| :--- | :--- |
| `key` | _{string}_ : API Key |

## Example

**REQUEST:** `/discord_status?key=YOUR_KEY`

This example only returns one user for brevity.

**RESPONSE:**

```text
GET https://api.tc-gaming.co.uk/discord_status?key=YOUR_KEY
HTTP/1.1 200 OK
```

```javascript
{
    "channels": [
        {
            "position": 3,
            "id": "197743799126982656",
            "name": "[TC] CityDriving One"
        },
        {
            "position": 5,
            "id": "197743857423745024",
            "name": "[TC] CityDriving Three"
        },
        {
            "position": 4,
            "id": "197743831792353281",
            "name": "[TC] CityDriving Two"
        },
        {
            "position": 6,
            "id": "197743902453661696",
            "name": "[TC] Events"
        },
        {
            "position": 7,
            "id": "197743923651805184",
            "name": "[TC] Racing"
        },
        {
            "position": 0,
            "id": "200027236546379776",
            "name": "AFK Channel"
        },
        {
            "position": 2,
            "id": "197735644892495872",
            "name": "General"
        },
        {
            "position": 8,
            "id": "198074635370102784",
            "name": "Other Games"
        }
    ],
    "instant_invite": null,
    "id": "197735644364144649",
    "members": [
        {
            "username": "44r0n_r3",
            "status": "online",
            "avatar_url": "https:\/\/cdn.discordapp.com\/avatars\/275310516295958539\/1933e82a9c842736022b01b4404b94da.jpg",
            "avatar": "1933e82a9c842736022b01b4404b94da",
            "discriminator": "3063",
            "id": "275310516295958539"
        },
        ...
    ],
    "name": "[TC] Gaming"
}
```

