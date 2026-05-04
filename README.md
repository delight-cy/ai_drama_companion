# AI 追剧搭子 · 庆余年演示

单页 Web 演示：在**视频播放场景**内提供「追剧搭子」与「剧中人物搭子（范闲）」两种对话形态，支持 DeepSeek API 与本地预设回复，并可在侧栏调节追剧搭子的性格、立场强度与说话密度。

![License](https://img.shields.io/badge/license-MIT-blue.svg)

---

## 功能概览

| 能力 | 说明 |
|------|------|
| 视频区 UI | 仿流媒体布局，进度条、音量、全屏等 |
| 右缘侧栏 | 鼠标移近屏幕右边缘约 10px 滑出设定与对话 |
| 追剧搭子 | 性格（高冷/八卦/毒舌/胆小/暖心）、立场三档、对话频率；启用后走 API 时写入动态 system 提示词 |
| 范闲模式 | 固定人设 system 提示词；需「启用范闲」后才可对话 |
| 2D 形象 | `models/girl.png`、`models/fanxian.png` 叠在视频左下角；对话气泡在角色头顶附近 |
| API 密钥 | 侧栏输入保存至本机 localStorage；支持**清空保存**与「清除」按钮 |

---

## 本地运行

1. 克隆本仓库到本地。
2. **将演示视频**放入 `video/qingyvnian.mp4`（见 [`video/README.md`](video/README.md)）。若暂无视频，页面仍可打开，但播放器会报错直至你提供文件或使用自己的路径。
3. 用**本地静态服务**打开（不要直接用 `file://` 打开，以免部分资源受限）：

```bash
# 任选其一，在项目根目录执行
npx --yes serve .
# 或
python -m http.server 8080
```

4. 浏览器访问：`http://127.0.0.1:<端口>/ai_drama_companion.html`
5. 在侧栏「对话」上方填入 DeepSeek API Key（`sk-` 开头），点**保存**。清空输入框后点**保存**或点**清除**可删除本机保存的密钥。

---

## 目录结构

```
ai_drama_companion.html   # 单页入口（样式 + 脚本）
models/
  girl.png
  fanxian.png
video/
  README.md               # 大视频不放仓库时的说明
  （本地放置 qingyvnian.mp4）
```

---

## 部署到 GitHub Pages（可选）

1. 仓库 `Settings` → `Pages` → Source 选分支与根目录或 `/docs`。
2. 若使用 `main` 分支根目录托管，访问形如：`https://<用户名>.github.io/<仓库名>/ai_drama_companion.html`（以你实际仓库名为准）。
3. **大视频**仍建议外链或 Git LFS，避免超出 GitHub 限制。

---

## 产品说明文档

若你在项目根目录放置了参赛用 **产品说明 PDF**，可一并提交；文件名以你本地实际为准。

---

## 开源协议

本项目以 [MIT License](LICENSE) 发布。

---

## 联系与参赛

提交比赛时建议同时提供：**仓库链接**、**在线演示链接**（Pages 或其它静态托管）、**演示录屏链接**。

## 上传到 GitHub

逐步命令见 [`GITHUB_SETUP.md`](GITHUB_SETUP.md)。本机已完成 `git init` 与首次 `commit`，你只需在 GitHub 新建仓库后执行 `git remote add` 与 `git push`。
