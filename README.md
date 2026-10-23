# Nosce · 省吾

*Know yourself, over time.*

自省是手段，自我认识才是目的。Nosce 通过轻量提问、自适应追问和可修正的长期观察，帮助你逐渐认识自己；不把每一次对话都变成自我改进任务。

## 使用

### 把链接发给 AI，安装或直接使用

复制下面这段话，发送给 ChatGPT App 或支持 Skill 的 AI 助手：

```text
请帮我安装并使用 Nosce（省吾）：https://github.com/hericyoung/nosce-skill

请先读取仓库 README，按其中的「给 AI 的安装说明」完成安装；如果当前环境无法安装，就读取技能文件并在本次对话中使用，如实说明状态。
完成后直接开始今天的日省，我只有两分钟。
```

AI 能访问仓库时，无需手动下载和逐个上传文件。支持安装时由 AI 完成安装；仅支持网页读取时，在当前对话中加载使用。[官方 Skill 说明](https://learn.chatgpt.com/docs/build-skills)

如果 AI 无法访问 GitHub，可以补发 [SKILL.md 原文链接](https://raw.githubusercontent.com/hericyoung/nosce-skill/main/SKILL.md)。若原文也无法访问，则需要改用可联网的环境，或上传仓库中的文件。

### 给 AI 的安装说明

先确认当前对话是否提供 Skill 安装能力：支持时使用内置安装功能安装 Nosce，并检查技能文件是否完整；只支持网页读取时，加载下列文件后直接开始聊天。分别如实告知“已安装”或“已在当前对话加载”。

读取以下文件，并将其用作当前对话的指引。网页页面无法取到完整内容时，使用对应的原文地址：

| 文件 | 原文地址 |
| --- | --- |
| 入口 | https://raw.githubusercontent.com/hericyoung/nosce-skill/main/SKILL.md |
| 选题 | https://raw.githubusercontent.com/hericyoung/nosce-skill/main/references/questions.md |
| 认知档案 | https://raw.githubusercontent.com/hericyoung/nosce-skill/main/references/memory.md |
| 定时提问 | https://raw.githubusercontent.com/hericyoung/nosce-skill/main/references/scheduling.md |

先完整读取入口，其他文件在对应功能需要时读取。远程读取时，相对引用按以上地址解析。仅加载使用时，说明新对话可能需要重新加载；不要将网页阅读描述为永久安装。读取失败时明确指出缺少哪个文件。

无论使用哪种方式，安装或加载本身都不创建提醒或个人档案。用户另行提出记录、回访或定时请求时，再按技能指引处理。

### 日常使用

安装或加载后，直接自然表达即可：

- “开始今天的日省，只聊两分钟。”
- “帮我回顾本周，我对什么事情的看法发生了变化？”
- “我想重新看看之前关于自己的判断。”
- “今天不记录，只聊聊。”
- “今天不想回答。”

在 ChatGPT 的技能选择器中可用时，也可以输入 `@` 选择 Nosce。

如需定时提问，可以说“每天晚上 21:00 提醒我省吾”。只有宿主实际创建成功的计划任务才会定时执行。[官方计划任务说明](https://learn.chatgpt.com/docs/automations)

长期认知观察以实际可读的历史为依据。可使用专属 ChatGPT 项目保留技能文件和经过你检查的摘要；项目文件与指令可供其中的对话共享。[官方项目说明](https://learn.chatgpt.com/docs/projects?surface=app)

## 项目结构

```text
Nosce/
├── SKILL.md                  对话入口与核心原则
├── README.md                 项目说明与使用方式
├── agents/openai.yaml        Skill 展示信息
├── references/
│   ├── questions.md          六个探索维度与选题策略
│   ├── memory.md             认知档案、证据与修正规则
│   └── scheduling.md         定时提问接入与能力边界
└── evals/
    └── scenarios.md          行为验收场景与试跑记录
```

这是一个以中文对话为默认体验、无运行时依赖的 Skill 项目。日省、周省、月省都是对话模式，时长仅作参考。持久化需要可读写的存储，定时发送需要宿主提供调度能力。

## 初版范围

包含日省、周省、月省、认知回访、可选的小实验、档案格式和调度接入协议。暂不提供独立应用、数据库服务或后台调度程序。

验证方式与行为场景见 [evals/scenarios.md](evals/scenarios.md)。`evals/` 用于开发和维护时检查提问节奏、历史不足、跳过、提醒和认知修正等行为，不参与 Skill 的日常运行，也不保存用户的个人反思记录。修改 Skill 后可用其中的场景做回归检查；发布时可选择不包含该目录。
