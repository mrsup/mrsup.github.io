title: Github+hexo搭建个人博客
date: 2015-05-25 20:53:25
categories: [Course]
tags: [Github,Hexo,Blog]
---
##写在前面（可忽略）
作为一个大四狗以及低智商程序狗，在赶论文的繁忙季节里忙里偷闲，居然写起来教程来，简直无可救药了。  
一直想搭建一个属于自己的博客网站，认真写一点技术总结，积累一点学习经验，只是以前沉不下心来，各种博客用着用着出现些莫名其妙的问题又没耐心查资料解决，因此以前的博客数据都丢失了，这应该是我目前新的第一篇博客吧。  
前几天在网上溜达的时候看见了Github+hexo搭建博客的教程，心痒无聊之下就试着玩了玩，结果一不小心就花了三两天时间，万幸终于还是成功搭建好了，在尝试搭建的过程中，出现了各种各样的问题，耐着性子百度查资料都解决了，心痒之下便想着整理一下博客的搭建教程，想着也许能帮助后来尝试者少走点弯路吧（网络上有很多Github+hexo搭建博客的教程都是以前写的，和现在的版本不合，因此内容将不同从而出现各种问题）。  
原谅我絮絮叨叨感概这么多，以下正文。  
PS. 本教程只涉及操作方法，不对其原理进行过多讨论，预知详情，请自行百度。
<!--more-->  
##基础准备
###写在前面
如果你还不知道本次教程的任务目标是什么，那你应该关注这么几个关键字：  
  
* **博客**：简单说来就是指可以发布文章的东东；
* **自定义**：文章的样式、博客的样式等完全可以自由定义，不像新浪博客、网易博客等界面固定；
* **免费**：不用花钱！
* **静态化**：一个页面对应一篇文章，不能向其他高级网站一样高度交互；
  
###准备工作
  
1. 注册 [Github](https://github.com) 帐号；
2. 安装 [nodejs](https://nodejs.org/) ；
3. 安装 [Git](http://www.git-scm.com/download/) ；
  
##预先配置
###配置SSH
1. 鼠标右键选择 **Git Bash Here**  
2. 输入`cd ~/.ssh` 回车
3. 输入`ssh-keygen -t rsa -C "邮件地址"` 邮件地址处填写你的邮件地址
4. 如果出现`Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa)` 直接回车就好
5. `Enter passphrase (empty for no passphrase)` 输入你的密码
6. `Enter same passphrase again` 再次输入密码
7. 如果出现一个虚线框包围的画则证明已经成功设置ssh key了！
###添加SSH Key到Github
1. 打开`C:\Documents and Settings\Administrator.ssh\id_rsa.pub`文件，如果没有找到`Documents and Settings`文件夹，请[设置显示隐藏文件](http://jingyan.baidu.com/article/574c5219e868cf6c8d9dc13a.html)，如果提示无法访问、拒绝访问，则可以[更改权限](http://jingyan.baidu.com/article/29697b91d55103ab20de3cc4.html)
2. 复制`id_rsa.pub`文件中的内容
3. 登录[Github](https://github.com)，点击右上角的`setting`按钮，再点击左侧的`SSH heys`选项，再选择`Add SSH key`，再在`key`输入框粘贴刚刚复制的内容，然后点击`Add key`
4. 验证是否设置成功：输入`ssh -T git@github.com`，如果出现`Are you sure you want to continue connecting (yes/no)?`则输入yes，如果出现`Enter passphrase for key '/c/Users/*/.ssh/id_rsa'`则输入你刚刚设置的密码，然后出现`Hi ***! You've successfully authenticated, but GitHub does not provide shell access.`则配置成功
5. 完善个人信息：`git config --global user.name "***"` ***处输入用户名
6. `git config --global user.email "****"` ****处输入用户名
###使用Github[新建博客](https://pages.github.com/)
1. 进入`https://github.com`，点击`New Repository`按钮
2. 设置`Repository name`为 用户名.github.io ，如用户名为test，则`Repository name`填写为test.github.io，然后点击`Create Repository`
3. 在本地环境下（如：`d:\`）点击右键，选择`Git Bash Here`,然后输入`git clone https://github.com/username/username.github.io` `username`处填写你的Github用户名
###使用Hexo
1. 参照[Hexo文档](http://hexo.io/zh-cn/docs/index.html)，安装Hexo：在刚刚的环境下输入`npm install -g hexo-cli`
2. 安装完成之后，输入`cd username.github.io`进入到项目文件夹（`username`处填写你的Github用户名），然后输入`hexo init`，再输入`npm install`
3. 使用[主题NEXT](https://github.com/iissnan/hexo-theme-next)：输入`git clone https://github.com/iissnan/hexo-theme-next themes/next`下载主题，然后更改站点的`_config.yml`文件中的`theme`字段为`next`(注意theme：后面必须要有一个空格)  
 
		theme: next
然后从资源管理器中进入`/themes/next/`，将`_config.yml.example`改名为`_config.yml`
4. 更新主题:  

		cd themes/next
		git pull
5. 本地查看  

		$ hexo g
		$ hexo s
在浏览器中访问[localhost:4000](localhost:4000)即可查看运行在本地的博客网站
###部署到Github
1. 配置你的本地站点下的`_config.yml`文件

		deploy:
			type: git
  			repo: git@github.com:username/username.github.io.git
  			branch: master
`username`处填写你的`Github`用户名
2. 在`Git Bash`中输入：

		hexo d
如果提示`Enter passphrase for key '/c/Users/*/.ssh/id_rsa'`则输入你设置的`SSH`密码
3. 待部署完成后访问：`http://username.github.io`(`username`处填写你的`Github`用户名)即可访问你的博客。
##后记
该教程还未编写完全，作者会随时更新！  
如果遇到什么问题，可以在下方留言，我很乐意和你一起共同讨论。