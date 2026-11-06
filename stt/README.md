# Speech-to-text (planned)

Kurmanji is not one of Whisper's trained languages, so a Whisper model needs a
fine-tune. Candidates:

| Model | Notes |
|---|---|
| [whisper](whisper/) | Fine-tune a small/medium Whisper on Kurmanji |
| MMS / wav2vec2 | Meta MMS covers `kmr`; a CTC fine-tune is a cheap baseline |

Public data to start from: Mozilla Common Voice (Kurmanji, `kmr`). Recordings
made for TTS can be added but are single-speaker, so they help less here.

STT models are scored with WER and CER on a held-out set in `eval/`.
