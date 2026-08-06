# 13. Concurrency

- Concurrency decouples *what* from *when*; it can improve throughput (I/O-bound work) and structure, but it's hard, and its bugs are rarely repeatable.
- Myths: it doesn't always improve performance, it *does* change design, and containers don't relieve you of understanding it. It adds overhead and complexity.
- Defense principles: SRP - keep concurrency code separate from other code; severely limit the scope of shared data (few, small critical sections); use copies of data where possible; make threads as independent as possible (own local data).
- Know your library: thread-safe collections (`ConcurrentHashMap`), executor framework, nonblocking atomics (CAS-based, usually faster than locks); know which classes are not thread-safe (e.g. SimpleDateFormat).
- Know the execution models and terms: bound resources, mutual exclusion, starvation, deadlock, livelock; producer-consumer, readers-writers, dining philosophers - most problems are variations of these.
- Dependencies between synchronized methods break code (individually safe methods, unsafe in combination). Avoid using more than one method on a shared object; otherwise use client-based locking, server-based locking (preferred), or an adapted server. Server-based wins: less repetition, single policy, smaller shared-variable scope.
- Keep synchronized sections as small as possible; locks are expensive.
- Deadlock requires all four: mutual exclusion, lock & wait, no preemption, circular wait - break any one (most commonly: global ordering of resource acquisition breaks circular wait).
- Graceful shutdown is hard (parents waiting on deadlocked children, consumers blocked on dead producers) - plan it early.
- Testing threaded code: treat spurious failures as threading bugs, not one-offs; get nonthreaded code (POJOs) working first; make threaded code pluggable and tunable; run with more threads than processors; run on all target platforms early and often; instrument with jiggling (yield/sleep/priority, hand-coded or tools like ConTest) to force rare interleavings.
