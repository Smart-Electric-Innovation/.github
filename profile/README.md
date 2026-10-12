# Smart-Electric Innovation

实验室资料与协作入口：整理资料、共享资源，集中管理成员贡献。

## 目录

1. [用户使用指南](#用户使用指南)
2. [仓库导航](#仓库导航)
3. [协作约定](#协作约定)

## 用户使用指南

面向已注册 GitHub 账号、首次使用 Git 的成员。

### 加入与权限

接受 GitHub 邮箱中的组织邀请，再由管理员分配权限。

| 权限 | 可以做什么 |
| --- | --- |
| Read | 下载仓库、接收更新 |
| Write | 下载、提交并推送修改 |
| Admin | 管理仓库与权限 |

新成员默认 Read。`members` Team 对 `contrib` 有 Write 权限，对 `resources` 有 Read 权限；直接上传到 `resources` 前需管理员授予 Write。其他成员以实际分配权限为准。

### 方式一：命令行（Windows / macOS）

**首次配置**

| 系统 | 安装 Git | 使用终端 |
| --- | --- | --- |
| Windows | 从 [Git 官网](https://git-scm.com/install/windows)安装 | CMD |
| macOS | 按 [Git 官方安装说明](https://git-scm.com/install/mac)安装；可运行 `xcode-select --install` 安装命令行工具 | Terminal（终端） |

安装后执行，两种系统相同；替换姓名和邮箱：

```sh
git --version
git config --global user.name "你的名字"
git config --global user.email "你的GitHub邮箱"
```

**下载仓库**

以 `resources` 为例，选择本地存放位置。下面命令会创建 `CodeProjects` 目录。

Windows（CMD）：

```cmd
mkdir "%USERPROFILE%\CodeProjects"
cd /d "%USERPROFILE%\CodeProjects"
git clone https://github.com/Smart-Electric-Innovation/resources.git
cd resources
```

macOS（Terminal）：

```sh
mkdir -p ~/CodeProjects
cd ~/CodeProjects
git clone https://github.com/Smart-Electric-Innovation/resources.git
cd resources
```

私有仓库需使用已获授权的 GitHub 账号登录。以上完成后即可在本地查看资料。使用其他仓库时，将地址中的 `resources` 替换为对应仓库名。

**上传资料（需 Write 权限）**

先在仓库目录同步最新内容：

```sh
git pull --rebase
```

再用文件管理器把 `Test` 文件夹复制到本地 `resources` 目录中，执行：

```sh
git status
git add "Test"
git commit -m "添加 Test 资料"
git push origin main
```

| 命令 | 含义 |
| --- | --- |
| `git pull --rebase` | 接收远程更新 |
| `git status` | 查看本地修改 |
| `git add "Test"` | 选择要提交的文件夹 |
| `git commit -m "说明"` | 保存本地提交 |
| `git push origin main` | 推送到 GitHub |

以后更新同样遵循：**先拉取 → 修改文件 → 选择文件 → 提交 → 推送**。操作前进入本地仓库目录，文件夹名和提交说明按实际内容替换。

### 方式二：VS Code + GitHub 插件

Windows 与 macOS 均可使用。安装 Git 和 [VS Code](https://code.visualstudio.com/)，在扩展面板安装官方 [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)，按提示登录 GitHub。

| 操作 | 在 VS Code 中完成 |
| --- | --- |
| 下载仓库 | 命令面板运行 `Git: Clone`，粘贴仓库地址，选择存放位置并打开 |
| 接收更新 | 在“源代码管理”的 `…` 菜单选择 Pull（拉取） |
| 上传资料 | 复制资料到仓库 → 点击文件旁的 `+` 暂存 → 填写说明并 Commit（提交）→ Push（推送） |
| 提交审核 | 使用 GitHub 扩展创建或查看 Pull Request |

命令面板快捷键：Windows `Ctrl+Shift+P`，macOS `Cmd+Shift+P`。拉取、提交和推送由 VS Code 内置 Git 功能提供，GitHub 插件用于 PR 和 Issue 协作；权限要求与命令行相同。详见 [VS Code 官方指南](https://code.visualstudio.com/docs/sourcecontrol/github)。

## 仓库导航

| 仓库 | 内容 | 维护者 |
| --- | --- | --- |
| [docs](https://github.com/Smart-Electric-Innovation/docs) | 资料整理与说明文档 | 管理员 |
| [resources](https://github.com/Smart-Electric-Innovation/resources) | 共享资料、文献索引与模板 | 管理员及获授权成员 |
| [contrib](https://github.com/Smart-Electric-Innovation/contrib) | 成员贡献，每人一个 `/GitHub用户名/` 目录 | 成员 |
| [.github](https://github.com/Smart-Electric-Innovation/.github) | 组织主页与公共协作说明 | 管理员 |

工作仓库为私有，需加入组织并获得访问权限。

## 协作约定

- 成员贡献集中到 `contrib`，每人一个目录，不单独建成员仓库。
- 修改前同步最新内容，只提交本次需要的文件，提交说明写清改动。
- 权限由 Teams 统一管理；资料归入 `resources` 前由管理员协调。
