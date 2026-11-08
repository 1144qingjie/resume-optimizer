# Resume Optimizer｜简历诊断与优化 Skill

面向国内互联网求职者的 Agent Skill。把简历和目标岗位交给 AI，得到有原文证据的评分、按优先级排列的问题，以及可直接采用的改写句。支持结合职位描述（JD）分析岗位匹配缺口，也兼顾外企与海外投递的格式差异。

**当前版本：1.4.0。** 这是一套供 AI Agent 加载的工作流、岗位评判标准和报告模板，不是独立网站或简历编辑软件。

## 能帮你做什么

| 能力 | 你会得到什么 |
|---|---|
| 简历诊断 | 找出定位不清、职责堆砌、亮点埋没、重复内容、时间线与指标口径等问题 |
| 七维评分 | 扫视可读性、成果化程度、量化与可核实性、系统读取、岗位匹配度、诚实与一致性、市场适配；每项 0–5 分并附简历证据 |
| 分岗位分析 | 根据岗位检查应有的能力证据，例如 AI 产品的质量、成本、评测，后端的规模与可靠性 |
| JD 匹配 | 有 JD 时分析关键要求的覆盖情况与缺口；无 JD 时评估表达质量和岗位通用要求 |
| 逐条改写 | 对重点问题给出“原文 → 为什么要改 → 建议改成”，优先呈现动作、产物与结果 |
| 补料追问 | 对缺失的指标、个人贡献、统计口径等提出具体问题，用 `[待补]` 或 `[CONFIRM]` 标记未知事实 |
| 篇幅与投递适配 | 根据资历和目标市场建议去重、重排与压缩；明确要求时可基于真实材料输出完整改写稿 |

“系统读取”指招聘系统能否正确抽取姓名、公司、日期和技能（这类系统英文叫 ATS）。国内投递时不机械地将其作为首要问题，外企或官网网申时再重点检查。相关检查不等于实际接入招聘公司的 ATS 测试。

## 支持哪些岗位

内置 7 套岗位评判标准：

- 产品经理
- AI 产品经理／大模型产品
- 前端工程师
- 后端工程师
- 架构师
- 测试／质量工程师
- FDE（Forward Deployed Engineer，前线部署工程师）

AI 应用开发、AI 平台开发、数据平台等相近岗位，会使用最接近的标准并说明适用范围。评估会结合目标职级和市场；未覆盖的岗位不冒充有专用标准。

## 安装方式

前提：安装并登录一个支持 Agent Skills 的 AI 工具。此仓库本身无需运行服务、安装 Python 依赖或配置 API Key；模型与文件读取能力由所使用的工具提供。

### 方式一：让支持安装 Skill 的 Agent 帮你安装

向 Agent 发送：

```text
请将 https://github.com/1144qingjie/resume-optimizer 安装为 resume-optimizer skill。
SKILL.md 位于仓库根目录，请同时保留 roles、references 和 templates 目录。
```

是否能自动安装取决于工具的安装能力和权限。不能自动安装时，使用下面的命令或手动复制。

### 方式二：Git 安装（macOS／Linux）

选择你使用的工具，只运行对应的一组命令。目标目录已存在时，先备份已有版本，不要直接覆盖。

**Codex：**

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/1144qingjie/resume-optimizer.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/resume-optimizer"
```

**Claude Code：**

```bash
mkdir -p "$HOME/.claude/skills"
git clone https://github.com/1144qingjie/resume-optimizer.git \
  "$HOME/.claude/skills/resume-optimizer"
```

其他支持 Skills 的工具，请将仓库放入该工具文档指定的 skills 目录，文件夹命名为 `resume-optimizer`。不同工具与版本的发现路径可能不同。

### 方式三：下载 ZIP，手动安装

1. 点击本仓库 **Code → Download ZIP** 并解压。
2. 将解压后的文件夹重命名为 `resume-optimizer`。
3. 将整个文件夹放入工具的 skills 目录。Codex 默认是 `~/.codex/skills/`，Claude Code 是 `~/.claude/skills/`。
4. 确认 `SKILL.md` 直接位于 `skills/resume-optimizer/` 下，避免多套一层目录。

安装后的关键结构应为：

```text
skills/
└── resume-optimizer/
    ├── SKILL.md
    ├── roles/
    ├── references/
    └── templates/
