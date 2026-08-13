# steam-monitor-mirror

OpenSteamTool pattern / IPC TOML 镜像仓库。

- **数据来源**: [OpenSteam001/steam-monitor](https://github.com/OpenSteam001/steam-monitor) 的
  `pattern` / `ipc` 分支, 由 [mirror_upstream.py](https://github.com/sowhat123ffff/steam-monitor-mirror)
  全量镜像(复刻作者分支布局, 只换 owner)。
- **自动维护**: `steam_monitor_bot.py` 轮询 Steam CDN 更新, 检测到新 build 后自动生成
  3 个 TOML(pattern×2 + ipc×1) 并通过质量门禁(0 容忍 WARNING)发布到 `pattern` / `ipc` 分支。
- **与上游关系**: 本仓库 = 上游全量镜像 + bot 自生成增量。上游作者停更或被墙时,
  用户仍能从本仓库获取最新 TOML。
- **分支布局**(与 DLL URL 模板同构, 只换 owner):
  - `pattern` 分支: `steamclient/*.toml` + `steamui/*.toml`
  - `ipc` 分支: `steamclient/*.toml`
- **使用方式**: 在 `<Steam>/opensteamtool.toml` 配置:
  ```toml
  [remote]
  url_template = "https://raw.githubusercontent.com/sowhat123ffff/steam-monitor-mirror/{channel}/{component}/{sha256}.toml"
  ```
  (jsDelivr 镜像: `https://cdn.jsdelivr.net/gh/sowhat123ffff/steam-monitor-mirror@{channel}/{component}/{sha256}.toml`)
- **免责声明**: 仅供学习研究使用。
