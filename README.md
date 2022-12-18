# frr-anycast
FRRouting configuration for sharing an IP address between two Linux hosts.

Includes a "poke daemon" for health checking (poking) a local service listening
on some arbitrary port with a stick and retracting the anycast route if it
becomes unavailable.

# Topology
Default IP addresses:
- Router: 10.10.10.1/24
- VIP:    10.10.10.10/32
- Host 1: 10.10.10.11/24
- Host 2: 10.10.10.12/24
- Host 3: 10.10.10.13/24

TODO: Embedded image.

# Installation
Clone this repository and adapt `config.ini` to match your environment. Once
the configuration file is complete, run `make` at the repository root.

The following will appear in the `build/` directory:
- Templated FRR configuration files.
- The static `poked` binary.
- The systemd service for adding the VIP to loopback on boot.

# License
MIT

