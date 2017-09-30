## 对于MAC
如果你使用的是mac，那么只需要在命令行里敲出brew install git，就可以安装上最新版本的git了。

如果你已经装了git，那么brew install git就会告诉你你已经装了git了。

如果你想装特定版本的git， 那么先使用brew search git命令，查看有哪些可以安装的git以及版本，然后brew install git@2.1.2指定版本号来安装指定版本的git。

如果你想卸载git，安装最新的git，那么只需要使用brew uninstall git命令就可以卸载git了。

查看git版本请使用git --version命令。

## 本地创建版本库然后同步到远端
我们可以在任意地方创建一个目录mkdir learngit，然后进入该目录cd learngit，使用gitinit来创建版本库。

完成之后，我们使用touch README.md来创建一个文件，并在里面加一些项目信息。

之后可以添加很多文件和目录

最后，回到learngit目录下，使用git add . 命令把文件添加到暂存区。暂存区是暂存提交文件的地方，可以保存多次git add . 的结果。

然后使用git commit -m "注释" 命令提交暂存区的内容到master分支上。master分支是主分支，也是第一个分支。提交之后，master的指针HEAD就会指向新的位置。

-------

添加远程库，首先需要在github上创建一个git仓库。步骤是进入https://github.com，找到new repository按钮，点击。然后输入一样的仓库名learngit。创建好之后找到仓库的git地址http或ssh的，有按钮可以直接复制。

然后使用git remote add origin https://github.com/xxx/learngit.git 命令，添加远程库。这里我们把远程库命名为origin，公认的叫法。而使用https是因为https保存了ssh-key，可以一次设置以后都免密码。

接下来，我们使用git push origin master 命令，把master推送到origin上。这样代码就保存到远程仓库上了。

## clone远端版本库
我们可以在任意位置使用git clone https://github.com/lqwgit/tutorial_git.git 命令来克隆远端版本库。克隆之后就会生成tutorial_git文件夹，这就是我们的本地仓库了。

修改文件，然后使用  
git add .  
git commit -m "注释"  
git push origin master  
把修改提交到github上


