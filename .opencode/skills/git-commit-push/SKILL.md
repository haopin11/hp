---
name: git-commit-push
description: Use when the user asks to commit the project, submit/提交 the code, or push the current project to a remote (Gitee/GitHub/GitLab). Handles staging all changes, writing a concise commit message, adding the remote, and pushing.
---

# Git Commit & Push

提交并推送当前项目到远程仓库（默认 Gitee: https://gitee.com/hao-pin/hp-632-gaoji.git）。

## 步骤

1. 检查仓库状态与远程配置：

   ```powershell
   git status
   git remote -v
   git log --oneline -5
   ```

2. 若 `git remote -v` 为空，先添加远程：

   ```powershell
   git remote add origin https://gitee.com/hao-pin/hp-632-gaoji.git
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
