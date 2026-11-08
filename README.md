# 简历优化器 Agent Skill（阶段 1）

面向国内互联网求职者的可安装 Agent Skill：解析简历 → 确认岗位与市场 → 通用维度 + 分岗位 rubric 打分 → 可执行改写与补料追问。

## 安装（示例）

将本目录复制到 Agent 的 skills 路径，至少保留：

- `SKILL.md`
- `roles/`
- `references/`
- `templates/`

Claude Code 示例：`~/.claude/skills/resume-optimizer/`  
Codex 示例：`~/.codex/skills/resume-optimizer/`  
Cursor 示例：项目或用户 skills 目录下同名文件夹。

## 扩展岗位

见 `SKILL.md`「岗位扩展机制」：新增 `roles/<slug>.md` 并更新路由表。

## 阶段 2

前端网站复用同一套 `roles/` 与输出契约（`templates/output-template.md`），仅更换输入输出壳。


## 可核验标准

- `references/common-standards.md` — 带 ID 的评判手册  
- `references/bibliography.md` — 完整出处 URL  
- `references/verification-protocol.md` — 复现打分流程  
审计输出必须引用标准 ID。


## 对外报告结构（1.3.0）

1. 初步结论（含亮点与不足）
2. 各维度分数，以及对应的简历证据
3. 按优先级列出的修改建议（问题、原文、为什么要改、建议改成）
4. 总结

报告写给求职者看：浅显易懂，言简意赅，每条建议都给出可直接采用的改写句。


## 系统读取（ATS）怎么讲

ATS 是公司用来自动收取和检索简历的招聘系统。对外写成「系统会不会正确读出你的姓名、公司、日期和技能」，不要只丢缩写。国内投递且没有明显读取问题时，不把它当作主要不足；外企或官网网申时再重点说明。
