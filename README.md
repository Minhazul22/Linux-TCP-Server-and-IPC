# Linux-Based TCP Server and Interprocess Communication

A systems-programming portfolio project covering embedded Linux networking, TCP client/server behavior, and operating-system mechanisms for communication and synchronization between processes.

The lab experience summarized for this project includes a TCP server on a BeagleBoard-class platform, remote access using Telnet, connection inspection with Wireshark, IPC using signals and message queues, process scheduling, and concurrent file access using file locks and `fcntl()`.

> **Current repository scope:** This first version documents the work and its technical concepts. The lab source code, packet captures, screenshots, and measured outputs have not yet been added. Results described here are based on the supplied project summary and lab task sheet, not on a fresh execution of code from this repository.

## Areas covered

| Area | Topics |
|---|---|
| TCP server | Listening sockets, connection lifecycle, client/server communication, TCP/IP |
| Remote interaction | Telnet-based testing in a controlled lab environment |
| Network analysis | Wireshark inspection of connection behavior and TCP packets |
| Interprocess communication | Unix signals and message queues |
| Process scheduling | Process priorities, `nice` / `renice`, and observing scheduler behavior |
| Synchronization | Concurrent file access, lock files, advisory record/file locks, `fcntl()` |
| Embedded Linux | Running and accessing services on a BeagleBoard-class platform |

## Repository map

- [TCP server and Telnet](docs/tcp-server-and-telnet.md)
- [IPC concepts](docs/interprocess-communication.md)
- [Scheduling and file locking](docs/scheduling-and-file-locking.md)
- [Validation checklist](docs/validation-checklist.md)
- [System overview diagram](diagrams/system-overview.mmd)

## Networking workflow

At a high level, a client opens a TCP connection to the server, exchanges data with the service, and closes the connection. Wireshark can be used to inspect the transport-level exchange and relate packet flags to the application's connection lifecycle.

This repository links to related, more detailed portfolio work:
- [C TCP Telnet Emulator](https://github.com/Minhazul22/C-TCP-Telnet-Emulator)
- [Network Traffic Analysis](https://github.com/Minhazul22/Network-Traffic-Analysis)

Those repositories describe adjacent exercises; they are not evidence that the source code from this project is included here.

## Build, test, and evidence status

The README intentionally does not provide a build command yet because the specific source files and build configuration for this project have not been supplied for publication. The validation checklist describes what should be demonstrated when the permitted code or original lab evidence is added.

Before publishing source code or raw evidence, confirm that course rules allow redistribution. Redact credentials, private IP/MAC addresses, device identifiers, and any lab access details that should not be public.

## Security considerations

- Telnet transmits application data without transport encryption; use it only in a controlled lab environment.
- Do not expose a demonstration TCP service to untrusted networks without appropriate access controls.
- IPC and file-locking examples should check system-call return values and handle interruption, cleanup, and concurrent access carefully.
- Avoid logging credentials or sensitive input.

## Skills demonstrated

C and Linux systems programming, TCP/IP, embedded Linux, Telnet-based testing, Wireshark, Unix signals, message queues, process scheduling, synchronization, file locking, and `fcntl()`.
