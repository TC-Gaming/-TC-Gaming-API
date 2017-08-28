# Basic Requests

If you're new to using REST APIs, this guide should help you get started with making basic requests. It provides reference implementations for fetching data from our API by using the [User Profile API](../citydriving-statistics-api/user-profile-api.md) as an example.

Our code examples are available in JavaScript and PHP _(change language in the top right)._

{% method %}
## Reference Implementations

{% sample lang="js" %}

### JavaScript

Here is our reference implementation for fetching data with JavaScript. You will need to change the values of `YOUR_KEY` and `USERNAME`.

**Try out this example on [JS Bin](https://jsbin.com/luqawoy/edit?js,console)**



```js
var key = 'YOUR_KEY';
var request = {
  api: 'citydriving/profile/get',
  params: {
    key: key,
    username: 'USERNAME'
  }
};

TCAPIRequest(request, function(data) {
  
  // Do something with the returned data
  console.log(data);
});

function TCAPIRequest(req, callback) {
  this.baseUrl = 'https://api.tc-gaming.co.uk/';
  this.xhr = new XMLHttpRequest();
  this.qs = "";
  if(Object.keys(req.params).length > 0) {
    for(var param in req.params) {
      this.qs.length == 0 ? (qs += "?") : (qs += "&");
      this.qs += param + '=' + req.params[param];
    }
  }
  this.url = this.baseUrl + req.api + this.qs;
  this.xhr.onreadystatechange = function() {
    if(this.xhr.readyState === XMLHttpRequest.DONE) {
      if(this.xhr.status === 200) callback(JSON.parse(this.xhr.response));
    }
  }.bind(this);
  this.xhr.open('GET', this.url);
  this.xhr.send();
}
```

### JavaScript (JQuery)

If you would prefer, here is our reference implementation for fetching data with [JQuery](https://jquery.org). You will need to change the values of `YOUR_KEY` and `USERNAME`.

**Try out this example on [JS Bin](https://jsbin.com/yecomiq/edit?js,console)**

```js
$.get(
  "https://api.tc-gaming.co.uk/citydriving/profile/get",
  {
    key: 'YOUR_KEY',
    username: 'USERNAME'
  }
).done(
  function(data) {
  
    // Do something with the returned data
    console.log(data);
  }
).fail(
  console.log('Error fetching data!\nMake sure you have set your API key and parameters.')
);
```

{% sample lang="php" %}

### PHP

Here is our reference implementation for requesting data with PHP. You will need to change the values of `YOUR_KEY` and `USERNAME`.

```php
$key = 'YOUR_KEY';
$api = 'citydriving/profile/get';
$params = [
  'key'      => $key,
  'username' => 'USERNAME'
];

$data = TCAPIRequest($api, $params);

// Do something with the returned data
print_r($data);

function TCAPIRequest($cmd, $queryData = null) {
  $opts = ['http' => [
    'method'        => 'GET',
    'timeout'       => 2,
    'ignore_errors' => true
  ]];
  $context = stream_context_create($opts);
  if ($queryData) $queryString = "?" . http_build_query($queryData);
  else $queryString = "";
  $url = 'https://api.tc-gaming.co.uk/' . $cmd . $queryString;
  $result = @file_get_contents($url, false, $context);
  if (!$result) throw new Exception('Query failed.');
  else {
    $ret = json_decode($result, true);
    if (json_last_error() > 0) throw new Exception($result);
    return $ret;
  }
}
```

{% endmethod %}