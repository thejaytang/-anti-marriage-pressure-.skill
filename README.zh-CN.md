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
