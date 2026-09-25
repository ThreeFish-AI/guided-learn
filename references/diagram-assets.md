# 图表资产规范（Phase 4 · archify 优先）

> Phase 4 沉淀笔记的配图**默认走 archify**（独立的 archify 技能），不再手写内联 Mermaid。
> 两个条件分开判定：① 宿主未安装 archify、或图类型无 archify 对应（erDiagram/timeline/mindmap/
> quadrantChart/gantt/pie/gitGraph/classDiagram）→ 降级内联 Mermaid；② 在 ① 未命中时，项目有无
> 资产管线决定走第一节还是第四节。本规范总结自真实图资产管线的规模化实测；archify 的命令与参数若与已安装
> archify 文档冲突，以其文档为准。

## 一、项目有资产管线时（如 `docs/assets/`）

四件套单向链路，顺序不可逆（判据与决策见项目 `docs/.agents/doc-media-assets.md` 类文档）：

1. **文本源 SSOT**：`docs/assets/mermaid/<分类>/<slug>.mmd`——头部四行溯源注释
   （`%% source / %% slug / %% type / %% derived`），注释后图体与原笔记中被替换的
   mermaid 块**逐字节一致**（字节一致断言是管线纪律；需修正语义时用 `%% fix:` 行显式记录）。
2. **archify 重绘**：读 `.mmd` 取拓扑与语义，**重新创作** archify JSON（新稳定 ID、领域措辞、
   自行布局——严禁机械照搬 Mermaid 样式），`deliver` 产出
   `docs/assets/architecture/<分类>/<slug>.html`（整体替换，严禁手改 HTML）。
3. **PNG 采集**：项目采集脚本（如 `scripts/capture-arch-diagram.mjs`）产出
   `<slug>-dark.png` / `<slug>-light.png`；**文档内嵌一律用暗色 PNG**（进 wiki 的文档只允许
   纯 markdown `![]()` 相对路径）。
4. **消费与登记**：笔记中「暗色 PNG + 图源 .mmd 链接 + 交互版 HTML 链接」三件引用；项目资产
   索引（如 `docs/assets/mermaid/README.md`）登记新行。资产与索引必须同一次 `git add`。

## 二、archify 快速创作要点（对照 archify 技能的 Fast authoring path）

- **类型映射**：`flowchart/graph` → `workflow`（组件图用 `architecture`）；流水线/血缘/治理
  → `dataflow`；`sequenceDiagram` → `sequence`；`stateDiagram` → `lifecycle`。新 workflow 用
  `schema_version: 2`（col = 逻辑秩 0..5，省略 viewBox 让编译器测量）。
- **构图纪律**：≤12 主节点；一条清晰主链，旁支从最近主链节点分出；`meta.quality_profile` 必须
  `"showcase"`；`meta.locale: "zh-CN"`；2–3 张结论卡片（cards）承载图中说不完的机制要点；
  先自动路由，诊断叫加什么几何控制才加（一次最多一个）。
- **验收门**：`validate --quality showcase` 0 错 0 警（9 项 artifact checks）→ `deliver`（冻结
  快照、SHA-256 回执）→ `visual-check`（真实浏览器 1440×900/1600×1000/1920×1080/2048×1320
  containment 全过，四视口为命令固定集合）。**validate 单图 ≤10 轮**是硬纪律；
  两轮聚焦修复无改善即停下如实报告。

## 三、实测硬约束（踩过的坑，按图型速查）

| 图型 | 硬约束 | 违反症状 |
| --- | --- | --- |
| 全部 | 按 `desktop-readability` 实测控制 viewBox 与字号；必要时缩窄布局或增大字号（930px 可视区 / 6px 最小投影字号） | desktop-readability 报 `projectedFontPx < 6` |
| 全部 | `visual-check` 固定四视口（1440×900、1600×1000、1920×1080、2048×1320）containment 须全过 | visual-check overflowY |
| dataflow | stageX 固定 `100+i×215`；stage0 节点宽 ≤152；相邻段节点宽度和 ≤ ~390 | bounds 越界 / 端点 stub <8px |
| dataflow | 多条流共享段间竖向通道时，标签须落在通道间隙的空窗内 | label-route-clearance 0px |
| workflow v2 | 同列纵向堆叠节点会把 intrinsic 高度撑爆（1259×1999 实测）——优先折叠进 sublabel 单行主链 | 高度爆炸 / readability 挂 |
| workflow v2 | `drop` 等 route 预设可能不可满足；先 auto，诊断后再设 | route-preset-conflict |
| architecture | 垂直链路两端显式 `fromSide/toSide`；上下相邻组件**中轴对齐**（同宽同 x）防 S 型微段 | micro-segment / endpoint-side |
| lifecycle | 相邻态间隙固定 ~36px 放不下标签——标签 `labelDy` 上移出态带；泳道能少则少（3 泳道高度即近 700） | label overlap / 垂直越界 |
| 全部 | 消费文档为进 wiki 的 markdown 时只用 `![]()`，`<picture>`/`<img>` 会 404 | wiki 图裂 |

## 四、降级路径（无 archify、无对应图型或项目无资产管线）

- 无 archify、图型无对应，或项目无 `docs/assets/` 管线：笔记内联 Mermaid，遵循「概念图轻量、深色可读、subgraph 分层」原则，并在笔记头部注明未入管线的原因。
- 图类型无对应：原地保留 Mermaid（不建 .mmd，避免文本源双份）。
