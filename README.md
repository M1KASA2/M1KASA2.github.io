# Jiahui Tian · 田佳辉

田佳辉的个人学术主页。布局参考 <https://zhaorw02.github.io/>，使用重新编写的 HTML、CSS 和原创 SVG 占位图。

## 当前版本

- 纯静态页面，无需 Node.js、框架、构建步骤或第三方在线服务。
- 桌面端采用个人简介在左、头像在右、论文缩略图在左的学术主页布局。
- 已展示真实姓名、学校、年级、专业、邮箱、GitHub 和教育信息。
- 根据本人要求，自我介绍与研究方向暂不填写。
- Publications、Projects、Honors and Awards 保留为不显示的 `<template>`；收到真实资料后启用。
- 支持手机、键盘导航和打印，样式、图片全部通过相对路径加载。
- 当前头像来自本人 GitHub 账号 M1KASA2 的公开头像，图片已保存在本地，可随时换成正式照片。
- 可见页面没有虚构履历、占位论文和无效按钮；模板内容不会显示在网页上。
- 已设置页面标题、分享摘要、Person 结构化数据、canonical、robots.txt 和站点地图。

## 本地查看

直接用浏览器打开 `index.html` 即可。也可以在本目录运行：

```powershell
python -m http.server 8766 --bind 127.0.0.1
```

然后访问 <http://127.0.0.1:8766/>。

## 补充信息

已知资料已记录在 `PERSONAL_INFO.md`。后续可补充真实照片、教育起止时间、简介、研究方向、项目和论文，不必每项都有。

论文、项目和奖项的示例结构在 `index.html` 的 `<template>` 中，不会渲染。补齐真实内容后，将对应 `<section>` 移到 `<template>` 外，即可显示。

主要修改位置：

| 内容 | 位置 |
| --- | --- |
| 姓名、简介、链接、论文、项目、教育经历 | `index.html` 中相应注释块 |
| 浏览器标题、作者、搜索摘要、分享标题 | `index.html` 的 `<head>` |
| 页面宽度、字体、颜色、手机布局 | `assets/css/style.css` |
| 个人照片 | 放入 `assets/images/` 后修改头像的 `src` 和 `alt` |
| 论文与项目图片 | 放入 `assets/images/` 后修改对应图片的 `src` 和 `alt` |
| PDF 简历 | 可放入 `assets/files/cv.pdf`，再添加对应链接 |

图片的 `width`、`height` 请填写真实尺寸。邮箱使用 `mailto:` 链接。没有目标的链接应直接省略。

论文作者应高亮自己的姓名；只有确实被接收的论文才填写相应会议或期刊，预印本可以标注为 arXiv / Preprint。没有论文也可以先保留真实项目和教育经历。

页面链接示例：

```html
<a href="mailto:your-email@university.edu">Email</a>
<a href="https://github.com/YOUR_USERNAME">GitHub</a>
<a href="assets/files/cv.pdf">CV</a>
```

## 发布到 GitHub Pages

对应的用户主页仓库为 `M1KASA2.github.io`，部署成功后的地址为 <https://m1kasa2.github.io/>。

1. 使用 M1KASA2 登录 GitHub，创建名为 `M1KASA2.github.io` 的仓库。
2. 将本目录中的文件上传到仓库根目录，确保 `index.html` 在根目录，而不是再套一层文件夹。
3. 打开仓库的 **Settings → Pages**。
4. 在 **Build and deployment → Source** 选择 **Deploy from a branch**。
5. 选择实际使用的分支（通常为 `main`）和 **/ (root)**，然后保存。
6. 等待部署成功，打开 Pages 页面显示的网站地址。

`.nojekyll` 已包含在项目中。页面使用相对资源路径，也支持部署到项目仓库。

canonical、`og:url`、分享头像和站点地图已指向 `https://m1kasa2.github.io/`。如果改用其他域名或项目仓库，需要同步修改 `index.html`、`robots.txt` 和 `sitemap.xml` 中的地址。

正式发布时建议仅上传 `index.html`、`assets/`、`.nojekyll`、`robots.txt`、`sitemap.xml`。README 和资料清单无需上传。

## 文件结构

```text
academic-homepage/
├── index.html
├── .nojekyll
├── .gitignore
├── README.md
├── PERSONAL_INFO.md
├── robots.txt
├── sitemap.xml
└── assets/
    ├── css/style.css
    └── images/
        ├── favicon.svg
        ├── github-avatar.png
        ├── portrait-placeholder.svg
        ├── publication-placeholder.svg
        └── project-placeholder.svg
```

参考页面仅用于布局参考，其姓名、照片、论文、代码与其他个人资料未用于本主页。
