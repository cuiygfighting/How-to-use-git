# Git使用补充

1.Git追踪的是修改，而不是文件
2.cat catalogname用于在Git Bash里显示文件内容
3.pwd显示当前目录

>   cd ..返回上一级,后面有空格 
>   cd filejianame：可查看文件夹有哪些文件
>   cd 或者cd ~：切换到用户主目录
>   cd /:切换到根目录
>   cd ./:相对引用当前目录
>   cd -:在最近两次目录之间来回切换

4.git reset HEAD <file>可以把暂存区的修改撤销掉（unstage），重新放回工作区
   git reset --hard commit_id用于切换版本
5.删除文件问题
	rm file:只是在工作区删除文件
	git rm file然后git commit -m:在版本库删除文件
	若是删错了，用checkout从版本库恢复
6.Git对文件名不区分大小写,可以有-,可以有中文字符，但不能有空格
7.git add file_1 file_2 file_3可以一次添加多个文件，文件名之间用空格隔开
   git add catalog_name可以一次性文件夹中的所有文件添加到暂存区
8.创建节点dev，要先返回master,然后再合并dev和master
9.git log之后光标会跳到：之后，输入q即可跳出
10.用checkout切换到另一个分支，当前的add不会保存，所有需要用stash封存一下当前工作状态
11.若是在本地有了新的commit，且远端也有了新的commit，那么无法直接把本地修改提交到远端，需要先pull，把远端的commit接到本地commit之前的节点之后，然后手动修改，生成新的commit，最后用push提交。(在提交前可以用rebase把这次冲突在本地造成的分叉提交历史整理成直线)
12.在github上直接clone别人的仓库到本地，在本地提交后是推送不到远程的，需要用pull request。一般先fork为自己的仓库，在clone到本地
13.取消本地目录下关联的远程库：git remote remove origin
14.git add *  将目录里的所有文件提交到暂存区后
15.git可以自动识别子文件夹中文件的改动，但是git add或者git checkout等命令必须加上子文件加的文字，如git add zicatalog/finame