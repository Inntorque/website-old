# 麟影科技旧版官网

网站源码位于 `website_old/index.html`，图片位于 `website_old/images/`。这是静态单页网站，无需安装依赖或构建。

## 本地预览

在项目根目录运行：

```bash
python3 -m http.server 8000 --directory website_old
```

打开 `http://localhost:8000`。

## GitHub Pages 发布

目标仓库：[Inntorque/website-old](https://github.com/Inntorque/website-old)。

仓库根目录应包含本文件、`.github/` 和 `website_old/`，不要只上传 `website_old/` 子目录。

1. 将项目上传到目标 GitHub 仓库的 `main` 分支。
2. 在仓库的 **Settings → Pages → Build and deployment → Source** 中选择 **GitHub Actions**。
3. 在 **Actions → Deploy website to GitHub Pages → Run workflow** 中选择 `main` 并运行。
4. 发布成功后，从部署记录打开站点地址。之后推送到 `main` 的页面或图片改动会自动发布。

工作流仅打包网页和图片；压缩包附带的 `__MACOSX/`、文案副本、图片说明和 PDF 不进入站点发布包。默认分支若不是 `main`，需同步调整工作流的 `branches` 和 `jobs.deploy.if`。

配置依据：[GitHub Pages 自定义工作流文档](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)。

## 待确定

- 具体文案、图片及其他内容修改。
- 旧域名、新域名及域名管理平台，以便配置 Pages 自定义域名和 DNS。

当前咨询表单只有前端成功提示，尚未接入实际发送服务。
