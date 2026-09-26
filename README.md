# CSworld

一个用于 Minecraft 服务端的跨服传送插件，支持通过 BungeeCord 通道传送到其他子服，并集成 Vault 经济系统实现免费、单次解锁和每次付费三种模式。

## 当前版本

- 插件版本：`1.2.3`
- Paper API：`26.3.build.41-alpha`
- Java 要求：`25+`

## 主要功能

- `/cs` 查看可用服务器列表
- 支持传送到配置的目标服务器
- 支持中文显示名和英文服务器名两种输入方式
- 支持免费模式
- 支持单次解锁后永久免费
- 支持每次传送单独收费
- 支持 `/cs reload` 热重载配置

## 运行要求

- Paper `26.3.x`
- Java `25+`
- Vault
- 任意 Vault 兼容经济插件
- 代理层支持 BungeeCord 插件消息通道

## 命令与权限

- `/cs`：显示服务器列表
- `/cs <服务器名>`：传送到指定服务器
- `/cs reload`：重载配置
- 权限节点：`csword.reload`

## 当前状态

- 已升级到官方当前最新可用 `paper-api 26.3.build.41-alpha`
- 已切换到 `Java 25`
- 已在 Paper 26.3 测试镜像完成三个后端的启动、重启、四服并联和正常关闭回归；实际收费与跨服传送流程仍需真人验收

## 构建

```bash
mvn clean package
```

## 发布资料

- [SpigotMC 正式资源页](https://www.spigotmc.org/resources/csworld.137017/)
- [更新日志](CHANGELOG.md)
- [MIT License](LICENSE)
