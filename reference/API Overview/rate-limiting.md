---
title: Rate Limiting
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
To provide the best service to all our customers we limit the number of API calls which can be made by each account to 15 calls per sec. For heavy users we can increase your throttling speed, but please contact us to discuss your requirements.

If you exceed this limit we will return two indicators which you can use in your code to detect that you have been throttled.

The first is the HTTP status code 429 "Too Many Requests", the second is the error code "OVER\_LIMIT" in the error block of the response body.

If this happens message requests will be dropped, they will not be retried.
