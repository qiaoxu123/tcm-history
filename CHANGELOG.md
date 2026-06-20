# Changelog

本项目的版本级变更记录。遵循语义化版本与「版本级变更才记录」的原则。

## [0.1.0] - 2026-06-20

### Features
- 确立全书脉络：编年史八章 + 专题卷五篇 + 附录四篇。
- 完成编年史八章（先秦至当代）初稿正文。
- 完成专题卷与附录的结构化骨架（含待扩充清单）。
- 搭建 MkDocs Material 文档站，支持网页浏览与 PDF 导出双形态。
- 确立写作立场：**第一性原理，不一味依据经典**（导论 §五 + 各章「批判性视角」框）。
- 配置 GitHub Actions：推送到 `main` 自动构建并部署到 GitHub Pages。

### Design Rationale
- 工具链选 MkDocs Material：Python 生态、中文友好、PDF 插件成熟、维护成本低。
- 体例采「编年为主、专题为辅」：兼顾时间主线与主题纵深。
- 双许可（内容 CC BY-SA 4.0 / 代码 MIT）：便于开源协作。

### Notes & Caveats
- 各章为初稿，史实、年代、引文待逐条核对并补脚注出处。
- 参考文献为占位条目，正式引用前需核实版本页码。
- PDF 导出依赖 weasyprint 系统库（pango、gdk-pixbuf、libffi）。
