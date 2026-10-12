# Smart-Electric Innovation

实验室协作组织，按资料整理、共享资源与成员贡献组织工作。

## 新成员指南：将本地资料上传到 resources

本指南适用于 Windows CMD。假设你已注册 GitHub 账号、安装 Git，并准备上传一个名为 `Test` 的文件夹。

### 1. 确认访问权限

请先联系管理员，确认你的账号已加入组织，并接受 GitHub 邀请。

当前 `members` Team 对 `resources` 只有 Read 权限，可以下载资料，但不能直接上传。要按下面步骤上传，请先由管理员授予 `resources` 的 Write 权限；如果保持只读，请将资料提交到 `contrib` 中自己的目录，由管理员整理到 `resources`。

### 2. 设置 Git 提交信息

打开 CMD，执行以下命令，将姓名和邮箱换成自己的信息。首次使用 Git 时设置一次即可。

```cmd
git config --global user.name "你的名字"
git config --global user.email "你的GitHub邮箱"
```

这些信息用于标记提交者，不是登录账号或密码。邮箱也可以使用 GitHub 邮箱设置页面提供的 noreply 邮箱。

### 3. 下载 resources 仓库

选择一个存放仓库的目录。下面以 `D:\GitHub` 为例；如果目录不存在，先在文件资源管理器中创建它，或改成你自己的已有目录。

```cmd
cd /d "D:\GitHub"
git clone https://github.com/Smart-Electric-Innovation/resources.git
```

这是私有仓库，需要组织访问权限。首次访问可能提示登录 GitHub，按提示在浏览器中登录自己的账号。GitHub 账号密码不能直接作为 Git 命令行认证密码。

### 4. 复制 Test 文件夹

在文件资源管理器中，将原来的整个 `Test` 文件夹复制到刚下载的 `resources` 文件夹中。目标结构为：

```text
D:\GitHub\resources\
├── README.md
└── Test\
    └── 你的资料文件
```

如果仓库已有同名目录，先确认内容，避免覆盖他人的文件。文件夹名称以实际名称为准；Git 不上传空文件夹。上传前检查资料，不要包含密码、密钥或不应共享的个人信息。

### 5. 提交并上传

回到 CMD，进入下载的仓库并检查文件：

```cmd
cd /d "D:\GitHub\resources"
git status
```

确认显示的是准备上传的文件后，执行：

```cmd
git add "Test"
git commit -m "添加 Test 资料"
git push origin main
```

`git add` 选择要提交的文件，`git commit` 保存本地提交，`git push` 将提交上传到 GitHub。

成功后，打开 [resources 仓库](https://github.com/Smart-Electric-Innovation/resources)，刷新页面即可看到 `Test` 文件夹。如果提示没有权限，请联系管理员检查 Write 权限；如果提示远程已有新提交，请先同步，不要使用强制推送。

### 6. 以后更新资料

每次开始修改前，先在 CMD 中进入仓库并同步最新内容：

```cmd
cd /d "D:\GitHub\resources"
git pull --rebase
```

然后修改或复制资料，确认内容后提交并上传：

```cmd
git status
git add "Test"
git commit -m "更新 Test 资料"
git push origin main
```

如遇冲突且不确定如何处理，请保留现场并联系管理员。
