# motrixlab-homework

MotrixLab 第五期「强化学习与 MotrixLab 入门」课后作业整理（共 8 周），纯静态站点，部署在 GitHub Pages。

## 目录结构

```
motrixlab-homework/
├── index.html            # 主页入口：8 周作业导航，点击卡片跳转对应页面
├── weeks/                # 每周作业（选择题含答案标绿）
│   ├── week1.html        # 第一周：第 1~4 讲，40 题已发布
│   ├── week2.html        # （后续周发布后按 weekN.html 命名加入）
│   └── ...
└── .github/
    └── workflows/
        └── deploy-pages.yml   # GitHub Pages 部署流水线
```

## 新增一周作业

1. 在 `weeks/` 下新建 `weekN.html`（复制 week1.html 改内容）；
2. 编辑根目录 `index.html`，把对应周的占位卡片改成 `<a class="week-card" href="weeks/weekN.html">` 并把标签改为「已发布」。

## 自定义域名（CUSTOM_CNAME）

两种方式任选其一：

- **仓库变量方式（推荐，由 CI 自动生成 CNAME 文件）**：
  1. 仓库 Settings → Secrets and variables → Actions → Variables → 新建变量 `CUSTOM_DOMAIN`，值为你的域名（如 `hw.example.com`）；
  2. 编辑 `.github/workflows/deploy-pages.yml`，取消 `environment.url` 和 `Write CNAME` 两处注释；
  3. 在 DNS 服务商处添加 CNAME 记录指向 `<user>.github.io`。
- **手动方式**：仓库根目录提交一个只含域名的 `CNAME` 文件，并在 Settings → Pages → Custom domain 填入域名（workflow 无需改动）。

## 部署

推送到 `main` 分支即自动部署（GitHub Actions → Deploy to GitHub Pages）。首次启用需在仓库 Settings → Pages → Source 选择 **GitHub Actions**。

## 说明

- 作业题目来自`巧工平台-Motphys 具身智能机器人仿真实训学习`课程，仅作个人学习用途。
