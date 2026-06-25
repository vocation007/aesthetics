# GitHub Pages 自动部署说明

本项目的 web 静态站点位于：

```text
web/web-html/
```

已经建立 GitHub Actions 工作流：

```text
.github/workflows/deploy-pages.yml
```

工作流会在 `main` 分支发生以下变更时自动部署：

- `web/web-html/**`
- `.github/workflows/deploy-pages.yml`

自定义域名本地标记文件：

```text
web/web-html/CNAME
```

当前域名：

```text
iskip.me
```

注意：使用 GitHub Actions 发布 Pages 时，真正生效的自定义域名以 GitHub 仓库 `Settings -> Pages -> Custom domain` 为准。`CNAME` 文件保留在站点目录里，主要是为了让本地项目也清楚记录当前域名。

## 第一次发布步骤

1. 在 GitHub 新建一个仓库，例如 `aesthetics`。
2. 在本地项目根目录初始化 Git：

```bash
cd /Users/skip/skip/vocation/Aesthetics
git init
git branch -M main
git add .github .gitignore web/README.md web/WEB_MEMORY.md web/GITHUB_PAGES_DEPLOY.md web/web-html
git commit -m "Set up GitHub Pages deployment"
```

不建议第一次直接使用 `git add .`，因为当前目录里还有草稿、备份文件和微信相关脚本。GitHub Pages 实际部署只需要 `.github/` 和 `web/web-html/`。

3. 连接远程仓库：

```bash
git remote add origin git@github.com:你的GitHub用户名/仓库名.git
git push -u origin main
```

4. 打开 GitHub 仓库设置：

```text
Settings -> Pages -> Build and deployment -> Source
```

选择：

```text
GitHub Actions
```

5. 到 `Actions` 页面查看 `Deploy web to GitHub Pages` 是否成功。

## 域名设置

在你的域名 DNS 服务商里，把 `iskip.me` 指向 GitHub Pages。

推荐设置：

```text
A     @     185.199.108.153
A     @     185.199.109.153
A     @     185.199.110.153
A     @     185.199.111.153
CNAME www   你的GitHub用户名.github.io
```

然后在 GitHub 仓库：

```text
Settings -> Pages -> Custom domain
```

填写：

```text
iskip.me
```

等待 DNS 生效后，勾选：

```text
Enforce HTTPS
```

GitHub 官方文档提示：DNS 变更可能需要最长 24 小时生效。

## 日常更新流程

以后只需要修改 `web/web-html/` 里的页面，然后提交并推送：

```bash
git add web/web-html web/WEB_MEMORY.md
git commit -m "Update web pages"
git push
```

GitHub Actions 会自动发布最新版本。
