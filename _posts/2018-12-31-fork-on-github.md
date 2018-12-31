---
title: 如何在GitHub上fork一个项目并与源项目保持同步
categories: [软件开发]
tags: [GitHub,fork]
---
# {{ page.title }}

本文主要说明从GitHub上`fork`一个项目后，如何保持与源项目的同步，如何把自己的修改提交给源项目，请求源项目的作者审核并把自己的修改并入(`merge`)源项目。

1. fork一个项目
要`fork`一个项目，你首先要注册一个GitHub账号，然后找到自己感兴趣的项目，点击项目主页右上角的`fork`按钮即可。我们`fork`一个项目，一般有两个目的，一是作为自己项目的一个起点，另一个目的可能是想参与到项目中，改进源项目，把自己的想法实现并提交给源项目。

2. 与源项目保持同步
当你`fork`一个项目后，需要把这个项目`clone`到本地以方便修改，以 octocat/Spoon-Knife 项目为例,当你`fork`这个项目后，项目库地址为 https://github.com/your-username/Spoon-Knife ，将此项目`clone`到本地：  

    git clone https://github.com/your-username/Spoon-Knife
    
然后导航到项目的本地工作目录，设置git:

    git remote add upstream https://github.com/octocat/Spoon-Knife.git
    
与源项目同步：首先导航到项目的本地工作目录，然后运行如下git命令：

    git fetch upstream
    git checkout master
    git merge upstream/master
    
在上面的命令中：  
命令1会在本地创建一个分支`upstream/master`，从源项目的`master`分支下载的`commit`会保存在这个分支；  
命令2切换到本地`master`分支；  
命令3将`upstream/master`分支的`commit`合并到`master`分支；

3. 把自己的修改提交给源项目作者
当你想把自己的修改提交到源项目时，可以通过GitHub提交一个`pull request`，你的修改提交后，可以在源项目的`pull request`页面与项目参与者讨论审查你提交的代码，在你提交的代码并入源项目前，你也可以进行修改，当你提交的代码通过审查后，就会被源项目作者并入源项目。

- 参考文档：  
[Fork a repo](https://help.github.com/articles/fork-a-repo/)  
[Syncing a fork](https://help.github.com/articles/syncing-a-fork/)  
[Creating a pull request](https://help.github.com/articles/creating-a-pull-request/)
