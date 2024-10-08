---
linkTitle: 贡献者许可协议
title: 贡献者许可协议（CLA）
weight: 3
---

###  贡献者许可协议（CLA）介绍

贡献者许可协议（CLA）是一种协议，确保在开源项目中贡献代码的个人或实体同意项目的许可条款。它有助于明确贡献者和项目维护者的权利和义务，避免法律纠纷。GitCode 提供的 CLA 功能允许组织在项目中启用 CLA 签署和检查，确保每个提交代码的贡献者在代码合并之前已签署 CLA。

> 注：在进行CLA（贡献者许可协议）检查时，已经加入组织或项目的成员将被自动排除在CLA协议检查之外。

### 组织 CLA 管理

组织 CLA 管理模块允许组织管理员创建、更新和管理组织的 CLA 协议，支持查看每个 CLA 协议已签署的个人开发者用户和签署状态。

#### 创建组织 CLA

{{% steps %}}

### 
**访问你的组织**：登录 GitCode，进入你的组织主页

###
**进入组织设置**：在组织主页中，点击导航栏上的的“组织设置”选项卡

###
**进入CLA 列表**：在左侧菜单中，找到并点击”贡献者协议 CLA“菜单

###
**新建 CLA**：点击右上角的“新建 CLA 协议”按钮，进入 CLA 创建页面

### 
**设置 CLA**：填写 CLA 模板的标题、版本号和协议内容，多个语言版本的 CLA 建议放在一个 CLA 协议中

###
**创建 CLA**：完成后，勾选”激活“并点击“保存”按钮保存 CLA 模板

{{% /steps %}}

#### 更新组织 CLA

此功能允许组织对已有的 CLA 模板进行修改和更新，确保 CLA 内容始终符合最新的法律和项目需求。在更新时还允许管理员选择是否需要开发者重新签署新版本的 CLA 协议。

{{% steps %}}

### 
**访问你的组织**：登录 GitCode，进入你的组织主页

###
**进入组织设置**：在组织主页中，点击导航栏上的的“组织设置”选项卡

###
**进入CLA 列表**：在左侧菜单中，找到并点击”贡献者协议 CLA“菜单

###
**编辑 CLA**：点击 CLA 协议的“编辑”按钮，进入 CLA 编辑页面

###
**设置重新签署（可选）**：若新修订的CLA协议需要所有贡献者重新确认，您可以选择“需要重新签署”选项。一旦选择，系统将自动要求所有贡献者对最新版本的协议进行签署

###
**保存 CLA**：更新完成后，并点击“保存”按钮保存最新的 CLA 模板

{{% /steps %}}

### 在项目中启用 CLA 检查

当在项目中启用 CLA 检查后，能自动在合并 PR 之前检查贡献者是的 CLA协议签署状态。当项目的 Pull Requests 设置中启用了“禁止合入未完成 CLA 签署检查的Pull Request”时，如果发现有未签署CLA的贡献者，其代码将无法被合并。

{{% steps %}}

### 
**访问你的项目**：进入你要启用 CLA 检查的项目页

### 
**进入项目设置**：在项目主页中，点击导航栏上的“项目设置”选项卡

### 
**进入 Pull Requests 设置**：在左侧菜单中，找到并点击“Pull Requests 设置”

###
**启用 CLA 签署**：在“外部贡献者 CLA 协议设置”中勾选“启用外部贡献者协议 CLA 签署”，并从组织中已激活的 CLA 协议中选择对应的 CLA 协议

###
**强制签署 CLA（可选）**：若希望所有外部贡献者都需签署 CLA 协议，可以选择激活“禁止合入未完成 CLA 签署检查的Pull Request”选项。一旦启用，任何包含未签署CLA贡献者的 Pull Request 将无法被合并

> 注：PR 中如果包含多个提交者，所有这些提交者都必须完成 CLA 签署后，才能合入该 PR

{{% /steps %}}

### 签署 CLA

#### 个人开发者签署 CLA

当个人开发者参与到启用了 CLA（贡献者许可协议）的项目中并通过 PR 贡献代码时，他们通常会被要求首先签署CLA，以表明他们接受并遵循该项目的条款和条件。

{{% steps %}}

###
**CLA 签署提示**：在个人开发者提交 PR 时，如果尚未完成 CLA 协议的签署，系统会在 PR 检查信息中提醒开发者进行 CLA 协议签署，并提供相应的签署入口

###
**查看 CLA**：在CLA签署页面，开发者需要详细阅读 CLA 协议的内容

###
**签署 CLA**：阅读完CLA协议后，开发者需在页面底部选择用于签署的邮箱和姓名，并点击“我同意”按钮以完成 CLA 协议的签署过程

###
**确认签署状态**：一旦签署成功，开发者将看到签署成功的提示页面，并可在PR页面查看到自己的签署状态

> 注：CLA 协议的签署状态是通过检查 PR 提交中的 `author.email` 来确认的。一旦用户完成了 CLA 协议的签署，其账号下所有认证的邮箱都将被视为已同意并签署了 CLA 协议

{{% /steps %}}

#### 管理已签署的 CLA

个人开发者可以通过已签署的 CLA 功能查看并管理他们在 GitCode 平台上签署过的所有 CLA 协议。

{{% steps %}}

###
**登录 GitCode**：登录 GitCode

###
**进入个人设置**：点击右上角的个人头像，并单击“个人设置”按钮

###
**已签署 CLA 列表**：在左侧菜单中，找到并点击“已签署 CLA”，进入已签署的 CLA 列表

###
**查看已签署 CLA**：你可以查看你已签署的所有 CLA 列表。每个 CLA 都显示了 CLA 的组织信息、版本号和签署状态，你也可以直接查看 CLA 的协议内容

###
**撤销 CLA**：你可以通过“删除”来撤销某个已签署的 CLA 协议，但请注意这可能会影响您在相关项目中的代码贡献，且你可能需要重新签署协议以继续参与贡献

{{% /steps %}}