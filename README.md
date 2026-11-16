# steam-monitor-mirror

OpenSteamTool pattern / IPC TOML 自有镜像仓库。

## 当前来源

- `author-main` 分支精确镜像
  [huanyuejue/steam-monitor](https://github.com/huanyuejue/steam-monitor) 的 `main`
  分支目录布局。
- 当前快照来源提交：`c53bb228a0900122c7182548f50ec227b749f8f7`。
- `AUTHOR_SOURCE.json` 记录来源提交、逐文件 SHA-256 和授权状态。
- 仓库维护者已确认获得作者授权，可复制、修改并自行使用。

## 分支布局

- `author-main`：当前重建版本使用的作者布局：
  - `pattern/steamclient/*.toml`
  - `pattern/steamui/*.toml`
  - `pattern/versions.json`
  - `ipc/steamclient/*.toml`
- `pattern` / `ipc`：历史分支，继续保留，但不与 `author-main` 混用。

## 使用方式

在 `<Steam>/opensteamtool.toml` 配置：

```toml
[remote]
url_template = "https://raw.githubusercontent.com/sowhat123ffff/steam-monitor-mirror/author-main/{channel}/{component}/{sha256}.toml"
```

jsDelivr 地址：

```text
https://cdn.jsdelivr.net/gh/sowhat123ffff/steam-monitor-mirror@author-main/{channel}/{component}/{sha256}.toml
```

当前 `author-main` 是经过逐文件校验的精确快照，尚未配置持续同步工作流；更新时必须重新记录上游提交并完成 TOML 解析和文件哈希验证。
