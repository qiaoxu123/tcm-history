# 参与贡献

欢迎对《中医发展历史》提出修订、补充与考据。本书是开源协作项目，所有改进通过 GitHub 进行。

## 本地预览与构建

```bash
# 1. 克隆仓库
git clone https://github.com/qiaoxu123/tcm-history.git
cd tcm-history

# 2. 创建虚拟环境并安装依赖
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# 3. 本地实时预览（默认 http://127.0.0.1:8000）
mkdocs serve

# 4. 构建静态网站（产物在 site/）
mkdocs build
```

## 导出整书 PDF

PDF 通过 `mkdocs-with-pdf` 插件生成，平时关闭以加快预览，导出时用环境变量开启：

```bash
ENABLE_PDF=1 mkdocs build
# 产物：site/pdf/中医发展历史.pdf
```

> macOS 上 `weasyprint` 需要系统库 `pango`、`gdk-pixbuf`、`libffi`：
> `brew install pango gdk-pixbuf libffi`

## 写作规范（重要）

本书遵循**第一性原理**，请所有贡献者注意：

1. **区分事实、观点与疗效断言**：参见 [导论 §五](../chapters/00-introduction.md)。叙述古代理论时标明「这是当时的认识」；涉及疗效/机理时区分「有经验」与「经现代研究证实」。
2. **孤证不立，引必有据**：重要史实、年代、引文应给出出处（脚注或参考文献）。
3. **不神化、不全盘否定**：对争议与阴性结果如实呈现。
4. **承认未知**：无定论处明说「尚不清楚 / 存在争议」。
5. **不构成诊疗建议**：本书是历史读物，不提供医疗指导。

## 文件组织

```
docs/
├── index.md            # 首页
├── chapters/           # 编年史八章
├── topics/             # 专题卷
├── appendix/           # 附录（年表、典籍、术语、参考文献）
├── about/              # 关于（贡献、更新日志）
└── stylesheets/        # 自定义样式
```

## 提交流程

1. 新建分支：`git checkout -b feat/补充-xxx`
2. 修改并本地 `mkdocs serve` 预览
3. 提交（遵循 `feat: / fix: / docs:` 约定）
4. 推送并发起 Pull Request，说明修改依据

---

← 返回 [首页](../index.md)
