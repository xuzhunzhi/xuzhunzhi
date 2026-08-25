# 流浪猫的避难所 (Stray Cat's Sanctuary)

一个部署在 GitHub Pages 的单文件个人网站，无需构建。内容与数据保存在浏览器本地存储(localStorage)，
右上角 Logo 连点 5 次或页脚「···」可进入后台管理。

## 本地预览

直接用浏览器打开 `index.html` 即可，或起一个本地服务（推荐，登录校验依赖 `crypto.subtle`，需要 HTTPS 或 localhost）：

```bash
# 任选其一
python -m http.server 8000
# 或
npx serve .
```

## 部署到 GitHub Pages

1. 在 GitHub 新建一个**公开**仓库，例如 `straycat-sanctuary`。
2. 把本目录内容推送上去：
   ```bash
   git add .
   git commit -m "publish straycat sanctuary"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```
3. 仓库 `Settings → Pages → Source` 选择 `Deploy from a branch`，分支 `main`、目录 `/ (root)` → `Save`。
4. 稍等约 1 分钟，访问 `https://<你的用户名>.github.io/<仓库名>/`。

> 若仓库名是 `<用户名>.github.io`，站点地址则为 `https://<你的用户名>.github.io/`。

## 说明

- **后台登录**：页脚「···」或连点 Logo 5 次。密码校验为加盐 PBKDF2-SHA256 哈希（明文不写入代码）。
- **背景音乐**：在同目录放一个 `music.mp3`，或到后台「设置」粘贴 MP3 直链。
- **GitHub 发布**：在后台「设置」填写自己的 GitHub Token + 仓库后，发布内容会自动通过 GitHub API 提交到仓库。
  注意：Token 仅保存在浏览器会话中，请勿把 Token 提交到任何公开位置。
- `流浪猫的避难所.html` 为本地工作备份，部署以 `index.html` 为准。
