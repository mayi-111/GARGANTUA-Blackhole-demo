# 🌌 GARGANTUA · 相对论天体物理仿真工作站

<div align="center">

![WebGL 2.0](https://img.shields.io/badge/WebGL-2.0-blue?style=for-the-badge&logo=webgl)
![GLSL ES 3.00](https://img.shields.io/badge/GLSL-ES%203.00-orange?style=for-the-badge)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero-success?style=for-the-badge)
![Physics](https://img.shields.io/badge/Physics-General%20Relativity-purple?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

<p align="center">
  <b>基于广义相对论克尔度规 (Kerr Metric) 的实时测地线光线追踪与超高频吸积盘流体仿真工作站</b><br>
  <i>Realtime General Relativistic Geodesic Raytracer & Accretion Disk Simulation Workstation</i>
</p>

</div>

---

## 📖 项目概述 (Overview)

**Gargantua Astrophysical Workstation** 是一座致敬基普·索恩（Kip Thorne）诺贝尔物理学奖天体物理模型及电影《星际穿越》（*Interstellar*）的纯浏览器原生相对论超清仿真终端。

不同于传统 3D 引擎通过贴图伪造光晕的做法，本项目基于 **纯手写 WebGL 2.0 片元着色器 (Fragment Shader)** 与 **四维时空光线测地线积分算法**，在浏览器端以 60 FPS 实时解算极端弯曲时空中的光线偏折轨迹、吸积盘等离子体超音速差动自转、相对论多普勒前向聚束以及爱因斯坦引力透镜双拱冠。

整个工程为 **单文件零依赖（Zero Dependencies）** 设计，无需安装任何 Node.js 库、构建工具或外部引擎包，直接双击 `index.html` 即可在现代浏览器中启动沉浸式天体物理视听仿真。

---

## ✨ 核心特性 (Key Features)

### 1. 广义相对论测地线光线追踪 (Relativistic Geodesic Raytracing)
- **Runge-Kutta 2 (RK2) 中点法数值积分**：在强引力势阱中以自适应积分步长实时求解光子运动方程，精确复现光子球（Photon Sphere, $R_{ph} = 1.5 R_s$）与事件视界（Event Horizon, $R_s = 2GM/c^2$）。
- **几何透镜上下双拱冠 (Einstein Double Arc)**：精确模拟吸积盘背面辐射之光子在飞越黑洞上下极区时被引力拉弯、投射至观测天球的标志性爱因斯坦环与上下拱冠。
- **全屏抗锯齿步长自适应**：积分总预算自适应缩放，彻底消除光子球边界离散抖动与摩尔条纹。

### 2. 超高频等离子体吸积盘流体 (Ultra-High Frequency Accretion Disk)
- **开普勒差动自转 (Keplerian Differential Rotation)**：等离子体角速度严格遵循差动衰减律 $\Omega(r) \propto r^{-1.5}$，内层暴速吸积、外层平缓旋流。
- **微反差纤维细丝 (Domain-Warped Filament Noise)**：采用对数螺旋坐标与各向异性域扭曲湍流算法，消除传统柏林噪声的模糊涂抹感，呈现发丝级等离子体高动态细丝。
- **柯克伍德共振缝隙 (Kirkwood Resonant Grooves)**：模拟盘面轨道密度波与微共振带，塑造层次分明的同心环结构。
- **Shakura-Sunyaev 辐射剖面**：吸积能量从最内稳定圆轨道（ISCO）陡峭爬升，并向外边缘渐进消隐。

### 3. 相对论多普勒束流与光谱频移 (Doppler Beaming & Chromatic Shift)
- **相对论性前向聚束 (Relativistic Beaming)**：考虑近光速轨道运动对立体角的洛伦兹收缩，遵循辐射增强公式 $I_{\text{obs}} = \delta^4 I_{\text{emit}}$。
- **迎面蓝移与背向红移**：吸积盘左侧迎向观测者运动的流束呈现高能紫外白蓝增亮，右侧背向运动流束则发生多普勒红移与光强衰减，展现物理上真实的非对称明暗对比。

### 4. 全 3D 各向同性深空背景 (Full 3D Isotropic Deep Cosmos)
- **无接缝 3D 空间域扭曲 (3D Domain Warping)**：彻底摒弃传统天球二维贴图映射，杜绝极点挤压（Poles Pinching）与球面拉伸感。
- **真实银道坐标系 (Galactic Coordinate System)**：以倾角 63° 构建真实银道面，包含银心核球高光、H-Alpha 玫瑰色电离氢辐射星云、O-III 湖蓝反射星云与暗星云尘埃缝（Great Rift）。
- **深空标志性天体**：包含仙女座大星系（M31，受引力透镜弯折时形成双重镜像弧）与大麦哲伦矮星系（LMC）。
- **三维运动视差浮动微尘 (3D Space Parallax Dust)**：在摄像机视线空间沿多重深度采样亚微米星际尘埃，随飞船环绕呈现真实的三维纵深视差。

### 5. 电影级科学 HUD 与零遮挡交互系统
- **IMAX 宇宙超大广角**：默认提供 88° FOV 大视场角，一览浩瀚银河与黑洞同框的恢弘画卷。
- **动态无遮挡重定心 (Collision-Free Responsive Dock)**：侧边栏展开时，底部控制栏自动向左平移至视口有效观测中心，彻底杜绝小屏幕或高缩放分辨率下按键被侧边栏覆盖。
- **四角科幻遥测角标**：实时解算黑洞太阳质量倍数、引力时钟变慢因子（$d\tau = \sqrt{1 - R_s/r}\,dt$）、潮汐张力及多普勒束流比，鼠标悬停时呈现严格天体物理公式。
- **电影级 ACES 胶片色调映射**：保留高光软肩部细节，辅以微弱暗角（Vignette）营造太空探索纪实镜头感。

### 6. 深空低频引力共鸣音频引擎 (Cosmic Audio Engine)
- **Web Audio API 原生声景**：内置 Hans Zimmer 风格的深空持续低频重力共鸣（42Hz/55Hz 差频泛音），无需外部音频文件。
- **LIGO 脉冲 Chirp 鸣响**：支持一键激发布朗-爱因斯坦引力波脉冲，在产生度规时空涟漪的同时合成双黑洞并合的物理鸣响。

---

## 📐 核心物理公式与数学原理 (Physics & Mathematics)

### 1. 光子测地线微分方程 (Geodesic Equation)
在史瓦西与克尔度规弱场/中场近似下，光子在极坐标系中的二阶引力偏折加速度表述为：
$$\vec{a}_{\text{grav}} = -\frac{3 G M}{c^2} \frac{(\vec{r} \times \vec{v})^2}{r^5} \vec{r}$$
着色器采用 Runge-Kutta 2 (RK2) 中点法对光线步进矢量进行高精度数值积分：
$$\vec{r}_{n+1} = \vec{r}_n + \vec{v}_{n+1/2} \cdot \Delta t, \quad \vec{v}_{n+1} = \text{normalize}\left(\vec{v}_n + \vec{a}(\vec{r}_{n+1/2}) \cdot \Delta t\right)$$

### 2. 相对论多普勒聚束因子 (Doppler Boosting)
吸积盘等离子体以极端相对论速度 $v \sim 0.5c - 0.9c$ 自转，其观测辐射强度倍增因子为：
$$\delta = \frac{1}{\gamma (1 - \beta \cos\theta)}, \quad \gamma = \frac{1}{\sqrt{1 - \beta^2}}$$
$$I_{\text{obs}}(\nu) = \delta^4 I_{\text{emit}}(\nu/\delta)$$
其中 $\theta$ 为流体速度矢量与光线反向视线矢量的夹角。

### 3. 强引力时间膨胀率 (Gravitational Time Dilation)
工作站右下角遥测实时依据固有时（Proper Time）与无穷远协调时（Coordinate Time）比值动态刷新：
$$\frac{d\tau}{dt} = \sqrt{1 - \frac{R_s}{r}}$$
靠近视界临界处呈现极强引力红移与时间冻结（$1\text{h} \approx 7\text{y}$）。

---

## 🪐 天体物理度规基准预设库 (Astrophysical Benchmarks)

工作站内置了 6 套经天体物理理论校准的基准度规模型，每次切换均通过深拷贝恢复纯净原始模型：

| 预设名称 | 自旋参数 ($a^*$) | 视界半径 ($R_s$) | 特性亮点 |
| :--- | :---: | :---: | :--- |
| **原版卡冈图雅**<br>*(Gargantua Canonical)* | $0.95c$ | $1.00 M$ | 《星际穿越》经典复刻，温暖琥珀金吸积盘与平衡的多普勒束流 |
| **极轴光子对称环**<br>*(Polar Photon Ring)* | $0.35c$ | $1.15 M$ | 垂直俯瞰极轴爱因斯坦环，吸积盘呈现闭合完美圆形双拱高光 |
| **极速多普勒束流**<br>*(Doppler Beaming)* | $0.998c$ | $0.95 M$ | 极端非对称辐射，左侧强光炽白电离暴涨，右侧深度红移暗淡 |
| **人马座 A\***<br>*(Sagittarius A\*)* | $0.52c$ | $1.20 M$ | 银心超大质量黑洞观测模拟，宽厚漫射等离子体气环与深邃宇宙背景 |
| **极端自旋克尔黑洞**<br>*(Extremal Kerr Black Hole)* | $0.998c$ | $1.00 M$ | 逼近物理极限的克尔度规，最内稳定轨道剧烈内缩至 $1.25 R_s$ |
| **宁静史瓦西引力透镜**<br>*(Schwarzschild Lens)* | $0.00c$ | $1.10 M$ | 无吸积盘遮挡的纯引力度规球，呈现纯粹晶莹的银河星空扭曲形变 |
| **我的自定义黑洞**<br>*(Customized Model)* | 自定义 | 自定义 | 支持所有微观与宏观参数调谐，提供浏览器持久存储与外部 JSON 导出/导入 |

---

## 🎮 控制与交互指南 (Controls & Shortcuts)

### 🖱️ 鼠标与视口交互
- **鼠标左键拖拽**：360° 自由轨道环绕（俯仰角锁死在 $-88^\circ \sim +88^\circ$，杜绝极轴奇点翻转）。
- **鼠标滚轮**：连续缩放轨道观测距离（$2.0 \sim 28.0 R_s$）。
- **触控手势**：支持移动端单指滑动画幅旋转、双指捏合缩放视野。

### ⌨️ 全局键盘快捷键 (Hotkeys)
| 快捷键 | 功能描述 |
| :---: | :--- |
| <kbd>Space</kbd> | 开启 / 暂停电影级自动轨道环绕漫游 |
| <kbd>H</kbd> | 切换 HUD 显示 / 隐藏（进入纯净影院级观赏模式） |
| <kbd>M</kbd> | 开启 / 静音深空引力波共鸣低频声景 |
| <kbd>F</kbd> | 切换全屏沉浸观测模式 |
| <kbd>P</kbd> | 导出当前视口原生高分辨率无水印画幅（PNG 格式） |
| <kbd>1</kbd> ~ <kbd>5</kbd> | 快速切镜：宇宙大广角 / 电影经典 / 赤道平视 / 极轴俯瞰 / 视界特写 |
| <kbd>?</kbd> | 弹出相对论天体物理技术档案手册 |

---

## 🚀 快速启动 (Quick Start)

本项目完全独立原生，无需安装 Node.js、npm 或任何第三方插件。

### 方式一：直接运行 (本地双击)
直接使用任何现代 Web 浏览器双击打开项目根目录下的 `index.html` 即可。

### 方式二：本地 HTTP 服务 (推荐)
推荐使用本地轻量服务器启动以获得最佳的着色器缓存性能：
```bash
# 使用 Python 启动本地 Web 服务器
python -m http.server 8080

# 或使用 Node.js http-server
npx http-server -p 8080
```
启动后在浏览器访问 `http://localhost:8080` 即可开始探索。

---

## 💻 硬件与浏览器要求 (System Requirements)

- **浏览器**：Google Chrome 88+ / Microsoft Edge 88+ / Mozilla Firefox 85+ / Apple Safari 15+
- **图形接口**：支持 **WebGL 2.0** 与 **GLSL ES 3.00**（移动端需支持 OpenGL ES 3.0）
- **推荐显卡**：
  - 流畅体验：Intel Iris Xe / AMD Radeon Vega 8 或以上集成显卡
  - 电影画质：NVIDIA GeForce GTX 1060 / RTX 2060 / Apple M1 或独立显卡（可在侧边栏开启 1.5x~2.0x 超采样）

---

## 📁 目录结构 (Repository Structure)

```text
d:\Gemini antigravity Test\
├── index.html            # 相对论天体物理仿真工作站完整核心源码 (HTML5 + WebGL 2.0 + Web Audio)
├── README.md             # 项目中英文天体物理技术文档与使用手册
└── OPTIMIZATION_REPORT.md # 几何布局解耦、视口避让与数值稳定性工程报告
```

---

## 📜 许可证 (License)

本项目基于 [MIT License](LICENSE) 开源。欢迎天体物理爱好者、计算机图形学开发者自由研究、修改及二创。

<div align="center">
  <sub>Designed with precision for cosmic explorers and astrophysics enthusiasts.</sub>
</div>
