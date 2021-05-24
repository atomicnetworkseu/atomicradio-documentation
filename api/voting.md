# Voting

{% hint style="warning" %}
A rate limiter takes care of this endpoint,  
find out more about all the security mechanisms we use [here](https://docs.atomicradio.eu/resources/ratelimits).
{% endhint %}

{% api-method method="get" host="https://api.atomicradio.eu" path="/voting" %}
{% api-method-summary %}
Get all songs
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns all the songs you can vote for.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "items": [
      {
         "id": 1,
         "unique_id": "9700f10db23f65122f75ba5c11c7dfa6",
         "artist": "ROBBY EAST & ROLIPSO",
         "title": "BREAKAWAY",
         "type": "#NEWCOMER",
         "votes": 0,
         "voted": false,
         "preview_url": "",
         "artworks":{
            "100": "https://cdn.atomicradio.eu/artworks/9700f10db23f65122f75ba5c11c7dfa6/0100.jpg",
            "250": "https://cdn.atomicradio.eu/artworks/9700f10db23f65122f75ba5c11c7dfa6/0250.jpg",
            "500": "https://cdn.atomicradio.eu/artworks/9700f10db23f65122f75ba5c11c7dfa6/0500.jpg",
            "1000": "https://cdn.atomicradio.eu/artworks/9700f10db23f65122f75ba5c11c7dfa6/1000.jpg"
         }
      },
      // Next 29 songs
   ],
   "created_at": 1621614601100,
   "closing_at": 1622217600000,
   "ending_at": 1622219400000,
   "closed": false
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "code": 500,
   "message": "A problem with our API has occurred. Try again later."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "code": 503,
   "message": "Voting is currently disabled. Try again later."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.atomicradio.eu" path="/voting?id={id}" %}
{% api-method-summary %}
Vote for a song
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to vote for a song.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="id" type="number" required=false %}
Song item id
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "code": 201,
   "message": "Thank you for your vote for ROBBY EAST & ROLIPSO - BREAKAWAY."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "code": 400,
   "message": "No id specified in the query."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "code": 403,
   "message": "Voting has been closed. Try again later."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "code": 404,
   "message": "There are currently no songs in the voting. Try again later."
}

// or

{
   "code": 404,
   "message": "The song with the given id was not found."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "code": 500,
   "message": "You have already voted for this song."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```typescript
{
   "code": 503,
   "message": "Voting is currently disabled. Try again later."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

