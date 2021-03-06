## git常用命令

### git 安装
- 安装：git apt install git 
- 查看是否安装：git
- 查看git版本:git --version 

### git 使用

#### 本地仓库命令
一、基本操作
- 初始化仓库 git init
- 查看仓库状态 git status
- 添加至暂存区 git add 文件名/.
- 添加至版本库 git commit -m '备注'
- 查看文件具体改动 git diff 文件名
二、撤销操作
- 添加暂存区(add)前：git checkout -- 文件名
- 添加暂存区(add)后，commit之前: git reset HEAD 文件名 --》 git checkout -- 文件名
- commit之后(版本回退)： git reset --hard (HEAD ^上一版本 ^^上上版本 ～num上num个版本)/版本号—对应版本
- 删除：git rm 文件名 --》git commit -m '备注' 
三、操作状态查看
- 查看提交历史记录：git log
- 只看版本号： git log --pretty=oneline
- 查看git历史操作：git reflog
四、分支操作
- 查看分支：git branch
- 选择分支：git checkout 分支名
- 创建分支：git checkout -b 分支名
- 合并分支：git merge 被合并的分支名
- 删除分支：git branch -d 分支名
- 强制删除分支：git branch -D 分支名
- 查看分支合并图：git log --graph
> 当Git无法自动合并分支时,就必须首先解决冲突。解决冲突后,再提交,合并完成。
> 解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容,再提交

- 分支合禁用默认的Fast-Forward模式：git merge ‐‐no‐ff ‐m 'commit备注' 分支名
> 禁用Fast-Forward模式后默认会产生新的commit命令，所以建议写上-m '备注'
> 合并分支时,加上--no-ff参数表示使用普通模式进行合并,合并之后可以查看历史 记录,而Fast-
Forword快速模式没有历史记录。

#### 远程仓库命令
一、前提
- 创建github账号
- 生成秘钥：ssh-keygen -t rsa -C "github的注册邮箱"
- 复制公钥至github
- 检测是否添加成功：ssh -T git@github.com

二、手动关联仓库

- 添加本地仓库关联远程仓库：git remote add origin 远程仓库地址
- 删除本地仓库与远程仓库关联：git remote remove origin 
- 本地推送至远程：git push origin master
- 远程推送至本地：git pull origin master
- 克隆仓库至本地：git clone 仓库地址


