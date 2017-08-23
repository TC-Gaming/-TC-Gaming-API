# API Keys

We currently offer two types of API key. The type of key you require depends on how you intend to use the API. You should pass your key to the API using the `key` parameter.

## Client Keys

If you are distributing software or apps that use our API, each user will need to generate their own API key. We suggest that you allow your users to enter their API key in a configuration file.

You can access/generate your personal API key on [TC] World under 'My Account': [world.city-driving.co.uk/?page=myaccount](http://world.city-driving.co.uk/?page=myaccount)

This key should be used during development and testing of your application. This key also acts as your personal access key for applications that use our API and should therefore not be used in production versions of your application.

## IP Restricted Keys

If you are serving web pages that use our API you will need an IP restricted API key which restricts requests to a list of IP addresses. To request an API key for your website please [drop us an email](mailto:info@city-driving.co.uk?subject=Request for IP Restricted API Key). 

## Access Errors

Whilst using our API you may encounter some error codes. If this happens, one of a small number of things may have occurred.

| `errorCode` | `errorMessage` |
| :--- | :--- |
| 400 | Bad request |
| 403 | Not authorised |
| 403 | Host not allowed |
| 403 | Rate limited exceeded |
| 403 | Command not allowed |
| 501 | Not implemented |


