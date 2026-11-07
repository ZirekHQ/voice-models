# Data

Only text lives here: dataset descriptions and manifests. Audio stays in
external storage (see
[`docs/modules/ROOT/pages/model-hosting.adoc`](../docs/modules/ROOT/pages/model-hosting.adoc)).

## Recording script

The Kurmanji recording script lives in [`recording-script/`](recording-script/):
`kurmanji_recording_script.csv` with columns `id,batch,part,text` (ids like
`kmr_00001`), split into 13 batch files of about one hour each for recording
sessions. Speakers follow the
[recording guide](../docs/modules/ROOT/pages/record-your-voice.adoc).
The text is CC0 1.0 (public domain); see
[`recording-script/README.md`](recording-script/README.md).

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
