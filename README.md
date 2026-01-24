# CSworld - 跨服传送插件

![Minecraft](https://img.shields.io/badge/Minecraft-1.21+-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)

一个基于 Spigot/Paper API 制作的 Minecraft 跨服传送插件，支持经济扣费、灵活的付费模式（单次解锁/每次付费）、多服务器配置和热重载功能。

## 功能特性
### 1. 跨服传送
- 通过 BungeeCord 通道将玩家传送到指定子服务器
### 2. 多服务器配置
- 支持在 `config.yml` 中配置多个目标服务器及独立价格
### 3. 灵活的经济系统集成
- **单次付费模式**：玩家首次传送支付费用，之后永久免费（解锁机制）
- **多次付费模式**：玩家每次传送都需要支付指定费用
- 需安装 Vault 及兼容的经济插件
### 4. 同服检测
- 自动阻止传送到当前所在服务器
- 提示 "您已在目标服务器！"
### 5. 免费模式
- 配置 `free-mode: true` 或未安装经济插件时，所有传送免费
### 6. 动态倒计时
- 传送前 3 秒倒计时提示
### 7. 数据持久化
- 记录玩家付费状态到 `data.yml`（仅在单次付费模式下生效）
- 重启服务器后仍有效
### 8. 热重载配置
- 通过 `/cs reload` 实时重载配置
- 无需重启服务器
### 9. 智能扣费逻辑
- 余额不足时取消传送并提示

## 适用场景
- **多世界生存服**  
  主城/空岛/地牢等场景切换（可设为单次解锁）
- **交通/传送站**  
  每次使用都需要购票（可设为多次付费）
- **测试服快速切换环境**  
  使用免费模式

## 安装指南

1. 将插件放入子服务器（每个子服务器都要有） `plugins/` 文件夹
2. 启动服务器生成配置文件
3. 修改 `plugins/CSworld/config.yml`
4. 重启服务器（首次安装需要）

## 配置文件

```yaml
# config.yml 示例
free-mode: false        # 设置为true则为全局免费模式
one-time-payment: true  # 是否开启单次付费（true=一次付费永久解锁，false=每次传送都需要付费）
current-server: "lobby" # 填写当前服务器名称（用于同服检测）

servers:
  lobby:         # 目标服务器名称
    cost: 0      # 传送价格
  survival:
    cost: 50
  skyblock:
    cost: 100
```

## 命令用法
| 命令        | 描述                          | 权限 |
|------------|------------------------------|--------|
| /cs   | 显示可用服务器列表       |无|
| /cs <服务器名>	   | 传送到指定服务器  |   无         |
| /cs reload     | 重载插件配置|csword.reload |

## 权限节点
|权限节点|	描述	|默认|
|------------|------------------------------|--------|
|csword.reload	|允许重载插件配置|	OP|

# 开发者指南
## 编译要求
```yaml
JDK 21+
Maven 3.8+
PaperMC API
```
## 构建步骤
```yaml
mvn clean package
//编译后的插件将生成在 target/CSword-版本号.jar
```
## 常见问题
### Q: 为什么传送不扣钱？
A: 1) 检查是否启用免费模式 free-mode 2) 检查是否已解锁该服务器（若开启了单次付费） 3) 确保已安装 Vault 和经济插件
### Q: 如何设置每次传送都收费？
A: 在 config.yml 中将 one-time-payment 设置为 false
### Q: 如何设置当前服务器名称？
A: 在 config.yml 中修改 current-server 值
### Q: 重载命令无效？
A: 需要 csword.reload 权限，OP 默认拥有

## 更新日志
### v1.1
1.插件名称更改为 CSworld <br>
2.新增 one-time-payment 配置项，支持切换“单次解锁”或“每次收费”模式<br>
3.优化扣费逻辑，关闭单次付费模式时不再保存玩家数据<br>
4.对版本1.21.11支持
### v1.0
1.添加热重载功能<br>
2.优化经济系统检测逻辑<br>
3.修复同服务器传送问题

## 开源协议
本项目采用 MIT License
