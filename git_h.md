2002: BitKeeper  
2005: BitKeeper --> git  

Git 使用 SHA-1 算法计算数据的校验和，通过对件的内容或目录的结构计算出一个 SHA-1 哈希值，作为指纹字符串。该字串由 40 个十六进制字符（0-9 及 a-f）组成，看起来就像是：24b9da6552252987aa493b52f8696cd6d3b00373


###文件的三种状态：
在 Git 内都只有三种状态：**已提交（committed）**，**已修改（modified）**和**已暂存（staged）**。  
文件流转的三个工作区域：**Git的工作目录**，**暂存区域**，以及**本地仓库**。  
![文件的状态](18333fig0106-tn.png)

###文件的状态变化周期
![文件的状态变化周期](18333fig0201-tn.png)




###git command
	git clone https://github.com/KellyZ/git_tmp_study.git  
	git config --global user.name "KellyZ"  
	git config --global user.email "work2012kk@gmail.com"  
	git config --list  
>获取帮助
	git help config  
>start git
	git init  
	git add git_h.md  
	git rm [--cache|-f] filename  
	git mv file1 file2
	**git status** 
	**git log [-p|-2|--stat|--pretty (online|short|full|fuller)|]**
	git diff [--cache|--staged]  
	git [-a] -m "commit verbos"  
>忽略某些文件如日志文件
	cat .gitignore   


**配置**
-`/etc/gitconfig`文件：系统中对所有用户都普遍适用的配置。若使用 git config 时用 --system 选项，读写的就是这个文件。
-`~/.gitconfig`文件：用户目录下的配置文件只适用于该用户。若使用 git config 时用 --global 选项，读写的就是这个文件。
-`.git/config`文件：当前项目的 git 目录中的配置文件，这里的配置仅仅针对当前项目有效。



##附录
###git log options
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


###git log --pretty format
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
