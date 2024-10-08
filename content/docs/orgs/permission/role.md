---
linkTitle: 系统角色
title: 系统角色及权限
weight: 1
---

不同的用户拥有不同的权限，这些权限取决于他们在组织或项目中的角色及权限。在公开项目、组织中，所有登录用户将享有以下权限：

- 创建新的问题
- 在项目中创建拉取请求（PR）
- 发表评论（包括在问题、PR、提交和讨论中进行评论）
- 克隆或下载项目代码
- 查看项目 wiki 页面
- 查看组织或项目的讨论
- 查看组织的公开看板

除了上述公开项目的权限，还有一些**功能不受权限系统**的限制：

1. 轻量级 PR 的创建不依赖于代码推送权限。当项目启用轻量级 PR 后，任何平台登录用户都可以提交轻量级 PR
1. 受保护的分支和受保护的标签将遵循最终生效的保护规则

## 系统角色

1. 管理员（Owner）：组织的管理员，拥有所有权限和最终决策权。
1. 维护者（Maintainer）：项目或组织的维护者，负责日常维护工作，如处理问题、PR等。
1. 开发者（Developer）：编写、提交代码，参与开发和讨论。
1. 参与者（Reporter）：报告问题，提供反馈，参与项目讨论。
1. 浏览者（Guest）：浏览项目权限，参与公开讨论区的讨论。

### 组织管理员

| 资源 | 权限 |    |    |    |    |    |    |    |
| --- | --- |  --- |  --- |  --- |  --- |  --- |  --- |  --- |
| 组织 | 删除 | 设置 | 更新 |    |    |    |    |    |
| 项目 | 创建 | fork | 更新 | 删除 | 设置 | 归档 | 转移  |    |
| 代码 | 推送 | 下载  |    |    |    |    |    |    |
| 成员 | 邀请 | 更新 | 移除 |    |    |    |    |    |
| Issue | 创建 | 更新 | 关闭/重开 | 置顶 | 锁定 |    |    |    |
| Label | 创建 | 更新 | 删除 |    |    |    |    |    |
| 里程碑 | 创建 | 更新 | 删除 |    |    |    |    |    |
| 分支 | 创建 | 删除 |    |    |    |    |    |    |
| Tag | 创建 | 删除 |    |    |    |    |    |    |
| PullRequest | 创建 | 更新 | 评审 | 审核 | 合并 | 关闭 | 重开 | 测试 |
| 评论 | 创建 | 解决 |    |    |    |    |    |    |
| 讨论 | 创建 | 更新 | 锁定 | 置顶 | 关闭/重开 |    |    |    |
| 看板 | 创建 | 更新 | 删除 | 关闭/重开  |    |    |    |    |

*项目成员权限最高的角色是管理员，管理员权限仅可通过组织继承，不支持在项目中单独添加“管理员”权限。*

1. 创建者可以更新issue、pr的标题和描述信息，也可以关闭或重新打开它们
1. 评论的作者可以编辑和更新评论
1. 组织和项目的成员列表只能由组织和项目成员查看
1. Label 权限包括组织 label 和项目 label
1. 用户提交的安全 issue 只能由 issue 的作者和项目成员查看
1. 项目 wiki 的权限与项目代码推送的权限相同
1. 项目发布版的权限与项目 tag 的权限相同
1. 在评论中的"解决"指的是在 pr 的代码评审中解决标记为需要解决的问题


### 组织/项目维护者

| 资源 | 权限 |    |    |    |    |    |    |    |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 组织 | 设置 |    |    |    |    |    |    |    |
| 项目 | 创建 | fork | 设置 |    |    |    |    |    |
| 代码 | 推送 | 下载  |    |    |    |    |    |    |
| 成员 | 邀请 | 更新 | 移除 |    |    |    |    |    |
| Issue | 创建 | 更新 | 关闭/重开 | 置顶 | 锁定 |    |    |    |
| Label | 创建 | 更新 | 删除 |    |    |    |    |    |
| 里程碑 | 创建 | 更新 | 删除 |    |    |    |    |    |
| 分支 | 创建 | 删除 |    |    |    |    |    |    |
| Tag | 创建 | 删除 |    |    |    |    |    |    |
| PullRequest | 创建 | 更新 | 评审 | 审核 | 合并 | 关闭 | 重开 | 测试 |
| 评论 | 创建 | 解决 |    |    |    |    |    |    |
| 讨论 | 创建 | 更新 | 锁定 | 置顶 | 关闭/重开 |    |    |    |
| 看板  | 创建 | 更新 | 删除 | 关闭/重开  |    |    |    |    |

