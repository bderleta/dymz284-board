# dymz284-board
Dual YMZ284 synth board design using retro technology (THT elements, DIP packages). Board designed to fit Hammond 1455C802 enclosure.

![Rev 1 board render](/assets/ymz284.png)

An application of ATMega8 8-bit MCU in PDIP package capable of driving two of YMZ284 PSG chips. This is a simplified derivative of [DYM2149](https://github.com/bderleta/dym2149-board) and runs similar firmware, but there are some differences:

- PSG data inputs are driven from '595 shift register controlled via SPI, instead of `PORTA` (note: '595 used has to be capable of running at 8 MHz+, as firmware uses SPI2X, making SPI clock equal to Tosc/2; plain SN74HC595 won't make it)
- Control pin assignments and names are different
- There is no JTAG and no SPI RAM
- Instead of single INT2 button, there are two hardware-debounced interrupt triggering buttons (INT0 and INT1)

As YMZ284 has only single DAC output, there is no mixing stage present, first PSG is assigned to the left channel, second - to the right. In contrary to YM2149 chips, YMZ has clock divider permamently enabled, therefore it is necessary to provide generator twice as fast to achieve identical behavior. This device has been tested with 4 MHz and 3.579545 MHz CXOs.

![Rev 1 board render](/assets/real.jpg)
