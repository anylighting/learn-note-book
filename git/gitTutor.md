

#### 设置帐号密码; `--global` 全局设置, 去掉global可以单独为某个项目设置用户名邮箱

    git config --global user.name "your userName"
    git config --global user.email "your email account"
    
    git config --global http.proxy socks5://127.0.0.1:1080
    git config --global https.proxy socks5://127.0.0.1:1080


    git init
    git status
    git add */fileName
    git commit -m "comment"

    git diff sourceVersion targetVersion
    --- before modify
    +++ after modify
    
    
    git log
    git log --pretty=online
    
#### 回退到版本 上一版本：HEAD^; 上2版本：HEAD^^;上n版本：HEAD～n

    git reset --hard HEAD^
    
    git reflog: 记录命令记录，可以看到版本号
    
#### 撤销修改;回退到暂存区的数据

    git checkout -- filename
    
    
#### 将工作区和暂存区回退到版本库状态，可以制定版本

    git reset HEAD filename
    
#### 与远程库关联，origin: 远程库的名称

    git remote add origin git@github.com:michaelliao/learngit.git
    
#### 将本地master分支推送到远程仓库，设置仓库名为origin，并和本地master分支关联

    git push -u origin master
    git push origin dev 将dev分支推送到远程仓库
    
    git clone git@github.com:zhaoji/learn
    
#### 分支管理

    git checkout -b dev 新建dev分支，并切换到dev分支，相当于以下两条命令
    git branch dev 新建dev分支
    git checkout dev 切换到dev分支
    git checkout -b dev origin/dev 创建远程dev分支
    
#### 查看分支信息,当前分支前会标有×号，星号

    git branch
    
#### 将dev分支合并到当前分支

    git merge dev
    
#### 删除分支dev

    git branch -d dev
    git branch -D dev 删除没有合并过的分支
    
#### 解决分支冲突问题

    修改冲突的文件，然后提交，冲突的地方会以<<<<<<<< ========= >>>>>>>>>>>分割
    
    
#### 显示日志信息

    git log --graph --pretty=oneline --abbrev=commit
    
    
#### 默认情况下，git合并会以Fast Forward模式，该模式中，删除分支后会丢失分支信息，

    可以用 --no-ff 参数，禁用该模式
    git merge --no-ff -m "merge dev to master with --no-ff" dev
    
    
#### 保存工作现场，将当前的修改隐藏起来

    git stash
    git stash list 列出stash列表
    git stash apply 恢复保护的现场，回复后需用 git stash drop 来删除
    git stash pop 回复现场，并删除该现场
    git stash apply stash@{0} 恢复指定的现场
    
    git remote [-v] 查看远程仓库的信息
    
#### 从远程拉取数据

    git pull
    git branch --set-upstream dev origin/dev 
    将本地dev 与远程dev链接,解决 no tracking information 错误
    
#### 标签，打的标签只存在本地，需要推送到远程仓库

    git tag v1.0 添加标签,打在当前的commit上
    git tag  查看标签,按标签的字母排序
    git tag v0.9 <-m "tag information description"> commitId 在指定的commit上打标签
    git show <tag name> 查看指定标签的详细信息
    
    git tag -d v1.0 删除标签,仅能删除未推送到远程的标签
    
    git push origin v1.0 推送指定标签到远程
    git push origin --tags 推送所有标签到远程
    
#### 删除已推送到远程的标签

    git tag -d v0.1  先删除本地标签
    git push origin :refs/tags/v0.1 在删除远程标签
