---
description: "Get the exact weather data from your surroundings via satellite data from our partner, even with a small picture for visualisation. ☀️"
---

# Weather

{% hint style="warning" %}
A rate limiter is connected upstream on this endpoint, find out more about all the security mechanisms we use [here](https://docs.atomicradio.eu/resources/ratelimits).
{% endhint %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/weather" %}
{% api-method-summary %}
Get weather informations
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns weather information based on your geo location.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="lat" type="number" required=false %}
Latitude
{% endapi-method-parameter %}

{% api-method-parameter name="lon" type="number" required=false %}
Longitude
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "city": String,
   "temp": Number,
   "humidity": Number,
   "weather":{
      "description": String,
      "icon": String
   }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "code": 500,
   "message": "Weather data could not be loaded. Please try again later."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



