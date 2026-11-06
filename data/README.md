# Data

Only text lives here: dataset descriptions and manifests. Audio stays in
external storage (see `docs/model-hosting.md`).

## Recording script

The Kurmanji recording script is `kurmanji_recording_script.csv` with columns
`id,batch,part,text` (ids like `kmr_00001`), split into 13 batch files of
about 56 KB each for recording sessions. It is kept in the project's shared
files under `recording-script/` for now.

## Manifests

`manifests/` holds one file per dataset, mapping utterance ids to audio and
text. Suggested CSV columns:

```
id,speaker,audio_path,text,duration_s,split
```

`split` is `train`, `val` or `test`. Sentences in `eval/sentences/` must never
appear in a `train` split.

## Datasets

| Name | Speaker(s) | Hours | Used by |
|---|---|---|---|
| berfin-renas | berfin-renas | TODO | Piper medium |
