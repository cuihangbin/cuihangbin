<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=22&duration=2600&pause=900&color=00FF41&background=0D1117&center=true&vCenter=true&width=900&height=70&lines=Hi%2C+I+am+Hangbin+%2F+cuihangbin%3BFlashInfer+Kernel+Engineering%3BCUDA+Kernel+Optimization%3BSGLang+%2F+vLLM+Inference+Optimization%3BFP8+Quantization+%26+Attention+Backends" alt="Hangbin — FlashInfer kernel engineering, CUDA optimization, SGLang and vLLM inference" />

</div>

# Hi, I'm Hangbin 👋

I work on LLM inference infrastructure, with a focus on GPU kernels, attention backends, and quantization. My open-source work centers on **SGLang, FlashInfer, vLLM, and SageAttention**.

## What I work on

- **SGLang:** Attention DP routing and load accounting, plus SM90 FA3 FP8 kernel performance and correctness.

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

## SGLang contributions

Status checked on **November 17, 2026**.

| Upstream PR | Contribution | Development branch | Status |
| --- | --- | --- | --- |
| [SGLang #50088](https://github.com/sgl-project/sglang/pull/50088) | Count the unprefilled portion of chunked requests in `total_tokens` routing load. | [`fix/dp-total-tokens-chunked-req`](https://github.com/cuihangbin/sglang/tree/fix/dp-total-tokens-chunked-req) | Open · Awaiting review |
| [sgl-flash-attn #55](https://github.com/sgl-project/sgl-flash-attn/pull/55) | Recover SM90 FA3 FP8 paged hdim256 performance with chunked two-level P@V accumulation while retaining the precision fix. | [`fp8-paged-hdim256-chunked-pv`](https://github.com/cuihangbin/sgl-flash-attn/tree/fp8-paged-hdim256-chunked-pv) | [Merged into `sgl-kernel`](https://github.com/sgl-project/sgl-flash-attn/commit/a1f7f16c8f23a7eb2775febb265e4e7f275f7f93) |

- **Reproducible DP routing benchmarks:** [scripts, commands, environment, and raw results](https://github.com/cuihangbin/sglang/tree/a7eaee3e39d831fb97c3fcf360e3c97bfb0d1f39/benchmark/dp_attention_routing). The benchmark material is maintained separately from the fix.
- Validation uses H20 GPUs. Performance results and streaming-latency trade-offs are documented in the PRs; gains are specific to the tested workloads.

## Projects & profiling

- [GDN prefill SM120 traces](https://github.com/cuihangbin/gdn-prefill-sm120-traces) — RTX 6000D profiler traces comparing FLA and FlashInfer fused GDN prefill paths.
- Development forks: [FlashInfer](https://github.com/cuihangbin/flashinfer) · [vLLM](https://github.com/cuihangbin/vllm) · [SageAttention](https://github.com/cuihangbin/SageAttention).

## Technical interests

GPU kernel optimization · Attention and linear attention · FP8 quantization · CUDA Graphs · LLM serving performance

## Follow my work

[FlashInfer PRs](https://github.com/flashinfer-ai/flashinfer/pulls?q=is%3Apr+author%3Acuihangbin) · [vLLM PRs](https://github.com/vllm-project/vllm/pulls?q=is%3Apr+author%3Acuihangbin) · [SageAttention PRs](https://github.com/thu-ml/SageAttention/pulls?q=is%3Apr+author%3Acuihangbin)
