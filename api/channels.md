---
description: "The official documentation of atomicradio api, with all information about usage and upcoming maintenance. \U0001F36D"
---

# Channels

{% hint style="warning" %}
This endpoint is protected by a rate limiter. All information about our Rate Limiter can be found here: [Rate Limiting](https://docs.atomicradio.eu/resources/ratelimits)
{% endhint %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/channels" %}
{% api-method-summary %}
Get all channels
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns you a list of our channels.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
The response is too big to show here.
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/channels/live" %}
{% api-method-summary %}
Get live information
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns you informations about our livestream.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "is_live": Boolean,
   "streamer": String
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/channels/:id" %}
{% api-method-summary %}
Get channel
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns you information about a single channel.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":id" type="string" required=true %}
Here you can use one, dance or trap as paramter value.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "name": String,
   "description": {
      "de": String,
      "en": String
   },
   "listeners": Number,
   "live":{
      "is_live": Boolean,
      "streamer": String
   },
   "song":{
      "artist": String,
      "title": String,
      "playlist": String,
      "start_at": Number,
      "end_at": Number,
      "duration": Number,
      "artworks":{
         "100": String,
         "250": String,
         "500": String,
         "1000": String
      }
   },
   "schedule":[
      {
         "artist": String,
         "title": String,
         "playlist": String,
         "start_at": Number,
         "end_at": Number,
         "duration": Number,
         "artworks":{
            "100": String,
            "250": String,
            "500": String,
            "1000": String
         }
      },
   ],
   "history":[
      {
         "artist": String,
         "title": String,
         "playlist": String,
         "start_at": Number,
         "end_at": Number,
         "duration": Number,
         "artworks":{
            "100": String,
            "250": String,
            "500": String,
            "1000": String
         }
      },
   ],
   "stream_urls":{
      "highquality": String,
      "middlequality":String,
      "lowquality": String
   }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "code": 404,
   "message": "This channel does not exist."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/channels/:id/live" %}
{% api-method-summary %}
Get live information
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns you informations about our livestream.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":id" type="string" required=true %}
Here you can use one, dance or trap as paramter value.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "is_live": Boolean,
   "streamer": String
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "code": 404,
   "message": "This channel does not exist."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "code": 500,
   "message": "Only our channel 'atr.one' has live metadata."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/channels/:id/song" %}
{% api-method-summary %}
Get song information
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns you informations about the current playing song on this channel.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":id" type="string" required=true %}
Here you can use one, dance or trap as paramter value.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "artist": String,
   "title": String,
   "playlist": String,
   "start_at": Number,
   "end_at": Number,
   "duration": Number,
   "artworks":{
      "100": String,
      "250": String,
      "500": String,
      "1000": String
   }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "code": 404,
   "message": "This channel does not exist."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/channels/:id/listeners" %}
{% api-method-summary %}
Get listener informations
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns you the information how many are listening to this channel.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":id" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "listeners": Number
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "code": 404,
   "message": "This channel does not exist."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/channels/:id/history" %}
{% api-method-summary %}
Get history list
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns you a list of songs that have already been played on this channel.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":id" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
   {
      "artist": String,
      "title": String,
      "playlist": String,
      "start_at": Number,
      "end_at": Number,
      "duration": Number,
      "artworks":{
         "100": String,
         "250": String,
         "500": String,
         "1000": String
      }
   }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "code": 404,
   "message": "This channel does not exist."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/channels/:id/schedule" %}
{% api-method-summary %}
Get schedule list
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns you a list of songs that will be played soon on this channel.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":id" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
   {
      "artist": String,
      "title": String,
      "playlist": String,
      "start_at": Number,
      "end_at": Number,
      "duration": Number,
      "artworks":{
         "100": String,
         "250": String,
         "500": String,
         "1000": String
      }
   }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "code": 404,
   "message": "This channel does not exist."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