```

安装后，在下一轮对话中明确指定使用 `resume-optimizer`；如工具未发现它，重新打开会话或按工具要求刷新 Skills。

### 更新已通过 Git 安装的版本

在安装目录执行 `git pull --ff-only`。例如 Codex 默认路径：

```bash
git -C "${CODEX_HOME:-$HOME/.codex}/skills/resume-optimizer" pull --ff-only
```

若有本地修改，先备份并处理差异；ZIP 安装则备份后重新下载替换。

## 如何使用

上传简历，或直接粘贴简历正文。为了得到更贴近投递场景的建议，最好同时提供：**目标岗位、目标职级、目标市场／公司类型，以及 JD（如有）**。

**诊断现有简历：**

```text
请使用 resume-optimizer 分析这份简历。
目标：国内互联网公司的资深 AI 产品经理。
先给出问题诊断、评分和修改优先级，不要直接重写整份简历。
```

**对照具体岗位：**

```text
请使用 resume-optimizer，对照下面的 JD 分析我的简历。
指出关键要求的匹配证据、尚未体现的能力，以及最先需要改的内容。
没有证据的经历和数据不要补写。

JD：
[粘贴职位描述]
```

**补齐事实后改写：**

```text
请根据刚才确认的信息改写这份简历，压缩到 2 页。
保留真实职位、经历和数据，仍然缺失的信息用 [待补] 标记。
```

支持简历文本，以及由宿主工具解析的 PDF、DOCX、Markdown 等材料。Skill 本身不包含 PDF／Word 解析器；若工具无法读取附件，请先粘贴正文。版面判断需要宿主具备 PDF 或图片查看能力。

## 报告长什么样

默认报告分为四部分：

1. **初步结论：** 能否支撑目标定位，主要亮点和不足。
2. **各维度评分：** 每项分数与简历原文证据。
3. **优先修改建议：** P1、P2、P3……，逐条说明问题、原文、影响、可采用的改写和待补事实。
4. **总结：** 保留什么、先改什么，以及还需要确认的信息。

默认提供诊断和重点句子的改写；只有明确要求时才输出完整重写稿。评分衡量的是简历已呈现的证据，不是对本人真实能力的鉴定，也不保证通过筛选或拿到 offer。

## 事实边界与评判依据

- 不虚构公司、职位、学历、工具、指标、用户规模等信息，不擅自抬高职级。
- 缺少证据时先追问或使用占位符；不把团队成果直接写成个人独立成果。
- 没有 JD 时，不声称完成了具体职位的关键词覆盖分析。
- 扣分与改写理由关联可核对的标准 ID；外部指南、行业经验和本 Skill 综合项会区分来源，不冒充招聘方官方标准。
- 简历由你选择的 AI 工具处理，可按需脱敏手机号、邮箱等个人信息。

## 仓库结构与扩展

| 文件／目录 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | 触发条件、完整工作流、事实边界与输出要求 |
| [roles/](roles/) | 7 套分岗位评判标准 |
| [references/common-standards.md](references/common-standards.md) | 通用标准、评分锚点与标准 ID |
| [references/verification-protocol.md](references/verification-protocol.md) | 可观察检查项与打分流程 |
| [references/bibliography.md](references/bibliography.md) | 标准的参考来源 |
| [templates/output-template.md](templates/output-template.md) | 四段式报告模板 |
| [skill_meta.json](skill_meta.json) | 版本信息 |

扩展岗位时，在 `roles/` 新增岗位文件，并同步更新 `SKILL.md` 的岗位路由与相关通用标准。
