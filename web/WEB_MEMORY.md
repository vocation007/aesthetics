# Web 长期记忆

## 2026-06-25

- 《审美的逻辑》的 web-first 版本已经发布到线上，对外域名是 https://iskip.me/。
- 本地 web 输出统一放在这个 `web/` 文件夹下。目前静态网站源码在 `web/web-html/`。
- 以后和网站相关的长期上下文、发布状态、SEO/GEO 方向、站点定位和关键决策，都记录在这个文件里，避免后续遗忘。
- 当前网站目标：持续优化网站，提升 GEO 可见性，增加自然流量。
- 已新增“关于我”页面，用于介绍作者 Skip，提供公众号关注入口和联系邮箱 `skipskkip007@gmail.com`。
- “关于我”页面路径：`web/web-html/about.html`。
- 公众号二维码资产路径：`web/web-html/assets/wechat-qrcode.jpg`。
- 顶部导航已调整为接近 Medium 的克制通栏样式：左侧文字字标，右侧极简链接，固定高度、细底线、active 状态贴合底线。不使用图片 logo，避免中文图片字标失真。
- “关于我”页面首屏应保持极简，不放右侧几何装饰图或说明卡片；保留左侧标题和大留白即可。
- 首页 masthead 标题需要有分量但不能抢过内容入口；当前首页 `h1` 尺度为桌面 `clamp(54px, 7.2vw, 118px)`、移动端 `clamp(46px, 14vw, 68px)`。
- 首页文章列表区参考 Medium，不使用大型 serif 分区标题；`所有文章` 只作为 15px 的轻量栏目标签，重点放在内容流本身。
- 已建立 GitHub Pages 自动部署配置：`.github/workflows/deploy-pages.yml`。部署源目录为 `web/web-html/`，本地保留域名标记文件 `web/web-html/CNAME`，域名是 `iskip.me`；使用 GitHub Actions 发布 Pages 时，真正生效的自定义域名以后以 GitHub 仓库 `Settings -> Pages -> Custom domain` 为准。第一次提交时不要直接 `git add .`，避免把草稿、备份和非网站文件一起推到 GitHub。
- 2026-06-25：GitHub 仓库已连接并推送成功：`https://github.com/vocation007/aesthetics.git`。Pages 已启用为 `workflow` 发布方式，最新工作流部署成功。临时 Pages 地址为 `https://vocation007.github.io/aesthetics/`。GitHub Pages 的 custom domain 已设置为 `iskip.me`，但 `https_enforced` 目前为 `false`，需要等域名 DNS 指向 GitHub Pages 并生成证书后再开启。
