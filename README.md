# Rate Limiters

This is an exercise to learn more about rate limiters.

This project will cover the following rate limiter algorithms:
### Token Bucket

Every user gets a bucket with a certain amount of “tokens”. On each request, tokens are removed from the bucket. If the bucket is empty, then the request is rejected.

New tokens are added to the bucket at a certain threshold (every n seconds). The bucket can hold a certain number of tokens, so if the bucket is full of tokens then no new tokens will be added.

### Fixed Window

The rate limiter uses a window size of n seconds for a user. Each incoming request from the user will increment the counter for the window. If the counter exceeds a certain threshold, then requests will be discarded.

After the n second window passes, a new window is created.

### Sliding Log

The rate limiter track’s every user’s request in a time-stamped log. When a new request comes in, the system calculates the sum of logs to determine the request rate. If the request rate exceeds a certain threshold, then it is denied.

After a certain period of time, previous requests are discarded from the log.