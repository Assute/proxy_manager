# Proxy Manager

![Bash Version](https://img.shields.io/badge/Bash-≥4.0-green.svg)
![License](https://img.shields.io/github/license/Assute/proxy_manager.svg)
![Release](https://img.shields.io/github/v/release/Assute/proxy_manager.svg)

## 简介

Proxy Manager 是一个功能强大的 BASH 脚本，用于管理和自动切换代理服务器。它提供了直观的菜单界面，支持多种代理类型配置、定时自动切换、代理测试及 IP 查询等功能，适用于需要频繁更换代理的场景。

## 🌟 主要功能

- **多代理管理**：支持 HTTP/HTTPS/SOCKS4/SOCKS5 多种代理类型
- **认证支持**：可添加带用户名/密码认证的代理服务器
- **自动切换**：基于日期自动循环切换代理（每天使用不同代理）
- **定时任务**：自定义每日自动切换时间（格式：HH:MM:SS）
- **连接测试**：测试单个或批量测试所有代理的连接有效性
- **IP 查询**：实时查询当前公网 IP 信息及地理位置
- **日志记录**：所有操作自动记录到日志文件，便于追踪和排查

## 🚀 快速开始

### 安装
# 下载脚本并赋予执行权限
```shell script
wget -N https://github.com/Assute/Proxy_Manager/blob/main/proxy_manager.sh && chmod +x proxy_manager.sh
```
### 运行
```shell script
./proxy_manager.sh
```

## 📋 菜单操作
运行脚本后，将看到以下菜单界面，使用数字键选择相应功能：

1. 添加代理
2. 删除代理
3. 取消代理
4. 手动设置代理
5. 列出所有代理
6. 检测可用代理
7. 检测当前代理IP
8. 设置每日自动切换代理定时任务
9. 移除每日自动切换代理定时任务
0. 退出
-------------------------------------
## ⚙️ 配置文件

脚本自动创建以下配置文件，位于 `~/.proxy_manager/` 目录：

| 文件名称          | 作用                                        |
|-------------------|---------------------------------------------|
| `proxies.conf`    | 存储代理服务器列表                          |
| `state.conf`      | 记录当前使用的代理索引                      |
| `cron_time.conf`  | 存储定时任务的时间设置                      |
| `proxy_switch.log`| 记录所有操作的日志文件                      |

## 🕒 定时任务设置

使用菜单选项 `8` 设置每日自动切换时间，支持格式如 `06:00:00`：
请设置每日自动切换代理的时间（24小时制，格式为HH:MM:SS，例如06:00:00）
输入时间: 06:00:00
系统会自动验证格式并创建对应的 cron 任务，确保每天指定时间自动切换代理。

## 📖 详细使用指南

### 添加新代理

选择菜单选项 `1`，按以下步骤操作：

1. 选择代理类型（HTTP/HTTPS/SOCKS4/SOCKS5）
2. 输入代理服务器 IP 地址
3. 输入代理服务器端口
4. 选择是否需要用户名/密码认证（如果需要，输入用户名和密码）

### 删除代理

选择菜单选项 `2`，从列表中选择要删除的代理索引。

### 取消代理

选择菜单选项 `3`，取消当前所有代理设置。

### 手动切换代理

选择菜单选项 `4`，从可用代理列表中选择要使用的代理索引。

### 列出所有代理

选择菜单选项 `5`，查看当前配置的所有代理服务器列表。

### 检测可用代理

选择菜单选项 `6`，脚本会依次测试所有配置的代理服务器，并显示连接结果。

### 检测当前代理IP

选择菜单选项 `7`，脚本会查询并显示当前公网 IP 信息及地理位置。

### 设置每日自动切换代理定时任务

选择菜单选项 `8`，按照提示输入时间（格式：HH:MM:SS），设置每日自动切换代理的时间。

### 移除每日自动切换代理定时任务

选择菜单选项 `9`，移除已设置的每日自动切换代理定时任务。

## 🛠️ 依赖项

- 需要安装 `curl` 工具（用于测试连接和查询 IP）
- 定时任务依赖系统 cron 服务（确保已安装并运行）

## ⚠️ 注意事项

- 首次运行时，脚本会自动创建配置目录和文件
- 代理配置文件包含敏感信息（如代理服务器地址和认证信息），请注意权限保护
- 如需卸载，只需删除脚本文件和配置目录 `~/.proxy_manager`

## 📄 许可证

本项目采用 [MIT 许可证](LICENSE)，允许自由使用、修改和分发。

## 🤝 贡献

欢迎提交 Issues 或 Pull Requests 来改进本项目！    
