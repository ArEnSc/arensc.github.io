---
layout: post 
title: ML and Audio Primitives Notes
categories: [AI Agents]
excerpt_separator: <!--more-->
---

# 🎧 Audio Engineering Basics – PCM, Sample Rate, Bit Depth
After working on Zero-Shot TTS (cascading), Sesame (multimodal), and a host of other pipelines, I've learned there are a few primitives you have to commit to muscle memory. When you can picture the inputs and outputs—down to the units and shapes—you can sanity-check a model's behavior in seconds.

<!--more-->

## 1. Mono vs Stereo
Think of channels as lanes on an audio freeway: the more lanes, the more parallel signals you have to juggle.
- **Mono** pushes the same signal everywhere.
- **Stereo** keeps left and right independent—each at the full sample rate.
- **5.1** (or any surround format) simply adds more lanes.
> Quick gut check: 48 kHz stereo means each ear still gets 48,000 samples every second.

---

## 2. Sample Rate
Sample rate is the metronome driving how often you capture amplitude. Speech stacks usually sit at 16 kHz; music master chains often ride at 44.1 or 48 kHz, and experimental rigs run higher when latency is a luxury.

---

## 3. Bit Depth
Bit depth is how many “clicks” your amplitude knob has.
- **16-bit PCM (int16)** lives in integer land: `-32768` to `32767`, two bytes per sample.
- **32-bit Float PCM (float32)** keeps everything normalized between `-1.0` and `+1.0`, with more headroom for DSP math.
> Translation: more bits = finer amplitude resolution, so transient details survive mixdowns.

---

## 4. Core Formulas
These are the sanity checks I reach for when a tensor feels off.

```text
duration_ms = (samples / sample_rate) * 1000
```

```text
samples = (sample_rate * duration_ms) / 1000
```

```text
chunk_duration_ms = (480 / 24000) * 1000  # 480-sample chunk at 24 kHz ≈ 20 ms
```

---

## 5. Data Rate Examples (Uncompressed PCM)
Once you know the frame composition, bandwidth math is just multiplication.

| Sample Rate | Bit Depth | Channels | Bytes/sec | kB/sec | MB/min |
|-------------|-----------|----------|-----------|--------|--------|
| 48 kHz      | 16-bit    | Mono     | 96,000    | 96     | 5.76   |
| 48 kHz      | 16-bit    | Stereo   | 192,000   | 192    | 11.52  |
| 48 kHz      | Float32   | Mono     | 192,000   | 192    | 11.52  |
| 48 kHz      | Float32   | Stereo   | 384,000   | 384    | 23.04  |

---

## 6. Frames in PCM
In PCM audio, a frame is the snapshot across every channel at a single instant.
- **Frame** = one sample from each channel.
- **Sample** = the amplitude value for one channel at that instant.

So:
- Mono → 1 channel → 1 sample per frame.
- Stereo → 2 channels → left + right samples per frame.
- 5.1 surround → 6 channels → six samples per frame.
> Frames keep multi-channel tensors aligned. One missing channel value and the whole frame is corrupt.

---

## 7. Frame Size Example
Let's walk the math for a frame you actually ship: **48 kHz, stereo, float32, 20 ms.**

```text
samples_per_channel = (48000 * 20) / 1000   # 960 samples
```

```text
total_samples = samples_per_channel * 2     # stereo → 1920 samples
```

```text
bytes = total_samples * 4                   # float32 → 7680 bytes
```

---

## ✅ Summary
- Sample rate = time resolution; bit depth = amplitude resolution.
- Frames bundle every channel’s sample at a moment so tensors stay synchronized.
- Keep those formulas in reach and you’ll know instantly whether a model output is reasonable—or about to blow up your real-time budget.

Draft notes for ML and audio primitives will be added here.
