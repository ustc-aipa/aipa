# 人工智能原理与应用课程网站

《人工智能原理与应用》课程的单页课程网站项目

## 本地运行

先安装依赖：

```bash
npm install
```

启动本地开发：

```bash
npm run dev
```

如果你在 Windows PowerShell 里遇到脚本限制，可以改用：

```powershell
npm.cmd run dev
```

本地构建：

```bash
npm run build
```

## 内容维护

课程基本信息和中英文大纲数据在：

- `scripts/course-source.mjs`

首页入口在：

- `site/index.md`

页面组件在：

- `site/.vitepress/components/`

站点配置在：

- `site/.vitepress/config.mjs`

## 课程资料目录

课程资料区会自动扫描 `course-materials/` 目录，并在首页“课程资料”表格中显示可下载文件。

目录结构如下：

```text
course-materials/
  week-02/
    class-material/
    homework/
  week-03/
    class-material/
    homework/
  ...
  week-15/
    class-material/
    homework/
```

规则如下：

- 放进 `week-xx/class-material/` 的文件会显示在 `Class Material`
- 放进 `week-xx/homework/` 的文件会显示在 `Homework`
- 没有文件时，页面会显示占位内容
- 新增文件后，重新运行 `npm run docs:prepare`、`npm run dev` 或 `npm run build` 即可刷新列表

## 自动部署

仓库已经配置 GitHub Actions：

- `.github/workflows/ci.yml`
- `.github/workflows/deploy.yml`

默认行为：

- push 到 `main` 时自动构建
- push 到 `main` 时自动部署到 GitHub Pages

首次使用时，需要在 GitHub 仓库设置中开启：

1. `Settings`
2. `Pages`
3. `Source: GitHub Actions`
