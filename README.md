# Nuked-OPF2
"High accuracy" Yamaha YM5173(OPF2) emulator.

The YM5173 is a fantasy chip based on the YM2612 used in Sega MegaDrive(Genesis) and FM Towns.

# Features:
- Removed SSG-EG (it is kinda useless)

- The YM2612 merged with the OPL3 and the OPZ, so, now, it is an YM2612 with all OPL3 waveforms (except the derived square) and all OPZ waveforms!!

- Based on YM3438 die shot reverse engineering and thus provides very high emulation accuracy as long you don't use extra waveforms.

- Cycle-accurate.

- Undocumented registers/features emulation.
- no more SSG-EG, but CSM mode emulation.
- Compatible with the YM2612 if you don't use extra waveforms.

# API documention
```
void OPF2_Reset(ym3438_t *chip) - Reset emulated chip
void OPF2_Clock(ym3438_t *chip, Bit32s *buffer) - Advances emulated chip state by 1 internal clock(6 master clocks). Writes signed 9-bit MOL, MOR pin states to buffer. 
void OPF2_Write(ym3438_t *chip, Bit32u port, Bit8u data) - Write 8-bit data to port.
void OPF2_SetTestPin(ym3438_t *chip, Bit32u value) - Set TEST pin value.
Bit32u OPF2_ReadTestPin(ym3438_t *chip) - Read TEST pin value.
Bit32u OPF2_ReadIRQPin(ym3438_t *chip) - Read IRQ pin value.
Bit8u OPF2_Read(ym3438_t *chip, Bit32u port) - Read chip status.
```