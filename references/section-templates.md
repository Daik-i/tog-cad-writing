# 可填写的段落模块

下列英文均为独立编写的功能模板，不是论文原文。选择相关模块，按材料合并、拆分或删除句子；方括号须由作者真实材料填写。技术结论、定理与比较需要用户方法及实际原文支持。

## Abstract

### A1 · 对象、缺口与技术洞察

1. 界定任务：`Computing [Boolean operation / arrangement] on [representation] is a key step in [specific workflow].`
2. 指出可核实缺口：`Existing approaches [specific limitation] when [configuration or workload].`
3. 引出洞察：`We address this issue by [core mechanism], which allows [specific stage] to [benefit].`
4. 保留契约：`For [valid input class], the algorithm produces [output representation] with [supported properties].`

### A2 · 结果与意义

1. `We evaluate the implementation on [dataset and valid subset] using [success criteria].`
2. `Under [comparison conditions], it achieves [measured performance] relative to [baselines].`
3. `These results enable [demonstrated workflow] within [scope].`

没有结果时保留占位，不补入来源论文的成功率或速度。代码/数据发布只在用户确已发布或明确承诺时写入。

## Introduction

### I1 · 从具体建模工作流建立问题

1. `In [modeling or manufacturing workflow], [users/system] repeatedly [specific operation].`
2. `This requires [geometric property] while accommodating [input variability or latency constraint].`
3. `A failure in [low-level operation] can [documented downstream consequence].`
4. `The challenge is therefore to [precise computational task] under [conditions].`

只用真实工作流，避免以“3D data has grown rapidly”代替具体问题。

### I2 · 从数值矛盾引出设计

1. `The difficulty arises when [constructed quantity] is reused by [decision or stage].`
2. `Approximating it can [specific inconsistency], whereas [established alternative] incurs [documented cost].`
3. `Our key observation is that [actual structural property].`
4. `We exploit this property to [algorithmic change], while retaining [precisely stated guarantee].`

用户未给动机实验或理论时，把 observation 降为 design idea；不伪造观察。

### I3 · CAD 混合表示的桥接动机

1. `A mesh approximation offers [useful operation], but the final result must remain in [required CAD representation].`
2. `A direct transfer is insufficient because [missed configuration or representation mismatch].`
3. `We retain [surface/parameter correspondence] and use [certified or tolerance-controlled mechanism] to connect the two representations.`
4. `This connection allows [operation] while [remaining condition or unresolved case].`

不要默认存在双射、全局 Hausdorff 界或无条件拓扑保证；这些需由用户方法提供。

### I4 · 贡献按证据组织

- 理论：`A [result] establishing [property] for [input class] under [assumptions].`
- 算法：`An algorithm for [task] based on [distinct mechanism].`
- 表示：`A representation that makes [operation or invariant] explicit through [structure].`
- 实现/验证：`An implementation and evaluation covering [workloads], with [actual released artifacts if any].`

将复用组件标成依赖，避免把“用了精确谓词库”写成新的精确算法贡献。

## Related Work

### R1 · 按技术问题分类

1. `Prior approaches differ in [representation], [numerical model], and [admissible input class].`
2. `[Category A] addresses [specific difficulty] by [mechanism], subject to [documented requirement].`
3. `[Category B] instead [mechanism], trading [verified cost] for [supported benefit].`
4. `Our method targets [remaining gap] while retaining [actual compatibility or restriction].`

可沿 vertex/plane/implicit/B-rep、单次/迭代、精确/容差、有效输入类组织；不必同时展开所有轴。

### R2 · 与最近工作的可核实差异

1. `[Closest method] computes [task] for [input class] using [mechanism].`
2. `Our setting differs in [specific requirement], which makes [specific design choice] necessary.`
3. `We compare the two methods under [shared conditions] and separately report [incompatible settings].`

没有原文支持时用 `[待补：最近工作条件与定位]`；不凭当前工具失败断言原论文不能处理某类输入。

### R3 · 先比较任务与 hybrid 的含义

1. `[Method A] computes [rendering / containment / boundary extraction] from [representation].`
2. `The representation in [Method A] connects [specific objects] to support [task], whereas [Method B] uses [representation] for [its task].`
3. `These approaches address [shared difficulty] but produce [distinct outputs], so we compare [appropriate property] separately.`

