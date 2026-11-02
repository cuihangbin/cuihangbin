# Hi, I'm Cui Hangbin 👋

I work on LLM inference infrastructure, with a focus on GPU kernels, attention backends, and quantization. My open-source work centers on **FlashInfer, vLLM, and SageAttention**.

## What I work on

- **FlashInfer:** Gated DeltaNet (GDN) prefill kernels, SM120 CuTe backend development, and profiling.
- **vLLM:** attention backend integration, FP8 quantization correctness, and DeepGEMM integration.
- **SageAttention:** sequence-length-aware attention and paged KV-cache decode paths for CUDA Graphs.
- **Next focus:** investigate Model Runner V2 (MRV2) performance through profiling and reproducible benchmarks.

## Open-source contributions

Selected upstream PRs. Status checked on **November 2, 2026**; follow the links for current progress.

| Project | Contribution | Status |
| --- | --- | --- |
| FlashInfer | [#6342 — Experimental SM120 CuTe GDN prefill backend](https://github.com/flashinfer-ai/flashinfer/pull/6342) | Merged |
| vLLM | [#55732 — SAGE_ATTN backend integration](https://github.com/vllm-project/vllm/pull/55732) | Open |
| SageAttention | [#402 — SM89/SM120 sequence lengths and paged KV decode for CUDA Graphs](https://github.com/thu-ml/SageAttention/pull/402) | Open |
| vLLM | [#52753 — Pin the static FP8 quantization pattern to `group_shape=None`](https://github.com/vllm-project/vllm/pull/52753) | Open |
| vLLM | [#49928 — Keep DeepGEMM FP8 quantization inside an opaque op for TMA scales](https://github.com/vllm-project/vllm/pull/49928) | Open |

The FlashInfer SM120 backend is experimental and explicitly selected. Its validation and performance results are scoped to the hardware and workloads documented in the PR.

## Projects & profiling

- [GDN prefill SM120 traces](https://github.com/cuihangbin/gdn-prefill-sm120-traces) — RTX 6000D profiler traces comparing FLA and FlashInfer fused GDN prefill paths.
- Development forks: [FlashInfer](https://github.com/cuihangbin/flashinfer) · [vLLM](https://github.com/cuihangbin/vllm) · [SageAttention](https://github.com/cuihangbin/SageAttention).

## Technical interests

GPU kernel optimization · Attention and linear attention · FP8 quantization · CUDA Graphs · LLM serving performance

## Follow my work

[FlashInfer PRs](https://github.com/flashinfer-ai/flashinfer/pulls?q=is%3Apr+author%3Acuihangbin) · [vLLM PRs](https://github.com/vllm-project/vllm/pulls?q=is%3Apr+author%3Acuihangbin) · [SageAttention PRs](https://github.com/thu-ml/SageAttention/pulls?q=is%3Apr+author%3Acuihangbin)
