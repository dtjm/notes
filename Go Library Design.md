---
date: 2020-12-01T15:07
---

1. No leaks! 
   - Background goroutines should be stoppable. Preferably no background goroutines if possible.
2. Minimize goroutines
3. No external dependencies
4. Don't force the user into a particular ecosystem (logging, metrics, etc)
5. Don't force the user to be asynchronous (make the caller say `go`) 
