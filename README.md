# 锅巴的奇妙冒险之迷失东京 GitBook

这是 2026/06/03 – 2026/06/09 日本关东 7 日旅行计划的 GitBook/HonKit 文档站点。

## 文档结构

### 行程入口

- [`index.md`](index.md)：7 日总览

### 每日行程

- [`day-1-2026-06-03.md`](day-1-2026-06-03.md)：横滨
- [`day-2-2026-06-04.md`](day-2-2026-06-04.md)：镰仓
- [`day-3-2026-06-05.md`](day-3-2026-06-05.md)：上野 / 秋叶原 / 东京巨蛋
- [`day-4-2026-06-06.md`](day-4-2026-06-06.md)：新宿 / 中野 / 短片影展
- [`day-5-2026-06-07.md`](day-5-2026-06-07.md)：山王祭 / 隈研吾轴
- [`day-6-2026-06-08.md`](day-6-2026-06-08.md)：涩谷 / 银座 / 歌舞伎座
- [`day-7-2026-06-09.md`](day-7-2026-06-09.md)：浅草 / 晴空塔 / 机场

### 景点介绍

- `intros/intro-*.md`：70+ 个独立地点介绍文档（按区域组织，详见 SUMMARY.md）

### 专题指南

- [`购物清单.md`](购物清单.md)
- [`羽田机场游玩购物指南.md`](羽田机场游玩购物指南.md)
- [`免税香烟品鉴指南.md`](免税香烟品鉴指南.md)

### 数据文件

- `places.json`：地点元数据
- `tst-segments.json`：交通与票券估算
- `lodging-luggage.json`：住宿与行李方案
- `build_places.py`：数据构建脚本

## 本地预览

需要 Node.js 20 或更高版本。

```bash
npm install
npm run serve
```

## 构建静态站点

```bash
npm run build
```

构建产物输出到 `_book/`。

## 发布到 GitHub Pages

仓库已包含 GitHub Actions 工作流（`.github/workflows/deploy-gitbook.yml`），推送到 `main` 分支后自动部署。

首次使用 GitHub Pages 时，请到 GitHub 仓库：

```
Settings → Pages → Build and deployment → Source
```

选择 `GitHub Actions`。

## 修订流程

```
Favorite places.csv → build_places.py → places.json
                                       ↓
                                tst-segments.json
                                       ↓
                             7 个 day-N markdown + intros/*.md
                                       ↓
                                    SUMMARY.md
```
