# 写作与发布

## 一份笔记，两个阅读入口

```text
本地 Markdown 笔记（docs/）
        │
        ├── Git 提交并推送 → GitHub 仓库：查看源文件与历史
        │
        └── MkDocs 读取正文与 mkdocs.yml
                    │
                    ▼
             生成 site/ 静态网页
                    │
                    ▼
             GitHub Pages：浏览网站
```

Git 负责版本管理，GitHub 保存仓库，MkDocs 生成网页，GitHub Pages 提供网站访问。网站没有业务后端或数据库；搜索索引也在构建时生成。

## 新增一篇笔记

1. 从仓库的 `templates/note.md` 复制一份到对应板块，例如 `docs/transformer/attention.md`。
2. 写正文，把图片放到 `docs/assets/transformer/`。
3. 在 `docs/transformer/index.md` 添加相对链接：`[Attention](attention.md)`。
4. 在 `mkdocs.yml` 的 Transformer 导航中添加：`- Attention: transformer/attention.md`。
5. 本地预览，再运行严格构建检查。
6. 提交并推送。

文件路径决定页面地址，`nav` 决定导航标题和顺序。新增文件会被 MkDocs 构建，但不会自动加入这里显式配置的导航，所以要同步更新 `nav`。

## 在现有环境中预览和检查

从 `D:\ai_infra\AI_Infra` 运行：

```powershell
..\.venv\Scripts\python.exe -m mkdocs serve
```

预览停止后，检查正式构建：

```powershell
..\.venv\Scripts\python.exe -m mkdocs build --strict
```

检查覆盖构建配置、导航和正文中的站内链接。它不替代对外部网址、代码结果和文章准确性的检查。

## 首次提交与推送

本地仓库已经初始化并配置了远程地址，目前尚无提交。确认文件后，在仓库目录执行：

```powershell
git status
git add .
git commit -m "Organize AI infrastructure learning repository"
git push -u origin main
```

如果远程已有独立提交，先检查远程历史并合并，避免强制推送。后续维护同样采用“修改 → 检查 → 提交 → 推送”。

## GitHub Pages 首次设置

1. 打开 GitHub 上的 `jiayinzhang271-lab/AI_Infra` 仓库。
2. 进入 **Settings → Pages**。
3. 在 **Build and deployment → Source** 选择 **GitHub Actions**。
4. 推送 `main`，或在 Actions 中手动运行 `Build and deploy learning site`。
5. 等待 `build` 和 `deploy` 成功，再访问网站。

发布配置为 `https://jiayinzhang271-lab.github.io/AI_Infra/`。修改用户名、仓库名或域名时，同步修改 `mkdocs.yml` 中的 `site_url` 和 `repo_url`。

工作流在 Pull Request 上只检查构建；在 `main` 推送或手动运行时才发布。发布依赖远程仓库实际存在、账号权限和 Pages 设置；本地构建成功并不代表已经上线。

## 常见问题

- 导航没有新文章：检查 `mkdocs.yml` 中的 `nav`。
- 构建报找不到文件：检查大小写和相对路径；GitHub 构建环境区分大小写。
- Git 没有忽略 `site/`：确认 `.gitignore` 位于仓库根目录 `AI_Infra/`。
- 推送后没有网站：检查 Pages 的 Source 设置与 Actions 运行结果。

## 官方说明

- [MkDocs：编写文档与导航](https://www.mkdocs.org/user-guide/writing-your-docs/)
- [MkDocs：构建与部署](https://www.mkdocs.org/user-guide/deploying-your-docs/)
- [GitHub：自定义 Pages 工作流](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)
