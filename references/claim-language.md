# 表达与论断强度

下列句式为本 skill 原创，不是论文原句。方括号表示作者需要提供的事实。选择表达前先确定结论性质；不要把技术审查变成只更换动词。

## 常用性质

| 想表达的内容 | 可用英文 | 需要保留的边界 |
|---|---|---|
| 精确谓词 | The predicate returns the exact sign of [expression] for [input representation]. | 表达式、输入和数值假设 |
| 有条件正确性 | Under [assumptions], [Theorem] establishes that [property]. | 不能删除 assumptions |
| 实测鲁棒性 | The implementation completed all [N] tested cases satisfying [criteria]. | 测试数量、有效输入、成功定义 |
| 实际速度 | On [hardware], the median end-to-end time is [value] for [workload]. | 统计量和计时边界 |
| 保守候选集 | The test retains every [target configuration] under [conditions], possibly including false positives. | 完备性依据和适用类 |
| 容差一致 | The output remains within [tolerance] of [reference] in [metric]. | 度量、单位、方向 |
| 输出转换限制 | Converting [exact representation] to [format] may invalidate [property]. | 有无实际反例/保证，勿扩大断言 |
| 未证推断 | These measurements suggest that [mechanism] accounts for [observed effect]. | 控制实验是否能识别因果 |
| 尚未覆盖 | The current algorithm does not cover [configuration]; [specific stage] requires [missing capability]. | 说明原因而非泛泛 future work |

## 容易过强的改法

- `works for arbitrary meshes` → 明确作者实际支持的输入类；未知时标记 `[待补：有效输入类]`。
- `guarantees robustness on Thingi10K` → `succeeded on all tested models in [specified subset]`；若有定理，另写定理条件。
- `the output is exact` → 指明是输入平面的精确 arrangement、精确交点，还是容差内 B-rep。
- `preserves topology` → 说明相对何种参考对象、采用何种拓扑关系；不能把减少裂缝自动写成同胚。
- `watertight and thus manifold` → 将两种性质拆开，分别核对。
- `interactive` → 写用户实际测得的延迟范围及 workload；没有延迟证据时用 `reduces computation time` 并标缺值。
- `X times faster` → 优先明确 `a speedup of [s]×`，其中 s 是同一协议下 baseline time / method time。
- `the first` / `state of the art` → 检索截至本次日期的直接相关工作；无法证实时改为具体差异。

## 领域用词

| 推荐区分 | 含义 |
|---|---|
| predicate / construction | 判定与生成几何对象 |
| intersection resolution / intersection detection | 处理相交与仅发现相交 |
| co-refinement / classification / extraction | 细分一致化、区域判断、边界输出 |
| near-degenerate / exactly degenerate | 近退化与数学退化 |
| general-position assumption / symbolic perturbation | 输入假设与消歧策略 |
| combinatorial structure / geometric realization | 组合连接与几何嵌入 |
| input geometry / quantized geometry | 原输入与转换后的参照对象 |
| regularized Boolean / boundary contact | 明确运算语义后再讨论低维接触 |
| trimming curve / p-curve / 3D edge curve | 不同表示空间中的曲线 |
| geometric tolerance / arithmetic error bound | 任务容许偏差与数值认证误差界 |

保留用户已有的合理术语和大小写约定。写 `Boolean operations` 或 `mesh Booleans` 均可，但不能把 Boolean collision query、二维曲面区域布尔与三维实体布尔混为一类。

## 段落连接

优先使用具体因果：`Because [specific predicate input] is [representation], we can [operation].` 或 `This construction maintains [invariant], which is needed by [next stage].`

减少空泛铺垫和未证定性词。每个 `therefore` 都应能指出前面的事实；每个 `guarantees` 都应能定位到证明、构造不变量或明确依赖。保留必要的限定，不为了“更像期刊”将 `can` 改成 `always`。
