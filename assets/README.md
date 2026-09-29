# 图表资产索引 (Diagram Assets)

本仓库图表资产管线登记表，遵循 [references/diagram-assets.md](../references/diagram-assets.md) 四件套纪律：Mermaid 文本源 SSOT → archify 重绘交互 HTML → 双主题 PNG 导出 → 文档消费与登记。

| Slug | 类型 | Mermaid 源 | 交互 HTML | 暗色 PNG | Spec SHA-256 | Artifact SHA-256 | 登记日期 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| dual-agent-adversarial-protocol | workflow | [源](mermaid/dual-agent-adversarial-protocol.mmd) | [HTML](architecture/dual-agent-adversarial-protocol.html) | [PNG](architecture/dual-agent-adversarial-protocol-dark.png) | `0bc8eb282f63bfb2976c11d3063e407bc2ccb774fa32d60dcb0790dafc49f3b8` | `6469ab51c8226af0b01f197d34f0ef2ae0bad94f8481b650674f169792a1d90f` | 2026-09-29 |
| six-phase-autonomous-pipeline | workflow | [源](mermaid/six-phase-autonomous-pipeline.mmd) | [HTML](architecture/six-phase-autonomous-pipeline.html) | [PNG](architecture/six-phase-autonomous-pipeline-dark.png) | `077e0e487d006ad2d0b84e2db370d7a7c0cff0220aff76eb02eade2dace87dce` | `fded4a603c022357dab03b2be2b12b2231d31f83db935099163043ba726f1c8a` | 2026-09-29 |
| rsi-self-improvement-hook | workflow | [源](mermaid/rsi-self-improvement-hook.mmd) | [HTML](architecture/rsi-self-improvement-hook.html) | [PNG](architecture/rsi-self-improvement-hook-dark.png) | `ff5e0da4a145bb68da1c6bc1651612c113935c86ef253aa5a0ec328413b6509f` | `fbf732a2a5a93f23d1c91951e32a3769572baa8459ab58a0f38da318e0a7380b` | 2026-09-25 |

> Spec SHA-256 对应 `architecture/<slug>.workflow.json`（archify 图谱 spec）；Artifact SHA-256 对应 `architecture/<slug>.html`（交互版交付物），均可执行 `shasum -a 256 <文件>` 复核。
