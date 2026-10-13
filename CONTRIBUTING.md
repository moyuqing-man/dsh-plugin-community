# 参与指南

> 读完这个再发帖，能省你很多时间。

---

## 先做这三件事

1. **搜一下**——你要问的问题很可能已经有答案了。Discussions 和 Issues 都能搜。
2. **确认是哪个仓库的问题**——插件的 bug 应该提给**插件自己的仓库**，不是这里。这里只处理「社区本身」的事（分类、规则、索引、内容）。
3. **选对入口**——见下表。

| 你想做的事 | 正确入口 |
|---|---|
| 插件用不了 / 报错 / 崩溃 | **插件自己的仓库开 Issue**。找不到的话，来[🐞 已知问题](https://github.com/moyuqing-man/dsh-plugin-community/discussions/categories/known-issues)发帖，大家帮你定位 |
| 发现插件有安全风险 | [SECURITY.md](SECURITY.md)，**不要开公开 Issue** |
| 推荐自己的插件 | [🧩 插件展示](https://github.com/moyuqing-man/dsh-plugin-community/discussions/categories/plugin-showcase) |
| 求一个不存在的插件 | [💡 想法与需求](https://github.com/moyuqing-man/dsh-plugin-community/discussions/categories/ideas) |
| 社区规则有问题 | 开 Issue 或在[闲聊区](https://github.com/moyuqing-man/dsh-plugin-community/discussions/categories/general)提 |

---

## 我想推荐自己的插件

**欢迎，而且不需要任何人批准。** 直接去 [🧩 插件展示](https://github.com/moyuqing-man/dsh-plugin-community/discussions/categories/plugin-showcase) 发帖，按表单填。

帖子请**至少包含**：

- **仓库地址**（必须是公开的）
- **一句话说清它解决什么问题**——不要写「强大的 XX 工具」，写「把 X 变成 Y」
- **安装方式**（npm 包名 / GitHub 地址 / `.tgz` 路径）
- **支持的环境**（DSH 版本、是否依赖原生模块）
- **有没有原生依赖**（⚠️ 见下）

### 一条硬要求：说明是否依赖原生模块

DSH 可以跑在 Android 上，但**任何依赖预编译 `.node` 的 npm 包在 Android 上都没有可用版本**。如果你的插件依赖原生模块，请在帖子里写明，并标注「不支持 Android」。这不是缺陷，是事实——写清楚比让人踩坑好。

### 不要做的事

- ❌ **不要重复发帖**。更新原帖，别开新帖——重复帖会被合并或关闭。
- ❌ **不要在这里放安装包**。仓库只承载讨论，不托管二进制。
- ❌ **不要在帖子里堆关键词**。这里没有排名算法，写清楚比写多有用。

---

## 我想求助

去 [🙋 求助](https://github.com/moyuqing-man/dsh-plugin-community/discussions/categories/ask-for-help)，按表单填。表单会问你要版本信息——**请真的填**。

「我装了插件但它不工作」这种帖子没人能回答。**能回答的帖子长这样**：

> **插件**：dsh-xxx v1.2.0
> **DSH 版本**：v0.2.x
> **系统**：Windows 11 / Node v24.21.0
> **做了什么**：装了插件后重启 DSH，侧栏没有出现入口
> **期望**：侧栏出现「XXX」按钮
> **实际**：没有任何变化，日志里有 `...`
> **已试过**：重装插件、清缓存，都没用

日志请贴**关键那几行**，不要贴整个文件。

### 问题解决了请回来收尾

1. **把有用的回答标成「答案」**（只有提问者能标）。求助分类的可见性就靠这个。
2. 如果最后发现是插件的 bug，把结论同步到插件仓库的 Issue。

**一个被标记了答案的帖子，价值超过一百个没结论的帖子。**

---

## 关于审核

本仓库的 Discussions **不做事前审核**——发帖即时可见。这意味着：

- **反垃圾的责任在维护者**，托管到 GitHub 不等于有人替你审帖；
- 违规内容会被**事后**处理（隐藏、锁定、删除），严重时封禁账号；
- 如果你看到垃圾或恶意内容，用 GitHub 的 report 功能，或来[闲聊区](https://github.com/moyuqing-man/dsh-plugin-community/discussions/categories/general)提醒维护者。

**不要**在帖子里贴别人的私人信息（真实姓名、住址、电话、私信截图）。这条没有例外。

---

## 给插件作者的建议

**把你的社区帖子链接放进插件 README。** 这样用户遇到问题时能找到活的讨论，而不是对着一个没人看的仓库发 Issue。

这是零成本的：你得到曝光，用户得到答案，社区得到内容。
