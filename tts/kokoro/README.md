# Kokoro

Kokoro is a small StyleTTS2-based model (82M parameters). It has no Kurmanji
support out of the box, so the work is a fine-tune on our data with a Kurmanji
phoneme front end.

Open questions to settle before training, record answers here:

- G2P: `espeak-ng` `ku` voice or a dedicated Kurmanji G2P.
- Base checkpoint and training code to fine-tune from.
- Export path for on-device use (ONNX) and its latency in `eval/`.

Per-voice configs go in `voices/<voice-id>/`.
