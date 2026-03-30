# Rate Limiting & Quotas

### Quotas

Each API plan comes with a daily quota of requests.
When you are on the free plan and your daily quota is used up, the API will respond with the error code **402** and no more calls can be made until your quota resets.
You have complete control over your quota by looking at your console dashboard and checking the API response headers that appear with every answer from the API. These response headers are:

- X-API-Quota-Request: The number of requests used.
- X-API-Quota-Used: The number of requests used in total today. This number resets to zero at midnight UTC (click here to compare to your local time zone).
- X-API-Quota-Left: The number of requests left today (depends on your plan)

### Rate Limiting

There is a limit of how many requests you can make per second. The limits depend on the plan you are on. If you try making more requests you will receive a 429 error.

- Free: 60 requests in 1 minute and 1 request at a time (1 concurrent request).
- Apprentice: 2 requests per second and 5 requests simultaneously.
- Artisan: 10 requests per second and 10 requests simultaneously.
- Maestro: 20 requests per second and 10 requests simultaneously.
