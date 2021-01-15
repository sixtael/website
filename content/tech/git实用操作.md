---
title: "Git实用操作"
date: 2021-01-16T00:06:20+08:00
hero: /images/MazdaAxela.jpg
hidden: false
draft: false
tags: [git]
---


## git实用操作  

> 工作中会涉及到的一些git实用操作  
+ 对刚才的commit描述进行修改  
	git commit --amend  
+ 查看commit记录  
	git log -N N为需要查看的commit次数  
	git log --graph 查看commit分支线路图   
+ 此分支有修改文件添加后暂未提交，需要切换到其他分支操作的  
	git stash 临时保存修改现场  
	git stash list 显示暂存的记录  
	git stash pop 弹出恢复暂存的工作区修改（会删除原来的保存）  
	git stash apply弹出恢复暂存的工作区修改（不会删除原来的保存）  
+ 版本回退与前进  
	git reset --hard HEAD~n n为回退次数，这里其实是修改HEAD指向  
	git reflog 查看指向的记录  
	git reset --hard sha1修改HEAD指向commit  
	git revert -n sha1 撤销某个提交，实际是新增一个该提交的反向操作  
+ 提交转移至其他分支（只能单个commit）  
	git cherry-pick sha1 在一个分支上面复制另外一个分支的某个提交  
+ 对本地的多个commit合并  
	git rebase -i HEAD~N N为合并commit的次数  
+ 主线有commit，需要在本分支更新主线commit并且保持自己的commit（支持多个commit）  
	git rebase master 相比于git pull，不会新增merge提交，保持提交线路的连贯  
	git rebase --continue在和主线提交有冲突的时候需要先解决冲突，然后执行此命令  
+ 删除最近部分提交  
	1、git checkout sha1先切换到需要删除的提交之前  
	2、git branch -D branch删除次分支  
	3、git checkout -b branch新建该分支    

