# 项目记忆：《中医发展历史》

> 本文件是本项目的长期记忆，进入本目录时由 Claude Code 自动加载，并随仓库版本化。
> 后续在此基础上持续开发，重要决策与约定都记在这里。

## 一句话定位

一部**开源、可持续修订的中医学发展通史**，提供**网页 + PDF** 两种阅读形态；面向公众的通识读物，不构成诊疗建议。

## 核心写作立场（最高优先级）

**遵循第一性原理，不一味依据经典**（用户 2026-06-20 明确要求）：

1. 严格区分三类陈述：*历史事实*（有史料/考古）、*历史观点*（古人的理论解释，标明「当时的认识」）、*疗效/机理断言*（区分「有经验」与「经现代研究证实」）。
2. 追问证据，不诉诸权威——「经典载」「医圣说」是考据起点而非论证终点。
3. 把概念放回历史语境理解（阴阳五行、经络=经验性建模），不神化也不简单斥为迷信。
4. 正视争议、失败、阴性结果与安全性问题（如马兜铃酸、含重金属药）。
5. 无定论处明说「尚不清楚/存在争议」。

体现位置：导论 §五「写作立场」；各章末尾的 `!!! warning "批判性视角"` 与 `!!! note` 框。**新增内容必须沿用这一体例。**

## 技术栈与命令

- **工具链**：MkDocs Material（用户在选项中明确选定，理由：Python 生态、中文友好、PDF 插件成熟、维护成本低）。
- **PDF**：`mkdocs-with-pdf` 插件 + weasyprint，默认关闭，靠环境变量 `ENABLE_PDF=1` 开启。
- **预览**：`python3 -m venv .venv && source .venv/bin/activate && pip install -r requirements.txt && mkdocs serve`
- **构建网页**：`mkdocs build`（→ `site/`）
- **构建 PDF**：`ENABLE_PDF=1 mkdocs build`（→ `site/pdf/中医发展历史.pdf`）
- **PDF 系统依赖（macOS）**：`brew install pango gdk-pixbuf libffi`
- **本机 Node/Python 装包若报 CA 错**：见全局记忆 npm/electron TLS 修复（NODE_EXTRA_CA_CERTS=/etc/ssl/cert.pem + 镜像 + 关代理）；pip 慢可用清华镜像 `-i https://pypi.tuna.tsinghua.edu.cn/simple`。

## 结构约定

```
docs/
├── index.md                 # 首页/前言
├── chapters/00-08*.md       # 编年史八章（先秦→当代），文件名英文 slug，nav 标题中文
├── topics/*.md              # 专题卷：本草/针灸/方剂/典籍/中外交流
├── appendix/*.md            # 附录：年表/典籍一览/术语表/参考文献
├── about/*.md               # 贡献指南、更新日志
└── stylesheets/extra.css    # 自定义样式（.era 朝代徽标等）
```

- 文件 slug 用英文/数字，章节标题在 `mkdocs.yml` 的 `nav` 里用中文。
- 章节正文体例：时代背景 → 主要成就 → 代表医家 → 代表典籍 → 批判性视角 → 本章小结 → 上下章导航。

## 许可与仓库

- 内容 `docs/` → CC BY-SA 4.0（`LICENSE`）；代码/配置 → MIT（`LICENSE-CODE`）。
- GitHub 私有仓库：`qiaoxu123/tcm-history`（`gh` 已登录 qiaoxu123）。
- CI：推送 `main` 自动构建网页+PDF 并部署 GitHub Pages（`.github/workflows/deploy.yml`）。Pages 站点 URL：https://qiaoxu123.github.io/tcm-history/ （需在仓库 Settings→Pages 选 GitHub Actions 源；私有仓库的 Pages 需相应套餐支持）。

## 当前状态（v0.1.0, 2026-06-20）

- ✅ 八章编年史初稿、专题/附录骨架、文档站配置、CI、双许可、README/CHANGELOG 全部就位。
- ⏳ 待办：史实/年代/引文逐条核对并补脚注出处；参考文献核实版本页码；专题与附录按各页「待办」清单扩充；补充少数民族医学内容。

## 与既有目录的关系

- 与 `~/Workspace/tcm-study`（用户**个人中医学习笔记**：中药/方剂/经典/分析）是**两个独立项目**，本书是可发布的通史，勿混淆、勿合并。

## 维护提醒

- 做版本级变更时更新 `CHANGELOG.md` 与 `docs/about/changelog.md`（保持同步）。
- 涉及代码审查时按全局约定走 `adversarial-review`。
