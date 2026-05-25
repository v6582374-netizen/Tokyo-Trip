# Tokyo Trip 2026 GitBook

这是 2026/06/03 – 2026/06/09 日本关东 7 日旅行计划的 GitBook/HonKit 文档站点。

- 在线入口文档：[`index.md`](index.md)
- GitBook 目录：[`SUMMARY.md`](SUMMARY.md)
- 每日行程：`day-1-2026-06-03.md` 至 `day-7-2026-06-09.md`
- 数据工件：`places.json`、`tst-segments.json`、`lodging-luggage.json`
- 原始输入：`Favorite places.csv`

## 本地预览

需要 Node.js 20 或更高版本。

```bash
npm install
npm run serve
```

然后打开 HonKit 输出的本地地址，默认通常为：

```text
http://localhost:4000
```

## 构建静态站点

```bash
npm run build
```

构建产物会输出到 `_book/`，该目录已被 `.gitignore` 忽略。

## 发布到 GitHub Pages

仓库已包含 GitHub Actions 工作流：

```text
.github/workflows/deploy-gitbook.yml
```

推送到 `main` 或 `master` 分支后，工作流会自动：

1. 安装依赖
2. 运行 `npm run build`
3. 将 `_book/` 发布到 GitHub Pages

首次使用 GitHub Pages 时，请到 GitHub 仓库：

```text
Settings → Pages → Build and deployment → Source
```

选择 `GitHub Actions`。

## 文档结构

### 行程入口

- [`index.md`](index.md)：7 日总览、逐日要点、排除地点说明

### 每日行程

- [`day-1-2026-06-03.md`](day-1-2026-06-03.md)：横滨
- [`day-2-2026-06-04.md`](day-2-2026-06-04.md)：镰仓
- [`day-3-2026-06-05.md`](day-3-2026-06-05.md)：上野 / 秋叶原 / 东京巨蛋
- [`day-4-2026-06-06.md`](day-4-2026-06-06.md)：新宿 / 中野 / 短片影展
- [`day-5-2026-06-07.md`](day-5-2026-06-07.md)：山王祭 / 隈研吾轴
- [`day-6-2026-06-08.md`](day-6-2026-06-08.md)：涩谷 / 银座 / 歌舞伎座
- [`day-7-2026-06-09.md`](day-7-2026-06-09.md)：浅草 / 晴空塔 / 机场

### 专题指南

- [`购物清单.md`](购物清单.md)
- [`羽田机场游玩购物指南.md`](羽田机场游玩购物指南.md)
- [`免税香烟品鉴指南.md`](免税香烟品鉴指南.md)
- [`重新发现日本之关东地区.md`](重新发现日本之关东地区.md)

### 规范与数据

- [`requirements.md`](requirements.md)：需求说明
- [`design.md`](design.md)：设计说明
- [`tasks.md`](tasks.md)：任务清单
- [`places.json`](places.json)：地点元数据
- [`tst-segments.json`](tst-segments.json)：交通与票券估算
- [`lodging-luggage.json`](lodging-luggage.json)：住宿与行李方案

## 修订流程建议

修改输入或地点时建议按以下顺序回溯，避免上下游不一致：

```text
Favorite places.csv → build_places.py → places.json
                                      ↓
                               tst-segments.json
                               lodging-luggage.json
                                      ↓
                            7 个 day-N markdown
                                      ↓
                                   index.md
```
