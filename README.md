# AI 产品经理求职资料

七份材料，对应求职的七个动作：读、练、查、看、翻、补、背。

| 文件 | 是什么 | 什么时候打开 |
|---|---|---|
| `handbook.html` | 面试问答手册 · 13 章 68 组 | 面试前一晚通读结论；出门前只看追问链 |
| `interview-sim.html` | 三类面试官模拟 · HR 12 / 老板 12 / 技术 14 | 确认了是第几轮之后，只练那一组 |
| `jd-interview.html` | JD 面试 Q&A · 四个项目的技术追问预案 | 对面是技术负责人或 CTO，需要现场画图讲架构 |
| `site/index.html` | 个人网站（对外展示） | 投简历时附在邮件里；被问「有作品集吗」 |
| `library.html` | 学习库 · 246 篇 | 被问到一个答不上来的概念，回来查 |
| `tech.html` | 技术底盘 · 高频词 · 成本 | 决定「先补哪一块」时看；14 天计划在最后一个 tab |
| `kg.html` | 知识图谱 & 背卡 · 79 知识点 / 79 知识点题 / 47 项目题 / 66 应用题 | 碎片时间用背卡过题；要看完整版点开追问链和流程图 |

根目录的 `index.html` 是入口页。

---

## 怎么上线（GitHub Pages）

**第一步：建仓库**

在 GitHub 新建一个仓库，名字随意（比如 `ai-pm-kit`），**设为 Public**（Pages 免费版只支持公开仓库）。

**第二步：上传这六个文件**

把本目录里的所有文件（含 `site/` 子目录和 `.nojekyll`）传到仓库根目录。

网页上传：仓库页 → `Add file` → `Upload files` → 把整个文件夹拖进去 → `Commit changes`。

> `.nojekyll` 是个空文件，作用是让 GitHub 不要用 Jekyll 处理页面。**别漏了它**，否则以下划线开头的路径可能被忽略。

**第三步：开 Pages**

仓库 → `Settings` → 左侧 `Pages` → `Source` 选 `Deploy from a branch` → 分支选 `main`、目录选 `/ (root)` → `Save`。

等 1–2 分钟，地址是：

```
https://你的用户名.github.io/ai-pm-kit/
```

打开就是入口页，五个链接都能点。

**以后更新**

改了本地文件，重新上传覆盖即可（`Add file` → `Upload files` → 拖进去 → 提交）。Pages 会自动重新构建，大约 1 分钟。

---

## 链接为什么用英文文件名

原文件名是中文（`面试问答手册.html`），在网址里会变成这样：

```
https://xxx.github.io/ai-pm-kit/%E9%9D%A2%E8%AF%95%E9%97%AE%E7%AD%94%E6%89%8B%E5%86%8C.html
```

能用，但没法记、发出去也难看。所以打包时统一改成了英文文件名，页面标题还是中文。

另外 `JD面试Q&A.html` 里的 `&` 在网址里必须写成 `%26`，否则会被当成参数分隔符——改成 `jd-interview.html` 也顺带解决了这个隐患。

---

## 口径一致性

七份材料讲的是同一套事实：四个项目、同样的数字、同样的边界。

任何一份里说不清的东西，换一份也说不清——那就说明该回去补的不是话术，是事实。

**数字纪律**：能自证的数字才用（工时、营收、图纸张数、评测集条数）；推出来的量级（延迟、并发、召回率）一律标注「没做压测」「给不了」。

---

## ⚠️ 两个仓库，别搞混

你有一个**已经在用的**个人网站：

```
https://lilmrmeeseeks.github.io/hudi/     ← 仓库名 hudi · 分享给 HR 的链接
```

这份包里也有个人网站（`site/index.html`）。**它和线上那份完全一样**——右边导航只有 00–07 八个页内锚点，没有任何指向面试资料的链接。

**规则只有一条：**

> 这份包**推到新仓库**（比如 `ai-pm-kit`），**永远不要推到 `hudi`**。

两个仓库的网址天然不同：`.../ai-pm-kit/` 和 `.../hudi/`。只要推对新仓库，HR 手上那个链接一个字符都不会变。

**如果你要更新线上的个人网站**（改内容、换项目），去 `hudi` 那个仓库改，不要改这里——这里只是副本，改了也不会同步上去。
## 体积说明（先看这个）

| 部分 | 大小 | 说明 |
|---|---|---|
| 五个 HTML | 2.6 MB | `library.html` 占 2 MB（246 篇全文内嵌） |
| `site/` 的个人网站 | 18.9 MB | 25 个媒体文件：15 张封面图 + 10 个演示视频 |
| **合计** | **约 21 MB** | |

单个文件最大 2.7 MB（`cv1.mp4`），**都低于 GitHub 的 25 MB 单文件限制**，但网页上传 33 个文件会慢，中途可能超时。

**三种上传方式，按你的情况选：**

**① GitHub Desktop（推荐）**
装 [GitHub Desktop](https://desktop.github.com/) → `File` → `Clone repository` → 选你新建的空仓库 → 把本目录所有文件复制进去 → 它会列出改动 → 填一句 summary → `Commit to main` → `Push origin`。21 MB 一次性推上去，最稳。

**② 命令行**
```bash
cd 你解压出来的目录
git init
git add .
git commit -m "init: AI PM interview kit"
git remote add origin https://github.com/你的用户名/ai-pm-kit.git
git push -u origin main
```

**③ 网页上传（只适合轻量版）**
如果嫌 21 MB 大，可以先只传五个 HTML + README + `.nojekyll`（共 2.6 MB），把 `site/` 整个目录先跳过。个人网站的链接会 404，等以后再补。

> 注：`site/index.html` 里的导航用 `../` 指向根目录的另外三个页面，这是正确的相对路径——GitHub Pages 上 `.../repo/site/` → `../handbook.html` 解析成 `.../repo/handbook.html`。本地双击 `site/index.html` 也一样能跳。
