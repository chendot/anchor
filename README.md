# Anchor 寻锚

一套帮助找到人生方向的 AI Prompt 系统。核心不是"制定计划"，而是先经过多个对抗性视角的压力测试，再落地成可执行结构。

## 这不是什么

不是软件，不需要安装。不是单一AI给建议的教练式工具——那种建议往往只反映一种视角，容易被"说得好听"蒙蔽。

## 核心逻辑

```
现状输入 → 阶段诊断 → 多角色辩论 → 输出结构 → 定期复盘
```

多角色辩论是整个系统的差异点：不是一个AI给你温和建议，而是至少两个立场对立的角色，针对同一个目标互相拆台，逼出目标里的自我欺骗和风险盲区。你看辩论过程，自己判断谁说得对。

## 怎么用（给 Cowork / GPT Work 这类agent工具）

1. 把整个 `anchor/` 文件夹丢给agent
2. 复制 `templates/life-state.md` 到 `inputs/YYYY-MM-DD-life-state.md`，在副本中填写现状
3. 让 agent 读取这份 `inputs/` 中的输入，依次执行 `prompts/00` 到 `prompts/03`
4. 将每一步输出保存到 `outputs/`，例如 `YYYY-MM-DD-diagnosis.md`、`YYYY-MM-DD-council.md`、`YYYY-MM-DD-structure.md`，方便以后回看变化

`inputs/` 与 `outputs/` 都包含个人信息，已被 Git 忽略；只提交模板、提示词和角色定义。

## 文件说明

- `templates/life-state.md` — 空白现状输入模板
- `inputs/` — 你填写后的个人输入（不会上传）
- `prompts/00-diagnosis.md` — 判断你现在处于 迷茫/愿景/心流/停滞 哪个阶段
- `prompts/01-council.md` — 核心环节，多角色辩论你的目标
- `prompts/02-structure.md` — 把讨论结果整理成主线任务/支线任务/行动清单
- `prompts/03-review.md` — 隔一段时间回来复盘用
- `roles/*.md` — 参与辩论的角色定义，可以增删改
- `outputs/` — 各阶段的个人输出与复盘记录（不会上传）

## 可以自己调整的地方

角色不是固定的。`roles/` 下每加一个新角色，辩论就多一个视角。想加"十年后的自己""最刻薄的批评者""现实主义会计师"都可以，照着现有角色的格式写一个新文件，在 `01-council.md` 里引用它即可。
