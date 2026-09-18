# Guided Learn — 导师式精读与领域掌控

以**严格且经验老到的老师**身份，带用户完整学习并掌控论文、文档、网页、视频等一手材料中的领域技能：
全貌解剖（先梳理后总结）→ 领域底层规律与争议提炼 → 类比化讲授 → 最小原型实践与破坏性实验 → 经验沉淀入库。

## 安装

本技能遵循 SKILL.md 开放标准，Claude Code 与 Antigravity IDE 通用，差异仅在技能目录：

| 宿主 | 全局技能目录 | 工作区级技能目录 |
| :--- | :--- | :--- |
| Claude Code | `~/.claude/skills/` | `<repo>/.claude/skills/` |
| Antigravity IDE | `~/.gemini/config/skills/` | `<workspace>/.agents/skills/` |

```bash
# 方式一：克隆即装（外部用户）——SKILL_DIR 取上表对应目录
SKILL_DIR=~/.claude/skills   # Antigravity IDE 改为 ~/.gemini/config/skills
git clone https://github.com/ThreeFish-AI/guided-learn.git $SKILL_DIR/guided-learn

# 方式二：symlink（本机维护模式——改仓库即改 Skill，多宿主共享单一事实源）
git clone https://github.com/ThreeFish-AI/guided-learn.git ~/{projects-dir}/guided-learn
ln -s ~/{projects-dir}/guided-learn ~/.claude/skills/guided-learn           # Claude Code
ln -s ~/{projects-dir}/guided-learn ~/.gemini/config/skills/guided-learn    # Antigravity IDE
```

> 技能清单在**会话开始时**扫描，安装后须重启 Agent 会话方可被发现。Antigravity 向后兼容旧路径 `~/.gemini/antigravity/skills/` 与 `.agent/skills/`。

## 使用

显式调用：`/guided-learn <材料 URL 或路径>`（Claude Code 与 Antigravity IDE 通用）；或自然语言触发——
「带我精读这篇论文」「先梳理全貌不要急着总结」「提炼这个领域的核心规律与争议」「以老师身份教我掌握 X」「帮我搞懂这份资料/视频并实践」。

## 工作流（五阶段线性单向演进）

| 阶段 | 核心内容 | 交付形式 | 阶段门禁 |
| :--- | :--- | :--- | :--- |
| **Phase 0** | 准入体检：摄取一手材料（含附录），提取前置门槛与补课建议 | 对话交互 | 3 道前置检测自测题 |
| **Phase 1** | 全貌解剖：一句话本质与贯穿总类比 + 最重要的几个部分（分层矩阵）+ 核心关系（因果脉络链）+ 基础层 vs 学习焦点排序与批判边界 | 对话交互 | 复述总类比与脉络主线，理解三大核心问题 |
| **Phase 2** | 底层规律、核心争议与严师考评闭环：<br/>• **2a. 规律篇**：正交分解 5 大底层规律（最简解释 + IEEE 锚点 + 解决什么问题 + 实证演示）<br/>• **2b. 争议篇**：统一世界观剖析 2~3 个核心技术争议（通俗场景 + 分歧根源 + 本质层级）<br/>• **2c. 严师考评篇**：资料研究范围界定 + 费曼三维考评 + 薄弱点诊断 + 针对性充分教授 + 同构变式复考 | 对话交互 | 完成资料研究范围确认；费曼考评通过同构变式复考全绿闭环 |
| **Phase 3** | 原型验证与破坏性实验：在 `.temp/` 构建轻量确定性 mock 原型，拔掉机制实测退化 | 代码与实测 (`.temp/`) | `selftest` 全绿 + 破坏性退化实测记录 |
| **Phase 4** | 经验结晶与系统映射：三拍结构通俗笔记（archify 优先）+ 代码行号精准映射报告 | 文档入库 (`docs/`) | 文档落盘 + 映射报告核验 + 知识索引同步 |

## 仓库结构

```
SKILL.md                      # 主工作流、触发契约、教学铁律与交互状态机
references/lecture-format.md  # 讲授与沉淀模板（全貌三问/规律/争议/严师费曼考评与变式复考/笔记与映射报告骨架）
references/prototype-lab.md   # 最小原型实验室方法论（确定性 mock / 场景设计 / 破坏性实验纪律）
references/diagram-assets.md  # 图表资产管线规范（archify 优先 / Mermaid 降级）
```

---

<div align="center">
  <sub>Built with 🧠, ❤️, and an absurd amount of coffee by <a href="https://github.com/ThreeFish-AI">ThreeFish-AI</a> · Released under the <a href="./LICENSE">MIT</a>.</sub>
</div>
