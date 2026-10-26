# TCP Server and Telnet-Based Testing

## Lab summary

The supplied project summary describes configuring and testing a TCP server on a BeagleBoard-class embedded platform, connecting remotely with Telnet, and inspecting connection behavior with Wireshark.

The source code and original capture files are not included in this repository at this stage, so this document records the workflow and the concepts to demonstrate rather than claiming a fresh test run.

## Conceptual lifecycle

1. The server creates a TCP listening socket.
2. The socket is bound to a local address and port.
3. The server listens for incoming connection requests.
4. A remote client initiates a connection to the service.
5. The server accepts and services the connection.
6. The client and server exchange application data over the established TCP stream.
7. One side closes the connection, and the endpoints complete TCP teardown.

The precise implementation details—such as single-client versus multi-client handling, concurrency model, port configuration, and shutdown behavior—should be filled in from the source code or lab notes when available.

## Telnet and Wireshark

Telnet can be used as a simple interactive TCP client to connect to a text-based service. Wireshark provides a view of the TCP handshake, packets in each direction, acknowledgements, connection teardown, and application payload where the traffic is not encrypted.

**Security note:** Telnet does not encrypt application data. Use it only in an isolated or otherwise authorized lab environment, never as a secure remote-administration method over an untrusted network.

## Evidence to add when available

- A sanitized system diagram showing the client, embedded target, and TCP service.
- A screenshot or export showing a successful connection lifecycle in Wireshark.
- The actual build/run procedure and server port, if publication is permitted.
- A short test table that separates observed results from planned tests.

Avoid publishing private host addresses, MAC addresses, login credentials, serial numbers, or network topology details that should remain internal.
