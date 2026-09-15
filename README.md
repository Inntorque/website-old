# 影拓传感旧版官网

中文版位于 `website_old/index.html`，英文版位于 `website_old/en.html`，图片共用 `website_old/images/`。这是静态网站，无需安装依赖或构建。

右上角的“中文 / EN”按钮用于切换语言。修改产品信息、规格或页面布局时，请同步更新两个 HTML 文件。

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

## 自定义域名

正式域名为 `inntorque.com`，DNS 在新网管理；`www.inntorque.com` 指向 `inntorque.github.io`，由 GitHub Pages 跳转到主域名。

域名绑定在仓库 **Settings → Pages → Custom domain** 中管理。本项目使用 GitHub Actions 发布，不依赖源码中的 `CNAME` 文件。

## 待确定

- 具体文案、图片及其他内容修改。

当前咨询表单只有前端成功提示，尚未接入实际发送服务。
