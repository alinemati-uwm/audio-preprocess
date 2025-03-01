# Fish Audio Preprocessor

[![PyPI Version](https://img.shields.io/pypi/v/fish-audio-preprocess.svg)](https://pypi.python.org/pypi/fish-audio-preprocess)


# Audio Processing Scripts

This repository contains various scripts for **audio processing**. The main features include:

## Features

- [x] **Video/Audio to WAV**
  - Converts video or audio files into the **WAV** format.
  - Supports common formats such as **MP3, MP4, AAC, and more**.
  - Likely uses **FFmpeg** or similar libraries for conversion.

- [x] **Audio Vocal Separation**
  - Separates **vocals** and **instrumental** parts of an audio file.
  - Uses deep learning models such as:
    - **Spleeter** (by Deezer)
    - **Demucs** (by Facebook AI)
  - Useful for karaoke, remixing, and speech enhancement.

- [x] **Automatic Audio Slicing**
  - Automatically detects **silence** and splits the audio into segments.
  - Likely uses:
    - **Silence detection algorithms** (e.g., FFmpeg’s `silencedetect`).
    - **Energy-based segmentation** (detecting low-energy regions).
  - Helps with podcast editing, speech processing, and dataset creation.

- [x] **Audio Loudness Matching**
  - Normalizes the **loudness** of multiple audio files to a consistent level.
  - Uses standard loudness measurement techniques:
    - **LUFS (Loudness Units Full Scale) normalization**.
    - **RMS (Root Mean Square) normalization**.
  - Ensures a uniform listening experience.

- [x] **Audio Data Statistics**
  - Extracts important metadata such as:
    - **Total duration (length)**.
    - **Sample rate, bit depth, and number of channels**.
  - Useful for analyzing large datasets and preprocessing for ML models.

- [x] **Audio Resampling**
  - Converts audio files to different sample rates (e.g., **48kHz → 16kHz**).
  - Uses resampling techniques like:
    - **FFmpeg resampler (`aresample` filter)**.
    - **SoX resampler** for high-quality conversions.
  - Commonly used in **Automatic Speech Recognition (ASR)** and dataset preparation.

- [x] **Audio Transcribe (.lab)**
  - Converts speech audio into **text transcriptions** stored in `.lab` files.
  - `.lab` format is commonly used in **speech processing** to store text aligned with timestamps.
  - May utilize:
    - **Whisper** (OpenAI’s ASR model).
    - **Kaldi** (for forced alignment and ASR tasks).

- [x] **Audio Transcribe via FunASR**
  - Uses **FunASR**, a speech recognition model developed by **Alibaba’s AI Lab**.
  - To enable this feature, use the flag:  
    ```sh
    --model-type funasr
    ```
  - Supports **real-time transcription** and **batch processing**.
  - Detailed usage can be found in the **code documentation**.
    
- [ ] Audio transcribe via WhisperX
- [ ] Merge .lab files (example: `fap merge-lab ./dataset list.txt "{PATH}|spkname|JP|{TEXT}"`)

([ ] indicates not completed, [x] indicates completed)

**This code has been tested on Ubuntu 22.04 / 20.04 + Python 3.10. If you encounter problems on other versions, feedback is welcome.**

## Getting Started:

```
pip install -e .
fap --help
```

## Reference

- [Batch Whisper](https://github.com/Blair-Johnson/batch-whisper)
