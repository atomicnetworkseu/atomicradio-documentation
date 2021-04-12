---
description: "All information about the security mechanisms against excessive requests to our API summarised and how you can see if you are complying with these limits. \U0001F6E1️"
---

# Rate Limiting

All requests to the public parts of our API are subject to rate limits, which we use to prevent abuse and overloading of our services. If you exceed this limit, your requests will be blocked for a period of time.

## Route-Specific Rate Limiting

| Endpoint | Requests | Block duration |
| :--- | :--- | :--- |
| `*` | 100/minute | 1 hour |
| `/weather/*` | 50/minute | 1 hour |

## Request Headers

| Header | Type | Description |
| :--- | :--- | :--- |
| X-RateLimit-Limit | Number | Total number of requests you can perform per minute. |
| X-RateLimit-Remaining | Number | Number of requests remaining in the current time frame. |
| X-RateLimit-Reset | Number | UNIX timestamp when your rate limit reset. |
| X-RateLimit-Retry | Number | Shows how many seconds are left until reset. |

## Exceeding the limit

If you exceed these limits you will be temporarily blocked from our API and requests will be handled with a `429 Too Many Requests` error. Our default limit is **250 requests per minute**. However, the limits may slightly deviate for some endpoints.

### Error response

```javascript
{
   "code": 429,
   "message": "You are being rate limited."
}
```

