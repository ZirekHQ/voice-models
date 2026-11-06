# Kurmanji recording script

Sentences for speakers to read when recording new Kurmanji TTS voices.

- `kurmanji_recording_script.csv`: all 12,944 sentences, columns
  `id,batch,part,text`. Ids look like `kmr_00001`. `part` is `core` or
  `extension`.
- `batches/batch_NN.txt`: the same sentences split into 13 recording
  sessions of about one hour each, one `id<TAB>text` line per sentence.
  Batches 01 to 10 are the 10 hour core; 11 to 13 are optional extensions.

## How the script was built

The text is mostly Common Voice Kurmanji sentences (CC0) plus the lines
from the berfin-renas dataset. Sentences are ordered so batch 01 alone
covers every common sound pair, and by batch 05 each pair has at least 10
examples. Sentences with rare foreign names are pushed to the end. Hour
counts are estimates until batch 01 is recorded.

Keep the ids stable: manifests in `../manifests/` refer to them. Sentences in
`../../eval/sentences/` must not be added here.

## License

The text is dedicated to the public domain under CC0 1.0. See
[LICENSE](LICENSE).
