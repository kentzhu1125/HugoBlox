---
linkTitle: GitHub 项目提交
title: 快速指南：将项目从 GitHub 提交到 GitCode
weight: 11
---

### 设置 SSH Key 或个人访问令牌

在注册 GitCode 账号之后，你需要先添加 SSH Key 或者创建好个人访问令牌，用于代码推送认证。

#### SSH Key 设置

如果你本地已经有生成好的 SSH Key，你也可以直接使用。如果没有，你可以参考下述步骤进行创建，详细的可以参考 [官方文档](https://docs.gitcode.com/docs/users/ssh-key/)

{{% steps %}}

###
**生成 SSH Key**

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

按提示操作，一般情况下保存到默认位置即可（`~/.ssh/id_rsa`）。

###
**添加 SSH Key 到 SSH-agent**

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

###
**复制 SSH 公钥**

```bash
cat ~/.ssh/id_rsa.pub
```
###
**在 GitCode 上添加 SSH Key**

- 登录到 GitCode。
- 前往 `设置` -> `SSH Key`。
- 将复制的公钥粘贴到对应位置并保存。

###
**验证 SSH Key**

在终端通过下述命令，查看 SSH Key 是否能够正常运行

```bash
ssh -T git@gitcode.com
```

终端中打印出如下信息时，表示添加成功

```bash
remote: Welcome to GitCode, your_username
```

{{% /steps %}}

#### 个人访问令牌设置

出于安全考虑，GitCode 目前已经不支持通过用户名和密码的校验方式，请使用个人访问令牌作为 https 代码推送时的认证密码，详细的可以参考 [官方文档](https://docs.gitcode.com/docs/users/pat/)

**生成个人访问令牌**

- 登录到 GitCode。
- 前往 `个人设置` -> `访问令牌（经典）`。
- 点击 `生成新令牌`，选择所需权限。
- 生成后复制令牌，并保存到安全的地方。

### 克隆 GitHub 项目并添加 GitCode 远程仓库

{{% steps %}}

###
**克隆 GitHub 项目**

如果本地已经有 GitHub 仓库，请忽略这一步，可以直接进入到下一步。

```bash
git clone git@github.com:username/repo.git
```

或者使用 HTTPS

```bash
git clone https://github.com/username/repo.git
```

替换 `username/repo` 为你的 GitHub 用户名和仓库名。

###
**进入项目目录**

```bash
cd repo
```

###
**添加 GitCode 远程仓库**

```bash
git remote add gitcode git@gitcode.com:username/repo.git
```

或者使用 HTTPS 和个人访问令牌

```bash
git remote add gitcode https://gitcode.com/username/repo.git
```

替换 `username/repo` 为你的 GitCode 用户名和仓库名。

{{% /steps %}}

### 推送代码到 GitCode

{{% steps %}}

###
**推送代码**

```bash
git push gitcode main
```

###
**或者指定分支**

```bash
git push gitcode branch-name
```
###
**或者全部分支**

```bash
git push gitcode --all
```

{{% /steps %}}

### 常见问题及解决

#### 验证失败

如果在设置 SSH Key 或使用个人访问令牌时遇到验证失败，请检查以下几点：

- 确保 SSH Key 已正确添加到 SSH-agent，并且公钥已添加到 GitCode。
- 确保使用的个人访问令牌具有足够的权限。
- 确保远程仓库 URL 正确无误。