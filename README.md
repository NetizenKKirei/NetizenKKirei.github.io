# NetizenKKirei.github.io

基于 [Hexo](https://hexo.io/) 与 [Butterfly](https://butterfly.js.org/) 的个人博客。

## 常用命令

```bash
npm install        # 安装依赖
npm run server     # 本地预览
npm run clean      # 清理 Hexo 缓存与构建结果
npm run build      # 生成静态网站到 public/
npm run deploy     # 生成并部署到 GitHub Pages
```

## 项目结构

```text
.
├── _config.yml               # Hexo：站点、URL、目录、部署
├── _config.butterfly.yml     # Butterfly：导航、外观、侧栏、页脚
├── package.json              # 依赖与常用命令
├── scaffolds/                # hexo new 使用的 Markdown 模板
├── source/
│   ├── _posts/
│   │   ├── journal/          # 随笔及其同名资源目录
│   │   ├── tech/             # 技术文章及其同名资源目录
│   │   └── travels/          # 游记及其同名资源目录
│   ├── _drafts/              # 草稿，不参与普通构建
│   ├── _data/                # Butterfly 扩展数据，例如友链
│   ├── images/
│   │   └── site/             # 头像、背景、favicon 等站点图片
│   ├── categories/           # 分类聚合页 /categories/
│   ├── tags/                 # 标签聚合页 /tags/
│   ├── link/                 # 友链页 /link/
│   ├── movie/                # 观影页 /movie/
│   ├── music/                # 音乐页 /music/
│   └── tour/                 # 旅行页 /tour/
└── themes/                   # 主题由 npm 提供，此处无需复制 Butterfly 源码
```

`public/`、`.deploy_git/`、`db.json` 和 `node_modules/` 都是生成物或本地依赖，已被 Git 忽略，不应手动维护。

## Hexo 与 Butterfly 的分工

- Hexo 读取 `source/` 中的 Markdown 和静态资源，根据 `_config.yml` 生成整个静态网站。
- Butterfly 是 Hexo 的主题，负责页面布局和视觉表现；它由 `hexo-theme-butterfly` 依赖提供，定制集中在 `_config.butterfly.yml`。
- `source/_posts/` 下的子目录仅用于整理源码。永久链接使用 `:name`，因此移动文章到栏目目录不会把目录名加入 URL。

## 新增内容

1. 在对应栏目中新建 Markdown，例如 `source/_posts/journal/my-post.md`。
2. 将图片放到文章旁边的同名目录，例如 `my-post/example.webp`。
3. 在文章中以 `![说明](example.webp)` 引用；封面可直接写 `cover: example.webp`。
4. 运行 `npm run server` 预览，发布前运行 `npm run clean && npm run build`。

草稿放在 `source/_drafts/`；需要预览草稿时运行 `npx hexo server --drafts`。
