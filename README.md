# Ondinha Bus Comp

**Console-style glue compressor for the mix bus and groups. Stepped ratio, attack and release, auto release, side-chain HPF and parallel mix.**

A VST3 and Audio Unit plug-in from [Ondinha](https://github.com/ondinha), a DAW 2.0: native AI tools combined with traditional sound engineering tools.

The compressor you put across the drum bus or the whole mix to make the parts sit together. It follows the classic console bus compressor recipe: a VCA, stereo-linked, with a handful of stepped settings that are hard to get wrong.

Two or three dB of gain reduction with the slow attack and auto release is usually all a mix needs.

## What it's good for

- Glue on the mix bus: ratio 2:1, attack 30 ms, release Auto, 1-3 dB of gain reduction.
- Drum bus punch: faster attack, ratio 4:1, then blend back with **Mix** for parallel compression.
- Stop the kick and bass pumping everything else: switch on the side-chain high-pass (**SC HPF**).

## Controls

| Control | Range | What it does |
|---|---|---|
| Threshold | -40 to 0 dB | Where compression starts. |
| Ratio | 1.5:1, 2:1, 4:1, 10:1 | How hard it pushes down. |
| Attack | 0.1, 0.3, 1, 3, 10, 30 ms | Slow attacks let the transients through. |
| Release | 0.1, 0.3, 0.6, 1.2 s, Auto | Auto is quick after short peaks and slow under steady compression. |
| Makeup | -6 to +18 dB | Level back after compression. |
| SC HPF | Off, 60-200 Hz | Keeps low end out of the detector. |
| Mix | 0-100 % | Dry / wet for parallel compression. |
| Knee | 0-12 dB | Soft knee width. |

## Download and install

Builds will be on the [Releases](../../releases) page.

**macOS:** copy `Ondinha Bus Comp.vst3` to `~/Library/Audio/Plug-Ins/VST3` and `Ondinha Bus Comp.component` to `~/Library/Audio/Plug-Ins/Components`, then rescan plug-ins in your DAW.

| Format | Platform |
|---|---|
| VST3 | macOS |
| Audio Unit (AU) | macOS |

Works in any VST3 or AU host: Ableton Live, Logic Pro, Reaper, Bitwig Studio, Cubase, Studio One, FL Studio and others.

## How it works

Feed-forward VCA design with stereo-linked peak sensing. Gain is computed in dB with a soft knee, and the envelope is a smooth decoupled detector (Giannoulis, Massberg and Reiss, 2012), so the gain never steps. Makeup and mix glide per sample. Double precision, no lookahead, **zero latency**.

## More Ondinha plug-ins

- [Ondinha Split EQ](https://github.com/ondinha/ondinha-split-eq): Transient / tonal split EQ: separate gain for the attack and the sustain in every band.
- [Ondinha Limiter](https://github.com/ondinha/ondinha-limiter): True-peak brickwall limiter for mastering, with an optional oversampled clipper.
- [Ondinha Unmask](https://github.com/ondinha/ondinha-unmask): Spectral side-chain ducking: dips a track only at the frequencies where the key is loud, only while it plays.
- [Ondinha Resonance](https://github.com/ondinha/ondinha-resonance): Dynamic resonance tamer for harsh mixes, vocals and guitars: pulls down narrow peaks only while they ring and leaves the broad tone alone.
- [Ondinha Imager](https://github.com/ondinha/ondinha-imager): Multiband stereo imager with mono low end: width for lows, mids and highs on phase-matched Linkwitz-Riley crossovers.
- [Ondinha Delay](https://github.com/ondinha/ondinha-delay): Tempo-synced stereo / ping-pong delay with filtered, saturated feedback and ducking, so the echoes stay out of the way of the vocal.
- [Ondinha Graphic EQ](https://github.com/ondinha/ondinha-graphic-eq): 10-band octave graphic EQ with analog-matched bells (31 Hz - 16 kHz, +-12 dB).
- [Ondinha Tube Air](https://github.com/ondinha/ondinha-tube-air): High-frequency exciter with a tube stage: adds warm even or bright odd harmonics above a frequency, under the untouched signal.

## Feedback

Found a bug or a host where it misbehaves? [Open an issue](../../issues) with your DAW, its version and your OS.
