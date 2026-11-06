# Piper

Piper is VITS exported to ONNX. Quality levels differ in model size and
sample rate:

| Quality | Sample rate | Notes |
|---|---|---|
| low | 16 kHz | Smallest, fastest; for low-end devices |
| medium | 22.05 kHz | Current `berfin-renas` model |
| high | 22.05 kHz | Larger model, best quality, slower |

The usual route is to fine-tune from an existing Piper checkpoint of the same
quality rather than train from scratch.

## Layout

- `voices/<voice-id>/voice.yaml`: speaker, dataset, phonemizer, and settings
  per quality level.

Training scripts and exact commands are added here as each quality level is
trained; record the Piper version used.
