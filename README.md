在本地

```
git checkout -b dev 新建并切换到本地dev分支
git pull origin dev 本地分支与远程分支相关联
```

在本地新建分支并推送到远程

```
git checkout -b test
git push origin test 远程仓库中也就创建了一个test分支
```

克隆代码

```
git clone https://github.com/master-dev.git  
```

查看所有分支

```
git branch --all  
```

创建本地新的dev分支

```
git branch dev  # 创建本地分支
git branch  # 查看分支
```

发布dev分支 同步dev分支的代码到远程服务器

```
git push origin dev:dev  # 这样远程仓库也有一个dev分支了
```

在dev分支开发代码

```
git checkout dev  # 切换到dev分支进行开发
```



```
git checkout master  # 切换到主分支
git merge dev  # 把dev分支的更改和master合并
git push  # 提交主分支代码远程
git checkout dev  # 切换到dev远程分支
git push  # 提交dev分支到远程
```

删除本地分支

```
git checkout master  # 切换到master分支
git branch -d dev  # 删除本地dev分支

git reset HEAD [fileName]撤销add
```


使用git log 查看提交的信息,记住commit id.

```
git checkout 要修改的分支

git cherry-pick 某个commit id   // 把某个commit id的提交合并到当前分支.
```

git commit 新修改的内容 添加到上次提交中 减少提交的日志
有时候提交过一次记录只有，又修改了一次，仅仅是改动一些较少的内容，可以使用git commit --amend. 添加到上次提交过程中；

    --amend               amend previous commit

```git
git commit --amend  # 会通过 core.editor 指定的编辑器进行编辑
git commit --amend --no-edit   # 不会进入编辑器，直接进行提交


git push --no-thin origin HEAD:refs/for/master 
```

如果你之前没有配置 core.editor 选项的时候，会出现：

error: There was a problem with the editor 'vi'. 
Please supply the message using either -m or -F option.
这个时候，你通过 git config 命令，配置全局变量，指定特定的编辑器就解决报错了；之后再进行git config --amend 命令来进行编辑；

```
git config --global core.editor /usr/bin/vim
```



拉取与合并

//方法一

```
git fetch origin master //从远程的origin仓库的master分支下载代码到本地的origin master
git log -p master.. origin/master//比较本地的仓库和远程参考的区别
git merge origin/master//把远程下载下来的代码合并到本地仓库，远程的和本地的合并
```

//方法二

```
git fetch origin master:temp //从远程的origin仓库的master分支下载到本地并新建一个分支temp

git diff temp//比较master分支和temp分支的不同

git merge temp//合并temp分支到master分支

git branch -d temp//删除temp

git branch -d Chapater8

git push origin --delete Chatpter
```

回滚

```
git reset --hard commit_id
```

强制推送更新远程

```
git push -f origin <branch name>
```

更改分支名称

```git
git branch -m old_branch new_branch # Rename branch locally 
git push origin :old_branch # Delete the old branch 
git push --set-upstream origin new_branch # Push the new branch, set local branch to track the new remote
```

 
