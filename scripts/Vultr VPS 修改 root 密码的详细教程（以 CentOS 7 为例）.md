# Vultr VPS 修改 root 密码的详细教程（以 CentOS 7 为例）

很多用户在使用 Vultr VPS 时可能会遇到需要修改 root 密码的情况，特别是在快照恢复后无法正常登录时。本文将详细介绍在 CentOS 7 系统上修改 root 密码的完整步骤。

## 准备工作
- 确保您已登录 Vultr 管理后台
- 准备好需要修改密码的 VPS 实例

👉 [【点击查看】2025年最新 Vultr 优惠码及特价云服务器方案汇总](https://bit.ly/VuLtr)

## 详细操作步骤

### 1. 访问 Vultr Console
1. 登录 Vultr 管理后台
2. 找到需要修改密码的 VPS 实例
3. 点击 "Console" 按钮打开在线控制台
4. 点击右上角的 "Send CtrlAltDel" 按钮
5. 按 ESC 键启动 GRUB boot prompt

### 2. 启动 GRUB boot prompt
1. 在控制台界面，再次点击 "Send CtrlAltDel"
2. 快速按 ESC 键进入 GRUB 引导界面

### 3. 修改启动参数
1. 按 `e` 键编辑第一启动项
2. 使用方向键向下移动光标
3. 找到以 "linux16" 开头的行
4. 将 `ro` 改为 `rw init=/sysroot/bin/sh`
5. 按 Ctrl + X 或 F10 启动单用户模式

### 4. 修改 root 密码
1. 输入命令：`chroot /sysroot` 进入系统
2. 输入命令：`passwd` 开始修改密码
3. 按照提示输入新密码并确认
4. 密码修改成功后，输入 `reboot -f` 重启系统

## 注意事项
- 修改密码时请确保输入的新密码足够安全
- 建议定期更换 VPS 密码以提高安全性
- 修改密码后请妥善保管新密码

通过以上步骤，您可以轻松完成 Vultr VPS 的 root 密码修改。如果在操作过程中遇到任何问题，可以参考 Vultr 官方文档或寻求技术支持。