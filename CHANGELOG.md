# 更新日志

本文档记录 CSworld 的主要版本变化。

## [1.2.2] - 2026-07-11

### 兼容性

- 将 Paper API 升级至 `26.2.build.56-alpha`。
- 保持 Java 编译目标为 Java 25。
- 插件版本升级至 `1.2.2`。

### 发布资料 - 2026-07-12

- 新增英文 SpigotMC 资源介绍页和完整 BBCode 文档。
- 新增 SpigotMC 手动发布指南。
- README 增加发布资料入口。
- 确认项目继续使用 MIT License。
- 本次不改变插件源码、功能、配置格式或数据格式。
- 重新构建的 JAR 内部文件与原 `1.2.2` Release 资产逐项一致；仅 JAR 归档时间戳使整体 SHA-256 变化，因此刷新同版本 Release 资产而不涨版本。

### 验证

- Maven `clean package` 构建成功。
- 项目没有测试源码，因此没有可运行的自动化测试。
- 未进行 Paper 26.2 服务器内实测。
- 发布 JAR：`CSworld-1.2.2.jar`，11,128 字节，SHA-256 `634E19CB803B97E1ED5A4805D1BCE4FDF9EAEBA285B049E73B446478AA0E8605`。

## [1.2] - 2026-02-13

- 新增服务器中文显示名称。
- 支持使用中文显示名称或英文代理服务器名称传送。
- 优化服务器列表与传送提示。

## [1.1] - 2026-01-24

- 插件名称调整为 CSworld。
- 新增一次付费永久解锁与每次传送收费模式。
- 修正关闭一次付费模式时的数据保存逻辑。

## [1.0] - 2025-06-25

- 首次发布。
- 提供 BungeeCord 跨服传送、Vault 经济扣费、同服检测和配置热重载。

[1.2.2]: https://github.com/yangzijian52/CSworld/releases/tag/1.2.2
[1.2]: https://github.com/yangzijian52/CSworld/releases/tag/1.2
[1.1]: https://github.com/yangzijian52/CSworld/releases/tag/1.1
[1.0]: https://github.com/yangzijian52/CSworld/releases/tag/1.0
