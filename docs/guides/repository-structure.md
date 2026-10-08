# 仓库组织

## 文件应该放在哪里

| 内容 | 位置 | 是否进入网站 |
| --- | --- | --- |
| 学习笔记、概念解释、实验总结 | `docs/对应板块/` | 是 |
| 图片、示意图、小型公开附件 | `docs/assets/对应板块/` | 是 |
| 可运行脚本、实验配置、结果说明 | `experiments/对应板块/实验名/` | 否 |
| 探索性 `.ipynb` 文件 | `notebooks/对应板块/` | 否 |
| 论文、官方文档、课程资料的索引 | `references/` | 否 |
| 写作模板 | `templates/` | 否 |
| 自动构建后的 HTML、CSS、JavaScript | `site/` | 发布产物，Git 忽略 |

`docs/` 是网站的内容源。根目录 README、实验代码和 Notebook 不会自动变成网页。想展示实验结论，就在对应板块写一篇 Markdown 总结，再链接代码。

六个板块采用固定目录名：`tools`、`ai-computing`、`ml-theory`、`transformer`、`inference-frameworks`、`model-deployment`。

## 命名与链接

- 文件和目录使用小写英文加连字符，例如 `kv-cache.md`。
- 页面主标题使用中文，例如 `# KV Cache 的原理`。
- 每个板块用 `index.md` 作为入口，记录学习顺序和文章列表。
- 文件名保持稳定；学习顺序写在入口页，避免为了排序反复改名。
- 笔记之间使用相对路径，例如从 Transformer 链到 `../inference-frameworks/index.md`。
- 图片放到 `docs/assets/`，在笔记中使用相对路径引用。

## 跨板块内容

一篇文章选择一个主要归属，其他板块用链接引用，避免复制两份。

- Attention 原理 → Transformer。
- GPU 带宽分析 → AI 计算体系。
- KV Cache 调度实现 → 推理框架。
- 推理服务的容器部署 → 模型部署。

现有 `docs/mixed/markdown_learning.md` 已归入 `docs/tools/markdown.md`，正文保留。

## 实验目录示例

```text
experiments/inference-frameworks/prefill-benchmark/
├── README.md          ← 目标、环境、运行方法、结果解释
├── run.py             ← 实验入口
└── config.example.yml ← 可公开的配置示例
```

模型权重、大数据和大量运行产物保留在本地，文档中记录获取方法和必要的汇总结果。
