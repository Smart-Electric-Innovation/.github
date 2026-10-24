# Smart-Electric Innovation

实验室共享资料与成员贡献仓库，用于整理硬件、嵌入式开发及相关工具资料。

## 1. 资料目录

| 分类 | 建议提交内容 |
|---|---|
| 实验室器件资源 | 器件型号、规格书、选型资料及资源汇总 |
| 硬件模块资源 | 模块介绍、参考教程、原理图、PCB、仿真图 |
| 嵌入式官方资源 | 官方固件库、数据手册、用户手册、最小工程及参考模板 |
| 嵌软模块 | 模块资料、使用手册、可运行的示例代码、移植方案 |
| 嵌软开发工具 | 烧录调试工具、官方 IDE、安装说明及开发流程 |
| 嵌软系统库 | FreeRTOS、Linux 等系统的相关源码及参考资料 |
| 开源软件 | 实用开源工具、软件源码及使用说明 |
| 个人贡献 | 开发经验、知识总结、技术文档、开发指南及个人项目 |

### 提交参考

- 器件资料：型号、数据手册、选型说明。
- 硬件模块：功能介绍、原理图、PCB 文件、测试结果。
- 嵌入式工程：芯片型号、开发环境、依赖说明、可运行的示例代码。
- 软件工具：下载地址、安装方法、使用说明。
- 技术总结：问题背景、解决方案、关键代码及参考链接。

建议按类别整理文件，尽量附带 README 或使用说明。优先提交有参考价值、可复用的资料；大型软件安装包、临时文件及无关生成文件不建议直接上传。

## 2. Git 基本操作

### 首次下载仓库

安装 [Git](https://git-scm.com/install)，打开终端执行：

```bash
git clone https://github.com/Smart-Electric-Innovation/resources.git
cd resources
```

### 添加并提交资料

将需要分享的文件复制到仓库目录，然后执行：

```bash
git pull --rebase
git status
git add .
git commit -m "添加相关资料"
git push
```

命令说明：

- `git pull --rebase`：同步远程仓库的最新内容。
- `git status`：查看本次修改。
- `git add .`：暂存当前目录下的所有变更。
- `git commit -m "说明"`：创建本地提交。
- `git push`：将提交推送到 GitHub。

**注意：** `git add .` 会暂存当前目录下的所有变更，包括删除和修改。提交前应使用 `git status` 检查，确认没有不需要提交的内容。推送需要具备相应的仓库写入权限。

### 提交说明参考

```bash
git commit -m "添加 STM32 外设驱动示例"
git commit -m "更新 FreeRTOS 学习资料"
git commit -m "补充硬件模块原理图"
git commit -m "整理开发工具安装指南"
```

## 3. GitHub CLI 与 Agent 操作

安装 [GitHub CLI](https://cli.github.com/)，完成账号认证后，可以通过终端管理仓库、提交代码及处理 GitHub 协作任务。

### 安装命令

Windows（PowerShell）：

```powershell
winget install --id GitHub.cli
```

macOS（已安装 Homebrew）：

```bash
brew install gh
```

其他系统可参考 [GitHub CLI 官方安装指南](https://github.com/cli/cli/blob/trunk/docs/install_linux.md)。

### 登录与配置

安装完成后执行：

```bash
gh auth login
gh auth setup-git
gh auth status
```

按照提示完成 GitHub 登录，并确认认证状态正常。

### 使用 CLI 下载仓库

```bash
gh repo clone Smart-Electric-Innovation/resources
cd resources
```

完成认证后，在已登录且具备仓库访问权限的终端环境中，可以让支持终端操作的 Agent 执行文件整理、Git 提交和推送等任务。

**注意：** 安装 CLI 不等于自动授权 Agent。Agent 还需要获得相应的终端操作权限，并使用已认证且具有仓库写入权限的环境。不要将个人访问令牌或密码写入仓库文件。

## 协作约定

1. 资料按类别整理，尽量附带使用说明。
2. 提交前同步远程更新，并检查本次变更。
3. 提交说明应清楚描述本次修改。
4. 仅提交必要文件，避免上传敏感信息及无关文件。
