### 常用命令记录

1. **git clone git@github.com:GitHub用户名/仓库名.git**:此方式是SHH
2. **git clone https: //github.com:GitHub用户名/仓库名.git**:此方式是HTTPS
3. **git branch**:查看、创建、删除分支，-a本地和远程分支名都显示
4. **git switch**:切换分支
5. **git remote -v**:查看远程名 + URL
6. **git remote add <name> <url>**:添加远程仓库，与本地关联
7. **git fetch origin**:从远程origin拉取最新分支，更新本地的origin/main，但不会动当前内容
8. **git checkout origin/main -- <文件>**:从远程分支origin/main，把指定文件直接拷贝到当前分支
9. **git pull**:用于更新仓库内容，防止冲突
10. **git add .**:将当前目录及其子目录更新的内容添加到暂存区
11. **git commit -m "参数: "**:同于提交修改说明，可选参数有
    | 指令 | 作用 |
    | :----: | :----: |
    | feat | 记录新增内容 |
    | upd | 记录原有内容的更新,修正 |
    | fix | 记录修复的错误 |
    | docs | 更新总README.md目录 |
12. **git push**:把本地仓库的提交记录同步到远程GitHub仓库
13. **git status**:查看当前所在分支、哪些文件修改但未提交、哪些文件已staged、哪些文件是不受git管理的
14. **git restore .**:把“已被Git跟踪的文件”即受git管理的文件恢复到最近一次commit状态
15. **git clean -fd .**:删除所有未被Git管理的文件/目录
16. **git clean -nfd .**:查看会删除哪些东西




