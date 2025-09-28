---
layout: post 
title: ML and Audio Primitives Notes
categories: [AI Agents]
excerpt_separator: <!--more-->
---

# 🎧 Audio Engineering Basics – PCM, Sample Rate, Bit Depth
After working on Zero-Shot TTS, Sesame (multimodal), and a host of other pipelines, I've learned there are a few primitives you have to commit to muscle memory. Understanding how the model inputs and outputs are shaped—and being able to calculate what those shapes mean in practice—is the baseline. Here are the things I make sure stay automatic.

## 1. Mono vs Stereo
Your Speakers or input should generally would be mono as most of the time the data models capture for input would only fall in mono. Then they are doubled at playback time.
- **Mono** = 1 channel (same signal to all speakers).  
- **Stereo** = 2 channels (Left + Right), each channel independent.  
- Example: 48 kHz stereo → left = 48k samples/sec, right = 48k samples/sec.
---

## 2. Sample Rate
- Number of audio samples per second **per channel**.  
- Common rates: 8k (phone), 16k (speech/VoIP), 44.1k (CD), 48k (studio), 96k+.  
---

## 3. Bit Depth
Generally the data will be in these two forms. 
Defines how precise each sample is stored.

- **16-bit PCM (int16)**
  - Range: `-32768` … `+32767`
  - 65,536 total steps
  - 2 bytes per sample

- **32-bit Float PCM (float32)**
  - Range: `-1.0` … `+1.0` (normalized)
  - Effective precision ~24 bits
  - 4 bytes per sample

---

## 4. Core Formulas

- **Duration from Samples in ms**
duration_ms = (samples × 1000) / sample_rate

**Samples from Duration**
samples = (sample_rate × duration_ms) / 1000

---

## 5. Data Rate Examples (Uncompressed PCM)

| Sample Rate | Bit Depth | Channels | Bytes/sec | kB/sec | MB/min |
|-------------|-----------|----------|-----------|--------|--------|
| 48 kHz      | 16-bit    | Mono     | 96,000    | 96     | 5.76   |
| 48 kHz      | 16-bit    | Stereo   | 192,000   | 192    | 11.52  |
| 48 kHz      | Float32   | Mono     | 192,000   | 192    | 11.52  |
| 48 kHz      | Float32   | Stereo   | 384,000   | 384    | 23.04  |

---

## 6. Frames in PCM

In PCM audio, a frame groups one sample from each channel:

- Frame = one sample per channel at a given moment
- Sample = the amplitude value for a single channel at that moment

So:
- Mono → 1 channel → 1 sample per frame
- Stereo → 2 channels → left + right samples per frame
- 5.1 surround → 6 channels → six samples per frame

---

## 6. Frame Size Example

**48 kHz, Stereo, Float32, 20 ms frame:**
- Samples/channel = `(48000 × 20) / 1000 = 960`  
- Total samples = `960 × 2 = 1920`  
- Bytes = `1920 × 4 = 7680 bytes`  

---

## ✅ Summary
- Sample rate = **time resolution** (samples per sec).  
- Bit depth = **amplitude resolution** (how precise each sample is).  
- Stereo = both ears get the **full sample rate**, not split.  
- 16-bit PCM uses fixed integers.  
- Float32 PCM uses normalized `-1.0 … +1.0` with much finer precision.  

<!--more-->

Draft notes for ML and audio primitives will be added here.
