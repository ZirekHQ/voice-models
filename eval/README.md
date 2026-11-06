# Benchmarks

Every model, whatever the engine, is measured the same way so results are
comparable.

## Latency

Measured on named reference hardware (record CPU, threads, OS, runtime):

- **Time to first audio**: ms from text in to first PCM chunk out.
- **Real-time factor (RTF)**: synthesis time / audio duration. Lower is
  better; below 1 is faster than real time.
- **Model size** on disk and **peak memory**.

## Quality

- **Intelligibility**: synthesize `sentences/`, transcribe with an STT model,
  report CER/WER against the input text.
- **Naturalness**: an automatic MOS predictor (e.g. UTMOS) as a quick check,
  plus listening tests by native speakers for release decisions.

## Layout

- `sentences/`: the fixed test set, held out of all training data.
- `results/`: one Markdown summary per run, named
  `<engine>-<voice>-<quality>-<YYYY-MM-DD>.md`. Generated audio is gitignored.
