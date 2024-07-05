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
  * Planning on ESP32-C3 via SPI (and maybe UART as fallback)
  * Use [esp-hosted](https://github.com/espressif/esp-hosted) to interface with Linux
  * Likely won't need any external flash, may design in the option just in case
* Ethernet connection
  * At least 10/100, undecided on specifics, SG2002 should already have a PHY,
    so should just need the port and magnetics (if not integrated, needs to
    support PoE).
* Linux-capable CPU
  * Planning on using SG2002 RISC-V SOC
  * Running Linux off of micro-SD card
    * Possible option for SPI flash?
* RS-232 via DE-9
  * Port pinout is as a DCE, as this is the most likely scenario in which the
    ring indicator would be useful. NULL-modem cable/adapter can be used to switch
    to DTE pinout.
  * Using MAX3237 transceiver to allow full functionality while in DCE mode
  * Headers availble to allow for custom daughter boards for different protocols
* Status LEDs
  * Separate serlal RX and TX LEDs
  * Possible ring-indicator LED
  * Possible "remote access active" LED
* Possibly integrating a security chip like the ATECC
* Possibly hardware watchdog

Use of third-party symbols/footprints
-------------------------------------

The following footprints were obtained from Digi-Key:
 * Amphenol 10067099-400LF: https://www.digikey.com/en/models/4238740
