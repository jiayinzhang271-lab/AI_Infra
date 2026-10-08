# AI Infra 学习库

围绕工具使用、AI 计算体系、机器学习理论、Transformer、推理框架和模型部署，持续积累笔记与实验。

- 网站源文件：`docs/`
- 网站配置：`mkdocs.yml`
- 学习路线：[学习路线](docs/guides/learning-roadmap.md)
- 写作与发布：[维护指南](docs/guides/workflow.md)
- 目录规则：[仓库组织](docs/guides/repository-structure.md)

## 目录

```text
AI_Infra/                         ← Git 仓库根目录
├── README.md                      ← GitHub 仓库首页
├── mkdocs.yml                     ← 网站主题、导航和网址
├── requirements-docs.txt          ← 网站构建依赖
├── .github/workflows/pages.yml    ← 自动检查与发布
├── docs/                         ← 网站正文，只维护这一份笔记
│   ├── index.md                  ← 网站首页
│   ├── tools/                    ← Markdown、Git、Linux 等工具
│   ├── ai-computing/             ← 硬件、计算、内存与通信
│   ├── ml-theory/                ← 数学基础、模型、优化与评估
│   ├── transformer/              ← Attention、模型结构与生成
│   ├── inference-frameworks/     ← 推理机制与框架学习
│   ├── model-deployment/         ← 服务、容器、监控与部署
│   ├── guides/                   ← 学习路线与维护指南
│   ├── assets/                   ← 网站图片与附件
│   └── aboutme.md                ← 关于我
├── experiments/                  ← 可运行实验与结果说明
├── notebooks/                    ← 探索性 Notebook
├── references/                   ← 论文与资料索引
└── templates/                    ← 笔记、实验和论文阅读模板
```

父目录 `D:\ai_infra` 是工作区；现有 `.venv` 在工作区内，Git 仓库在 `AI_Infra` 内。提交和推送应在本目录执行。仓库自己的 `.gitignore` 已补齐，父目录的忽略规则不会替代它。

## 本地预览

使用现有环境，在 PowerShell 中运行：

```powershell
cd D:\ai_infra\AI_Infra
..\.venv\Scripts\python.exe -m pip install -r requirements-docs.txt
..\.venv\Scripts\python.exe -m mkdocs serve
```

打开终端显示的本地网址，通常为 `http://127.0.0.1:8000/`。修改 Markdown 后页面会自动刷新。

在新电脑上可在仓库内创建环境：

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements-docs.txt
.\.venv\Scripts\python.exe -m mkdocs serve
```

## 构建与发布

```powershell
..\.venv\Scripts\python.exe -m mkdocs build --strict
```

构建结果在 `site/`，由工具生成，不手写、不提交。将源文件推送到 GitHub 的 `main` 分支后，Actions 会自动构建和发布。

第一次发布前，在 GitHub 仓库 **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**。

- 已配置远程：`https://github.com/jiayinzhang271-lab/AI_Infra`
- 配置中的网站地址：`https://jiayinzhang271-lab.github.io/AI_Infra/`
- 这些是配置地址，不代表本次已经完成线上发布。

首次提交和推送的步骤见[维护指南](docs/guides/workflow.md)。
