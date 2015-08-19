## TTLCache - an in-memory LRU cache with expiration

TTLCache is a minimal wrapper over a map[string][]byte in golang, entries of which are

1. Thread-safe
2. Auto-Expiring after a certain time

[![Build Status](https://travis-ci.org/MalteJ/ttlcache.svg)](https://travis-ci.org/MalteJ/ttlcache)

#### Usage
```go
import (
  "time"
  "github.com/MalteJ/ttlcache"
)

func main () {
  cache := ttlcache.NewCache(time.Second)
  cache.Set("key", []byte("value"))
  value, exists := cache.Get("key")
  count := cache.Count()
}
```
