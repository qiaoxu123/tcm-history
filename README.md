# 中医发展历史

> 一部开源、可持续修订的**中医学发展通史**，提供**网页**与 **PDF** 两种阅读形态。

[![docs](https://img.shields.io/badge/docs-MkDocs%20Material-526CFE)](https://qiaoxu123.github.io/tcm-history/)
[![content license](https://img.shields.io/badge/content-CC%20BY--SA%204.0-lightgrey)](./LICENSE)
[![code license](https://img.shields.io/badge/code-MIT-green)](./LICENSE-CODE)

## 简介

本书沿历史脉络，呈现中医从远古萌芽到当代现代化的完整演进，回答「它从哪里来、如何成形、走向何方」三个问题。

**写作立场**：遵循**第一性原理，不一味依据经典**——尊重经典作为历史文献的价值，但不把「经典如是说」当作「事实如是」。严格区分*历史事实*、*历史观点*与*疗效/机理断言*，追问证据而非诉诸权威。详见[导论](docs/chapters/00-introduction.md)。

## 结构

- **编年史（八章）**：先秦 → 秦汉 → 魏晋南北朝 → 隋唐 → 宋金元 → 明清 → 近代 → 当代
- **专题卷（五篇）**：本草学史 / 针灸史 / 方剂学史 / 典籍流变 / 中外交流史
- **附录**：历代医家年表 · 重要典籍一览 · 术语表 · 参考文献

## 本地预览

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve          # http://127.0.0.1:8000
```

## 构建产物

```bash
mkdocs build                  # 网页 → site/
ENABLE_PDF=1 mkdocs build     # 整书 PDF → site/pdf/中医发展历史.pdf
```

> PDF 依赖 weasyprint 的系统库：`brew install pango gdk-pixbuf libffi`

## 参与贡献

见 [贡献指南](docs/about/contributing.md)。欢迎史实考据、引文补注、章节扩充。

## 许可

- **内容**（`docs/` 下文字）：[CC BY-SA 4.0](./LICENSE)
- **代码与配置**（`mkdocs.yml`、CSS、CI 等）：[MIT](./LICENSE-CODE)

## 免责声明

本书为面向公众的历史读物，**不构成任何诊疗建议**。涉及具体医学论断时以呈现历史观点为主。
