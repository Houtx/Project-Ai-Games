# 🚀 GitHub 发布指南

本文档将指导您如何将 Project-Ai-Games 发布到 GitHub。

## 📋 发布前检查清单

- [x] README.md 已更新
- [x] LICENSE 文件已创建
- [x] .gitignore 已配置
- [x] 所有游戏都有完整的文档
- [x] 截图已添加到各游戏的 screenshots 文件夹

## 🔧 初始化 Git 仓库

如果还没有初始化 Git,执行以下命令:

```bash
# 进入项目目录
cd E:\soft\IdeWorkSpace\Project-Ai-Games

# 初始化 Git 仓库
git init

# 添加所有文件
git add .

# 创建首次提交
git commit -m "🎮 Initial commit: AI Snake game with collision risk assessment"
```

## 📤 推送到 GitHub

### 1. 在 GitHub 上创建新仓库

1. 访问 https://github.com/new
2. 仓库名称: `Project-Ai-Games`
3. 描述: `A collection of AI-powered web games built with vanilla JavaScript`
4. 选择 Public (公开)
5. **不要**勾选 "Add a README file" (我们已经有了)
6. **不要**勾选 "Add .gitignore" (我们已经有了)
7. **不要**选择 License (我们已经有了)
8. 点击 "Create repository"

### 2. 关联远程仓库并推送

```bash
# 添加远程仓库 (替换 your-username 为你的 GitHub 用户名)
git remote add origin https://github.com/your-username/Project-Ai-Games.git

# 推送到 GitHub
git branch -M main
git push -u origin main
```

## 🌐 启用 GitHub Pages

### 方法 1: 通过仓库设置

1. 进入你的 GitHub 仓库页面
2. 点击 "Settings" (设置)
3. 在左侧菜单找到 "Pages"
4. 在 "Source" 下选择 `main` 分支
5. 点击 "Save"
6. 等待几分钟,访问 `https://your-username.github.io/Project-Ai-Games/`

### 方法 2: 使用 GitHub Actions (自动部署)

创建 `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./
```

## 🎮 游戏访问链接

发布后,游戏可以通过以下链接访问:

- **AI Snake**: `https://your-username.github.io/Project-Ai-Games/auto-snake/`
- **未来游戏**: `https://your-username.github.io/Project-Ai-Games/game-name/`

## 📝 后续更新流程

### 添加新游戏

```bash
# 1. 创建新游戏文件夹
mkdir new-game
cd new-game

# 2. 创建游戏文件
# - index.html
# - README.md
# - screenshots/

# 3. 更新项目根目录的 README.md
# 在游戏列表中添加新游戏的介绍和链接

# 4. 提交更改
git add .
git commit -m "✨ Add new game: [游戏名称]"
git push
```

### 更新现有游戏

```bash
# 1. 修改游戏文件
# 2. 更新游戏的 README.md
# 3. 如有需要,更新截图

# 4. 提交更改
git add .
git commit -m "🔧 Update [游戏名称]: [更新内容]"
git push
```

## 🏷️ 版本标签

为重要更新创建版本标签:

```bash
# 创建标签
git tag -a v1.0.0 -m "Release version 1.0.0: AI Snake with risk assessment"

# 推送标签
git push origin v1.0.0

# 推送所有标签
git push --tags
```

## 📊 提交信息规范

使用 emoji 和清晰的描述:

- 🎮 `:video_game:` - 新增游戏
- ✨ `:sparkles:` - 新功能
- 🐛 `:bug:` - 修复 bug
- 📝 `:memo:` - 更新文档
- 🎨 `:art:` - 改进 UI/样式
- ⚡ `:zap:` - 性能优化
- 🔧 `:wrench:` - 配置修改
- 🚀 `:rocket:` - 部署相关

示例:
```bash
git commit -m "✨ Add collision risk assessment feature to AI Snake"
git commit -m "🐛 Fix tail collision detection bug"
git commit -m "📝 Update README with new screenshots"
```

## 🌟 推广建议

1. **添加 Topics**: 在 GitHub 仓库页面添加相关标签
   - `javascript`
   - `html5-game`
   - `ai-algorithms`
   - `bfs-algorithm`
   - `game-development`
   - `web-game`
   - `canvas`

2. **创建 Release**: 为每个重要版本创建 GitHub Release

3. **分享到社区**:
   - Reddit: r/javascript, r/gamedev
   - Twitter: 使用 #JavaScript #GameDev 标签
   - Dev.to: 写技术文章介绍项目

4. **添加徽章**: README 中的徽章已配置好

## 🔗 有用的链接

- [GitHub Pages 文档](https://docs.github.com/en/pages)
- [Git 基础教程](https://git-scm.com/book/zh/v2)
- [Markdown 语法指南](https://www.markdownguide.org/)

## ❓ 常见问题

### Q: GitHub Pages 没有显示最新内容?
A: 清除浏览器缓存,或等待几分钟让 GitHub Pages 重新构建。

### Q: 图片无法显示?
A: 检查图片路径是否正确,确保使用相对路径。

### Q: 如何删除错误的提交?
A: 使用 `git reset --soft HEAD~1` 撤销最后一次提交。

---

**准备好了吗? 让我们把你的 AI 游戏分享给全世界! 🚀**
