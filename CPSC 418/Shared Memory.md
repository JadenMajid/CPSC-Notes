## Cache
different cores have individual caches(L1,L2).
### Types
- Write-back
	- Writes only update the cache, main memory is updated when cache line is evicted
	- we will assume write-back is used in 418
- write-through
	- writes update cache and main memory
	- waaaaaaay slllllooooooooowwwweeeeeeerrrr
Does either cache change contents when the other CPU does a write?
- if yes then the caches are watching the memory actions of the other
- if no then the CPUs have stale values
- write through is a performance killer![[Screenshot 2026-01-21 at 15.11.41.png]]

### Coherence Protocols
caches communicate so that multiple CPUs can have read only copies of data
#### MESI
- Cache coherence protocol
- States
	- Modified
		- This cache has the only copy of this line and it differs from main memory
	- Exclusive
		- This cache has the only copy and it matches main memory
	- Shared
		- Multiple caches have this copy and all match main memory
	- Invalid
		- This cache does not have a valid copy of the line



