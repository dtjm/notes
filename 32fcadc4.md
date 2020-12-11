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
- [Envoy, Take the Wheel: Real-time Adaptive Circuit Breaking (Youtube)](https://www.youtube.com/watch?v=CQvmSXlnyeQ) Tony Allen (Lyft), Sep 2020
  - "Modern service mesh deployments are equipped with hundreds of tunables, such as timeouts and circuit breakers. Finding ideal initial values requires deep technical expertise. Workloads change over time, requiring regular effort to re-tune stale parameters. As a consequence, configuration errors have become a source of operational toil and one of the major causes of system failures across the industry. The service mesh should aim to expose a minimal configuration surface by dynamically adjusting parameters based on observations."
  - [Envoy adaptive concurrency configuration](https://www.envoyproxy.io/docs/envoy/latest/configuration/http/http_filters/adaptive_concurrency_filter)

# Links
- [[[5d6c9066]]]
- [[[a04a8f54]]]
- [[[3e563a75]]]