按实际任务选句；不得将曲线 GWN、CSG 渲染和合法 B-rep 构造列在同一无条件正确率排名。

## Method

### M1 · 输入输出契约与总览

1. `The input consists of [objects] satisfying [conditions], together with [operator or expression].`
2. `We represent [numerical/structural object] as [actual representation].`
3. `The algorithm first [stage and intermediate output], then [stage using that output].`
4. `The final output is [format], with [properties] under [assumptions].`
5. `Figure [id] illustrates the stages on [running example].`

### M2 · 表示驱动的数值设计

1. `We store [constructed entity] as [explicit coordinates / unevaluated expression / supporting planes].`
2. `The algorithm queries [predicate] to determine [decision].`
3. `Evaluating [expression] in this representation preserves [invariant] because [argument].`
4. `The implementation first uses [actual filter]; unresolved cases are handled by [actual certified fallback].`
5. `Conversion to [output number type] occurs at [stage], where [guarantee or limitation].`

没有认证 fallback 就不能填 exact；未评估转换效应则标缺口。

### M3 · arrangement 与一致剖分

1. `We collect [candidate primitive pairs] using [broad-phase structure].`
2. `For each [intersected primitive], we construct [intersection entities] and enforce [consistency constraint].`
3. `[Deduplication or triangulation rule] ensures that [shared geometric entity] receives [consistent representation].`
4. `The resulting [complex] supplies [adjacency or geometry] to [next stage].`

只计算局部 arrangement 时说明如何拼接，不声称已得到全局 cell decomposition。

### M4 · 分类、嵌套与边界提取

1. `Each [cell or patch] is assigned [label] with respect to [input objects].`
2. `We initialize these labels using [reference or query] and update them through [rule].`
3. `[Nested components / degenerate rays / coplanar regions] are handled by [actual mechanism].`
4. `A boundary element is retained when [selection condition], with its orientation determined by [rule].`
5. `We propagate [provenance or attributes] from [source elements] to the result.`

不要默认 ray casting、winding-number propagation 或图割是所有方法的共同步骤。

### M5 · CAD 对应、容差和回写

1. `For each [surface patch], we retain [parameter/domain/face correspondence] during discretization.`
2. `The approximation satisfies [one-/two-sided error condition] in [metric], with tolerance [definition].`
3. `We detect candidate [intersection or overlap configurations] using [conservative criterion].`
4. `The discrete candidates initialize [continuous computation], and [recovery procedure] handles [failure].`
5. `Finally, [curves and topology] are mapped to [B-rep output], subject to [verified consistency conditions].`

### M6 · 局部化或并行优化

1. `The baseline procedure spends [measured fraction or qualitative bottleneck] on [operation].`
2. `We restrict [work] to [local domain] because [dependency argument].`
3. `This permits [independent computation / reduced dimension / early termination] without changing [invariant].`
4. `Section [id] isolates the effect of this change from [thread count or other optimization].`

没有 profile 时不要编造耗时比例；说明机制，列待测项。

### M7 · 正确性与可实现条件

1. `Assume [complete assumptions, including arithmetic and degeneracy conditions].`
2. `The construction maintains [invariant] after each [operation].`
3. `Since [argument linking invariant to goal], [claimed property] follows.`
4. `This result concerns [internal representation]; [conversion or unsupported case] is treated separately.`

证明缺失时可写 proof obligation 清单，不将合理直觉写成已证明结论。

### M8 · 复杂度与资源

1. `Let [symbols] denote [input, intersection, output and arithmetic complexity].`
2. `[Stage] requires [derived bound] under [assumptions], including [relevant output/bit complexity].`
3. `The implementation stores [dominant structure], requiring [supported memory bound].`
4. `We separately measure [cost not captured by the bound].`

没有推导则写实测 scaling；不能将模型数横轴上的平滑曲线称为渐近证明。

### M9 · 连续曲线/曲面上的包含查询

1. `We evaluate [field or quantity] at [query points] on the basis of [continuous geometry].`
2. `[Mathematical reformulation] reduces the computation to [integral or certified equivalent construction].`
3. `We control [numerical evaluation error] using [actual tolerance or certificate], and handle [coincident / near-boundary configurations] by [actual procedure].`
4. `The query returns [scalar or classification]; constructing [explicit Boolean boundary] requires [separate algorithm, if present].`

