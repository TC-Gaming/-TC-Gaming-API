# Basic Requests

If you're new to using REST APIs, here are the basics for making your first data requests.

{% method %}
## How many players are online?

In this first example we will make a request to the [Server Status API](../citydriving-statistics-api/server-status-api.md) to work out how many players are online and present this information to our user.

{% sample lang="js" %}
Here's how to return the number of connections using JavaScript ([JQuery](https://jquery.org)).

```js
$.get("https://api.tc-gaming.co.uk/citydriving/live/status?key=YOUR_KEY&server=all", function(data) {

    // Get connections to each server
    var one = parseInt(data.one.guests);
    var two = parseInt(data.two.guests);
    var three = parseInt(data.three.guests);
    
    // Get maximum possible connections to each server
    var maxOne = parseInt(data.one.maxGuests);
    var maxTwo = parseInt(data.two.maxGuests);
    var maxThree = parseInt(data.three.maxGuests);
    
    // Sum the total connections
    var total = one + two + three;
    
    // Sum the total possible connections
    var maxTotal = maxOne + maxTwo + maxThree;
    
    // Output a formatted string
    console.log("[TC] CityDriving Connections: " + total + "/" + maxTotal);
  });
```

{% sample lang="php" %}
Here's how to return the number of connections using PHP

```php
$api = 'https://api.tc-gaming.co.uk/citydriving/live/status?server=all';
$key = 'YOUR_KEY';
$data = json_decode(file_get_contents($api.'&key='.$key));

// Get connections to each server
$one = intval($data->one->guests);
$two = intval($data->two->guests);
$three = intval($data->three->guests);

// Get maximum possible connections to each server
$maxOne = intval($data->one->maxGuests);
$maxTwo = intval($data->two->maxGuests);
$maxThree = intval($data->three->maxGuests);

// Sum the total connections
$total = $one + $two + $three;

// Sum the total possible connections
$maxTotal = $maxOne + $maxTwo + $maxThree;

// Output a formatted string
echo('[TC] CityDriving Connections: ' . $total . "/" .$maxTotal);
  });
```

{% common %}
Here's the resulting output:

```bash
"[TC] CityDriving Connections: 78/120"
```
{% endmethod %}
