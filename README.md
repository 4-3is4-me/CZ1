# CZ1
Jan Ostman's phase distortion module CZ1 style original code
*************************************************************

They are built on the ATtiny85 and uses the TinyAudioBootloader.

The name “Paperface” comes from the classic Serge look with white panels.

The TinyAudioBootloader makes it possible to upload new firmware through the audio out port without a programmer just replaying a wavefile at startup.

The module has 3 Analog CV jacks, 2 with attenuators and an audio out jack.

The PCB and BOM:

PCB

IC1 ATtiny85
IC2 78L05
R1 1Kohm
R2, R3, R4 22Kohm
R5, R6 10Kohm
C1 100nF
C2, C3 10uF
D1 1N4148
POT1, POT2 10Kohm Alpha 9mm
CN1, CN2, CN3, CN4 3.5mm mono switch Thonkiconn jack

 
At powerup the module waits for 5 seconds for an audio signal with firmware on the output jack. If nothing is input it starts normal operation. Otherwise it updates its firmware. No programmer required.

This HEX uses PB1, pin6 for the programming audio signal input.
The pin should be lifted to Vcc/2 with a resistor divider.

Set the fuses to 0xE1, 0xDD, 0xFE when programming.

More info on the TinyAudioBootloader can be found here:
https://github.com/ChrisMicro/TinyAudioBoot

If nothing is plugged in to the CV1/CV2 jack the knobs works as parameter dials. If they are jacked the knobs work as attenutators for any signal plugged in.

The CV3 jack can be used to input both digital and analog signals and output a digital signal.

All inputs are protected against euro voltages and the power has a reverse protection diode.

The Paperface line is of course open-source so the disclaimer:

The Phase Distortion Oscillator
The PD oscillator works like the classic Casio CZ synthesizer. In essence it is really a form of FM. At the time Yamaha had patent on their FM (or PM) synthesis so Casio had to come up with a workaround.

It works by modulating a cosine wave by a modulation index and enveloping it with a slope to remove the nasty level jump.

So it really simulates a saw wave run through a resonant lowpass filter.

The modules CV1 input is Pitch 1V/Octave and the CV2 input is the modulation index, 0.125 – 16x

The CV3 input is an audio gate input that allows you to run it with for example the Beatstep Pro without having a VCA module for some Acid patterns.

CZ1modindex
