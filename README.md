
# 🎙️ YouTube Transcriber using Whisper Large-v3

This repository provides a Colab-ready pipeline for automatically transcribing **audio from YouTube videos** using [OpenAI's Whisper large-v3 model](https://huggingface.co/openai/whisper-large-v3) via Hugging Face Transformers.

## 🧠 What It Does

Given a YouTube link, this notebook:
1. Downloads the best-quality audio using `yt-dlp`.
2. Converts the audio to 16 kHz mono WAV format using `ffmpeg`.
3. Splits the audio into 30-second chunks to fit Whisper's context window.
4. Transcribes each chunk using `Whisper large-v3`.
5. Combines the transcriptions into one file.
6. Saves the result as `transcription.txt`.

---

## 🔧 Requirements

These are the libraries you are going to use before running the code:

```bash
pip install pytube pydub moviepy transformers accelerate datasets[audio] torchaudio yt-dlp
apt update && apt install -y ffmpeg
```

---

## 🚀 Model Used

- **Model**: [`openai/whisper-large-v3`](https://huggingface.co/openai/whisper-large-v3)
- **Framework**: Hugging Face 🤗 Transformers
- **Capabilities**:
  - Speech recognition in 99 languages
  - Robust transcription with noisy and accented audio
  - Zero-shot generalization

---

## 📂 File Outputs

- `converted_audio.wav`: Clean WAV audio generated from YouTube.
- `chunk_*.wav`: Temporary 30-second audio chunks (auto-deleted after transcription).
- `transcription.txt`: Full transcript of the YouTube video.

---

## ▶️ Usage

Paste your YouTube link in the code cell like so:

```python
youtube_link = "https://www.youtube.com/watch?v=YOUR_VIDEO_ID"
process_youtube_video(youtube_link)
```

The transcript will be saved in your working directory as `transcription.txt`.

---

## 📌 Notes

- This pipeline uses GPU acceleration when available (`torch.float16`).
- Whisper handles language detection automatically.
- To translate speech instead of transcribing it, modify the `pipe(...)` call using `generate_kwargs={"task": "translate"}`.

---

## 📜 License

This repo uses OpenAI’s Whisper under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0).

---

## ✍️ Author

This project was assembled for efficient multilingual speech transcription from long-form YouTube videos using modern open-source tools by **Muhammad S. Abdo**
