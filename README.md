# dymz284-board
Dual YMZ284 synth board design using retro technology (THT elements, DIP packages). Board designed to fit Hammond 1455C802 enclosure.

![Rev 1 board render](/assets/ymz284.png)

An application of ATMega8 8-bit MCU in PDIP package capable of driving two of YMZ284 PSG chips. This is a simplified derivative of [DYM2149](https://github.com/bderleta/dym2149-board) and runs similar firmware, but there are some differences:

- PSG data inputs are driven from '595 shift register controlled via SPI, instead of `PORTA`
- Control pin assignments and names are different
- There is no JTAG and no SPI RAM
- Instead of single INT2 button, there are two hardware-debounced interrupt triggering buttons (INT0 and INT1)

![Rev 1 board render](/assets/real.jpg)
