Network-Connected Serial Server
===============================
This project intends to develop a simple and (relatively) low-cost Linux-based
network-connected (Ethernet or WiFi) serial (RS-232) device, that can act as
either a console server, or emulate a serial device such as a modem.

Intended hardware features
* Multiple power sources
  * PoE
  * USB (also doubles as serial debug port)
  * External power
* WiFi connection
  * Undecided on specific chip, doesn't need to be very performant, might use
    as ESP-32 along with something like [esp-hosted](https://github.com/espressif/esp-hosted)
* Ethernet connection
  * At least 10/100, undecided on specific PHY
* Linux-capable CPU
  * Planning on using SG2002 RISC-V SOC
  * Running Linux off of micro-SD card
    * Possible option for SPI flash?
* RS-232 via DE-9
  * Port pinout is as a DCE, as this is the most likely scenario in which the
    ring indicator would be useful. NULL-modem cable/adapter can be used to switch
    to DTE pinout.
  * Using MAX3237 transceiver to allow full functionality while in DCE mode
* Status LEDs
  * Separate serlal RX and TX LEDs
  * Possible ring-indicator LED
  * Possible "remote access active" LED
* Possibly integrating a security chip like the ATECC

