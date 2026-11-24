# DeepSeek-V4-Flash 的推理上下文并行系统设计

[阅读演示文稿（PDF，14 页）](./DeepSeek-V4-Flash-CP.pdf)

这份技术笔记用 SGLang 的四卡预填充示例，跟踪一个查询如何取得其他 GPU 上的 KV，以及跨卡通信如何影响长输入的首 token 延迟（TTFT）。

| 页码 | 内容 |
| --- | --- |
| 3–5 | 用 16 个输入 token 跟踪 Q₉。GPU 1 本轮接收 12 个外卡位置的 KV，其中 Q₉ 用到 7 个。 |
| 6 | DeepSeek-V4-Flash 的模型参数与权重占用，以及一个单独的 GQA 算例，用于计算每卡的 KV 缓存大小和通信量。 |
| 7–11 | Prefill CP 与 FFN、专家并行和 KV 缓存布局的关系，并用 MLA 解码示例说明 Decode CP 如何合并局部注意力结果。 |
| 12–14 | 四卡 B200 配置示例、SGLang 路线图与性能验证方法。 |

模型参数与混合精度见 [DeepSeek 官方模型卡](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash)。预填充的切分与通信策略见 [SGLang Prefill CP 文档](https://github.com/sgl-project/sglang/blob/main/docs/docs/advanced_features/prefill_cp.mdx)。
