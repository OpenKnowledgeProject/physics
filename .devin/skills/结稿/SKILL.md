---
name: 结稿
description: 定稿收尾——评审记录归档、状态卡、tag、合回 main 推送、根 README 书架更新（G5）
argument-hint: "<书名>"
allowed-tools:
  - read
  - edit
  - grep
  - glob
  - exec
---

前提：审读 P0/P1 清零、字数全达标、作者认可。按序执行：

1. 评审记录已写入 `章节设计.md` 末尾 `## 评审记录`；章节状态表全部"定稿"。
2. `novel/<书名>/README.md` 状态卡：状态=定稿 v1.0，进度=全章数与实测总字数。
3. `novel/<书名>/正文/README.md` 若不存在：比照已成书（如 `novel/离岸/正文/README.md`）新建——书名、一句话、体量/状态、简介、全章目录表。
4. 提交 `<书名>: 定稿 v1.0`。
5. `git tag <书名>-v1.0`。
6. 合回 main：在 main checkout 执行 `git merge <书名>-初稿`（通常 fast-forward）→ `git push origin main` → `git push origin <书名>-v1.0`。
7. **根 README（易漏，必做）**：书架表加/更新该书行——一句话、字数、定稿、序章链接（先 `ls` 核对序章实际文件名）；目录链接行追加该书目录链接。
8. `notes/ideas.md` 该书行状态更新。提交并推送。
