<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=22&duration=2600&pause=900&color=00FF41&background=0D1117&center=true&vCenter=true&width=900&height=70&lines=Hi%2C+I+am+Hangbin+%2F+cuihangbin%3BFlashInfer+Kernel+Engineering%3BCUDA+Kernel+Optimization%3BSGLang+%2F+vLLM+Inference+Optimization%3BFP8+Quantization+%26+Attention+Backends" alt="Hangbin — FlashInfer kernel engineering, CUDA optimization, SGLang and vLLM inference" />

</div>

# Hi, I'm Hangbin 👋

I work on LLM inference infrastructure, with a focus on GPU kernels, attention backends, and quantization. My open-source work centers on **SGLang, FlashInfer, vLLM, and SageAttention**.

### Featured upstream contributions

<a href="https://github.com/sgl-project/sglang/pull/50088"><img src="https://avatars.githubusercontent.com/u/147780389?s=64&amp;v=4" width="24" height="24" alt="" /> <strong>SGLang #50088</strong></a> — DP routing load accounting for chunked prefill · Merged

<a href="https://github.com/flashinfer-ai/flashinfer/pull/6342"><img src="https://avatars.githubusercontent.com/u/145061914?s=64&amp;v=4" width="24" height="24" alt="" /> <strong>FlashInfer #6342</strong></a> — Experimental SM120 CuTe GDN prefill backend · Merged

### ./current_work

| Area | Current work |
| --- | --- |
| Frameworks | SGLang attention DP routing and load accounting; vLLM attention backend integration, FP8 quantization correctness, DeepGEMM integration, and Model Runner V2 profiling. |
| Kernels | FlashInfer Gated DeltaNet prefill on SM120; SM90 FA3 FP8 paged attention; SageAttention sequence-length handling and paged KV-cache decode for CUDA Graphs. |

### ./selected_systems

#### Frameworks

| Project | Contribution | Status |
| --- | --- | --- |
| SGLang | Count the unprefilled portion of chunked requests in `total_tokens` routing load. [PR #50088](https://github.com/sgl-project/sglang/pull/50088) · [Development branch](https://github.com/cuihangbin/sglang/tree/fix/dp-total-tokens-chunked-req) · [Reproducible benchmarks](https://github.com/cuihangbin/sglang/tree/a7eaee3e39d831fb97c3fcf360e3c97bfb0d1f39/benchmark/dp_attention_routing). | Merged |
| vLLM | [#55732 — SAGE_ATTN backend integration](https://github.com/vllm-project/vllm/pull/55732) | Open |
| vLLM | [#52753 — Pin the static FP8 quantization pattern to `group_shape=None`](https://github.com/vllm-project/vllm/pull/52753) | Open |
| vLLM | [#49928 — Keep DeepGEMM FP8 quantization inside an opaque op for TMA scales](https://github.com/vllm-project/vllm/pull/49928) | Open |

#### Kernels

| Project | Contribution | Status |
| --- | --- | --- |
| FlashInfer | [#6342 — Experimental SM120 CuTe GDN prefill backend](https://github.com/flashinfer-ai/flashinfer/pull/6342) | Merged |
| SageAttention | [#402 — SM89/SM120 sequence lengths and paged KV decode for CUDA Graphs](https://github.com/thu-ml/SageAttention/pull/402) | Open |
| sgl-flash-attn | Recover SM90 FA3 FP8 paged hdim256 performance with chunked two-level P@V accumulation while retaining the precision fix. [PR #55](https://github.com/sgl-project/sgl-flash-attn/pull/55) · [Development branch](https://github.com/cuihangbin/sgl-flash-attn/tree/fp8-paged-hdim256-chunked-pv) · [Integration into `sgl-kernel`](https://github.com/sgl-project/sgl-flash-attn/commit/a1f7f16c8f23a7eb2775febb265e4e7f275f7f93). | Merged |

Validation and performance results are documented in the linked PRs and apply to their tested hardware and workloads.
