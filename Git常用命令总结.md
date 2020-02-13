### ﻿一、常用命令：

	mkdir XX：创建一个空目录 XX指目录名
	pwd：显示当前目录的路径
	cat xx：查看xx文件内容
	【git init：把当前的目录变成可以管理的git仓库，生成隐藏的.git文件夹】
	【git add xx：把xx文件添加到暂存区】
	【git commit -m “xx”：提交文件 -m后面的是注释】
	git status：查看仓库状态
	git log：查看历史记录
	【git reset --hard HEAD^：往上回退一个版本】
	git reflog：查看历史记录的版本号id
	git checkout -- xx：把xx文件在工作区的修改全部撤销
	git rm xx：删除xx文件 之后要commit
	【git remote add origin https://github.com/xxxxx/a.git 关联一个远程库】
	【git push -u（第一次要用-u，以后不用）origin master：把当前master分支推送到远程库】
	【git clone https://github.com/xxxxx   从远程库中克隆】
	【git checkout -b dev：创建dev分支 并切换到dev分支上】
	git branch：查看当前所有的分支
	git checkout master：切换回master分支
	git merge dev：在当前分支合并dev分支
	git branch -d dev：删除dev分支
	git branch xxx：创建分支xxx
	git remote：查看远程库信息
	git remote -v查看远程库的详细信息
	【git pull origin master 将远程库的更新拉取到本地并自动合并】
	【git push origin master：git会把master分支推送到远程库对应的分支上】
- 如果本地没有此分支，是拉取不到的，可以执行git pull 命令看一下

* git checkout -b dev origin/dev // 克隆仓库后切换到dev分支（根据远程分支生成本地分支）

### 二、不小心关联错了仓库,怎么办？

	* 暴力解决：删除.git，重新建立本地仓库
	* 优雅解决：git remote remove origin，再在重新关联仓库

### 三、pull和fetch的区别？
	* git pull origin master
		* 将远程仓库的master分支上代码版本复制/合并到本地master分支上
	* git fetch origin master:dev
		* 新建了一个dev分支，将远程仓库的master分支上代码版本复制到dev分支上
		* 就一定不会产生冲突
		* git diff master dev对比两分支内容，观察会不会产生冲突
		* 如果会，先解决，在合并分支。如果不会，就直接合并分支