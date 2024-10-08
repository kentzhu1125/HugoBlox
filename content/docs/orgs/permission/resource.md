---
linkTitle: 自定义角色
title: 自定义角色及权限
weight: 2
---

除了系统角色外，GitCode 还允许组织的管理员和维护者在**组织设置**的**角色与权限**中进行自定义角色的创建和管理。

## 允许自定义的权限

目前支持配置的资源及权限点包括：

| 资源 | 权限点 | 权限说明   |
| --- | --- |  --- |
| 组织 | 设置 | 组织基本信息设置的权限，包括组织名称、组织简介、组织 logo、组织邮箱、官网、所在地等  |
| 项目 | 创建 | 组织内创建项目的权限，注：如果采用独立模式，则创建人默认也会被添加到项目成员中 |
|  | fork | fork 组织中的项目权限 |
|  | 设置 | 组织项目基本信息设置权限，包括项目名称、项目简介、项目模块等设置 |
| 代码 | 推送 | 组织内项目的代码推送权限，注：如果项目有设置保护分支，则优先以保护分支规则为准 |
|  | 下载 | 组织内项目的代码下载权限，包括：clone、下载 zip 包 等 |
| Issue | 创建 | 组织内项目的 issue 创建权限 |
|  | 更新 | 组织内项目的 issue 更新权限，包括设置 issue 负责人、设置 label、设置里程碑、设置关联pr、关联看板等 |
|  | 关闭/重开 | 组织内项目的 issue 关闭、重开权限，注：issue 的创建者默认拥有 issue 标题、描述的更新权限，issue 的关闭、重开权限|
|  | 置顶 | 组织内项目的 issue 置顶、取消置顶权限，注：每个项目最多置顶 6 个 issue |
|  | 锁定 | 组织内项目的 issue 锁定、解除锁定权限，issue 锁定后只允许项目成员参与 issue 讨论 |
| 项目 Label | 创建 | 组织内项目的 label 创建权限 |
|  | 更新 | 组织内项目的 label 更新权限 |
|  | 删除 | 组织内项目的 label 删除权限 |
| 里程碑 | 创建 | 组织内项目里程碑的创建权限 |
|  | 更新 | 组织内项目里程碑的更新权限 |
|  | 删除 | 组织内项目里程碑的删除权限 |
| 分支 | 创建 | 组织内项目分支的创建权限，注：如果项目有设置保护分支，则优先以保护分支规则为准 |
|  | 删除 | 组织内项目分支的删除权限，注：如果项目有设置保护分支，则优先以保护分支规则为准 |
| Tag | 创建 | 组织内项目的 tag 创建权限，注：如果项目有设置保护 tag，则优先以保护 tag 规则为准 |
|  | 删除 | 组织内项目的 tag 删除权限，注：如果项目有设置保护 tag，则优先以保护 tag 规则为准 |
| PullRequest | 创建 | 组织内项目的 PR 创建权限 |
|  | 更新 | 组织内项目的 PR 更新权限，包括设置 PR 负责人、设置 label、设置审查人、设置测试人、设置评审人、设置里程碑、设置关联pr、关联看板等 |
|  | 评审 | 组织内项目的 PR 评审权限  |
|  | 审查 | 组织内项目的 PR 审查权限，包括重置所有审查状态权限 |
|  | 测试 | 组织内项目的 PR 测试权限，包括重置所有测试状态权限 |
|  | 合并 | 组织内项目的 PR 合并权限，注：如果目标分支有设置保护分支，则优先以保护分支规则为准 |
|  | 关闭 | 组织内项目的 PR 关闭权限 |
|  | 重开 | 组织内项目的 PR 重开权限 |
| 评论 | 创建 | 组织内项目的评论权限（包括项目 issue 评论、项目 PR 评论、项目 PR CodeReview、项目 commit 评论、项目讨论评论等），以及组织讨论评论权限 |
|  | 解决 | 组织内项目 PR CodeReview 的解决问题权限，可以将某个 CodeReview 问题标记为已解决 |
| 讨论 | 创建 | 组织内项目讨论或组织讨论的创建权限 |
|  | 更新 | 组织内项目讨论或组织讨论的更新权限，包括问题型讨论的采纳答案权限 |
|  | 锁定 | 组织内项目讨论或组织讨论的锁定、解除锁定权限 |
|  | 置顶 | 组织内项目讨论或组织讨论的置顶、取消置顶（包括全部分类置顶、单个分类置顶）权限 |
|  | 关闭/重开 | 组织内项目讨论或组织讨论的关闭/重开权限 |
| 看板 | 更新 | 组织看板的更新权限，包括更新看板内容、更新看板设置、添加自定义字段设置等 |
|  | 关闭/重开 | 组织看板的关闭/重开权限 |

1. 组织和项目成员管理权限不支持自定义放开
1. 在自定义权限中，仅项目 label 权限可用，组织 label 权限不适用。组织标签仍然由组织管理员和维护者操作和管理
1. 在自定义权限资源中存在一些关联的资源权限。在配置自定义角色权限时，系统会默认勾选依赖的权限

相互依赖的权限点包括：

| 资源 | 权限 | 依赖资源 | 依赖权限 |
| ----- | ---- | -------- | ------- |
| tag | 创建 | 代码 | 推送+下载 |
| tag | 删除 | 代码 | 推送+下载 |
| 代码 | 推送 | 代码 | 下载 |
| 项目 | fork | 代码 | 下载 |
| pr | 合并 | 代码 | 推送 |
| 看板 | 更新 | issue+PR | 更新 |
| 分支 | 创建 | 代码 | 推送+下载 |
| 分支 | 删除 | 代码 | 推送+下载 |
| 里程碑 | 更新 | issue+PR | 更新 |


## 自定义角色

组织管理员可以根据组织的实际需求创建自定义的用户角色，并灵活地定义角色名称和权限。

{{% steps %}}

### 

**打开角色与权限**： 组织管理员或组织维护者需前往“组织设置”，并点击“角色与权限”，打开角色列表页面

###

**创建角色**： 在角色列表页面，点击“+新增角色”按钮。在弹出的窗口中，输入角色名称及角色介绍信息。确保名称具有描述性并清晰表达角色的职责

###

**赋予角色权限**： 在“权限配置”弹窗中，根据实际需求为该角色分配需要管控的资源及权限点

###

**保存角色**： 配置完成后，点击“保存”按钮，即可完成角色的创建

{{% /steps %}}

### 自定义角色限制

在创建自定义角色时请注意：

1. 最大角色数： 每个组织最多允许创建 50 个自定义角色。
1. 角色名称： 角色名称必须是唯一的，并且不能与系统预设角色名称重复。

在角色创建完成后，你可以开始向该角色[添加组织或项目成员](/docs/repo/member/)，添加的成员将被赋予该角色所配置的全部权限。