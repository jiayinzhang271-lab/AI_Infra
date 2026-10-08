# 推理框架

目标：理解推理引擎如何组织模型执行，以及性能优化的来源。

## 学习顺序

- [ ] 推理流程：Prefill、Decode 与请求生命周期。
- [ ] 性能指标：首 Token 延迟、每 Token 延迟、吞吐量。
- [ ] 调度：批处理、连续批处理与请求队列。
- [ ] 内存管理：KV Cache 的容量、分配与回收。
- [ ] 优化机制：量化、算子融合与并行策略。
- [ ] 框架阅读：选择一个框架，跑通最小示例再读关键模块。
- [ ] 横向比较：在统一条件下比较不同框架。

框架候选：vLLM、SGLang、TensorRT-LLM、llama.cpp、ONNX Runtime。这个列表用于规划学习主题，实际安装与参数以对应版本的官方文档为准。

建议文件：`prefill-and-decode.md`、`batching-and-scheduling.md`、`kv-cache-management.md`、`vllm.md`、`sglang.md`。

## 实验方向

固定模型、硬件、输入长度、输出长度和并发，记录版本与配置，测量延迟和吞吐量。代码放到 `experiments/inference-frameworks/`。
