# Guided Learn — 导师式精读与领域掌控

以**严格导师（Mentor Agent） + 求知学徒（Learner Subagent）双代理对抗内省**，带用户系统化精读并掌控论文、长文档、网页、视频等一手材料：
全貌解剖（先梳理后总结）→ 领域底层规律与争议提炼 → 双 Agent 费曼考评闭环（白话推演/诊断/培优/变式复考）→ 最小原型实践与破坏性实验 → 经验沉淀入库。

**核心创新**：全流程所有确认、答复、考核评估与通过性测试均由内置定制的 **Learner Subagent** 代管协助完成，消除中途交互阻塞；整套高价值知识与工程资产端到端自治交付，用户在获取完整沉淀后可按需发起追问与费曼自我考核。

---

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

---

## 使用

显式调用：`/guided-learn <材料 URL 或路径>`（Claude Code 与 Antigravity IDE 通用）；或自然语言触发——
「带我精读这篇论文」「先梳理全貌不要急着总结」「提炼这个领域的核心规律与争议」「以老师身份教我掌握 X」「帮我搞懂这份资料/视频并实践」。

---

## 工作流（五阶段自治演进流水线）

| 阶段 | 核心内容 | 协同执行机制 | 门禁验收（内部自治） | 用户交互状态 |
| :--- | :--- | :--- | :--- | :--- |
| **Phase 0** | 准入体检：摄取一手材料（含附录），提取前置门槛与补课建议 | Mentor 提取门槛自测题 ↔ Learner Subagent 独立自检作答 | 明确知识盲区与补课建议 | 免阻塞（自治演进） |
| **Phase 1** | 全貌解剖：一句话本质与贯穿总类比 + 最重要的几个部分（分层矩阵）+ 因果脉络链 + 基础层 vs 学习焦点排序与批判边界 | Mentor 讲授解剖 ↔ Learner Subagent 脉络复述与主线验证 | 建立贯穿总类比；理清因果主线与 5 条批判边界 | 免阻塞（自治演进） |
| **Phase 2** | 底层规律、核心争议与双 Agent 费曼考评：<br/>• **2a. 规律篇**：正交分解 5 大底层规律（最简解释 + IEEE 锚点 + 实证演示）<br/>• **2b. 争议篇**：统一世界观剖析 2~3 个核心技术争议<br/>• **2c. 费曼考评篇**：资料研究范围界定 + 费曼三维考评 + 薄弱点诊断 + 针对性充分教授 + 同构变式复考 | Mentor 出题与审校 ↔ Learner Subagent 独立应答、暴露薄弱点、吸收教授并完成变式复考 | 完成研究范围界定；费曼三维考评通过同构变式复考全绿闭环 | 免阻塞（自治演进） |
| **Phase 3** | 原型验证与破坏性实验：在 `.temp/` 构建轻量确定性 mock 原型，实机逐一拔掉 3~5 个机制记录真实退化 | 实验脚本执行与断言自验 | `selftest` 全绿 + 破坏性退化实测记录 | 免阻塞（自治演进） |
| **Phase 4** | 经验结晶与系统映射：三拍结构通俗笔记（archify 优先）+ 代码行号精准映射报告 + 知识索引同步 | 结晶落盘与系统代码核验 | 精读笔记与映射报告落盘入库；知识索引登记；原子化提交 | **端到端完整交付** |
| **Post-Mastery** | 用户费曼研讨与自我考核套件：提供 3 道高阶费曼思考题与追问入口 | 用户按需自由选择 ↔ Mentor 导师级答疑与费曼点评 | 用户按需选答或追问，导师提供即时深度反馈 | **按需用户互动** |

---

## 仓库结构

```
SKILL.md                      # 主工作流规约、双代理对抗协议、自治流水线与触发契约
references/lecture-format.md  # 讲授/考评模板（全貌三问/规律/争议/双Agent费曼考评实录/用户自测套件/笔记与映射报告骨架）
references/prototype-lab.md   # 最小原型实验室方法论（确定性 mock / 场景设计 / 破坏性实验纪律）
references/diagram-assets.md  # 图表资产管线规范（archify 优先 / Mermaid 降级）
```

---

<div align="center">
  <sub>Built with 🧠, ❤️, and an absurd amount of coffee by <a href="https://github.com/ThreeFish-AI">ThreeFish-AI</a> · Released under the <a href="./LICENSE">MIT</a>.</sub>
</div>
