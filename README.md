# OVCS BASE Can System RPI4

This a [custom Nerves system](https://hexdocs.pm/nerves/customizing-systems.html) for RPI4.
It adds support for CAN bus, can-utils, iproute2 and socketcand.

It is used to run the [OVCS VMS](https://github.com/open-vehicle-control-system/ovcs/tree/main/vms) software inside a vehicle.

## Upstream base

Tracks upstream [`nerves_system_rpi4`](https://github.com/nerves-project/nerves_system_rpi4)
**v2.0.3** (`nerves_system_br` 1.33.7, Erlang/OTP 28.5).

Upstream v2.0.0 changed the MicroSD/eMMC layout to A/B firmware slots
with automatic rollback, and it is a **one-way** upgrade: a device on
the older layout must be reflashed, not updated over the air. Firmware
built against this system must also call
`Nerves.Runtime.validate_firmware/0`, or every update is reverted on the
next boot.
