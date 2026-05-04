
## 🙋‍♀️ About Us
  WpLabs is the studio behind WarpParse, focusing on building industry-leading ETL engines. We are committed to addressing enterprises' growing needs for log parsing and governance, helping clients extract and integrate data value more easily.
  
  WpLabs 是 WarpParse 背后的工作室，我们专注于打造业界领先的 ETL 引擎，致力于解决企业日益增长的日志解析与治理需求，帮助客户更轻松地实现数据价值的提取与整合。

## WarpParse

### install
```bash
## 稳定版
curl -sSf https://get.warpparse.ai/inst-x.sh | bash -s -- wparse
## 验证版
curl -sSf https://get.warpparse.ai/inst-x.sh | bash -s -- wparse beta
## 开发版
curl -sSf https://get.warpparse.ai/inst-x.sh | bash -s -- wparse alpha
## install wp-skills
curl -sSf https://get.warpparse.ai/inst-x.sh | bash -s -- wp-skills

## install monitor-docker
curl -sSf https://get.warpparse.ai/inst-x.sh | bash -s -- monitor-docker alpha
```
Warpparse is faster than vector.

### Mac Mini4 FileToBlackHole   [Performance Report](https://example.warpparse.ai/benchmark/report/report_mac.html)

![wp-pk3](https://github.com/user-attachments/assets/5fa94354-a023-4eef-bf5e-f0a47d783778)


## 🧩 Key Crates

| Component | Type | Description |
|---|---|---|
| **warp-parse** | Binary | Processing program and engineering toolset. The main binary that drives log ingestion, pipeline orchestration, and operational commands (check, run, bench, etc.). |
| **wp-motor** | Crate | Core engine library. Provides the WPL runtime, rule compiler, pattern matching, and stream processing primitives consumed by `warp-parse`. |
| **wp-connectors** | Crate | Stable, production-grade connector library for integrating with external systems (storage, messaging, observability). |
| **wp-editor** | Binary | Browser-based rule editor with syntax highlighting, live preview, and assisted WPL authoring. |
| **wp-monitor** | Binary | Engine processing monitor — tracks throughput, latency, error rates, and resource usage of running wparse instances. |
| **wp-skills** | Skills | Security hardening and rule-writing skills package. Encodes best practices for writing safe, performant WPL rules. |
| **warp-parse-labs** | Binary | Experimental engine binary. Incubates new WPL features, parser optimizations, and prototype pipelines before graduation to `warp-parse`. |
| **wp-connectors-labs** | Crate | Experimental connector library. Sandbox for new connector ideas that may later stabilize into `wp-connectors`. |

### Crate Relationships

```
              wp-skills [skills]
                 │
                 ▼
           warp-parse [bin] ──┬──► wp-connectors [lib]
                 │            └──► wp-motor [lib]
                 │                       ▲
                 │                       │
                 │                  wp-editor [bin]
                 │
          warp-parse-labs [bin] ──► wp-connectors-labs [lib]

          wp-monitor [bin]
```

- **wp-motor** is the standalone engine library — WPL runtime, compiler, and pattern matching. It has no external dependencies on other crates in this set.
- **warp-parse** is the binary that integrates **wp-motor** (for parsing) and **wp-connectors** (for delivery) into a complete processing toolset. Rules are authored via **wp-skills**.
- **warp-parse-labs** depends on **warp-parse** and layers experimental engine features on top; its connector surface maps to **wp-connectors-labs**.
- **wp-editor** depends on **wp-motor** for WPL syntax validation and live preview. **wp-monitor** observes engine health at runtime.

> `[bin]` = executable binary &nbsp;|&nbsp; `[lib]` = library crate &nbsp;|&nbsp; `[skills]` = skills package


##  🌈 Contribution Guidelines

* We welcome community members to participate and grow together through the following ways:
* Connector Development: Share your connectors to help others with similar needs
* Documentation Improvement: Assist in improving or translating documentation
* Example Projects: Submit practical case studies using WarpParse to showcase best practices
* Engine Extensions: Participate in extending and optimizing WPL & OML language features

## 👩‍💻 Useful Resources
* 📘 [User Guide](https://docs.warpparse.ai/)  [Online Editor](https://editor.warpparse.ai)
* 📦 [WarpPase release ](https://github.com/wp-labs/warp-parse/releases)
* 🚀 [Examples](https://example.warpparse.ai/)
* 💬 Community Discussions: Exchange ideas, ask questions, or share experiences here
