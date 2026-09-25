# 图表资产索引 (Diagram Assets)

本仓库图表资产管线登记表，遵循 [references/diagram-assets.md](../references/diagram-assets.md) 四件套纪律：Mermaid 文本源 SSOT → archify 重绘交互 HTML → 双主题 PNG 导出 → 文档消费与登记。

| Slug | 类型 | Mermaid 源 | 交互 HTML | 暗色 PNG | Spec SHA-256 | Artifact SHA-256 | 登记日期 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| dual-agent-adversarial-protocol | workflow | [源](mermaid/dual-agent-adversarial-protocol.mmd) | [HTML](architecture/dual-agent-adversarial-protocol.html) | [PNG](architecture/dual-agent-adversarial-protocol-dark.png) | `13abce3f77530e520f2b14221d0e62689186c0e4da5c1136b7674df540679dad` | `2143c9f940a14b0f44c86416ff044f6893e7fb2be694480110329af4ac00e681` | 2026-09-22 |
| six-phase-autonomous-pipeline | workflow | [源](mermaid/six-phase-autonomous-pipeline.mmd) | [HTML](architecture/six-phase-autonomous-pipeline.html) | [PNG](architecture/six-phase-autonomous-pipeline-dark.png) | `3f577e845cd9c4bfc9cec10bd01b08c08e0e343751cff90befca35f54f33b1b6` | `d29f5870eae0c54729bf995180ce379e2ab6d0cb0616c535241cd45f22959ea8` | 2026-09-25 |
| rsi-self-improvement-hook | workflow | [源](mermaid/rsi-self-improvement-hook.mmd) | [HTML](architecture/rsi-self-improvement-hook.html) | [PNG](architecture/rsi-self-improvement-hook-dark.png) | `ff5e0da4a145bb68da1c6bc1651612c113935c86ef253aa5a0ec328413b6509f` | `fbf732a2a5a93f23d1c91951e32a3769572baa8459ab58a0f38da318e0a7380b` | 2026-09-25 |

> Spec SHA-256 对应 `architecture/<slug>.workflow.json`（archify 图谱 spec）；Artifact SHA-256 对应 `architecture/<slug>.html`（交互版交付物），均可执行 `shasum -a 256 <文件>` 复核。
