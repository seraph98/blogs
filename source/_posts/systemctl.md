---
title: systemctl
date: 2024-11-03 18:06:09
categories:
- linux
- 常见命令解释
tags:
- linux
---

# What

systemctl 如果硬要拆分解释，可以这么理解

- system 表示它用于系统级别的管理。

- ctl 是 “control”的缩写，表示控制的意思。



是 systemd 的命令行接口工具，用于控制 systemd 系统和服务管理器。在这里，“systemd” 是一个系统守护进程的名称，负责在Linux系统中初始化用户空间并管理系统进程。systemctl 命令用于与这个守护进程交互，执行如启动服务、停止服务、获取服务状态等操作。

# Why

需要结合 `systemd` 来理解， `systemd` 是系统和服务管理器， systemctl 是用来管理这些服务的工具，为 `systemd` 提供支持。 处于以下原因， linxu 引入了 sysmted 和 systemctl

1. **并发启动服务**：systemd 通过使用 systemctl 能够并发启动服务，这可以大大加快系统启动时间。
2. **依赖性管理**：systemd 提供了对服务之间依赖关系更好的管理。systemctl 使管理这些依赖变得简单，允许系统只启动在特定时间真正需要的服务。
3. **按需启动服务**：systemd 可以按需启动服务，这意味着仅当请求服务时，服务才会被启动。这通过使用 socket 激活等技术实现，而 systemctl 提供了管理这一行为的接口。
4. **日志管理**：systemd 引入了 journald，一个新的日志系统，systemctl 可以用来管理和查询 systemd 的日志信息，提供了对系统日志的更好访问。
5. **服务管理**：与旧的初始化系统相比，systemd 使用 unit files 替代脚本来启动和管理服务，systemctl 提供了一个简单的方式来启动、停止、重启、显示状态和管理这些 unit files。
6. **配置管理**：systemd 允许通过 systemctl 重新加载其配置，不仅仅是单个服务的配置，而且是整个系统的配置，而不需要重启。
7. **一致的接口**：systemctl 提供了一个一致的命令行接口来控制不只是系统服务，还有定时器、设备、挂载点等。这种一致性简化了系统管理。

# How

1. **启动服务**：启动（激活）一个服务。

```
systemctl start 服务名.service
```

2. **停止服务**：停止（去激活）一个正在运行的服务。

```
systemctl stop 服务名.service
```

3. **重启服务**：重启一个服务。如果服务正在运行，这将会停止后再启动它；如果服务未运行，则会启动服务。

```
systemctl restart 服务名.service
```

4. **查看服务状态**：检查一个服务的运行状态。

```
systemctl status 服务名.service
```

5. **启用服务**：启用一个服务，使之在系统启动时自动启动。

```
systemctl enable 服务名.service
```

6. **禁用服务**：禁用一个服务，使之在系统启动时不自动启动。

```
systemctl disable 服务名.service
```

7. **重新加载服务配置**：无需停止服务就能重新加载配置文件。

```
systemctl reload 服务名.service
```

8. **查看所有服务状态**：列出并查看所有服务的当前状态。

```
systemctl list-units --type=service
```
