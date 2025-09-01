# Tiny Tone PWM Audio Peripheral

Author: pranav0x0112

Peripheral index: 15

## What it does

Tiny Tone is a simple PWM-based audio tone generator peripheral for Tiny Tapeout and TinyQV.  
It allows you to generate square wave audio tones of programmable frequency and control the output via memory-mapped registers.  
The output can be connected to a speaker or buzzer for sound generation.

## Register map

|Address|Name|Access|Description|
|---|---|---|---|
|0x00|CONTROL|R/W|Control register (enable, mode, etc.)|
|0x04|FREQ|R/W|Frequency register (sets output tone frequency)|
|0x08|PWM|R|Current PWM output value (read-only)|
|0x0C|VERSION|R|Version register (read-only)|

## How to test

1. Write a value to the CONTROL register at address 0x00 to enable the tone generator.
2. Write the desired frequency value to the FREQ register at address 0x04.
3. Observe the PWM output on the `uo_out` pin(s) or connect to a speaker/buzzer.
4. Read back the PWM register at 0x08 to monitor the current output value.
5. The VERSION register at 0x0C can be read to verify the peripheral version.

## External hardware

- Optional: Speaker or piezo buzzer connected to the `uo_out` pin(s) to hear the generated tone.