# Leeeo 数字基地导航

18 个自营/朋友站点的总览导航页。

## 包含站点（18）

| 分类 | 站点 | 域名 |
|---|---|---|
| 写作 & 博客 | 不二学习笔记 | blog.imoons.cn |
| 写作 & 博客 | 不二的轻创业笔记 | read.imoons.cn |
| 写作 & 博客 | 不二 · 数字基地 | buer-astro.pages.dev |
| 写作 & 博客 | 不二 · AI 效率手册 | buer-site.pages.dev |
| 写作 & 博客 | 鹏飞日记 | yanming-ji-blog.pages.dev |
| 写作 & 博客 | imoonr Blog | imoonr-blog.pages.dev |
| 写作 & 博客 | 鹏飞的个人主页 | pengfei-portfolio.pages.dev |
| 量化 & 金融 | quant · A股量化信号 | quant.imoons.cn |
| 量化 & 金融 | FundQuant · 基金量化助手 | funds.imoons.cn |
| 量化 & 金融 | fenxi · dsa-web | fenxi.imoons.cn |
| AI 产品 & SaaS | 喵极 AI · 表情包生成 | meow.imoons.cn |
| AI 产品 & SaaS | 图片风格转换 | img.imoons.cn |
| AI 产品 & SaaS | 起名网 · AI 八字起名 | name.imoons.cn/app/ |
| AI 产品 & SaaS | Hermes Studio | hermes.imoons.cn |
| 工具 & 导航 | 全能王工具箱 | tools.imoons.cn |
| 工具 & 导航 | 工具导航 · page | page.imoons.cn |
| 工具 & 导航 | 月光 · Moonlight 导航 | moonlight.imoons.cn |
| 文档 & 实验室 | Leeeo · 编程实验室 | www.leeeo.cn |
| 文档 & 实验室 | Hermes Studio · 后台 | hs.imoons.cn/admin/login |
| 文档 & 实验室 | Hermes 工作台 · 资源入口 | hermes-portal.pages.dev |
| 文档 & 实验室 | 综合知识库 | api-docs-51h.pages.dev |

## 本地预览

```bash
cd /root/nav-imoons
python3 -m http.server 8080
# 浏览器打开 http://localhost:8080
```

## 部署

### 1. 同步到 GitHub

```bash
# 首次
cd /root/nav-imoons
git init
git add .
git commit -m "feat: 18 站导航页"
gh repo create nav-imoons --public --source=. --push

# 后续改动
git add . && git commit -m "update" && git push
```

### 2. Cloudflare Pages 绑定

1. 登录 Cloudflare Dashboard → Workers & Pages → Create application → Pages
2. Connect to Git → 选 `nav-imoons` 仓库
3. Build settings:
   - **Build command**: 留空
   - **Build output directory**: `.` (根目录)
   - **Root directory**: `/`
4. 点击 Save and Deploy

部署完成后会得到一个 `nav-imoons.pages.dev` 子域名。

### 3. 绑定自定义域名

如果想用 `nav.imoons.cn`：

1. Cloudflare Pages 项目 → Custom domains → Set up a custom domain
2. 输入 `nav.imoons.cn`
3. 按提示在 Cloudflare DNS 加 CNAME 记录

## 维护清单

- 新增站点：在 `index.html` 对应 `<section>` 下加一张 `<a class="card">` 即可
- 改色：调整 `:root` 里的 `--accent` / `--self` / `--friend` / `--tool` / `--doc` 5 个 CSS 变量
- 改分类：调整 `<section data-section="...">` 和上方 `stats` 数字
