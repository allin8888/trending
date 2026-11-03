# GitHub 热门话题排行榜 · 每日报告

每日自动抓取 [GitHub Trending](https://github.com/trending) 日榜 Top 15，生成中文报告：话题聚类、总榜（含中文简介 + 原文折叠）、语言分布（Linguist 官方配色）、两期对比与连续在榜统计。

## 仓库结构

```
/
├── index.html                                  # 最新一期报告（每日覆盖更新）
└── archive/
    └── deliver-github-trending-YYYY-MM-DD.html # 历史各期归档
```

- **最新报告**：直接访问站点根路径（`index.html`）
- **历史回看**：从页面内「← 上一期 / 下一期 →」导航跳转 `archive/` 下对应日期

## 发布（Cloudflare Pages）

纯静态、零构建：

- Framework preset: **None**
- Build command: 留空
- Build output directory: `/`（仓库根）
- 入口：`index.html`（自动识别）

## 更新机制

本地自动化每日 11:00（GMT+8）执行：抓取 Trending → AI 中文简介翻译 + 话题聚类 → 渲染双轨（dated + latest）→ 同步本仓库结构。

## 数据纪律

数据源未到位时报告以「待核实」占位，不编造任何数据；解析行数不足（<5 行）视为采集失败。话题聚类由 AI 按简介语义生成（非 GitHub 官方分类），仅作风向参考。

---

数据版权归 GitHub 及各仓库作者所有。
