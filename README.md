# Guided Learn — 导师式精读与领域掌控

以**严格且经验老到的老师**身份，带用户完整学习并掌控论文、文档、网页、视频等一手材料中的领域技能：
全貌解剖（先梳理后总结）→ 领域底层规律与争议提炼 → 类比化讲授 → 最小原型实践与破坏性实验 → 经验沉淀入库。

## 安装

```bash
# 方式一：克隆即装（外部用户）
git clone https://github.com/ThreeFish-AI/guided-learn.git ~/.claude/skills/guided-learn

# 方式二：symlink（本机维护模式——改仓库即改 Skill）
git clone https://github.com/ThreeFish-AI/guided-learn.git ~/{projects-dir}/guided-learn
ln -s ~/{projects-dir}/guided-learn ~/.claude/skills/guided-learn
```

## 使用

显式调用：`/guided-learn <材料 URL 或路径>`；或自然语言触发——
「带我精读这篇论文」「先梳理全貌不要急着总结」「提炼这个领域的核心规律与争议」「以老师身份教我掌握 X」「帮我搞懂这份资料/视频并实践」。

## 工作流（五阶段线性单向演进）

| 阶段 | 核心内容 | 交付形式 | 阶段门禁 |
| :--- | :--- | :--- | :--- |
| **Phase 0** | 准入体检：摄取一手材料（含附录），提取前置门槛与补课建议 | 对话交互 | 3 道前置检测自测题 |
| **Phase 1** | 全貌解剖：一句话本质与贯穿总类比 + 重要性分层（Tier 1~3）+ 因果脉络链 + 批判性边界 | 对话交互 | 复述总类比与脉络主线 |
| **Phase 2** | 底层规律与争议：正交分解提炼底层规律（IEEE 锚点 + 实证演示）+ 核心技术争议剖析 | 对话交互 | 费曼测试（方案差异/流程推演/场景预测） |
| **Phase 3** | 原型验证与破坏性实验：在 `.temp/` 构建轻量确定性 mock 原型，拔掉机制实测退化 | 代码与实测 (`.temp/`) | `selftest` 全绿 + 破坏性退化实测记录 |
| **Phase 4** | 经验结晶与系统映射：三拍结构通俗笔记（archify 优先）+ 代码行号精准映射报告 | 文档入库 (`docs/`) | 文档落盘 + 映射报告核验 + 知识索引同步 |

## 仓库结构

```
SKILL.md                      # 主工作流、触发契约与交互状态机
references/lecture-format.md  # 讲授与沉淀模板（全貌/规律/争议/费曼测试/笔记与映射报告骨架）
references/prototype-lab.md   # 最小原型实验室方法论（确定性 mock / 场景设计 / 破坏性实验纪律）
references/diagram-assets.md  # 图表资产管线规范（archify 优先 / Mermaid 降级）
```

---

<div align="center">
  <sub>Built with 🧠, ❤️, and an absurd amount of coffee by <a href="https://github.com/ThreeFish-AI">ThreeFish-AI</a> · Released under the <a href="./LICENSE">MIT</a>.</sub>
</div>
