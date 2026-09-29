# Jushawn Skills

集中管理收集和编写的 Codex 技能，通过 GitHub 市场统一安装、启用和更新。
整个仓库提供一个 `jushawn-skills` 插件，分类目录只用于组织文件。

当前仅包含初始化框架，`skills/` 为空，没有可调用的技能，也尚未验证实际安装加载。

## 目录结构

```text
.codex-plugin/plugin.json          插件声明
.agents/plugins/marketplace.json   仓库市场入口
skills/                           技能根目录（未预建分类）
README.md                         使用说明
```

市场配置中的 `source.path` 为 `./`，相对于市场所在的仓库根目录解析，指向本仓库插件。
它不是相对于 `.agents/plugins/` 解析，也不需要额外创建 `plugins/jushawn-skills/`。

## 添加技能

将完整技能文件夹复制到 `skills/`。可以直接放入，也可以自行创建分类：

```text
skills/<技能名>/SKILL.md
skills/<分类>/<技能名>/SKILL.md
```

以上是路径示例，仓库不预建这些目录。每个技能的 `SKILL.md` 至少包含：

```markdown
---
name: my-skill
description: 说明技能的用途，以及应该在什么情况下使用它。
---

技能的具体执行指令。
```

- 技能名称在本插件内保持唯一；分类目录不会替代技能名称。
- 连同技能需要的 `scripts/`、`references/`、`assets/` 等资源一起复制，保持相对路径有效。
- 插件统一指向 `./skills/`，递归发现其中的 `SKILL.md`；新增技能或分类无需逐项修改插件清单。
- `skills/` 下的技能都属于安装内容。草稿或暂不启用的技能应放在该目录之外。
- 收集的技能保留原作者署名、许可证和所需依赖说明；指向其他技能的依赖也需在使用环境中可用。

## 首次安装

先添加至少一个实际技能，再自行将仓库内容提交并推送到 `https://github.com/SpxZhu/skills`。
下面的命令由使用者在需要安装的电脑上执行，初始化过程不会自动执行它们。

添加 GitHub 市场：

```powershell
codex plugin marketplace add SpxZhu/skills
```

成功后安装插件：

```powershell
codex plugin add jushawn-skills@jushawn-skills
```

`@` 前是插件名，后是市场名。本仓库将两者都命名为 `jushawn-skills`。
也可以在 Codex 插件界面中找到对应市场的插件并安装、启用。
安装后新建聊天，检查添加的技能是否可用。

## 更新技能

1. 在本仓库的 `skills/` 中添加、修改或移除技能。
2. 更新 `.codex-plugin/plugin.json` 的 `version`，例如从 `0.1.0` 升为 `0.1.1`，标识本次发布的内容。
3. 自行提交并推送到 GitHub。
4. 在使用该插件的电脑上依次刷新市场并重新安装插件：

```powershell
codex plugin marketplace upgrade jushawn-skills
codex plugin add jushawn-skills@jushawn-skills
```

5. 新建聊天，确认新增或修改的技能可用。

Codex 使用安装缓存。只复制本地文件、只推送 GitHub 或只刷新市场，都不应视为已完成已安装插件的更新。
上述命令需要首次安装步骤中的市场注册已成功完成；不会代替 Git 提交或推送。

## 配置与验证

本框架不包含 MCP、应用连接或自动执行钩子；无需构建，也无需为每个技能维护注册列表。
初始化检查只覆盖 JSON 格式、插件声明和路径一致性。实际技能加载需在加入技能并安装后验证。

配置依据：[OpenAI 插件打包与市场文档](https://developers.openai.com/plugins/build/plugins)。