1. Issue、PR 的创建者允许更新 issue、pr 的标题、描述信息，允许创建者关闭、重新打开 issue、pr
1. 评论的作者允许编辑、更新评论信息
1. 组织、项目的成员列表，仅允许组织、项目成员查看
1. Label 权限包括组织 label 和项目 label
1. 用户提交的安全 issue 仅允许 issue 作者、项目成员进行查看
1. 项目 wiki 的权限与项目的代码推送权限保持一致
1. 项目发行版的权限与项目 tag 的权限保持一致
1. 评论中的解决是指在 pr 代码评审中解决标记为需要解决的问题

### 组织/项目开发者

| 资源 | 权限 |    |    |    |    |    |    |
| --- | --- |  --- |  --- |  --- |  --- |  --- |  --- |
| 项目 | 创建 | fork |    |    |    |    |    |
| 代码 | 推送 | 下载  |    |    |    |    |    |
| Issue | 创建 | 关闭/重开  |    |    |    |    |    |
| 分支 | 创建 | 删除 |    |    |    |    |    |
| Tag | 创建 |    |    |    |    |    |    |
| PullRequest | 创建 | 评审 | 合并 | 测试 | 关闭 | |
| 评论 | 创建 | 解决 |    |    |    |    |    |
| 讨论 | 创建 | 更新 | 关闭/重开 |    |    |    |
| 看板  | 创建 | 更新 | 关闭/重开 |    |    |    |    |

1. Issue、PR 的创建者允许更新 issue、pr 的标题、描述信息，允许创建者关闭、重新打开 issue、pr
1. 评论的作者允许编辑、更新评论信息
1. 组织、项目的成员列表，仅允许组织、项目成员查看
1. 如果选择了“禁止开发人员创建标签”，则他们将无法创建标签
1. 如果选择了“禁止开发人员创建分支”，则他们将无法创建分支
1. 用户提交的安全 issue 仅允许 issue 作者、项目成员进行查看
1. 项目 wiki 的权限与项目的代码推送权限保持一致
1. 项目发行版的权限与项目 tag 的权限保持一致
1. 评论中的解决是指在 pr 代码评审中解决标记为需要解决的问题

### 组织/项目参与者

| 资源 | 权限 |    |    |    |    |    |    |
| --- | --- |  --- |  --- |  --- |  --- |  --- |  --- |
| 项目 | fork |    |    |    |    |    |    |
| 代码 | 下载 |     |    |    |    |    |    |
| Issue | 创建 | 关闭/重开  |    |    |    |    |    |
| PullRequest | 测试 |    |    |    |    |    |    |
| 评论 | 创建 | 解决 |    |    |    |    |    |
| 讨论 | 创建 | 关闭/重开 |    |    |    |    |    |

1. 评论的作者允许编辑、更新评论信息
1. 组织、项目的成员列表，仅允许组织、项目成员查看
1. 用户提交的安全 issue 仅允许 issue 作者、项目成员进行查看
1. 评论中的解决是指在 pr 代码评审中解决标记为需要解决的问题

### 组织/项目浏览者

| 资源 | 权限 |    |    |    |    |    |    |
| --- | --- |  --- |  --- |  --- |  --- |  --- |  --- |
| Issue | 创建 |     |    |    |    |    |    |
| 评论 | 创建 |    |    |    |    |    |    |
| 讨论 | 创建 |    |    |    |    |    |    |

1. 评论的作者允许编辑、更新评论信息
1. 组织、项目的成员列表，仅允许组织、项目成员查看
1. 用户提交的安全 issue 仅允许 issue 作者、项目成员进行查看