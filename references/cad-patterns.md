# CAD 写作的功能段落模式

均为独立编写的英文模板，不复制原句。方括号须由用户事实填入，不能将模板当作用户新方法的证据。布尔专项模式另见 [section-templates.md](section-templates.md)。

## CP1 表示为何值得引入

`Existing representations support [operation], but combining [property A] with [property B] remains difficult under [conditions]. We represent [object] using [construction], making [relationship] explicit. This representation provides [proved properties] for [domain], while [unverified or excluded property] is assessed separately.`

不要把连续性、正则性、拓扑和视觉质量合并为一句 guarantees high quality。

## CP2 用具体设计动作定位问题

`In [workflow], the designer repeatedly [operation]. Current tools require [specific intermediate action], which makes [task] difficult. Our system lets the designer specify [intent or constraints] through [interaction]. The algorithm converts these inputs into [geometric problem] and returns [editable output].`

最后补真实延迟或用户任务证据；未做用户研究不推断可用性提升。

## CP3 限定近似与设计空间

`We target [class of shapes] within [regime]. The representation exposes [design variables], which control [geometric properties]. We approximate [target] by minimizing [defined error] subject to [constraints]. This choice reduces [specific cost or complexity] but restricts [remaining design freedom].`

误差、复杂度和自由度的取舍应能在后续实验找到对应结果。

## CP4 从连续条件到离散算法

`The continuous condition requires [property] over [domain or trajectory]. We discretize [object] as [variables] and enforce [conditions]. Under [proved assumptions], these conditions imply [precise conclusion]. In the implementation, [numerical mechanism] controls [residual or certification], and [conversion] is treated separately.`

没有证明时将第三句改为经验验证陈述，不能以采样密度大代替连续结论。

## CP5 优化 formulation 与初始化

`Let [variables] encode [geometry or structure]. We minimize [objective] while enforcing [constraints], where [term] measures [design goal]. We initialize the variables using [procedure] because [observed or derived reason]. Optimization stops when [criterion]; unsuccessful or infeasible cases are detected by [check].`

权重、单位、初始化和约束残差分别可查；未证明全局性不填 globally optimal。

## CP6 制造约束如何进入几何设计

`The fabrication process requires [restriction]. We encode it as [geometric constraint] on [representation]. The resulting design is converted to [panels / tool paths / assembly geometry] using [procedure]. We validate [geometric property] computationally and evaluate [physical outcome] on [actual prototypes].`

只能保留已经完成的验证句；仿真、加工和实物结果分开写。

## CP7 表示、工具与应用贡献各司其职

`The geometric result characterizes [class or relationship]. Based on this result, we develop [construction or algorithm], which enables [actual design operation]. We demonstrate its use in [applications], subject to [conditions].`

贡献列表可按“理论结果、实现算法、设计工具、应用验证”裁剪，不把每个阶段都包装成独立创新。

## CP8 参数化/网格实验的有效分母

`We retain [N] inputs satisfying [eligibility rule] and report [validity] separately from [quality]. Quality and runtime are compared on [defined subset], while failures over the complete set are listed as [categories]. We additionally evaluate the exported [mesh or spline], since [internal property] alone does not establish [downstream property].`

## CP9 学习辅助几何的分阶段结论

以下是任务契约建议；具体文献引用须来自实际读取的相关原文。

`The model predicts [quantity] from [input representation]. We separate prediction accuracy from the validity of [constructed curves / patches / topology]. Training and evaluation use disjoint [original model units], with [noise or distribution shift] evaluated separately. A downstream experiment measures [actual CAD task], rather than inferring it from [proxy metric].`

## CP10 诚实解释失败与限制

`The current method relies on [assumption or initialization]. When [configuration] violates this requirement, [observed behavior] occurs at [stage]. The evidence supports [limited conclusion] on [tested regime]; extending it to [unverified case] requires [specific capability].`

失败机理若为推测则用 may / suggests，并保留观察与解释之间的区别。
