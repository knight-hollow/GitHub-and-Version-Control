# GitHub-and-Version-Control
这里简单介绍了如何使用github对代码进行版本控制的方法
## 一些术语
__VCS__: 版本控制系统  
__SCM__: 源代码管理  
__Commit (snapshot)__: 在 Git 里，每一次 commit 就是给项目拍了一张“照片”，记录下这一刻所有文件的样子。所有 commit 串起来，就形成了项目的 历史版本树。  
__Repository (仓库/目录)__: 包含了项目所有文件 + Git 历史信息的目录。  
__Working Directory(工作区)__: 正在编辑文件的那个目录。  
__Checkout__: 切换 (switch) 或恢复 (restore) 代码的状态。  
__Staging Area / Staging Index / Index(缓存区)__: 保存你即将要提交的文件快照。  
__SHA__: Git 里用 SHA-1 哈希（40 位十六进制字符串）来唯一标识每一个对象（commit、blob、tree、tag）。  
__Branch__: 分支 = 指针，指向某一个 commit。  
## 创建Git Repo: 
`git init`: 创建新的仓库  
`git clone`: 克隆或复制现有仓库  
`git status`: 检查仓库状态  
`git log`: 查看提交历史  
`git log --oneline`: 快速查看提交历史，每个 commit 一行，简洁明了。  
`git log --stat`: 在查看提交历史时，顺便显示每个提交修改了哪些文件，以及增加/删除的行数统计。  
`git log -p`: 查看提交历史 + 每个提交的代码差异，是追踪 bug 和学习别人代码修改的利器。
`git show`: 单个对象（commit/tag/file）的详情。
## Commits, Tag, Conflicits
`git add`: 把改动放进缓存区，等待commit。  
`git commit -m`: 把暂存区里的改动永久保存到仓库中，并生成一个新的 commit 对象。-m 选项用来 直接在命令行里写提交信息 (commit message)，而不用打开编辑器。  
`git diff`: 显示文件之间的差异。  
`.gitignore`: 用来告诉 Git：哪些文件或目录不需要纳入版本控制。  
`git tag`: 给某个 commit 打上一个标签  
`git branch`: 查看分支列表  
`git branch dev`: 创建 dev 分支  
`git branch -d dev`: 删除 dev 分支  
`git checkout dev`: 切换到 dev 分支  
`git checkout -b feature`: 新建并切换到 feature 分支  
`git checkout -- file.txt`: 丢弃文件修改  
`git merge`: 把一个分支的修改合并到当前分支。
```
git checkout main        # 切换到目标分支
git merge dev            # 把 dev 分支合并进 main
```
`git commit --amend`: 修改最近一次提交。  
`git revert`: 撤销某个 commit 的修改，但会创建一个新的 commit。  
`git reset`: 把分支的 HEAD 移动到指定 commit，可以理解为“回到过去”。  
## 远程仓库
`git remote -v`: 查看远程仓库  
`git remote add origin https://github.com/username/repo.git`: 添加远程仓库  
`git remote set-url origin git@github.com:username/repo.git`: 修改远程仓库地址  
`git remote remove origin`: 删除远程仓库  
`git remote rename origin upstream`: 重命名远程仓库  
`git push <remote-shortname> <branch>`: 把本地分支推送到远程仓库  
`git pull`: git fetch + git merge 的组合。从远程仓库拉取最新代码，并合并到当前分支。  
`git fetch`: 从远程仓库下载最新的提交、分支和标签，但不会自动合并到你当前的分支。
`git fork`: 在远程平台上复制一份别人的仓库，放到你自己的账户下。
## 文档
文档的存在是为了帮助我们理解自己编写的代码。一个有用的README文档应当包括以下部分:
- 标题和描述
- 安装说明和软件依赖项
- 常用信息
- 已知错误
当然随着代码库的增长或需求的变化README文件中可以添加其他的信息。
### Markdown
为了建立良好的排版并可自动转化为HTML进行显示，使用Markdown语法进行方便快速的内容排版。

[基本撰写和格式语法](https://docs.github.com/zh/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#links)通过链接进行查找学习
