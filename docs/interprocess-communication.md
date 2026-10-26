# Interprocess Communication (IPC)

The supplied CV summary identifies signals and message queues as IPC mechanisms studied in this work. The original implementation files and detailed test output have not yet been supplied, so this page explains the role of each mechanism without inventing implementation-specific behavior.

## Signals

Signals notify a process that an event has occurred. Depending on the signal and program design, a process may use a default action, ignore a signal where permitted, or install a signal handler.

When documenting the actual lab implementation, record:
- which signals were used and why;
- how the receiving process handled them;
- how the program handled interrupted system calls and shutdown;
- the observed behavior when the signal was delivered.

Signal handlers should do as little work as possible; complex work is generally better deferred to normal program flow.

## Message queues

Message queues allow processes to exchange discrete messages through a kernel-managed queue. The exact API may be POSIX message queues or System V message queues; the source code is needed to identify which one this lab used.

When documenting the implementation, record:
- the message-queue API and creation/opening flags;
- the message format and message priorities, if used;
- blocking versus non-blocking behavior;
- cleanup of queue objects on normal exit and error paths.

## Why use different IPC mechanisms?

Signals are well suited to event notification. Message queues are better suited to passing structured pieces of data. The right choice depends on whether a process needs to be notified that something happened or needs to receive an actual message.

## Evidence to add when available

Add permitted, authored source files or small standalone examples, plus the compile/run commands and sample output. Do not claim a specific queue type, signal number, or measured result until it can be confirmed from the original lab materials.
