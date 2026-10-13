# 讨论分类：怎么建、建什么

> 这份是**给维护者照着点**的操作单。GitHub 的分类只能在网页上手动建，
> 没有任何 API 能一次建好，所以只能一步步来。

---

## 为什么这一步不能跳过

`DISCUSSION_TEMPLATE/*.yml` 里的发帖表单，**文件名必须等于分类的 slug**
（GitHub 官方原文：*"The name must correspond with the slug for one of your discussion categories."*）。

也就是说：

- 分类叫 `plugin-showcase` → 表单文件名必须是 `plugin-showcase.yml`
- 分类叫 `插件展示` → slug 很可能变成 `插件展示`，那 `plugin-showcase.yml` 就**永远不生效**

**表单不生效是静默的**——GitHub 不会报错，只是发帖时不出现那个表单。
所以这一步错了很难自己发现，务必按下面的顺序做。

---

## 顺序（建议照做）

### 1. 建仓库

公开仓库：`moyuqing-man/dsh-plugin-community`

> 换成组织只需要改地址，本目录里所有文件都不用动。

### 2. 开启 Discussions

**Settings → General → Features → 勾上 `Discussions`**

不勾这一步，后面所有讨论相关的东西都不存在。**这是最容易漏的一步。**

开启时 GitHub 会自动塞 **5 个默认分类**（Announcements / General / Ideas / Polls / Q&A / Show and tell）。
下面第 4 步会处理掉不需要的。

### 3. 推文件

把 `community-repo/` 里的内容推到仓库根目录（`.github/` 要一起推）。

### 4. 建分类

Discussions 页面 → 左侧分类栏 → 铅笔图标 → 进入分类管理。

**保险做法：先用英文名创建，再改名成中文。**

因为 slug 在创建时就定下来了，之后改显示名通常不会改 slug。所以：

| 第一步：创建时用这个名字（= 想要的 slug） | 第二步：改成这个显示名 |
| --- | --- |
| `announcements` | 📣 公告 |
| `plugin-showcase` | 🧩 插件展示 |
| `ask-for-help` | 🙋 求助 |
| `ideas` | 💡 想法与需求 |
| `known-issues` | 🐞 已知问题 |
| `general` | 🗣️ 闲聊 |

### 5. 核对 slug（重要）

建完之后，**点进每个分类，看地址栏**：

```
https://github.com/moyuqing-man/dsh-plugin-community/discussions/categories/<slug>
```

那个 `<slug>` 就是真相。如果和上表不一致，有两个选择：

- **改分类名**（回到分类管理里改）——推荐
- **改文件名**：把 `.github/DISCUSSION_TEMPLATE/<slug>.yml` 改成实际 slug

只要两边对上了，表单就会在发帖时出现。

---

## 六个分类分别干什么

| Emoji | 名称 | slug | 格式（Format） | 用途 | 发帖表单 |
| --- | --- | --- | --- | --- | --- |
| 📣 | 公告 | `announcements` | Announcement | 维护者发布。普通成员发不了帖，这是出通知的地方 | 无 |
| 🧩 | 插件展示 | `plugin-showcase` | Open-ended discussion | 自荐或推荐插件。**不需要任何人批准** | `plugin-showcase.yml` |
| 🙋 | 求助 | `ask-for-help` | **Question and answer** | 插件用不明白、报错、装不上 | `ask-for-help.yml` |
| 💡 | 想法与需求 | `ideas` | Open-ended discussion | 想要一个还不存在的插件 | `ideas.yml` |
| 🐞 | 已知问题 | `known-issues` | Open-ended discussion | 记录确认存在、但一时修不掉的坑和绕过方法 | `known-issues.yml` |
| 🗣️ | 闲聊 | `general` | Open-ended discussion | 兜底，什么都行 | 无 |

### 三个关键选择，解释一下

**`ask-for-help` 必须选 Question and answer 格式。**
这是整个社区最有价值的一个设置：它允许把某条回复**标记为答案**。
一个被标了答案的帖子，对后来者的价值超过一百个没有结论的帖子。
一旦建错格式，帖子右上角的「Mark as answer」不会出现。

**`announcements` 选 Announcement 格式**，只有维护者能发，
避免公告区被别人的帖子冲掉。

**`known-issues` 和「插件 Bug 汇报」Issue 是两回事**：
Issue 用来**推动修复**（提给插件自己的仓库），
讨论帖用来**让下一个踩坑的人搜得到**（包括绕过方法）。
两个都要有，缺一个就断链。

---

## 建好之后怎么验

- [ ] 仓库页面顶部能看到 **Discussions** 标签
- [ ] 分类列表里是上表那 6 个，没有多余的默认分类
- [ ] 进 🧩 插件展示 发帖时，能看到带「仓库地址 / 是否依赖原生模块」的表单
- [ ] 进 🙋 求助 发帖时，能看到带「我想做 / 我做了 / 结果是」的表单
- [ ] 在 🙋 求助 里回复一条，能点出 **Mark as answer**
- [ ] 地址栏里的 slug 与上表**逐字一致**

最后一项不过，前面几项都是假象。
