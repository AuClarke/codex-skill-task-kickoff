# Codex 任务启动 Skill 🚦

> 复杂任务开始前，先把目标、资料源、输出形式、验收方式和边界讲清楚，让 Codex 不跑偏。

`codex-task-kickoff` 是一个轻量但非常实用的 Codex Skill。它不负责“多问问题”，而是帮助 Codex 在执行复杂任务前建立一个清晰框架：**我要做什么、依据什么做、交付什么、怎么判断完成、哪些不能碰**。

## 解决什么问题？

很多 AI 任务失败不是因为模型不会，而是因为一开始没有对齐：

- 用户想要 PPT，Codex 只给了文字；
- 用户要真实网页资料，Codex 凭记忆回答；
- 用户要改一个文件，Codex 顺手重构一大片；
- 用户要最终文件，Codex 没检查能不能打开；
- 任务涉及权限/全局配置，但没有提前说明风险。

这个 Skill 用一个 5 项启动框架减少这些问题。

## 适合谁？

- 经常让 Codex 做多步骤任务的人；
- 需要文件、PPT、网页调研、本地执行的人；
- 希望 Codex 自主推进，但又不乱改的人；
- 想让每次交付都有验收标准的人。

## 快速安装

```bash
git clone https://github.com/AuClarke/codex-skill-task-kickoff.git
cd codex-skill-task-kickoff
mkdir -p ~/.codex/skills
ln -s "$PWD/codex-task-kickoff" ~/.codex/skills/codex-task-kickoff
```

如果已经在仓库目录内：

```bash
mkdir -p ~/.codex/skills
ln -s "$PWD/codex-task-kickoff" ~/.codex/skills/codex-task-kickoff
```

## 卸载

```bash
rm ~/.codex/skills/codex-task-kickoff
```

## 如何触发

```text
Use $codex-task-kickoff 帮我先对齐这个任务，再开始做。
```

也适合自然触发：

```text
帮我做一个小红书调研 PPT，资料要联网，最后给我文件。
```

遇到这种多步骤任务时，Codex 应先补齐：

```text
目标：
资料源：
输出形式：
验收标准：
边界：
```

## 什么时候应该停下来问？

应该问：

- 要写入全局配置；
- 要安装依赖或插件；
- 要删除、重置、覆盖文件；
- 要改安全权限、Keychain、TCC、账号、浏览器授权；
- 用户目标明显不完整，且错误假设会造成浪费。

不应该每次都问：

- 简单翻译；
- 一行命令；
- 用户已经说“继续/执行/直接做”；
- 低风险、可逆、范围明确的小任务。

## 输出应该长什么样？

完成时建议说明：

- 做了什么；
- 文件在哪里；
- 检查了什么；
- 还有什么风险或需要用户确认。

## 使用示例

用户说：

```text
帮我做一个旅行攻略 PPT，要有小红书链接、图片和每天安排。
```

Codex 应该先压缩成启动框架：

```text
目标：制作可交互检查的旅行攻略 PPT
资料源：用户原始行程、小红书、住宿/交通信息
输出形式：.pptx + 检查记录
验收标准：能打开预览；链接可点；每天行程不漏项
边界：不改全局配置；登录/验证码由用户处理
```

## 目录结构

```text
codex-task-kickoff/
  SKILL.md
  agents/openai.yaml
  references/template.md
```

## 对别人有什么帮助？

这个 Skill 的价值在于“少返工”。它让 Codex 在开始前自己建立任务边界，尤其适合团队把 AI 当执行助理时使用。

## License

MIT
