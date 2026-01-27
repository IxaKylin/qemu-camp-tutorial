# 仓库指南

## 项目结构与模块组织
本仓库为 MkDocs/Zensical 文档站点。
- `docs/` 是全部内容源文件。
- `docs/tutorial/<year>/ch*/` 与 `docs/exercise/<year>/stage*/` 是主课程（示例：`docs/tutorial/2026/ch2/qemu-tcg.md`）。
- `docs/blogs/`、`docs/news/`、`docs/image/`、`docs/plugins/`、`docs/template/` 分别用于博客、新闻、资产、站点插件与模板。
- `site/` 为生成目录，禁止手工改动。
- `mkdocs.yml`、`requirements.txt`、`package.json` 定义构建与校验工具。

## 构建、测试与本地开发命令
所有检查仅在本地手工执行，不使用 CI。
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
npm install
zensical serve
autocorrect .
markdownlint-cli2 "**/*.md"
```
以上命令用于安装依赖、启动预览，并进行中文排版与 Markdown 规范检查；预览地址为 `http://127.0.0.1:8000`。

## 编码风格与命名约定
- 每个 Markdown 文件必须以单一 `#` 一级标题开头。
- 文件名使用 `kebab-case`，章节入口统一为 `index.md`。
- 提示框使用 admonition（如 `!!! note`、`!!! warning`）。
- 图片必须添加配字并紧随 `{: .caption }`。
- 章节主要作者需添加提示框，例如：
```markdown
!!! note "主要贡献者"
    - 作者：@example
```
- Markdown 块级内容缩进使用 4 个空格。

## 测试指南
仓库无单元测试框架，以 `autocorrect`、`markdownlint-cli2` 与本地预览作为验证基线。

## Commit 与 Pull Request 规范
- Commit 消息遵循 `scope: action`（英文），常见为 `docs/...: <verb>`，如 `docs/tutorial/2026: update gpgpu article`。
- 单次提交保持原子性，只覆盖一类改动。
- PR 必须遵循 `.github/pull_request_template.md`，写明修改路径、改动类型、简要说明与本地验证结果。
- 大规模内容新增应先提 Issue 对齐范围。

## 手工流程
CI/CD 自动化被禁用，构建、检查与发布全部由贡献者手工完成。
