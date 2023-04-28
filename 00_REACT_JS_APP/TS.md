# FATAL ERROR: CALL_AND_RETRY_LAST Allocation failed - JavaScript heap out of memory
- Solution: https://support.snyk.io/hc/en-us/articles/360002046418-JavaScript-heap-out-of-memory

```sh
export NODE_OPTIONS=--max-old-space-size=8192
```


 - https://docs.aws.amazon.com/amplify/latest/userguide/ttl.html