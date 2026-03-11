# 📚 Research Hub · CV Papers

一个为计算机视觉研究者打造的论文管理网站，支持**本地 PDF 内嵌阅读**，部署于 GitHub Pages。

## 📁 目录结构

```
你的仓库/
├── index.html                  ← 网站主文件（唯一需要的 HTML）
├── data/
│   ├── papers.json             ← 论文索引（在这里管理所有论文信息）
│   ├── detection/              ← 目标检测论文 PDF
│   │   ├── detr.pdf
│   │   └── yolov8.pdf
│   ├── segmentation/           ← 图像分割论文 PDF
│   │   ├── mask-rcnn.pdf
│   │   └── segment-anything.pdf
│   ├── transformer/            ← Transformer 论文 PDF
│   │   ├── attention-is-all-you-need.pdf
│   │   └── vit-image-worth-16x16.pdf
│   ├── generation/             ← 图像生成论文 PDF
│   ├── tracking/               ← 目标跟踪论文 PDF
│   ├── classification/         ← 图像分类论文 PDF
│   ├── 3d/                     ← 三维视觉论文 PDF
│   └── multimodal/             ← 多模态论文 PDF
└── README.md
```

---

## ➕ 如何添加论文

### 方法一：编辑 `data/papers.json`（推荐，批量高效）

1. 把 PDF 文件放入对应的 `data/分类/` 文件夹
2. 在 `data/papers.json` 中新增一个条目：

```json
{
  "id": "detection-002",
  "title": "YOLOv8: Real-Time Object Detection",
  "category": "detection",
  "tags": ["YOLO", "Real-time", "Anchor-free"],
  "authors": "Jocher, G., Chaurasia, A., Qiu, J.",
  "firstAuthor": "Jocher",
  "year": 2023,
  "venue": "arXiv 2023",
  "abstract": "YOLOv8 是 Ultralytics 推出的新一代实时目标检测模型...",
  "link": "https://github.com/ultralytics/ultralytics",
  "code": "https://github.com/ultralytics/ultralytics",
  "pdf": "data/detection/yolov8.pdf",
  "notes": "工程落地首选，速度极快。",
  "starred": false,
  "addedAt": 1700000010000
}
```

3. `git add . && git commit -m "add YOLOv8" && git push`，几分钟后网站自动更新。

### 方法二：通过网页界面添加

点击右上角「添加论文」→ 填写表单 → 在「本地 PDF 路径」栏填写路径，如 `data/detection/yolov8.pdf`。

> ⚠️ 通过界面添加的论文存储在浏览器 localStorage，换设备或清除缓存会丢失。建议最终统一写入 `papers.json`。

---

## 🗑️ 如何删除论文

直接从 `data/papers.json` 中删除对应条目，并删除 `data/分类/` 下的 PDF 文件，提交推送即可。

---

## 📎 PDF 字段说明（`pdf` 字段）

| 场景 | 填写方式 |
|------|---------|
| 本地 PDF 已放入 data/ | `"pdf": "data/detection/detr.pdf"` |
| 暂无 PDF | `"pdf": ""` 或省略该字段 |
| 外部 PDF 链接 | `"pdf": "https://arxiv.org/pdf/2005.12872"` |

PDF 将在论文详情页右侧**全屏内嵌显示**，左侧显示摘要、笔记等元信息。

---

## 🚀 GitHub Pages 部署

```bash
# 1. 创建仓库并克隆
git clone https://github.com/你的用户名/research-hub
cd research-hub

# 2. 复制文件
cp -r index.html data/ ./

# 3. 推送
git add .
git commit -m "🚀 deploy Research Hub"
git push origin main

# 4. 开启 GitHub Pages
# 仓库 Settings → Pages → Source → Deploy from branch → main → / (root)
```

访问：`https://你的用户名.github.io/research-hub/`

---

## ⌨️ 快捷键

| 快捷键 | 功能 |
|--------|------|
| `Ctrl/⌘ + K` | 聚焦搜索框 |
| `Ctrl/⌘ + N` | 快速添加论文 |
| `Esc` | 关闭弹窗 |
| 右键卡片 | 编辑 / 删除 / 收藏 |

---

## 🔧 category 可选值

`detection` · `segmentation` · `transformer` · `generation` · `tracking` · `classification` · `3d` · `multimodal`
