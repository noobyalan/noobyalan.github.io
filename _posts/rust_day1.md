---
layout: post
title: rust学习day1
categories: [开源操作系统, rust]
description: 开源操作系统第一阶段的rust学习记录
keywords: rust, beginner
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---

## WSL项目Rust Analyzer 无法在VScode运行：

VS Code加载Rust Analyzer时需要先运行`rustlings lsp`，是因为Rustlings的项目结构与普通的Cargo项目不同。`rustlings lsp`命令为Rust Analyzer提供了正确的配置，使其能够识别和分析Rustlings项目，从而提供代码补全和错误检查等功能。

## 当前目录只能用sudo写内容：

使用 `chown` 或 `chmod` 命令来更改当前目录的权限，以便不需要 `sudo` 也可以写入。

1. **更改所有权 (`chown`)**：
将当前目录的所有权更改为你自己的用户，使你可以直接写入：
    
    ```
    sudo chown -R $USER:$USER /path/to/directory
    ```
    
    - `R` 表示递归应用到目录及其子目录。
2. **更改权限 (`chmod`)**：
使所有用户对目录都有写入权限：
    
    ```
    sudo chmod -R 777 /path/to/directory
    ```
    
    这会给所有用户读、写、执行权限，但这种方式可能带来安全风险，建议根据需要调整权限。
    

## [git@github.com](mailto:git@github.com): Permission denied (publickey).fatal: Could not read from remote repository.

1.检测SSH Agent是否运行

`ssh-add -l`

如果里面没有key的信息，则导入key：

`ssh-add ~/.ssh/id_rsa`

如果Agent没有启动，则启动Agent，再导入key：

`eval "$(ssh-agent -s)"`

`ssh-add ~/.ssh/id_rsa`

2.检测SSH连接

`ssh -T [git@github.com](mailto:git@github.com)`

3.成功连接显示：

 "Hi noobyalan! You've successfully authenticated...".

SSH（Secure Shell）是一种用于安全远程访问和管理的网络协议。关键内容如下：

1. **用途**：
    - 远程登录：通过加密方式管理远程服务器。
    - 文件传输：使用 `scp` 和 `SFTP` 进行安全的数据传输。
    - 端口转发：实现内网穿透和隐私保护。
2. **认证方式**：
    - 密码认证
    - 公钥认证（更安全）
3. **常用命令**：
    - 连接服务器：`ssh user@hostname`
    - 文件传输：`scp file.txt user@hostname:/remote/directory`
    - 生成密钥对：`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`