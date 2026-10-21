# TOG CAD Writing Skill

面向 CAD 与计算几何设计的 TOG 论文写作 skill：从真实方法、数学条件和实验出发，组织英文正文、核对论断范围，并按任务选择段落模板与评估方法。

English drafting patterns with Chinese guidance for CAD research: spline and freeform surfaces, parameterization, meshing, shape editing, computational fabrication, and robust Boolean operations.

## 覆盖范围

- 曲线、样条、自由曲面及表示转换。
- 参数化、三角/四边形/体网格与高阶几何有效性。
- 交互建模、形状编辑、几何约束与优化。
- 建筑几何、可展曲面、可部署结构与制造。
- 三维布尔、mesh arrangements、NURBS 求交与包含查询。

按实际研究任务选择规则；参数化、服装设计、几何分析接口和工程 B-rep 不共享同一套有效性结论。

## 当前内容

- 39 个功能段落模块：10 个 CAD 通用模式与 29 个布尔专项模块。
- CAD 技术契约、论断强度检查、分任务实验与图表指南。
- 中文说明与可填写的英文正文模板。

发布包仅包含可直接使用的 skill 指令与指南。具体论文的引用和技术结论须根据用户提供或当次读取的原文核对。

## 快速使用

直接阅读 [SKILL.md](SKILL.md)，或把下面的请求与真实研究材料交给支持 skill 的写作助手：

```text
使用 $tog-cad-writing 帮我修订英文 Introduction。

研究任务与输入输出：……
最接近的工作与具体差异：……
核心设计及其数学条件：……
已完成实验和真实结果：……
已知失败与适用边界：……
现有草稿：……

保留技术含义和引用键，检查“问题—困难—设计—性质—证据”的衔接。
缺失事实用 [待补：具体事实] 标记。
```

更多示例：

```text
使用 $tog-cad-writing 检查 Method 中的可行性、收敛性与最优性是否混写。
```

```text
使用 $tog-cad-writing 为我的曲面参数化算法规划实验，分别验证单射性、质量与导出几何。
```

```text
使用 $tog-cad-writing 修订制造实验章节，区分几何条件、物理模型与实物测量。
```

## 安装

本仓库根目录就是 skill 目录。将整个目录命名为 `tog-cad-writing`，放入所用助手的个人 skills 目录。以 Codex 的默认个人目录为例：`~/.codex/skills/tog-cad-writing/`；自定义了 CODEX_HOME 时使用其下的 skills 目录。已有同名安装时先保留本地修改。

Windows PowerShell，需要已安装 Git：

```powershell
$repositoryUrl = Read-Host '粘贴本仓库的 HTTPS 克隆地址'
$skillBase = if ($env:CODEX_HOME) { Join-Path $env:CODEX_HOME 'skills' } else { Join-Path $HOME '.codex\skills' }
git clone $repositoryUrl (Join-Path $skillBase 'tog-cad-writing')
```

也可以下载仓库 ZIP、解压，并将含有 SKILL.md 的目录放到上述位置。之后使用 `$tog-cad-writing` 调用。

## 文件导航

| 文件 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | 核心指令、任务分支与阅读路由 |
| [CAD 技术契约](references/cad-contract.md) | 表示、参数化、优化、交互与制造主张 |
| [CAD 段落模式](references/cad-patterns.md) | 10 个可填写的 CAD 英文功能模式 |
| [CAD 评估](references/cad-evaluation.md) | 按实际贡献选择实验与图表 |
| [布尔技术契约](references/domain-contract.md) | 布尔、arrangement、CAD 求交与数值边界 |
| [布尔段落模块](references/section-templates.md) | 29 个章节功能模块 |
| [布尔评估](references/evaluation.md) | 鲁棒性、性能、容差与导出检查 |
| [论断强度](references/claim-language.md) | 证明、经验观察与推测的区分 |
| [投稿规范](references/venue.md) | 投稿路线区分；使用时核对最新官方规则 |

## 使用边界与贡献

模板是原创功能抽象，不能把参考论文的结果、定理或数值当作用户方法的证据。精确性、连续性、单射性、水密性、最优性与可制造性分别核查。此项目是写作辅助，不是 ACM 官方规范，也不承诺录用。

欢迎通过 Issue 或 Pull Request 提交规则修正、模板改进及不适用场景。涉及具体研究结论时，请说明相应依据与条件。

## 来源与许可

组织思路参考 [Fasuiker/ai-graphics-paper-writing](https://github.com/Fasuiker/ai-graphics-paper-writing)，并针对 CAD 研究独立改写和扩充。上游署名及 MIT 声明保留于 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

本仓库的原创指令、模板和归纳采用 [MIT License](LICENSE)。原论文、作者稿及幻灯片属于各自权利人，其许可不由本仓库的 MIT 许可证替代。
