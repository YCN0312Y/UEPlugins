<div align="center">

# UE5 Multiplayer Plugin

**基于 OnlineSubsystemSteam 的虚幻引擎多人联机插件**

[![Unreal Engine](https://img.shields.io/badge/Unreal%20Engine-5-black?style=flat-square&logo=unrealengine)](https://www.unrealengine.com/)
[![Language](https://img.shields.io/badge/Language-C%2B%2B%20%7C%20Blueprint-blue?style=flat-square)](https://www.unrealengine.com/)
[![Network](https://img.shields.io/badge/Network-Steam%20Online%20Subsystem-1b2838?style=flat-square&logo=steam)](https://store.steampowered.com/)

</div>

---

## 📖 简介

本插件依托虚幻引擎官方 `OnlineSubsystemSteam` 构建，封装了多人联机核心框架，支持 Steam 同区域匹配联机。可作为独立模块集成到任意 UE5 项目中，快速搭建多人游戏基础设施。

---

## ✨ 功能特性

- **Steam 匹配联机** — 基于 `OnlineSubsystemSteam`，支持同区域房间创建与搜索
- **服务器权威架构** — 遵循服务器权威原则，使用 UE Replication + RPC 保证多端状态一致
- **大厅系统** — 涵盖玩家加入/退出、房主管理、赛制配置等完整大厅流程
- **会话管理** — 封装 CreateSession / FindSession / JoinSession / DestroySession 全流程

---

## 🛠️ 技术栈

| 类别 | 技术 |
|------|------|
| 引擎 | Unreal Engine 5 |
| 开发语言 | C++ / 蓝图（Blueprint） |
| 联机插件 | OnlineSubsystemSteam |
| 网络框架 | UE Replication + RPC |

---

## 🚀 使用方式

1. 将插件文件夹复制到项目的 `Plugins/` 目录下
2. 在 `DefaultEngine.ini` 中启用 OnlineSubsystemSteam：
```ini
[OnlineSubsystem]
DefaultPlatformService=Steam

[OnlineSubsystemSteam]
bEnabled=true
SteamDevAppId=480
```
3. 在项目 `.uproject` 中启用插件：
```json
{
  "Name": "MultiplayerPlugin",
  "Enabled": true
}
```
4. 重新生成项目文件并编译
5. 在 `BP_LoginPlayerController` 的 `HallPath` 中填入进入房间后的地图路径，即可使用

> ⚠️ **注意：** 房间列表中的 Ping 值为随机数，非真实延迟，暂未修复，介意请谨慎使用。

---

## 📬 联系方式

如有问题欢迎提交 [Issue](../../issues)
