# VibeProject-1

使用 [Matt Pocock's Skills](https://github.com/mattpocock/skills) 协作开发的项目。当前处于需求定义阶段。

## 开发准备

- 使用已安装的 `mattpocock-skills` 插件；本次配置基于 1.2.3。
- 安装 Git 和 GitHub CLI（`gh`），登录有仓库访问权限的 GitHub 账号。
- 在本仓库目录开始工作，先读取 [AGENTS.md](AGENTS.md)。
- 用 `gh auth status` 和 `gh issue list --repo playchaodd68/VibeProject-1 --limit 5` 检查连接。

产品目标、技术栈、运行命令和测试工具将在需求明确后补充。

## 开发流程

以下为插件中的技能名；在 Codex 中选择对应技能，或明确要求使用它。

| 阶段 | 技能 | 产物 |
| --- | --- | --- |
| 明确需求 | `grill-with-docs` | 需求边界、领域术语和已确定的决策 |
| 固化规格 | `to-spec` | GitHub 上的规格 Issue |
| 拆分任务 | `to-tickets` | 可独立验证的任务及依赖关系 |
| 分流任务 | `triage` | 明确的准备状态和负责人类型 |
| 实现功能 | `implement` | 经 TDD 验证和审查的改动 |
| 排查问题 | `diagnosing-bugs` | 可复现问题、修复及回归验证 |

复杂项目可使用 `wayfinder`；不确定下一步时使用 `ask-matt`。日常改动使用独立分支，完成验证后提交 Pull Request。

## 项目配置

- [任务跟踪](docs/agents/issue-tracker.md)：GitHub Issues，以及规格、依赖和子任务的操作约定。
- [分流标签](docs/agents/triage-labels.md)：五个默认标签及含义。
- [领域文档](docs/agents/domain.md)：单一上下文布局及阅读规则。

这些配置可直接编辑。`CONTEXT.md` 和 `docs/adr/` 由后续需求讨论在形成实际术语和决策时创建。
