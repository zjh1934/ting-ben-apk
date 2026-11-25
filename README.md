# 听本安装包 · 与 Pages 页面

每次发版提供 `tingben-v<版本>.apk`（软件名+版本号，下载器里一眼分清项目与版本）；
`app-debug.apk` 是同内容的兼容旧名，只给没刷新的老直链兜底，订阅源不再推它。

订阅源：`updates.atom`（带 enclosure）。

GitHub Pages 页面：
- `index.html` 项目入口（下载 / 订阅 / 指南 / 中继入口，不收集 Token）
- `relay.html` 跨网中继调用页（提交文字、轮询、取回 M4A）

两页的唯一真值在源码仓 `docs/pages/`，R392 之前它们内容完全相同，已分开。
源码与 CI 在 zjh1934/tingben。
