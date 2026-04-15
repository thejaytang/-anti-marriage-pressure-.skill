# anti-marriage-pressure-skill

[![简体中文](https://img.shields.io/badge/README-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-1f6feb?style=for-the-badge)](README.zh-CN.md)
[![English](https://img.shields.io/badge/README-English-111827?style=for-the-badge)](README.en.md)

一个面向 Codex / Claude Code / 兼容 Agent Skills 规范环境的开源 skill，用来处理催婚、逼相亲、追问生育、关系进度审问这类高频压力场景。

## 这个 skill 做什么

- 默认使用`防御模式`，给出冷静、明确、可直接说出口的边界表达
- 在用户明确要求时切到`进攻模式`，更尖锐地拆对方逻辑和越界感
- 对疑似强迫婚姻、控制、威胁、未成年人压力等高风险场景强制切换到安全优先
- 同时支持中文和英文输出

这个项目不是“纯回怼语录合集”。它更像一个可控的语言工具：先保住边界，再决定要不要加力度。

## 安装

### Codex

```bash
git clone https://github.com/thejaytang/-anti-marriage-pressure-.skill.git anti-marriage-pressure-skill
cp -R anti-marriage-pressure-skill/anti-marriage-pressure ~/.codex/skills/
```

### Claude Code

```bash
git clone https://github.com/thejaytang/-anti-marriage-pressure-.skill.git anti-marriage-pressure-skill
cp -R anti-marriage-pressure-skill/anti-marriage-pressure ~/.claude/skills/
```

如果你之后把仓库改名为 `anti-marriage-pressure-skill`，把上面的 clone URL 替换成新的仓库地址即可。安装目录仍然使用 `anti-marriage-pressure/`。

## 使用示例

### 防御模式

```text
请用 $anti-marriage-pressure，按防御模式帮我回：
“你都这么大了还不结婚，家里人都替你着急。”
```

### 进攻模式

```text
请用 $anti-marriage-pressure，按进攻模式给我更硬一点的版本：
“别人孩子都上小学了，你怎么还没动静？”
```

### 英文场景

```text
Use $anti-marriage-pressure to draft a short English reply to:
"When are you getting married? Your parents must be worried."
```

## 实际对比例子

### 例子 1：饭桌催婚

问题：

> “你都这么大了还不结婚，家里人都替你着急。”

普通模型应对：

> “我理解家人的关心，也知道他们是为我好。我会认真考虑自己的人生安排，希望大家给我一点时间。”

接上 skill 以后，防御模式：

> “我知道你们关心，但这件事我自己决定，今天不聊这个。”

接上 skill 以后，进攻模式：

> “你们着急是你们的情绪，不是我的截止日期。我没打算拿婚姻给别人交差。”

### 例子 2：拿别人做比较

问题：

> “你看谁谁谁孩子都上小学了，你怎么还没动静？”

普通模型应对：

> “每个人的人生节奏都不一样，我相信合适的时间会遇到合适的人。”

接上 skill 以后，防御模式：

> “别人的人生进度不适合拿来当我的标准，这个比较对我没有帮助。”

接上 skill 以后，进攻模式：

> “别人结婚是别人交的人生答卷，不是给我抄的标准答案。一直拿别人压我，不叫建议，叫越界。”

### 例子 3：结婚后追问生育

问题：

> “都结婚了，什么时候要孩子？再晚就来不及了。”

普通模型应对：

> “生孩子是很重要的决定，我们会根据自己的情况来考虑，谢谢关心。”

接上 skill 以后，防御模式：

> “生育计划属于私人决定，我不回答这个问题，请不要继续追问。”

接上 skill 以后，进攻模式：

> “把别人的生育安排当公共议题，本身就很越界。你担心时间线，不代表你有提问权限。”

## 输出结构

默认输出包含四部分：

- 一句主回复
- 2 到 3 条递进替代说法
- 一句收口或转移话题
- 必要时的一句退出/求助建议

如果你只想要一句，直接说“只给我一句”即可。

## 安全边界

以下情况不会进入进攻模式：

- 强迫结婚或被逼订婚
- 被威胁、被控制出行、证件、手机、资金
- 未成年人相关婚姻压力
- 明显存在人身风险或家庭暴力风险

遇到这些情况，skill 会优先给出安全建议，而不是更狠的话术。

## 仓库结构

```text
.
├── README.md
├── README.zh-CN.md
├── README.en.md
├── LICENSE
└── anti-marriage-pressure/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
        ├── principles.md
        ├── scenarios.md
        └── style-notes.md
```

## 资料方法

这个项目用了两层资料：

- 权威层：用于边界、**assertive communication**、**de-escalation** 和强迫婚姻风险覆盖
- 社交平台层：只提炼语气、句型、升级节奏和高频场景，不原样搬运帖子内容

## License 与免责声明

本项目使用 `MIT`。

这个 skill 提供的是沟通辅助，不是法律、心理危机或人身安全服务。只要问题已经超出普通催婚对话，优先考虑现实中的安全支持渠道。
