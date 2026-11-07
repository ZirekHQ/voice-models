# voice-models

Training recipes, configs, datasets metadata and benchmarks for Kurmanji
(Northern Kurdish, `kmr`) speech models used by Dengjen.

This repo holds code and configuration only. Model weights live on Hugging
Face and audio lives outside git; see
[Where weights and audio live](docs/modules/ROOT/pages/model-hosting.adoc).

The docs under [`docs/`](docs/modules/ROOT/pages/) are published at
<https://zirekhq.github.io/voice-models/next/>. To record your voice for a new
model, read [Record your voice](docs/modules/ROOT/pages/record-your-voice.adoc).

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
docs/                Antora docs, published to zirekhq.github.io
```

Each engine folder uses the same shape: a `README.md` with how to train and
export, and `voices/<voice-id>/` with one config per voice. Adding a voice
means adding a folder, not changing engine code.

## Current models

| Voice | Engine | Quality | Licence | Weights |
|---|---|---|---|---|
| berfin-renas | Piper | medium | [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) | [rojanu/piper-ku-berfin-renas-medium](https://huggingface.co/rojanu/piper-ku-berfin-renas-medium) |

The berfin-renas voice is trained on recordings provided by
[Zarok TV](https://zarok.tv) in partnership with Zirek.

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
