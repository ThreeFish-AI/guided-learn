# 图表资产索引 (Diagram Assets)

本仓库图表资产管线登记表，遵循 [references/diagram-assets.md](../references/diagram-assets.md) 四件套纪律：Mermaid 文本源 SSOT → archify 重绘交互 HTML → 双主题 PNG 导出 → 文档消费与登记。

| Slug | 类型 | Mermaid 源 | 交互 HTML | 暗色 PNG | Spec SHA-256 | Artifact SHA-256 | 登记日期 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| dual-agent-adversarial-protocol | workflow | [源](mermaid/dual-agent-adversarial-protocol.mmd) | [HTML](architecture/dual-agent-adversarial-protocol.html) | [PNG](architecture/dual-agent-adversarial-protocol-dark.png) | `13abce3f77530e520f2b14221d0e62689186c0e4da5c1136b7674df540679dad` | `2143c9f940a14b0f44c86416ff044f6893e7fb2be694480110329af4ac00e681` | 2026-09-22 |
| five-phase-autonomous-pipeline | workflow | [源](mermaid/five-phase-autonomous-pipeline.mmd) | [HTML](architecture/five-phase-autonomous-pipeline.html) | [PNG](architecture/five-phase-autonomous-pipeline-dark.png) | `9255793dc2246c224cc3912b0b321caafdfa7eb5698f11b689fafc1acf6814a9` | `6c02ca56f498eb673e818bf8d5d00f6f5262e26d2826f97c99fd41e9b340e15b` | 2026-09-22 |
| rsi-self-improvement-hook | workflow | [源](mermaid/rsi-self-improvement-hook.mmd) | [HTML](architecture/rsi-self-improvement-hook.html) | [PNG](architecture/rsi-self-improvement-hook-dark.png) | `a7fcab9022524ebeef5d7f2e5b11d9ba0f00490e1125635508337b41006f5ca8` | `c957dd598a677307ac0a71bb8953d42175bec5a4d05323e461e7daa9d8ecee9c` | 2026-09-23 |

> Spec SHA-256 对应 `architecture/<slug>.workflow.json`（archify 图谱 spec）；Artifact SHA-256 对应 `architecture/<slug>.html`（交互版交付物），均可执行 `shasum -a 256 <文件>` 复核。
