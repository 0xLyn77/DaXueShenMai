# 大雪深埋（DaXueShenMai）

面向中国考研学习场景的 Agent Skills，统一使用 `dxsm-` 前缀。

| Skill | 用途 |
|---|---|
| [dxsm-math](skills/dxsm-math/SKILL.md) | 数学一、二、三题目求解、原理讲解与作答纠错 |
| [dxsm-english](skills/dxsm-english/SKILL.md) | 英语一、二大小作文与英译汉批改、练习评分与复盘 |

由 Agent 直接执行，无需 API Key 或额外依赖。

## 手动安装

```bash
git clone https://github.com/0xLyn77/DaXueShenMai.git
mkdir -p ~/.agents/skills
cp -R DaXueShenMai/skills/dxsm-math ~/.agents/skills/
cp -R DaXueShenMai/skills/dxsm-english ~/.agents/skills/
```

按需复制对应 Skill。目标目录已存在时先备份旧版本，安装后刷新 Skills 或开始新会话。

## 交给 Agent 安装

```text
请从 https://github.com/0xLyn77/DaXueShenMai 安装 dxsm-math 和 dxsm-english，
源目录为 skills/，目标目录为 ~/.agents/skills/。已有版本请先备份再更新。
```

## 使用

- 数学：发送题目文字、公式或截图；检查作答时附上解题过程。
- 英语：说明英语一或英语二，提供作文题目或翻译原文，以及自己的作答。

## 许可证

[MIT License](LICENSE)
