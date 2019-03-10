# git help document
*参考《GitHub入门与实践》-大塚弘记著*

## 一. 配置

如果第一次使用git，需要设置署名和邮箱   
`git config --global user.name "username"`   
`git config --global user.email "your email"`   

新建sshkey，省略ssh的使用  `ssh-keygen -t rsa -C "youremail" `

## 二. 基础指令

克隆github上的仓库   `git clone git@github.com:vagabondize/Hello-World.git ` 
 
获取远程仓库的更新 `git pull`

查看仓库上的更新状况 `git status `  
                                  
向暂存区中添加文件helloworld.php `git add helloworld.php` 

添加本地所有改变的状态 `git add . `
    
删除github中的文件夹，本地保留 `git rm -r --cached some-directory`  
    
保存仓库的历史记录, 引号里是提交信息，是对这次提交的一个概述 `git commit -m "add hello-world by php" `    
            
推送到远程仓库中 `git push `                            
    
接下来的三行可以让你git push的时候无需输入github的用户名和密码
`git remote rm origin`  
`git remote add origin git@github.com:(your github name)/(your repository name)`  
`git push -u origin master`  

查看日志 `git log`   
  
git log 后面加上目录名，便会只显示该目录下日志,加上 -p 就会显示文件前后的差别 `git log -p README.md`

查看当前工作树与暂存区的区别 `git diff`  

## 三. 分支操作

创建分支feature-A `git branch feature-A`  

把当前操作切换到分支feature-A下 `git checkout feature-A`     

查看分支 `git branch`   

下面是合并分区，注意：要在分支feature-A中执行 `git merge --no--ff feature-A`

以图表形式查看分支 `git log --graph `    

设置为本地仓库的远程仓库 `git remote add origin git@.... `   

## 四. 其他功能

### git stash

[官方参考文档](https://git-scm.com/book/zh/v1/Git-%E5%B7%A5%E5%85%B7-%E5%82%A8%E8%97%8F%EF%BC%88Stashing%EF%BC%89)

将修改的代码暂存 `git stash`

查看有哪些暂存代码 `git stash list`

取最新的暂存区代码 `git stash apply`, 或者自己指定暂存区代码 `git stash apply stash@{2}`

移除暂存区 `git stash drop stash@{0}`

可以使用 `git stash pop` 来取代码，同时立刻将其从暂存中移走

## 五. 场景模拟

### 删除远程服务器文件同时保留本地文件

* git rm --cached filename / -r directory
* git commit -m "xxx"
* git push

### 修改上一次commit message

`git commit --amend`



