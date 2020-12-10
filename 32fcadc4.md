---
date: 2020-10-20T01:24
--- 

# Dynamic Capacity Management

## Why use concurrency limits instead of rate limits?
  - Rate limits can be overcome easily with additional concurrency
  - Concurrency limits cannot be overcome by increasing the request rate
  - Concurrency limits avoid wasted capacity 
  - Auto-negotiated concurrency limits scale in sync with your systems

## Links
- [Stop Rate Limiting!](https://thestrangeloop.com/2017/stop-rate-limiting-capacity-management-done-right.html)
  - Strange Loop talk by [Jon Moore](https://blog.jonm.dev) (Sep 2017) 
  - Little's Law & using concurrency limits instead of rate limits
- [Performance Under Load](https://medium.com/@NetflixTechBlog/performance-under-load-3e6fa9a60581) (Netflix) - Adaptive concurrency limits
- [Netflix/concurrency-limits](https://github.com/Netflix/concurrency-limits)
  - "Instead of thinking in terms of RPS, we should be thinking in terms of concurrent requests"
- [platinummonkey/go-concurrency-limits](https://github.com/platinummonkey/go-concurrency-limits)
  - Go implementation of Netflix library 
- [TCP Congestion Control](https://web.cs.wpi.edu/~rek/Undergrad_Nets/B07/TCP_Congestion_Control.pdf), Lecture from Worcestershire Polytechnic Institute, Advanced Computer Networks course

# Links
- [[[5d6c9066]]]
- [[[a04a8f54]]]
- [[[3e563a75]]]
