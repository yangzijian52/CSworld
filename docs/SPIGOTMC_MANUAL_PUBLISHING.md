# CSworld SpigotMC 手动发布指南

本文档供项目维护者在 SpigotMC 手动创建资源时使用。Codex 不代替维护者登录或提交 SpigotMC 表单。

## 发布信息

| 项目 | 内容 |
| --- | --- |
| Resource type | **Free** |
| Price | **Free / USD 0.00** |
| License | **MIT License** |
| Version | `1.2.2` |
| Upload file | `target/CSworld-1.2.2.jar` |
| File size | `11,128 bytes` |
| SHA-256 | `634E19CB803B97E1ED5A4805D1BCE4FDF9EAEBA285B049E73B446478AA0E8605` |
| GitHub release | https://github.com/yangzijian52/CSworld/releases/tag/1.2.2 |
| Source code | https://github.com/yangzijian52/CSworld |
| Resource page BBCode | `docs/SPIGOTMC-RESOURCE.md` |
| Full documentation BBCode | `docs/SPIGOTMC-RESOURCE-BBCODE.txt` |

## 免费资源选择理由

CSworld 体量较小、源码公开、采用 MIT License、不依赖专有在线服务，核心功能适合透明的社区分发。因此建议在 SpigotMC 选择 **Free Resource**，价格为 `0.00 USD`，不应填写为付费资源。

## Suggested SpigotMC Fields

| Field | Suggested value |
| --- | --- |
| Resource name | `CSworld - Cross-Server Teleport with Vault` |
| Tag line | `Free, one-time unlock and per-use cross-server teleport payments` |
| Version | `1.2.2` |
| Category | `Teleportation` if available; otherwise the closest `Tools` or `Miscellaneous` category |
| Native server software | `Paper` |
| Tested/Supported version | `Paper 26.2` only |
| Java requirement | `Java 25+` |
| Required dependency | `Vault` |
| Optional/external dependency | A Vault-compatible economy plugin for paid modes; a proxy network for transfers |
| Source URL | `https://github.com/yangzijian52/CSworld` |
| Support URL | `https://github.com/yangzijian52/CSworld/issues` |
| License | `MIT` |
| Download method | Upload `CSworld-1.2.2.jar` directly |

不要为了通过版本选择器而勾选未经验证的 Spigot 或旧版 Minecraft 兼容性。如果 SpigotMC 暂未提供 `26.2` 选项，在介绍页正文中保留准确的 `Paper 26.2 only` 声明，并选择界面允许的最接近项。

## Important Warnings

- The SpigotMC resource page, documentation and support channel are English-only. Chinese-language support is not provided on SpigotMC.
- 插件本体的玩家提示、管理反馈、控制台信息和默认配置注释当前为中文。
- 仅声明支持 Paper 26.2；未测试且不声明支持 Spigot 服务端。
- Vault 在 `plugin.yml` 中是硬依赖，即使启用免费模式也必须安装。
- 付费模式还需要 Vault 兼容经济插件。
- 必须运行在正确配置的代理网络中；单独 Paper 后端不能完成跨服传送。
- 插件不能确认代理传送结果。扣款成功后若代理连接失败，不会自动退款或回滚解锁。
- `current-server` 由管理员手动填写，插件不会自动检测当前后端。
- 当前项目没有自动化测试源码，本版本也未完成 Paper 26.2 服内实测；只能写“构建成功”，不能写“服务器实测通过”。
- 不要上传 `target` 目录、源码压缩包、`.idea`、`*.iml` 或临时文件，只上传最终 JAR。

## Manual Publish Steps

1. 打开 GitHub Release `1.2.2`，确认 `CSworld-1.2.2.jar` 资产、SHA-256 和构建说明存在。
2. 登录 SpigotMC，进入资源发布页面并选择 **Free Resource**。
3. 填写上表中的资源名称、版本、依赖、许可证和支持链接。
4. 将 `docs/SPIGOTMC-RESOURCE.md` 的完整内容原样粘贴到资源介绍页；它已经是 BBCode，不要转换成 Markdown。
5. 将 `docs/SPIGOTMC-RESOURCE-BBCODE.txt` 作为完整说明粘贴到资源说明的后续部分或 SpigotMC 提供的文档区域。
6. 上传 `target/CSworld-1.2.2.jar`，不要上传整个 `target` 文件夹。
7. 在预览页检查 BBCode 的居中、标题、列表、代码块和链接是否正常显示。
8. 再次确认页面明确显示 Paper 26.2、Java 25、Vault、代理网络、中文插件界面和未服内实测等限制。
9. 发布前核对下载文件的 SHA-256 与 GitHub Release 完全一致。
10. 手动提交资源，等待 SpigotMC 审核；审核反馈需要由维护者本人处理。

## 发布后检查

- 下载按钮应指向 `CSworld-1.2.2.jar`。
- 页面版本应为 `1.2.2`。
- Resource type 应为 Free，价格应为 0。
- Source、Release、Issues 和 License 链接应可访问。
- 英文 Language notice 必须保留，且不得承诺中文 SpigotMC 支持。
