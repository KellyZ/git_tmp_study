﻿2002: BitKeeper  
2005: BitKeeper --> git  

Git 使用 SHA-1 算法计算数据的校验和，通过对件的内容或目录的结构计算出一个 SHA-1 哈希值，作为指纹字符串。该字串由 40 个十六进制字符（0-9 及 a-f）组成，看起来就像是：24b9da6552252987aa493b52f8696cd6d3b00373


###文件的三种状态：
在 Git 内都只有三种状态： **已提交（committed）**， **已修改（modified）**和 **已暂存（staged）**。  
文件流转的三个工作区域： **Git的工作目录**， **暂存区域**，以及 **本地仓库**。  
![文件的状态](18333fig0106-tn.png)

###文件的状态变化周期
![文件的状态变化周期](18333fig0201-tn.png)


###git command
	git clone https://github.com/KellyZ/git_tmp_study.git  
	git config --global user.name "KellyZ"  
	git config --global user.email "work2012kk@gmail.com"  
	git config --list  
###获取帮助  
	git help config  
###start git  
	git init  
	git add git_h.md  
	git rm [--cache|-f] filename  
	git mv file1 file2  
	git reset HEAD <file>...(暂停缓存)  
	git checkout -- filename(恢复缓存)  
	**git status**  
	**git log [-p|-2|--stat|--pretty (online|short|full|fuller)|--sine=2.weeks]**  
	git diff [--cache|--staged]  

	git commit [-a] -m "commit verbos"  
	git commit --amend  

	git remote [-v]  
	git remote add name url  
	git remote rm localname(不再跟踪对应远端仓库)
	git remote show [remote-name]  
	git remote rename newlocalname oldlocalname(修改远程仓库本地的简称)
	git fetch remotename(抓取到本地仓库)  
	git pull remotename(合并到本地仓库当前分支)  
	git push [remote-name] [branch-name]  
	git push [远程名] :[分支名] (删除远程分支)  
	git push [远程名] :refs/tags/<tagname>(删除远程tag)  
	git push origin --delete [tag] <branchName|tagName>

	git tag  [-a|-s] tagname [checksum] -m ''  
	git show tagname  
	git push remotelocalname --tags(推送标签)

	git branch [-v|--merged|--no-merged]  
	git branch [-d(删除)|-D(强制删除)] branchname  
	git checkout [-b] branchname(切换分支) [[远程名]/[分支名]]  
	git merge branchname  
	git mergetool  

	git rbase branchto [branchfrom]  
	git rbase --onto branchto branch1 branch2  

####忽略某些文件如日志文件
	cat .gitignore   


**配置**  
- `/etc/gitconfig`文件：系统中对所有用户都普遍适用的配置。若使用 git config 时用 --system 选项，读写的就是这个文件。  
- `~/.gitconfig`文件：用户目录下的配置文件只适用于该用户。若使用 git config 时用 --global 选项，读写的就是这个文件。  
- `.git/config`文件：当前项目的 git 目录中的配置文件，这里的配置仅仅针对当前项目有效。  



##附录
###git log options
>  
选项	说明  
-p	按补丁格式显示每个更新之间的差异。  
--stat	显示每次更新的文件修改统计信息。  
--shortstat	只显示 --stat 中最后的行数修改添加移除统计。  
--name-only	仅在提交信息后显示已修改的文件清单。  
--name-status	显示新增、修改、删除的文件清单。  
--abbrev-commit	仅显示 SHA-1 的前几个字符，而非所有的 40 个字符。  
--relative-date	使用较短的相对时间显示（比如，“2 weeks ago”）。  
--graph	显示 ASCII 图形表示的分支合并历史。  
--pretty	使用其他格式显示历史提交信息。可用的选项包括 oneline，short，full，fuller 和 format（后跟指定格式）。  
-(n)	仅显示最近的 n 条提交  
--since, --after	仅显示指定时间之后的提交。  
--until, --before	仅显示指定时间之前的提交。  
--author	仅显示指定作者相关的提交。  
--committer	仅显示指定提交者相关的提交。  


###git log --pretty format
>  
选项	说明  
%H	提交对象（commit）的完整哈希字串  
%h	提交对象的简短哈希字串  
%T	树对象（tree）的完整哈希字串  
%t	树对象的简短哈希字串  
%P	父对象（parent）的完整哈希字串  
%p	父对象的简短哈希字串  
%an	作者（author）的名字  
%ae	作者的电子邮件地址  
%ad	作者修订日期（可以用 -date= 选项定制格式）  
%ar	作者修订日期，按多久以前的方式显示  
%cn	提交者(committer)的名字  
%ce	提交者的电子邮件地址  
%cd	提交日期  
%cr	提交日期，按多久以前的方式显示  
%s	提交说明  
