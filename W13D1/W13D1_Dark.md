# Memory Consisitency Model.

- Schemes faster execution to sequential consistency.
- Only those programs willing to be non-deterministic will not sync. ("data race")


# User level sync.

Spin locks: Continuously tries to acquire lock.

- Allow only one thread to enter critical section.
- No sleeping. (Busy waiting, so CPU intensive)

Solution:

- Atomic exchange: Compare and swap. (Easy to understand)
- load linked(ll) and store conditional(sc). (I'm lasy, plz refer to [wiki](https://en.wikipedia.org/wiki/Load-link/store-conditional) for more details)
