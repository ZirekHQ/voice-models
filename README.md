# voice-models

Training recipes, configs, datasets metadata and benchmarks for Kurmanji
(Northern Kurdish, `kmr`) speech models used by Dengjen.

This repo holds code and configuration only. Model weights live on Hugging
Face and audio lives outside git; see [docs/model-hosting.md](docs/model-hosting.md).

## Layout

```
tts/                 Text-to-speech, one folder per engine
  piper/             Piper (VITS) recipes, low / medium / high quality
    voices/<voice>/  Per-voice config: speaker, dataset, HF repo, per-quality settings
  kokoro/            Kokoro (StyleTTS2-based) experiments
    voices/<voice>/
stt/                 Speech-to-text (planned)
  whisper/           Whisper fine-tune
data/                Dataset docs and manifests (text only, no audio)
  manifests/         CSV/JSONL manifests pointing at audio stored elsewhere
eval/                Shared latency and quality benchmarks for every model
  sentences/         Fixed test sentences, kept out of every training set
  results/           Benchmark summaries, one file per model and run
docs/                Cross-cutting notes (hosting, conventions)
```

Each engine folder uses the same shape: a `README.md` with how to train and
export, and `voices/<voice-id>/` with one config per voice. Adding a voice
means adding a folder, not changing engine code.

## Current models

| Voice | Engine | Quality | Weights |
|---|---|---|---|
| berfin-renas | Piper | medium | [rojanu/piper-ku-berfin-renas-medium](https://huggingface.co/rojanu/piper-ku-berfin-renas-medium) |

## Roadmap

1. Piper `berfin-renas` at `low` and `high` beside the existing `medium`.
2. Kokoro (and other low-latency engines) trained on the same data, compared
   in `eval/` against Piper.
3. More voices from the new recordings of the recording script (see
   [data/README.md](data/README.md)).
4. STT: Whisper fine-tune for Kurmanji.

## Naming

- Voice id: lowercase, hyphenated speaker name, e.g. `berfin-renas`.
- Hugging Face repo: `<engine>-ku-<voice>-<quality>`, e.g.
  `piper-ku-berfin-renas-high`.
- Benchmark result: `eval/results/<engine>-<voice>-<quality>-<YYYY-MM-DD>.md`.
