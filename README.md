# 王思涵的学术主页

使用 GitHub Pages 内置的 Jekyll。英文首页位于 `/`，中文首页位于 `/zh/`。每个页面有独立地址，可以直接发给同事或学生。样式随站点提供，字体使用访客设备上的本地字体。

## 发布与历史

目标仓库是 [arckiCriss/arckicriss.github.io](https://github.com/arckiCriss/arckicriss.github.io)，发布分支是 `master`，发布目录是根目录。发布后的[英文首页](https://arckicriss.github.io/)和[中文首页](https://arckicriss.github.io/zh/)分别有独立网址。

这次迁移使用普通 Git 提交替换旧博客。上一个版本是 [d2e9051](https://github.com/arckiCriss/arckicriss.github.io/tree/d2e90518fe154c4b72c6658398129d0633e1c577)。可以随时从 Git 历史查看旧文章，或用 `git revert` 撤销这次迁移。

推送到 `master` 后，GitHub Pages 会重新构建站点。在仓库的 **Actions** 查看构建结果。如需核对，发布设置位于 **Settings → Pages → Deploy from a branch → master → /(root)**。详见 [GitHub Pages 文档](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)。

## 日常维护

| 要改的内容 | 仓库文件 | 操作 |
| --- | --- | --- |
| 研究简介、职务、教育、项目、教学、招生 | `_data/home/zh.yml`、`_data/home/en.yml` | 分别编辑中文和英文 |
| 新闻 | `_data/news.yml` | 把新条目加在顶部，同一条填写两种语言，可附论文链接 |
| 论文 | `_data/publications.yml` | 添加英文原题、作者、年份、刊会和 DOI。设定 `selected: true` 和 `selected_order` 可放上首页 |
| 刊会等级 | `_data/venue_ranks.yml` | 按刊会简称维护 CCF 第七版推荐类别，同一刊会的论文共用一项 |
| 邮箱、肖像 | `_config.yml` | 更新 `email` 或 `portrait` |
| 字体、版式与颜色 | `assets/css/site.css` | 所有语言共用 |

新增论文后，两种语言的列表、篇数和年份导航都会自动更新。选择三篇代表作，在对应条目中设置 `selected: true` 和 `selected_order`。对于短文、海报等不适用 CCF 分类的条目，填写 `ccf_eligible: false`。单篇论文的奖项或研究亮点可分别写入 `honor.zh` 和 `honor.en`。

上传照片时，把文件放在 `assets/images/portrait.jpg`，然后将 `_config.yml` 中的设置改为 `portrait: "/assets/images/portrait.jpg"`。头像使用 4:5 的竖幅，桌面显示在姓名下方，手机上显示在姓名旁。照片配置留空时，页面使用已预留的位置。

### 写随笔

在站点仓库的 `_posts/` 目录中新建 Markdown 文件即可。目录可以在发布第一篇时创建。文件名使用 `YYYY-MM-DD-slug.md`，例如 `2026-11-27-reading-protocols-zh.md`。中文和英文文章分别出现在 `/zh/notes/` 和 `/notes/`，按日期从新到旧排列。

```markdown
---
layout: note
lang: zh-CN
title: "读通信协议时，我会记下哪些问题"
---

从这里开始写正文。页面使用文件名中的日期。
```

发英文随笔时将 `lang` 改为 `en`。两种语言各自独立发文。如果同一篇有译文，用不同的文件名（例如分别以 `-zh.md` 和 `-en.md` 结尾），并在两份文件的头部填写相同的 `translation_key: reading-protocols`。发布后，两篇文章会在日期旁显示对方的入口。每个键只用于一对译文。`description` 为可选的一句话摘要，会显示在归档列表中。

网站有第一篇随笔时，两个首页都会出现随笔入口。如果只有一种语言有文章，导航直接带访客进入有内容的归档。你可以只用一种语言写。

发布后，在 GitHub 网页上编辑 YAML 或添加 Markdown，提交到 Pages 的发布分支即可更新。原始求职简历及私人联系方式没有放入源码，公开的联系渠道为学校邮箱。
