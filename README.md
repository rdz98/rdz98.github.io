# Dazhong Rong | Academic Homepage · 个人学术主页

[网站 / Website](https://rdz98.github.io/) · [中文](#中文) · [English](#english) · [License](LICENSE)

## 中文

### 项目简介

本仓库是 Dazhong Rong 的个人学术主页源码，展示个人简介、研究方向、最新动态、代表性论文、学术服务与简历。研究方向包括侵入式脑机接口（视觉编码与解码、运动意图解码）以及可信人工智能。

网站基于 Jekyll 和 [Minimal Light](https://github.com/yaoyao-liu/minimal-light) 主题定制，使用本地布局与样式文件，支持移动端显示、Markdown 内容、基础 SEO 和跟随系统的深色模式。

### 本地运行

需要 Git、Ruby 和 Bundler。当前本地已验证环境为 Windows、Ruby 4.0.6、Bundler 4.0.16 和 Jekyll 4.3.4；依赖以 [Gemfile](Gemfile) 和 [Gemfile.lock](Gemfile.lock) 为准。

```sh
git clone https://github.com/rdz98/rdz98.github.io.git
cd rdz98.github.io
gem install bundler -v 4.0.16
bundle install
bundle exec jekyll serve
```

在浏览器打开 [本地预览](http://localhost:4000)。使用 Ctrl+C 停止服务；修改 `_config.yml` 后重新启动服务。

仅生成静态文件：

```sh
bundle exec jekyll build
```

输出位于 `_site/`，该目录和 Jekyll 缓存已被 Git 忽略。日常修改应在源文件中完成。命令用法见 [Jekyll 文档](https://jekyllrb.com/docs/usage/)。

### 内容与文件

| 文件或目录 | 用途 |
| --- | --- |
| [index.md](index.md) | 个人简介、研究方向、动态，以及论文和学术服务的引入 |
| [_config.yml](_config.yml) | 姓名、职位、单位、联系方式、链接和显示选项 |
| [_data/publications.yml](_data/publications.yml) | 论文数据，按文件中的顺序显示 |
| [_includes/publications.md](_includes/publications.md) | 论文列表的 Liquid/HTML 模板及局部样式 |
| [_includes/services.md](_includes/services.md) | 学术服务 |
| [_layouts/homepage.html](_layouts/homepage.html) | 页面结构、元信息与侧栏 |
| [_sass/](_sass/) | 支持深色模式和仅浅色模式的主样式 |
| [assets/css/](assets/css/) | Sass 入口、字体与论文样式 |
| [assets/js/](assets/js/) | favicon 切换和页面辅助脚本 |
| [assets/img/](assets/img/) | 头像、favicon 等图片 |
| [assets/files/](assets/files/) | 简历 PDF 及 Markdown 文件 |
| [Gemfile](Gemfile)、[Gemfile.lock](Gemfile.lock) | Ruby 依赖声明和锁定版本 |

在 `_data/publications.yml` 的 `main:` 列表下添加论文，例如：

```yaml
main:
  - title: "Paper title"
    authors: "<strong>Dazhong Rong</strong>, Coauthor"
    venue: "Conference or journal name"
    venue_short: "VENUE"
    venue_rank: "CCF-A"
    url: "https://example.org/paper"
    notes: "Optional note"
```

`venue_rank`、`url` 和 `notes` 可省略。标题在提供非空 `url` 时显示为链接；没有链接时显示为普通文本，并带有“Accepted but not yet published”的悬停提示。作者字段支持 HTML，可用 `<strong>` 加粗姓名。

### 配置与外观

在 `_config.yml` 中维护：

- `title`、`position`、`affiliation`、`email`：个人信息。
- `google_scholar`、`github_link`、`cv_link`：侧栏链接；简历当前指向 `assets/files/CV_DazhongRong.pdf`，更新 Markdown 后需另行更新 PDF。
- `keywords`、`description`、`canonical`：搜索元信息及主页规范地址。
- `avatar`、`favicon`、`favicon_dark`：头像和浅色/深色 favicon。
- `auto_dark_mode`：选择支持深色模式或仅浅色模式的主样式。
- `font`：`"Serif"` 或 `"Sans Serif"`。
- `enable_footnote`：是否显示主题页脚。

主样式分别位于 `_sass/minimal-light.scss` 和 `_sass/minimal-light-no-dark-mode.scss`，由 `assets/css/` 下对应的 Sass 入口通过 `@import` 加载。两个入口顶部的 YAML front matter（两行 `---`）需要保留。

论文模板还包含独立的深色模式媒体查询；调整论文外观时，也要检查 `_includes/publications.md`。

### 发布

主页地址配置为 [rdz98.github.io](https://rdz98.github.io/)。GitHub Pages 的实际发布来源以仓库 Settings → Pages 为准；当前源码中没有自定义 Actions 工作流。

如需用本项目的依赖构建并发布，可按照 [GitHub Pages 自定义工作流文档](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages) 配置构建与部署。配置 Linux 构建环境时，还需为锁文件添加对应平台；当前锁文件记录的是 Windows 平台 `x64-mingw-ucrt`。

也可将 `bundle exec jekyll build` 生成的 `_site/` 内容部署至静态网站服务器。

## English

### Overview

This repository contains the source for Dazhong Rong's personal academic homepage, featuring a biography, research interests, news, selected publications, academic service, and a CV. Research interests include invasive brain-computer interfaces (visual encoding and decoding, and motor intention decoding) and trustworthy AI.

The site is built with Jekyll and customized from [Minimal Light](https://github.com/yaoyao-liu/minimal-light). It uses local layouts and styles, with mobile support, Markdown content, basic SEO, and system-based dark mode.

### Run locally

Git, Ruby, and Bundler are required. The locally verified environment is Windows with Ruby 4.0.6, Bundler 4.0.16, and Jekyll 4.3.4. [Gemfile](Gemfile) and [Gemfile.lock](Gemfile.lock) define the dependencies and locked versions.

```sh
git clone https://github.com/rdz98/rdz98.github.io.git
cd rdz98.github.io
gem install bundler -v 4.0.16
bundle install
bundle exec jekyll serve
```

Open the [local preview](http://localhost:4000). Stop the server with Ctrl+C, and restart it after changing `_config.yml`.

To generate the static site:

```sh
bundle exec jekyll build
```

Output is written to `_site/`. This directory and Jekyll caches are ignored by Git; edit source files for ongoing maintenance. See the [Jekyll command documentation](https://jekyllrb.com/docs/usage/).

### Content and files

| File or directory | Purpose |
| --- | --- |
| [index.md](index.md) | Biography, research interests, news, and inclusion of publications and service |
| [_config.yml](_config.yml) | Personal details, contact information, links, and display settings |
| [_data/publications.yml](_data/publications.yml) | Publications, displayed in their listed order |
| [_includes/publications.md](_includes/publications.md) | Publication Liquid/HTML template and local styles |
| [_includes/services.md](_includes/services.md) | Academic service |
| [_layouts/homepage.html](_layouts/homepage.html) | Page structure, metadata, and sidebar |
| [_sass/](_sass/) | Main styles with dark-mode support and the light-only alternative |
| [assets/css/](assets/css/) | Sass entry points, fonts, and publication styles |
| [assets/js/](assets/js/) | Favicon switching and page helper scripts |
| [assets/img/](assets/img/) | Avatar, favicons, and other images |
| [assets/files/](assets/files/) | CV PDF and Markdown files |
| [Gemfile](Gemfile), [Gemfile.lock](Gemfile.lock) | Ruby dependencies and locked versions |

Add publications under `main:` in `_data/publications.yml`:

```yaml
main:
  - title: "Paper title"
    authors: "<strong>Dazhong Rong</strong>, Coauthor"
    venue: "Conference or journal name"
    venue_short: "VENUE"
    venue_rank: "CCF-A"
    url: "https://example.org/paper"
    notes: "Optional note"
```

`venue_rank`, `url`, and `notes` are optional. A nonempty `url` makes the title a link. Without a URL, the title is plain text with an “Accepted but not yet published” tooltip. Author names support HTML formatting, including `<strong>`.

### Configuration and appearance

Maintain these settings in `_config.yml`:

- `title`, `position`, `affiliation`, `email`: personal information.
- `google_scholar`, `github_link`, `cv_link`: sidebar links. The CV currently points to `assets/files/CV_DazhongRong.pdf`; updating the Markdown CV does not regenerate the PDF.
- `keywords`, `description`, `canonical`: search metadata and the canonical homepage URL.
- `avatar`, `favicon`, `favicon_dark`: profile image and light/dark favicons; both modes currently share `assets/img/favicon.ico`.
- `auto_dark_mode`: select the main styles with dark-mode support or the light-only alternative.
- `font`: `"Serif"` or `"Sans Serif"`.
- `enable_footnote`: show or hide the theme footer.

Main styles live in `_sass/minimal-light.scss` and `_sass/minimal-light-no-dark-mode.scss`. Their corresponding Sass entry points in `assets/css/` load them using `@import`. This import syntax is retained for compatibility with the default GitHub Pages build; local Dart Sass may emit a deprecation warning without failing the current build. Keep the YAML front matter (two lines of `---`) at the top of both entry points.

The publication template also contains independent dark-mode media queries. Check `_includes/publications.md` when changing publication styles.

### Publishing

The configured homepage URL is [rdz98.github.io](https://rdz98.github.io/). Check Settings → Pages in the repository for the actual publishing source. The current source tree does not include a custom Actions workflow.

To build and publish using this project's dependencies, configure a workflow following the [GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages). A Linux build environment also requires its corresponding platform in the lockfile; the current lockfile lists Windows `x64-mingw-ucrt`.

Alternatively, deploy the contents of `_site/`, generated by `bundle exec jekyll build`, to a static web server.


## 许可与致谢 / License and acknowledgements

仓库保留 [CC0 1.0 Universal](LICENSE) 许可文件。网站基于 Minimal Light 定制，并保留原主题对以下项目的致谢。

The repository retains its [CC0 1.0 Universal](LICENSE) license file. The site is customized from Minimal Light and retains the upstream theme's acknowledgements.

- [Minimal Light](https://github.com/yaoyao-liu/minimal-light)
- [pages-themes/minimal](https://github.com/pages-themes/minimal)
- [orderedlist/minimal](https://github.com/orderedlist/minimal)
- [al-folio](https://github.com/alshedivat/al-folio)
