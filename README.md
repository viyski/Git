


## git

 ssh

	ssh-keygen -t rsa -C "your.email@example.com" -b 4096

 修改信息

	git config user.name
	git config user.email
	git config --global user.name
	git config --global user.email

 常用命令
	
	git help
	git init
	git diff
	git rm filename
	git clone 仓库地址
	git status
	git log
	git log --graph 分支合并图

添加远程
	
	git remote add 仓库地址

冲突

	git checkout dev
	git rebase master # 将dev上的c2、c5在master分支上做一次衍合处理
	# git提示出现了代码冲突，此处为之前埋下的冲突点，处理完毕后
	git add readme # 添加冲突处理后的文件
	git rebase --continue # 加上--continue参数让rebase继续处理

 拉取分支最新 
 
	git pull origin test:test
	 
 分支创建 
  
 	git branch test

分支切换 
	 
	git checkout test


 创建分支并切换 

	git checkout -b test


添加文件 
	 		
	git add .


提交 
 
	git commit -m "test commit"


推送到远程分支 

	git push origin test
 	git push origin test:test


拉取master最新 
 
 	git checkout master 
	git pull


合并分支 
 
	git merge test


推送到远程 
 
 	git push origin master
