# 上传到 GitHub 操作指南

在**本文件夹** `ai_drama_companion` 内打开终端（不要在上一级目录执行 `git init`，避免误把整个用户目录纳入版本库）。

## 1. 首次初始化并提交

```powershell
cd $HOME\Desktop\ai_drama_companion
git init
git branch -M main
git add .
git status
git commit -m "chore: initial demo for AI drama companion"
```

## 2. 在 GitHub 网页新建仓库

1. 登录 [GitHub](https://github.com)，右上角 **New repository**。
2. 仓库名例如：`ai-drama-companion`（可自定）。
3. **不要**勾选 “Add a README”（本仓库已有 README）。
4. 创建后，复制页面上的 **HTTPS** 地址，例如：  
   `https://github.com/<你的用户名>/ai-drama-companion.git`

## 3. 绑定远程并推送

```powershell
git remote add origin https://github.com/<你的用户名>/ai-drama-companion.git
git push -u origin main
```

浏览器若提示登录，按 GitHub 要求完成身份验证（Personal Access Token 或 Git Credential Manager）。

## 4. 使用 GitHub CLI（可选，一条命令建库并推送）

若已安装 [GitHub CLI](https://cli.github.com/) 且已 `gh auth login`：

```powershell
cd $HOME\Desktop\ai_drama_companion
gh repo create ai-drama-companion --public --source=. --remote=origin --push
```

将 `ai-drama-companion` 换成你想要的仓库名。

## 5. 关于大视频

本仓库 `.gitignore` 已忽略 `video/*.mp4`。推送后评委克隆仓库需**自行放入** `video/qingyvnian.mp4`，或你在 README / 比赛表单里提供**在线演示与录屏链接**。
