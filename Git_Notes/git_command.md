### 常用命令记录

1. **git clone git@github.com:GitHub用户名/仓库名.git**:此方式是SHH
2. **git clone https: //github.com:GitHub用户名/仓库名.git**:此方式是HTTPS
3. **git branch**:查看、创建、删除分支，-a本地和远程分支名都显示
4. **git switch**:切换分支
5. **git remote -v**:查看远程名 + URL
6. **git remote add <name> <url>**:添加远程仓库，与本地关联
7. **git fetch origin**:从远程origin拉取最新分支，更新本地的origin分支的内容，但不会做出修改。
8. **git rebase remotes/xx**:重写提交历史，把自己的在本地的提交移动到远程新的基点上，最好写全名加上remotes
9. **git stash push -u**：保存追踪以及未跟踪文件的更改，方便实现单修改文件的提交操作
10. **git stash pop**:用于恢复最近保存的stash并删除该stash,等价于apply+drop操作
11. **git checkout origin/main -- <文件>**:从远程分支origin/main，把指定文件直接拷贝到当前分支
12. **git pull**:用于更新仓库内容，会进行merge操作，慎重使用
13. **git add .**:将当前目录及其子目录更新的全部内容添加到暂存区
14. **git commit -m "参数: "**:同于提交修改说明，可选参数有
    | 指令 | 作用 |
    | :----: | :----: |
    | feat | 记录新增内容 |
    | upd | 记录原有内容的更新,修正 |
    | fix | 记录修复的错误 |
    | docs | 更新总README.md目录 |
15. **git push**:把本地仓库的提交记录同步到远程GitHub仓库
16. **git push origin HEAD:main**:把HEAD(当前分支的内容),提交到远程origin仓库的main分支上
17. **git push origin :refs/tags/版本号**:删除远程仓库origin上的标签版本号
18. **git log --oneline**:查看提交历史
19. **git tag 版本号 历史序列**:在提交的历史序列上创建轻量标签
20. **git tag -d 版本号**:删除本地标签
21. **git status**:查看当前所在分支、哪些文件修改但未提交、哪些文件已staged、哪些文件是不受git管理的
22. **git restore .**:把“已被Git跟踪的文件”即受git管理的文件恢复到最近一次commit状态
23. **git restore --ours/theirs**:用于解决合并冲突时选择保留哪个版本,--ours保存本地修改版本，--theirs保存远程修改版本
24. **git restore --staged**:取消文件暂存,将文件从暂存区移回工作区,用于取消暂存区不想commit的文件
25. **git clean -fd .**:删除所有未被Git管理的文件/目录
26. **git clean -nfd .**:查看会删除哪些东西




