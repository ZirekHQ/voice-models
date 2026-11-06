# Text-to-speech

One folder per engine. Each engine has `voices/<voice-id>/` for per-voice
configuration.

| Engine | Status | Why |
|---|---|---|
| [piper](piper/) | medium trained; low and high planned | Fast on CPU, ONNX export, already used by Dengjen |
| [kokoro](kokoro/) | planned | Small (82M) StyleTTS2-based model, good quality for its size |

Other candidates to evaluate against the same data and `eval/` benchmark:
Matcha-TTS, MMS-TTS (Meta, has a `kmr` checkpoint), StyleTTS2, F5-TTS. An
engine earns a folder here once there is a training recipe for it.

All engines share the text front end question: Kurmanji phonemes come from
`espeak-ng`'s `ku` voice unless an engine needs its own G2P. Record the choice
in the engine's README.
