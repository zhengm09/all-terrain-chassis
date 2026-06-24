# 双电机双液压回路 6 轮被动摇臂式全地形入户底盘

> 参考火星车被动摇臂悬架构型，兼顾平地行驶、坡面通行、楼梯攀爬三类核心工况，作为动力机甲承载底盘，完成从货车卸载至室内入户的全流程作业。

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/Version-v0.1--alpha-orange.svg)](CHANGELOG.md)
[![Issues](https://img.shields.io/github/issues/zhengm09/all-terrain-chassis.svg)](https://github.com/zhengm09/all-terrain-chassis/issues)

---

## 📋 项目概述

### 这是什么？

双电机独立驱动 + 双路独立液压源的 6 轮中驱被动摇臂底盘完整工程设计。采用火星车式被动摇臂悬架，前/后轮通过独立摇臂铰接实现地形自适应贴合，仅左右中轮为主动驱动轮，通过差速实现转向。

### 为什么做这个？

入户作业场景（从货车卸载 → 坡道 → 平地 → 楼道 → 楼梯 → 房门）对底盘通过性要求极高。本项目以 ≤50kg 满载质量约束下，验证该架构能否同时满足 30° 爬坡和连续爬楼至 7 层楼的工程可行性。

### 核心特性

- ✨ **火星车式被动摇臂悬架** — 前后轮独立摇臂铰接，纯地形自适应
- ⚡ **双电机一端行走 + 一端液压** — 每台电机非行走端同步驱动齿轮泵
- 🎯 **差速转向** — 左右中轮转速差实现前进/后退/原地转向
- 🔧 **开源协作模式** — 30+ 微任务池，单次交付、即做即走、碎片时间可认领

---

## 📊 技术指标

| 指标 | 参数 | 备注 |
|------|------|------|
| 总质量 | ≤ 50 kg | 满载 |
| 车轮直径 | 300 mm | 6 轮统一 |
| 布局 | 左右对称 6 轮中驱 | 前/后轮被动从动 |
| 最大速度 | 5 km/h | 平地标称 |
| 爬坡能力 | ≥ 30° | 理论最大 |
| 楼梯攀爬 | 连续至 7 层楼 | 标准民用楼梯 |
| 驱动方式 | 双电机独立差速转向 | 左右完全解耦 |
| 供电电压 | DC 48 V | |
| 伺服电机 | 80TM-04830C10-RHD | 1.5kW / 3000rpm |
| 驱动器 | BCPC-09050-OPE | 50Arms 连续 / 100Arms 峰值(6s) |

> 💡 完整技术指标请参考 [需求规格说明书](docs/requirements.md)

---

## 🏗️ 项目结构

```
all-terrain-chassis/
├── README.md                    # 你正在看的文件
├── LICENSE                      # 开源协议
├── CONTRIBUTING.md              # 贡献指南
├── CHANGELOG.md                 # 版本更新日志
│
├── docs/                        # 文档
│   ├── requirements.md          # 需求规格说明书
│   └── design-baseline.md       # 设计输入基线参数表
│
├── mechanical/                  # 机械设计
│   ├── layout/                  # 轮系布局设计
│   ├── suspension/              # 摇臂悬架设计
│   ├── cad/                     # CAD 文件（STEP / STL）
│   └── drawings/                # 工程图（PDF）
│
├── powertrain/                  # 动力传动
│   ├── calculations/            # 动力匹配计算
│   └── steering/                # 转向性能分析
│
├── hydraulic/                   # 液压系统
│   ├── schematics/              # 液压回路原理图
│   ├── pump-selection/          # 泵选型计算
│   └── tank-design/             # 油箱设计
│
├── simulation/                  # 仿真校核
│   ├── kinematics/              # 运动学通过性校核
│   ├── dynamics/                # 动力学与倾覆校核
│   └── thermal/                 # 热负载校核
│
└── bom/
    └── bom.csv                  # 物料清单
```

---

## 🚀 快速开始

### 查看设计成果

直接在 GitHub 上浏览各目录下的 Markdown 文件和图片即可。

### 参与设计

1. 查看 [Issue 列表](https://github.com/zhengm09/all-terrain-chassis/issues)，找到感兴趣的任务
2. 在对应 Issue 下留言「认领」
3. Fork 本仓库，在你的分支上完成设计
4. 提交 Pull Request，等待审核合并

> 📖 详细步骤请参考 [贡献指南](CONTRIBUTING.md)

---

## 📋 任务进度

### 当前阶段：概念设计阶段

| 模块 | 进度 | 状态 |
|------|------|------|
| 设计输入基线 | 0% | ⏳ 待认领 |
| 机械构型设计 | 0% | ⏳ 待认领 |
| 动力传动匹配 | 0% | ⏳ 待认领 |
| 液压系统设计 | 0% | ⏳ 待认领 |
| 运动学校核 | 0% | ⏳ 待认领 |
| 动力学校核 | 0% | ⏳ 待认领 |

> 🎯 实时进度请查看 [Issue 看板](https://github.com/zhengm09/all-terrain-chassis/issues)

---

## 🤝 如何参与

### 协作规则

本项目适配开源社区零星投入、碎片时间协作的模式：

- **认领即开工**：任务池长期开放，无前置依赖的随时可领
- **单次交付制**：做完提交即算完成，无需跟进后续。每个成果标注 V1 版本
- **迭代自由领**：校核发现问题后新增「XX 优化迭代」微任务，任何人可认领升级到 V2
- **低门槛上手**：优先认领基础层任务熟悉项目；有专业背景的可直接认领设计/校核类任务

### 贡献方式

1. **认领任务**：在 Issue 下评论「认领」
2. **完成设计**：在你的 Fork 仓库中完成
3. **提交 PR**：描述清楚做了什么、对应哪个 Issue
4. **审核合并**：维护者审核后合并到主分支

### 提交规范

- 文件名使用英文，小写加连字符（如 `wheel-layout-params.md`）
- 计算类内容优先使用 Markdown 表格
- Commit 信息格式：`类型: 简短描述`
  - `feat: 添加轮系布局参数表`
  - `fix: 修正爬坡扭矩计算错误`
  - `doc: 更新设计基线文档`

---

## 🛠️ 技术栈

| 类别 | 推荐工具 | 说明 |
|------|----------|------|
| 文档撰写 | Markdown | GitHub 原生支持，版本对比友好 |
| 机械 CAD | Fusion 360 / SolidWorks / FreeCAD | 导出 STEP / STL 提交 |
| 工程图 | AutoCAD / SolidWorks | 导出 PDF 提交 |
| 计算分析 | Excel / Python / MATLAB | 结果用 Markdown 表格呈现 |
| 仿真分析 | ADAMS / RecurDyn / 简化计算 | 报告用 Markdown + 截图 |

> 💡 不强制使用特定软件，只要能输出通用格式成果即可。

---

## 📄 开源协议

本项目采用 [MIT License](LICENSE) 开源协议。

- ✅ 可以商用
- ✅ 可以修改
- ✅ 可以分发
- ✅ 可以私用
- ⚠️ 必须保留版权声明
- ⚠️ 作者不承担责任

---

## 📞 联系方式

- 💬 **讨论区**：[GitHub Discussions](https://github.com/zhengm09/all-terrain-chassis/discussions)
- 🐛 **提问题**：[提交 Issue](https://github.com/zhengm09/all-terrain-chassis/issues/new)

---

*最后更新：2026年6月24日*
