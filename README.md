---
AIGC:
  ContentProducer: '001191110102MAD55U9H0F10002'
  ContentPropagator: '001191110102MAD55U9H0F10002'
  Label: '1'
  ProduceID: '3aed807e-6775-49da-ad9b-5271ba44ccbe'
  PropagateID: '3aed807e-6775-49da-ad9b-5271ba44ccbe'
  ReservedCode1: 'b0bdbc27-9357-493f-9fe6-94ab1b5592a0'
  ReservedCode2: 'b0bdbc27-9357-493f-9fe6-94ab1b5592a0'
---

# MindVista-AI · 新智视觉

> 洞察心智全景，开拓人工智能新视界
> 明眸善断，思理通达

一个零依赖的静态单页站点，上传到 GitHub 后开启 GitHub Pages 即可直接访问。

## 文件结构

```
MindVista-AI/
├── index.html    # 全部内容（HTML + CSS + JS 自包含，无外部依赖）
└── README.md     # 本说明文件
```

`index.html` 不引用任何外部字体、JS 库或图片，离线可用、加载快，也不受网络环境影响。

## 上传到 GitHub 并访问

### 方式一：网页上传（最简单）

1. 登录 GitHub，点右上角 **+** → **New repository**。
2. Repository name 填 `MindVista-AI`，选择 **Public**，点 **Create repository**。
3. 进入新仓库，点 **uploading an existing file**。
4. 把 `index.html` 和 `README.md` 两个文件拖进去，点 **Commit changes**。
5. 打开仓库 **Settings** → 左侧 **Pages**。
6. **Source** 选 `Deploy from a branch`，**Branch** 选 `main` + `/ (root)`，点 **Save**。
7. 等待 1–2 分钟，刷新 Pages 页面，会看到访问地址：

   ```
   https://<你的用户名>.github.io/MindVista-AI/
   ```

### 方式二：命令行上传

在本文件夹内执行：

```bash
git init -b main
git add .
git commit -m "Add MindVista-AI landing page"
git remote add origin https://github.com/<你的用户名>/MindVista-AI.git
git push -u origin main
```

推送完成后，按上面第 5–7 步开启 Pages 即可。

### 本地预览

直接双击 `index.html` 用浏览器打开即可；或在本文件夹内启动一个本地服务：

```bash
python3 -m http.server 8000
# 然后访问 http://localhost:8000
```

## 页面结构

| 区块 | 内容 |
| --- | --- |
| 顶栏 | 品牌名 `MindVista-AI` + `新智视觉`，底部以细线分隔 |
| 首屏 | 小标题「思考式观察 · Thinking Vision」+ 主标语「洞察心智全景，开拓人工智能新视界」+ 一句话阐释 + 注意力图版（Fig. 01） |
| 核心能力 | 「新智视觉：明眸善断，思理通达」寓意说明 + 两大支点 + 四项能力标签 |
| 页脚 | 品牌署名与版权 |

首屏右侧的 **Fig. 01** 是页面的视觉签名：用点阵表示视野，四个注视点表示模型的视觉注意力，
连线表示逐步推理链，随页面载入依次点亮，直观对应「先决定看哪里，再决定想什么」。

## 如何修改

- **改文案**：直接在 `index.html` 里搜索中文原文替换即可，无需改样式。
- **改配色**：文件顶部 `:root` 中是全部颜色变量，最常改的两个是
  - `--teal: #0C6270`（主色，用于线条、小标题）
  - `--amber: #B4690E`（注意力强调色，用于注视点与序号）
- **改字体**：`:root` 中的 `--serif`（标题，宋体系）与 `--sans`（正文，黑体系）均为系统字体栈，
  不依赖网络；如需换成思源宋体等，替换字体名即可。
- **调注视点位置**：修改 SVG 中 `polyline` 的 `points` 与四个 `<g class="pop-init">` 里圆心的 `cx/cy`。

## 兼容性

- 响应式布局，适配手机 / 平板 / 桌面。
- 已适配 `prefers-reduced-motion`（系统开启「减少动态效果」时自动关闭动画）。
- 无 JavaScript 时自动降级为静态展示，不会出现空白。
- 已在 Chrome / Safari / Edge 现代版本验证。

> AI生成