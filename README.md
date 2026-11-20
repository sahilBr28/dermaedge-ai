> ⚠️ **RESEARCH PROTOTYPE — NOT A MEDICAL DEVICE**
>
> This software is a research prototype. It is **not** a registered medical device under
> CDSCO (India), FDA (US), CE (EU), or any other regulatory authority. It must **not** be
> used for clinical decision-making without independent validation and regulatory clearance.

# dermaedge-ai

Privacy-preserving, edge-deployed multimodal AI for skin-lesion triage. Runs entirely
offline on a Raspberry Pi 5-class device — no patient data ever leaves the clinic.

## What it does

- **On-device lesion detection** — YOLO26n, INT8-quantized ONNX, runs in < 100 ms on ARM64.
- **Multimodal triage** — Qwen2-VL-2B (Q4_K_M GGUF, ~1 GB) reads the lesion image + a short
  clinical note and outputs a triage recommendation (benign / suspicious / urgent referral).
- **Federated learning** — model updates are aggregated across simulated clinic nodes without
  raw images leaving the edge device.
- **RAG explanations** — a local FAISS index retrieves similar anonymised historical cases and
  a small LLM (Llama 3.2 1B via Ollama) writes a plain-language referral justification.

## Architecture
