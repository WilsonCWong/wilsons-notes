<b><a id="top" href="../../../README.md">< Back</a></b>

# Synthesizers<!-- omit in toc -->
- [What are Synthesizers?](#what-are-synthesizers)
- [Monophonic vs Polyphonic](#monophonic-vs-polyphonic)
- [Types of Synthesizers](#types-of-synthesizers)
  - [Subtractive Synthesis](#subtractive-synthesis)
  - [Additive Synthesis](#additive-synthesis)
  - [FM (Frequency Modulation)](#fm-frequency-modulation)
- [S & S (Sample & synthesis)](#s--s-sample--synthesis)
- [Wavetable, Wave Sequencing & Vector Synthesis](#wavetable-wave-sequencing--vector-synthesis)
- [Phase Distortion](#phase-distortion)
- [Physical Modeling / Soft Synthesis / Virtual Synthesis](#physical-modeling--soft-synthesis--virtual-synthesis)
- [References](#references)


## What are Synthesizers?
Synthesizer &mdash; often referred to by its shorthand, synth &mdash; are electronic devices that can create sound vibrations that can be manipulated to give different notes (speed, pitch, etc.). This is done by feeding electricity to a circuit called an oscillator. This signal can then amplified and passed through a speaker, converting it into vibrations in the air (sound) that we hear. We call this an analog synth, as it uses electricity and physical oscillators to produce analog signals.

Digital synths are the same, but the oscillators are digital, so the oscillations produced are just 1s and 0s. The signal produced is then converted to an analog signal and then audio (through speakers). 

Digital synths tend to have less of the "warmth" and character of analog sounds (they are not as organic since analog synths can have imperfections due to varying voltages), but they don't suffer from calibration issues, are cheaper, less heavy (or weightless if software), and can do a lot more. Digital synths exist that mimic analog synths, too.

## Monophonic vs Polyphonic
Monophonic synths can only play one note at a time, where as polyphonic synths can play multiple. Most analog synths were monophonic, due to the extra circuitry and electronics required for polyphony. However, digital synths have made polyphony easy to implement.

## Types of Synthesizers

### Subtractive Synthesis
Subtractive synthesis was what was originally used by analog synths, hence it is also referred to as analog synthesis.

It uses the oscillator to create electrical pressure soundwaves which are then processed by a filter to subtract away frequencies from it.

Think of the original waveform as a marble statue; the filter is the chisel.

### Additive Synthesis
Additive synthesis is the emulation of the way sound is created in nature. It has multiple oscillators producing a simple sine wave, which can be manipulated individually.

Combining these sine waves together can form a complex waveform. This emulates the way natural sound is created with multiple harmonics.

**What the heck's harmonics?**

Harmonics are frequencies that are whole number multiples of another signal. This other signal is usually the fundamental frequency, which is the frequency with the most energy in that specific sound. This helps you recognize the pitch. Harmonics complement the fundamental frequency and they sound nice and not out of place. Note that some sounds don't have a fundamental frequency (lack of pitch). These sounds are called noise. For example, white noise, wind, waves at the shore, etc.

Keep in mind that sound doesn't just come out at one frequency, it is made up of many individual frequencies. That's why the same note on a violin sounds different than a piano. The harmonics (as well as the inharmonic) frequencies all contribute to the "timbre" of the instrument. All sounds in nature have harmonics, though you can synthetically create sine waves with only one pitch/frequency, which doesn't have harmonics.

### FM (Frequency Modulation)
Frequency modulation is similar to additive synthesis, in that it uses 6 sine wave creating oscillators (called Operators in FM).

The difference ends there though, because instead of combining the sine waves, the output of one operator is set to modulate or "wobble" to the next, which goes on in a chain until a complex waveform is produced by the final oscillator, called the Output Operator.

## S & S (Sample & synthesis)
S & S synthesis uses pre-recorded samples as its sound source. It's best suited for creating sounds by combining samples of real instruments with samples created from other forms of synthesis.

## Wavetable, Wave Sequencing & Vector Synthesis
This form of synthesis is ideal for slow pad-like and rhythmical evolving sounds. The basic concept is that it sequentially cycles through (wave sequencing) or morphing between (vector synthesis) a number of waveforms overtime. These waveforms are digitally stored in a "wave table" and may be samples or digital "models".

## Phase Distortion
Phase distortion uses an algorithm to create a sine wave, then a second algorithm to distort the shape of the sine wave to create a new waveform.

It is best used with other forms of synthesis, such as FM, where creating variations of sine waves is useful for creating new tones.

## Physical Modeling / Soft Synthesis / Virtual Synthesis
Utilizes powerful digital signal processors (DSPs) and high quality digital to analog conveters (D.A.Cs). The software version is called a soft synth or plug-in.

When a note is triggered, the DSP mathematically calculates in real time the stream of digital data required to create the sound it will output through the D.A.Cs.

A physical modeling synthesiser is actually generating the binary data (sound) in real time, tailored and responsive to the nuances of the performance arriving from a controller (usually a MIDI keyboard).

This form of synthesis can emulate any other form of synthesis. It's range of sound is only limited by the available software models.

You can make a lot of cool, wacky instruments which this, such as snare drums that change pitch, or even instruments that don't exist. It's also used to emulate physical instruments as closely as possible<sup>[1](#1)</sup>.

<sup>1</sup> <span id="1">https://en.wikipedia.org/wiki/Karplus%E2%80%93Strong_string_synthesis</span>

## References
- http://www.planetoftunes.com/synthesis/synthesis-types.htm
- http://synthesizeracademy.com/what-is-a-synthesizer/
- http://synthesizeracademy.com/types-of-synthesizers/
- https://en.wikipedia.org/wiki/Karplus%E2%80%93Strong_string_synthesis
- And a bunch of other things I forgot to note down when researching (Sorry! It's not a university paper, okay?)