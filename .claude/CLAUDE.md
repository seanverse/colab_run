# Project: Colab T4 Model Testing

## Purpose

Use Google Colab T4 GPU instances to benchmark small open-source models. NOT local execution — every notebook targets Colab runtime.

## Workflow

1. User creates `.ipynb` notebook in this repo
2. Notebook uploaded to Google Colab via VSCode Colab extension
3. Colab connects to T4 runtime, runs cells, produces results
4. Audio/output files downloaded back, notebooks committed

## Notebook Rules

- Every notebook must be self-contained (install deps in first cells)
- Target hardware: T4 GPU (15GB VRAM, fp16)
- Models must be publicly downloadable (HuggingFace / ModelScope / GitHub)
- Include benchmark harness: timing, VRAM, RTF, per-sentence metrics
- Output audio saved to `/content/tts_outputs/` in Colab runtime
- Cell 0 always: `%pip install` ALL deps (common + model-specific) — use `%pip` not `!pip`
- Cell 1 always: GPU check + common setup + imports (no pip in this cell)

## File Naming

- `{domain}_{focus}_bench.ipynb` — e.g. `tts_zh_en_sota_bench.ipynb`
- Keep test sentences small but representative
- Chinese + English mixed text preferred

## VSCode Setup

Required extension: **Colab (Google Colab)** — connects VSCode to Colab runtime.
Install from VSCode marketplace, then use "Connect to Colab" command.

## Model Selection Criteria

- Third-party dependencies must be installable at runtime; model weights must be publicly downloadable from HuggingFace, ModelScope, or equivalent platforms.
- Installable via `!pip install` or a straightforward `!git clone` + `!pip install .` workflow (no complex build toolchains).
