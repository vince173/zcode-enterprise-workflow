# Enterprise Workflow for ZCode

基于 ZCode Skill 体系的企业级角色分工开发流程 —— 将模糊需求通过 10 个专业 AI Agent 逐步转化为可交付的软件。

## 流水线

```
Strategist → PM → UX → SE → DBA → Security → DEV → CodeOwner → TEST → DevOps
```

每个角色有标准化的输入契约、产出模板、自检清单。

## 安装

将 `skills/` 目录下的所有角色复制到你的 ZCode 技能目录：

```bash
# 用户级安装（所有项目可用）
cp -r skills/* ~/.agents/skills/

# 项目级安装（仅当前项目）
cp -r skills/* .agents/skills/
```

## 使用

```
/flow start {功能名称}    # 初始化工作流
/flow next                # 推进到下一阶段
/flow status              # 查看当前流程状态
/flow retry {角色}         # 重新执行指定角色
/flow skip {角色}          # 跳过可选角色
/flow resume              # 恢复中断的流程
```

也可以单独调用某个角色（不走流程）：

```
/pm        # 只写 PRD
/se        # 只做架构设计
/dev       # 只写代码
```

## 角色列表

| 角色 | 命令 | 职责 |
|------|------|------|
| Strategist | — | 产品方向、竞品研究、Vision Canvas |
| PM | `/pm` | 需求分析、PRD、验收标准 |
| UX | `/ux` | 用户流程、交互设计 |
| SE | `/se` | 架构设计、ADR、API 契约 |
| DBA | `/dba` | Schema 评审、索引策略 |
| Security | `/security` | 威胁建模、OWASP 检查 |
| DEV | `/dev` | 代码实现（内置 TDD + 自检） |
| CodeOwner | `/codeowner` | 代码审查、合并审批、版本标签 |
| TEST | `/test` | 测试策略、验收测试 |
| DevOps | `/devops` | 部署方案、灰度策略、监控告警 |

## 设计文档

详见 [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)

## 许可

MIT
