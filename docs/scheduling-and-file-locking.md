# Process Scheduling and Concurrent File Access

This page summarizes the operating-systems lab tasks described in the supplied OS Lab 2 sheet. The tasks focus on observing scheduling behavior and coordinating two processes that access a shared file.

## Process scheduling exercise

The lab task sheet describes creating two competing processes that both write characters to the screen, then observing the output while changing scheduling-related conditions.

The proposed observations in the sheet are:

1. Change the nice value of one process using `renice` and observe the output.
2. Add a 1 ms waiting period after each output and observe how this affects the distribution of CPU time.
3. Run a computationally intensive program simultaneously and compare the behavior.

The sheet notes that stream-function buffering affects the scheduler's visible output. Therefore, terminal output should not be treated as a direct or precise measure of CPU scheduling without considering buffering and other effects.

## Concurrent file access exercise

The task sheet describes two processes, A and B, alternating roles:
1. One process writes a short string to a file.
2. The other process reads the file.
3. The writer removes the file after the read/write cycle.
4. The two processes swap roles.

The assignment asks for two coordination strategies.

### Lock-file approach

A process creates or acquires a designated lock file before accessing the shared resource, and releases it afterward. The implementation must handle stale locks, race conditions during lock acquisition, and cleanup after abnormal termination.

### `fcntl()` file locking

The task sheet asks for an exclusive-access implementation using `fcntl()`. These locks are advisory: cooperating processes must check and honor them. The implementation should check return values and handle errors such as interrupted system calls.

## Comparison points

| Concern | Lock-file approach | `fcntl()` locking |
|---|---|---|
| Coordination mechanism | Convention around a lock file | Kernel-managed advisory locks |
| Cleanup | Must consider stale lock files | Locks are associated with open file descriptions/process behavior as defined by the selected lock type |
| Correctness | Depends on safe lock creation and consistent cooperation | Depends on all participants honoring the locking protocol |
| Useful discussion | Atomic acquisition and stale-lock recovery | Lock ranges, lock type, errors, and process lifecycle |

Exact behavior depends on the locking API and operating-system semantics used by the implementation; use the source and lab observations to make the final comparison precise.

## What to record in the final report

- The code path used for each locking strategy.
- How both processes coordinate writer/reader roles.
- What happens if one process exits unexpectedly.
- Observed output with and without locking.
- Any race condition or interleaving reproduced during testing.
- The limitations of the experiment and whether the result was repeated.
