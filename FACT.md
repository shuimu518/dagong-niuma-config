# FACT.md - 事实知识文件

## OpenClaw Gateway 后台启动经验（2026-08-14 记录）

### 核心结论
Windows 下 Gateway 必须用 **PowerShell Start-Process -WindowStyle Hidden** 方式启动，才能实现无窗口、持久化、独立于 bash 会话的后台运行。

### 三种方式（按推荐顺序）
1. **Start-Process 隐藏窗口**（推荐）：
   `Start-Process -FilePath "node" -ArgumentList "...dist\\index.js", "gateway", "--port", "18790" -WorkingDirectory "openclaw目录" -WindowStyle Hidden`
   
2. **VBS 脚本**（OpenClaw自带）：
   `wscript.exe openclaw\\.openclaw\\gateway.vbs` — 内部调用 WScript.Shell.Run 0=False 隐藏模式

3. **CMD 批处理**（弹窗口，需配合方式1/2）

### 经验教训
- ❌ `run_in_background=true` 跑 `openclaw gateway` → bash结束进程被杀
- ❌ `start "" cmd /c` → 弹黑色窗口占桌面
- ✅ `Start-Process -WindowStyle Hidden` → 完全无窗口、持久运行

### Gateway 掉线问题解决备忘
- Scheduled Task 已注册但中文路径编码导致启动失败
- 标准修复流程：检查端口 → doctor --fix → Start-Process 启动 → 验证端口
- 每天 8:20 cron 自动检查并重启

## Codex 会话恢复报错修复（2026-08-18 记录）

### 报错现象
`⚠️ agent 失败:codex exited with code 1: Error: thread/resume: thread/resume failed: failed to resolve rollout path \\?\D:\...\Codex\.codex\sessions\2026\08\10\rollout-....jsonl: file does not exist (code -32600)`

### 根因
- **微云同步盘清理了 `.codex\sessions\` 下的历史 rollout 文件**（8月10日~17日整批消失）
- Codex 状态数据库 `state_5.sqlite` 的 `threads` 表仍保留这些线程记录（rollout_path 指向已删除文件）
- Codex 桌面版/app-server 尝试恢复（thread/resume）失效线程 → 报"file does not exist"
- `codex doctor` 诊断：`⚠ threads state DB rows point at missing or unusable rollout files`

### 修复流程
1. **诊断**：`codex doctor --summary` / `--all` / `--json`
2. **定位**：检查 `state_5.sqlite` 的 `threads` 表，逐条核对 `rollout_path` 对应文件是否存在
3. **备份**：`cp state_5.sqlite state_5.sqlite.bak-YYYY-MM-DD-fix`
4. **清理**：删除 rollout 文件缺失的线程行（归档 archived=1 不够，doctor 仍报 stale rows，必须 DELETE）
5. **验证**：`codex doctor` → `✓ threads rollout files and state DB thread inventory agree`

### 关键数据库
- `state_5.sqlite` → `threads` 表（线程状态，rollout_path，thread/resume 的直接依据）
- `thread_history_1.sqlite` → `thread_turns`/`thread_items`（线程历史内容，孤儿记录不影响 doctor，无需清理）
- `session_index.jsonl` → 线程索引（无需改）

### 预防建议
- `.codex` 目录在微云同步盘内，同步清理是根因
- 建议：微云同步排除 `.codex`，或将 CODEX_HOME 指向非同步路径