明确等价性是对一个查询点、整个区域还是全部输入；不将用户容差等同于 arithmetic filtering 的误差认证。

## Experiments

### E1 · 可比较的实验协议

1. `We evaluate [task] on [dataset], retaining [N] inputs according to [published selection rule].`
2. `All methods use [hardware, versions, settings and thread counts], with [limits].`
3. `We report [correctness criteria] separately from [timing metrics].`
4. `The reported times include [stages] and exclude [stages], which are listed separately.`
5. `For [methods with different domains], results are stratified by [compatibility condition].`

### E2 · 鲁棒性及失败

1. `A run is considered successful when [explicit output checks].`
2. `We distinguish [invalid inputs], [algorithmic failures], [invalid outputs], and [resource-limit failures].`
3. `Among [denominator], the method satisfies [checks] on [measured count].`
4. `These tests establish [empirical conclusion]; [unverified property] is not implied by them.`

### E3 · 效率与尾部样例

1. `We compare end-to-end runtime on [defined workload] and component costs for [stages].`
2. `On the [common-success subset], [statistic] changes from [baseline] to [ours].`
3. `Over the full benchmark, [timeouts/failures] account for [measured counts], reported separately.`
4. `Performance varies with [intersection/output complexity], as shown in [figure].`
5. `For the most demanding cases, we report [runtime and peak memory] rather than omitting them.`

### E4 · 从机制到消融

1. `To isolate [mechanism], we compare [controlled variants] with [fixed conditions].`
2. `Removing [change] affects [target quantity], while [checked property] remains [observed status].`
3. `[Filter statistics / predicate counts / local workload / component timing] explains [measured difference].`
4. `This supports [limited mechanism claim] on [tested regime].`

若替换 exact kernel 会改变正确性，须同时报告该变化，不把不等价变体仅当速度消融。

### E5 · CAD 几何和拓扑质量

1. `We assess [curve residual / patch correspondence / boundary consistency] relative to [reference].`
2. `The tests include [small loops, tangencies, boundary intersections, overlaps] within [defined scales].`
3. `At tolerances [values], we report [geometric error], [topological checks], and [runtime].`
4. `Figure [id] shows [verified discrepancy] together with [diagnostic close-up].`
5. `For features below [supported resolution], [observed failure or explicit restriction].`

## Figures and captions

### F1 · 管线图与运行示例

1. `Overview of [method] on [example].`
2. `From left to right: [input], [intermediate states with distinct roles], and [output].`
3. `[Colors or symbols] indicate [consistent semantics].`
4. `[Inset] highlights [mechanism or actual invariant], rather than only the final appearance.`

正文逐一解释图中的实际状态；不要把细节机制全部挤入 teaser。

### F2 · 对比图、接触与失败

1. `Comparison on [configuration], with [matched settings or documented difference].`
2. `[Marker/inset] reveals [verified failure or geometric difference].`
3. `[Slice/wireframe/topological annotation] shows [hidden structure].`
4. `The result satisfies [checked property]; [different property] is not assessed by this view.`

### F3 · 统计图和表格

1. `[Metric and aggregation] on [exact dataset/subset].`
2. `[Axis/units/log scale and normalization] are defined as [definition].`
3. `[Failure marker] denotes [timeout, invalid output, unavailable result], and is not treated as zero.`
4. `[Excluded cases] are reported in [separate location] with [reason].`

## Discussion and conclusion

### D1 · 导出与级联边界

1. `The guarantee applies while [intermediate representation] is retained.`
2. `Converting to [format] can [failure mechanism] under [conditions].`
3. `Consequently, [cascaded workflow] requires [actual preservation or recovery mechanism].`
4. `Our current implementation [supported behavior], leaving [specific unresolved case].`

### D2 · 失败原因与适用范围

1. `The method assumes [condition] and does not cover [counterexample class].`
2. `This restriction arises in [stage] because [specific reason].`
3. `[Actual experiment] illustrates the boundary at [scale or condition].`
4. `Addressing it would require [specific capability], which is outside the current validation.`

### C1 · 收束已被支持的贡献

1. `We presented [actual contribution] for [task and input class].`
2. `[Theoretical result or experiments] supports [exactly scoped conclusion].`
3. `The method enables [demonstrated application], while [material boundary] remains.`

若用户只要一两句结论，可合并前两句；不要首次加入新应用、性能或保证。
