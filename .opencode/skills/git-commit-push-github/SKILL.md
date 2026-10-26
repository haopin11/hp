---
name: git-commit-push-github
description: Use when the user asks to commit the project and push it to GitHub (default: https://github.com/haopin11/hp). Handles staging all changes, writing a concise commit message, setting the GitHub remote, and pushing.
---

# Git Commit & Push (GitHub)

提交并推送当前项目到 GitHub 远程仓库（默认：https://github.com/haopin11/hp）。

## 步骤

1. 检查仓库状态与远程配置：

   ```powershell
   git status
   git remote -v
   git branch
   git log --oneline -5
   ```

2. 配置 GitHub 远程仓库（若不存在或需要替换）：

   ```powershell
   git remote add origin https://github.com/haopin11/hp.git
   ```

   若已存在指向其他地址的 `origin`，先移除再添加：

   ```powershell
   git remote remove origin
   git remote add origin https://github.com/haopin11/hp.git
   ```

3. 暂存全部改动并提交：

   ```powershell
   git add -A
   git commit -m "<简明描述，遵循仓库提交风格>"
   ```

4. 推送到远程：

   ```powershell
   git push -u origin master
   ```

   若分支非 `master`（如 `main`），以 `git branch` 实际结果为准。

## 注意事项

- 仅提交与当前改动相关的文件，不要提交密钥、凭证或无关的大文件。
- 提交信息要简洁、用仓库既有语言与风格。
- 推送前再次 `git status` 确认暂存内容符合预期。
- 若推送被拒绝（远程有更新），先 `git pull --rebase origin master` 再推送。
