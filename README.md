# 听本安装包

每次发版提供 `tingben-v<版本>.apk`（软件名+版本号，下载器里一眼分清是哪个项目、哪个版本）。
订阅源 `updates.atom` 的附件就指向它，下载器按此取包。
`app-debug.apk` 是同内容的兼容旧名，只给还没刷新的老直链兜底，不会再新增分不清的条目。
源码与 CI 在 zjh1934/tingben。

## 只留两份 APK（R410）

jsdelivr 对单个 gh 包有 **50MB 总大小上限**。每个安装包约 19MB，攒到 3 个就会撞线，
新版本文件名的直链会 403 `Package size exceeded the configured limit of 50 MB`，
而旧路径还能靠 CDN 缓存返回 206，很容易漏判。因此每次发版 `publish_apk.py` 会
自动删掉历史带版本名的 APK，只保留：

- `tingben-v<当前版本>.apk`（主名，订阅源 enclosure 指向它）
- `app-debug.apk`（同字节兼容旧名，只给没刷新的老直链兜底）

历史版本都在源码仓 [`zjh1934/tingben` 的 Releases](https://github.com/zjh1934/tingben/releases)，
这个仓库只做分发镜像，不留旧包。

## 页面

`docs/index.html`（首页，不收集 Token）与 `docs/relay.html`（提交文字）由源码仓
`tingben/docs/pages/` 同步过来，脚本是 `scripts/sync_pages.py`（R411）。
首页入口 <https://zjh1934.github.io/ting-ben-apk/>，提交页在 `/relay.html`。
