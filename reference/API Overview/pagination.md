---
title: Pagination
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
Some responses are too large to be returned in one go so we paginate. To identify which calls use pagination look for the "page" and "max" parameters in the parameter descriptions for each API call.

These calls include a "page" block in the response with two values, "count" and "number". Count tells you how many pages are available and number indicates the page number you are on.

```Text JSON
{  
    "page":{  
        "count":1,  
        "number":1  
    }  
}
```

The page parameter is used to request a certain page, it defaults to 1. The max parameter is used to limit the number of results returned per page, the default is 10, the maximum is 100.
