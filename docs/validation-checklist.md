# Validation Checklist

Use this checklist when permitted source files or original lab evidence are ready to include. Mark a check as complete only after it has actually been tested.

## TCP server

- [ ] Record the target platform and Linux environment.
- [ ] Record the server startup command and configured port.
- [ ] Connect from an authorized client using the lab's intended client tool.
- [ ] Verify expected behavior on connect, data exchange, disconnect, and server shutdown.
- [ ] Use Wireshark to identify handshake packets, application traffic, acknowledgements, and teardown.
- [ ] Redact addresses, credentials, and device-identifying information from public screenshots.

## Signals and message queues

- [ ] Identify the exact signals used from the source code.
- [ ] Identify whether the queue is POSIX or System V.
- [ ] Document message structure and blocking behavior.
- [ ] Test normal operation and error paths.
- [ ] Verify cleanup on normal shutdown.

## Scheduling

- [ ] Run the two-process output experiment.
- [ ] Compare default scheduling behavior with the changed nice value.
- [ ] Compare behavior after adding the 1 ms delay.
- [ ] Compare behavior under additional CPU load.
- [ ] Account for stdout buffering when interpreting results.

## File synchronization

- [ ] Run the alternating writer/reader exercise without synchronization to observe possible race behavior.
- [ ] Repeat with lock-file coordination.
- [ ] Repeat with `fcntl()` locking.
- [ ] Verify both processes release or recover resources appropriately on failure.
- [ ] Record what was observed, rather than assuming a race or success must occur every run.

## Publication readiness

- [ ] Check permission to redistribute every source file and course artifact.
- [ ] Remove passwords, tokens, private addresses, and irrelevant personal details.
- [ ] Include build instructions only after confirming the actual source and dependencies.
- [ ] Keep planned checks distinct from completed experiments.
