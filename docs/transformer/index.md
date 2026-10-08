# Transformer

目标：从张量形状和数据流入手，理解 Transformer 的结构与生成过程。

## 学习顺序

- [ ] Tokenizer 与 Embedding：文本如何变成模型输入。
- [ ] Attention：Q、K、V 的含义、计算与维度。
- [ ] Multi-Head Attention：多个注意力头的组织方式。
- [ ] Position Encoding：如何表示顺序信息。
- [ ] Transformer Block：注意力、前馈层、残差与归一化。
- [ ] Encoder / Decoder：不同模型结构的用途。
- [ ] 自回归生成：逐 Token 输出与采样。
- [ ] KV Cache：缓存内容与推理阶段的衔接。

建议文件：`tokenizer-and-embedding.md`、`attention.md`、`transformer-block.md`、`autoregressive-generation.md`。

## 实验方向

先用小张量手算一次 Attention，再用 PyTorch 实现最小版本。记录每一步的输入形状、输出形状与计算含义。

模型结构与原理放在这里；KV Cache 的调度、内存管理和框架实现放到推理框架板块，并互相链接。
