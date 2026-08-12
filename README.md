# DesRedTeam — 开源项目来源说明 (README)

> 本文档说明 DesRedTeam 应用与开源项目 CyberStrike、GSL5 的关系。
> 本文件为**包外补充文档**, 不包含在 `desredteam-src-min-*.tar.gz` 源码包内。

---

## 项目定位

**DesRedTeam** 是一个 AI 原生的红队渗透作战平台 — 规划、执行、人工监督、证据与复盘汇聚于同一个可审计工作空间。基于 Go 构建,融合 Eino 多代理引擎、MCP 原生工具、RAG 知识库、可视化工作流与攻击链建模能力,面向已获得明确授权的安全任务。

DesRedTeam 并非从零起步的封闭项目,而是**建立在两个开源项目之上**的集成与再开发成果:

---

## 1. CyberStrike — AI 原生安全平台(项目基石)

| 项       | 内容                                         |
| -------- | -------------------------------------------- |
| 开源项目 | CyberStrike                                  |
| GitHub   | https://github.com/CyberStrikeus/cyberstrike |
| 角色     | DesRedTeam 的**前身与基石**                  |

**CyberStrike 提供的核心能力(DesRedTeam 继承并演进)**:

- Go + Gin 后端架构
- Eino 多代理引擎(任务编排/流式执行)
- MCP 联邦(多 MCP 服务器统一接入)
- 四层记忆架构
- AI 围栏(HITL)审批 — "AI 自主渗透 + 人工审批兜底"的工程实践

**DesRedTeam 在其基础上完成**:

- 品牌重塑
- Windows 部署加固
- 信息收集 / 股权穿透 / 供应链模块落地
- GSL5 前端适配
- DesShell C2 深度集成

> 代码中仍保留 CyberStrike 的痕迹(如 `CYBERSTRIKE_HTTPS` 环境变量),即源于此。

---

## 2. GSL5 (Godzilla Super) — WebShell 管理与前端适配

| 项       | 内容                                       |
| -------- | ------------------------------------------ |
| 开源项目 | GSL5 (Godzilla Super)                      |
| GitHub   | https://github.com/Xaaaa-bip/GodzillaSuper |
| 角色     | WebShell 管理服务 + 平台前端适配           |

**GSL5 提供的能力**:

- 45 个 MCP 工具:shell 增删改查 / 命令执行 / 文件管理 / 数据库操作 / 流量伪装 / 进程管理
- 作为 Godzilla(哥斯拉)的增强管理服务

**DesRedTeam 的集成方式**:

- 以 streamable-http 方式将 GSL5 接入外部 MCP
- 平台前端直接适配 — 用户在平台内即可完成哥斯拉 WebShell 的全生命周期管理
- 仓库内 `gsl5/` 目录(jar + license + profile + jre8)来自该项目

---

## 授权与合规

- 本项目使用 **Apache License 2.0** 开源(见 `LICENSE.txt`)
- 详细致谢见项目内 `ACKNOWLEDGEMENTS.md`
- ⚠️ 仅可对自有系统或已获得明确授权的目标使用
- ⚠️ 在共享/生产环境启用高风险工具、WebShell 或 C2 前,请先阅读安全模型与加固指南

---

*生成时间: 2026-08-13 | 用途: 包外补充说明, 不随源码包分发*
