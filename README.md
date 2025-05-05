# 🎙️ YouTube Arabic Transcriber with Whisper Large-v3

This repository provides a simple pipeline to transcribe **long Arabic (or multilingual) YouTube videos** using [OpenAI's Whisper large-v3](https://huggingface.co/openai/whisper-large-v3) model via Hugging Face Transformers. It automates the process of downloading audio, chunking it into Whisper-compatible segments, and transcribing it using GPU acceleration.

---

## 🚀 Features

- ✅ Download audio from any YouTube video using `yt-dlp`
- ✅ Convert to high-quality 16kHz WAV format using `ffmpeg`
- ✅ Automatically chunk audio into 30-second segments
- ✅ Transcribe each chunk using `Whisper large-v3`
- ✅ Save the full transcription to a text file
- ✅ Supports Arabic and 98+ other languages
- ✅ Fully compatible with Google Colab

---

## 🛠️ Installation

### In Google Colab or Linux environment:

```bash
pip install pytube pydub moviepy transformers accelerate datasets[audio] torchaudio yt-dlp
apt update && apt install -y ffmpeg
