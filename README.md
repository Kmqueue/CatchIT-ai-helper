# CatchIT AI helper

Files for the optional AI bobber detection of CatchIT (a fishing helper for CatchIT).
CatchIT downloads them once on request and checks them against the checksums in `ai-manifest.ini`.
Everything runs locally on the user's computer; nothing is sent anywhere.

## Release files (see Releases, tag `ai-v1`)

| File | What it is |
|---|---|
| `ai-manifest.ini` | names, sizes and SHA256 of the two files below, read by CatchIT |
| `catchit-ai-helper.zip` | `CatchITAi.exe` (self-contained, no .NET needed) with ONNX Runtime and DirectML |
| `model-fp32.onnx` | the detector: OWLv2 image tower and heads exported to ONNX, text queries baked in (about 360 MB) |

The helper finds the bobber in a screenshot with the model, on a DirectML graphics card (AMD, NVIDIA, Intel) or on the CPU.

## Licenses

- Model: OWLv2 (`google/owlv2-base-patch16-ensemble`), Copyright Google, Apache License 2.0 - see `LICENSE-Apache-2.0.txt`.
  The ONNX file is a converted derivative: only the image tower and heads are kept, the text queries are precomputed.
- ONNX Runtime (MIT) and DirectML, Copyright Microsoft; .NET runtime (MIT), Copyright .NET Foundation and contributors.
  See `NOTICE.txt`.
