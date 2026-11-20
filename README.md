# 伽尔顿板 · 3D 交互课件

基于 **12.2 物质的微观模型、统计规律性** 中的“小球在伽尔顿板中的分布规律”制作。

单文件、内联 Three.js、无需构建，可直接部署到 GitHub Pages。

## 页面

- 3D 伽尔顿板：金属框架、钉阵、透明面板、红色小球与透明落袋
- 小球按“每层左右各 1/2”的概率下落，落袋后柱高按 **已落袋球数占比** 增长
- 实时显示总球数、在途球数、平均格位、标准差、中心三格占比
- 二项分布与正态近似曲线
- 层数切换：6 / 8 / 10 / 12
- 投放速度、自动播放 / 暂停、单球、100 球、重置
- 3D 旋转 / 缩放、自动旋转、重置视角
- 电脑端三栏布局，手机端单栏布局

## 文件结构

```text
.
├── index.html    # 完整页面
├── assets/
│   └── preview.png
├── README.md
└── .nojekyll
```

`index.html` 必须放在仓库根目录，GitHub Pages 会自动作为首页。

## 部署到 GitHub Pages

### 网页上传

1. 新建 GitHub 仓库，例如 `galton-board-3d`。
2. 将本文件夹中的全部内容上传到仓库根目录。
3. 打开 **Settings → Pages**。
4. **Build and deployment** 中选择：
   - Source：`Deploy from a branch`
   - Branch：`main`
   - 目录：`/(root)`
5. 点击 **Save**，等待约 1 分钟。

访问：

```text
https://<你的用户名>.github.io/galton-board-3d/
```

如果仓库名是 `<你的用户名>.github.io`，则访问 `https://<你的用户名>.github.io/`。

### Git 命令

```bash
git init
git add .
git commit -m "Add Galton board 3D page"
git branch -M main
git remote add origin https://github.com/<用户名>/<仓库名>.git
git push -u origin main
```

然后在 Settings → Pages 中选择 `main` / `/(root)`。

## 本地预览

直接双击 `index.html`，或在当前目录执行：

```bash
python -m http.server 8000
```

打开 `http://localhost:8000/`。

## 适配说明

- 电脑：三栏布局，控制台 / 3D 舞台 / 分布图同屏
- 平板：两栏或单栏自适应
- 手机：单栏，3D 舞台优先，按钮和滑块加大触控尺寸
- 已按 1440px、768px、390px 宽度验证，无横向溢出
- 需要浏览器支持 WebGL；推荐较新的 Chrome、Edge、Safari

## 物理说明

- 小球按理想伽尔顿板模型逐层随机左右，不模拟刚体碰撞
- 分子/小球数量是教学可视化抽样，不代表真实比例
- `n` 层对应 `n+1` 个格位，落袋位置满足二项分布

![页面预览](assets/preview.png)

## 来源

依据课程 PPT **12.2 物质的微观模型、统计规律性** 制作，仅用于教学展示。
