# guided-learn — 导师式精读与领域掌控（Claude Code Skill）

以**严格且经验老到的老师**身份，带用户完整学习并掌控论文、文档、网页、视频等一手材料中的领域技能：
全貌解剖（先梳理后总结）→ 领域底层规律与争议提炼 → 类比化讲授 → 最小原型实践与破坏性实验 → 经验沉淀入库。

## 安装

```bash
# 方式一：克隆即装（外部用户）
git clone https://github.com/ThreeFish-AI/guided-learn.git ~/.claude/skills/guided-learn

# 方式二：symlink（本机维护模式——改仓库即改 Skill）
git clone https://github.com/ThreeFish-AI/guided-learn.git ~/Documents/projects/aurelius/guided-learn
ln -s ~/Documents/projects/aurelius/guided-learn ~/.claude/skills/guided-learn
```

## 使用

显式调用：`/guided-learn <材料 URL 或路径>`；或自然语言触发——
「带我精读这篇论文」「先梳理全貌不要急着总结」「提炼这个领域的核心规律与争议」「以老师身份教我掌握 X」「帮我搞懂这份资料/视频并实践」。

## 工作流（五阶段）

| 阶段 | 内容 |
| --- | --- |
| Phase 0 | 摄取与前置体检（前置自测三题，不通过先补课） |
| Phase 1 | 全貌讲授——Tier 分层 + 因果链脉络 + 批判性边界（先梳理，后总结） |
| Phase 2 | 领域扩展——N≈5 条底层规律（正交分解 + IEEE 锚点 + 实证演示）+ 2–3 个争议辨析 |
| Phase 3 | 学习路径——验收五题 + 费曼测试（复述差异 / 手画图 / 预测题） |
| Phase 4 | 最小原型 + **破坏性实验**：每个机制亲手拆一次、实测退化 |
| Phase 5 | 沉淀入库——三拍结构笔记 + 机制映射报告 + memory |

## 结构

```
SKILL.md                      # 主工作流与教学铁律
references/lecture-format.md  # 讲授模板（全貌/规律/争议/验收题/笔记与映射报告文档骨架）
references/prototype-lab.md   # 原型实验室方法论（确定性 mock / 场景设计 / 破坏性实验纪律）
```

## 出处

提炼自 arXiv:2609.09153《Procedural Graphs》导师式精读实战（2026-09）：讲授范式、类比体系（菜谱批注 / 导航三连 / 月度复盘）、pg-lab 最小原型与三个破坏性实验、PG↔negentropy 机制映射报告均为该次实战的原生产物。

## License

[MIT](./LICENSE)
