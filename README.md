# 舔狗平台

一个单文件网页应用。表面是吐槽站，内核是一个「关系投入失衡」的自测工具。

**在线体验：https://huichengh.github.io/tiangou-platform/**

## 里面有什么

| 模块 | 做什么 |
|---|---|
| 舔狗自测 | 12 道题，满分 36，四档结果。结果页会标出你在哪几道题选了失衡那一侧，并给具体建议。 |
| 语录库 | 24 条常见操作，分试探期 / 日常 / 邀约 / 冲突 / 收尾。每条写清「实际效果」和「换成这样」。 |
| 发前三问 | 三个问题，过一条答不上来就别发。 |
| 冷静期 | 上头时想发的话写进来，24 小时后系统问你还想不想发。三个选项：不发了 / 改一改再发 / 还是发了。 |
| 树洞 | 匿名投稿 + 「同款 +1」计数。别人的帖子可以一键存进冷静期。 |
| 我的 | 本地统计、徽章、数据导出与清空。 |

## 数据存在哪

全部在浏览器 `localStorage`，key 是 `tgg_v1`。不上传、不联网、没有后端。清理浏览器数据会一起清掉，可以在「我的 → 数据」里导出 JSON 备份或直接清空。

## 部署

纯静态页面，GitHub Pages 从 `main` 分支的 `/docs` 目录发布。

```bash
git init -b main
git add -A
git commit -m "feat: 舔狗平台单页应用"
gh repo create huichengh/tiangou-platform --public --source=. --remote=origin --push \
  --description "舔狗平台 · 关系投入失衡自测工具。在线演示：https://huichengh.github.io/tiangou-platform/"
gh api -X POST repos/huichengh/tiangou-platform/pages \
  -f "source[branch]=main" -f "source[path]=/docs"
```

## 技术说明

单个 HTML 文件，CSS/JS 全内联，零外部依赖（不引 CDN、字体或图表库），图标全部是内联 SVG。断网也能正常打开。

## 一句话说明

本项目用于辅助自查关系中的投入状态，不提供任何话术操控、情绪施压或挽回技巧。涉及明确拒绝或已被要求停止联系的情形，站内建议一律指向「停下」。
