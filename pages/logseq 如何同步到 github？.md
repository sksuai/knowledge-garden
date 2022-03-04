- [[Metadata]]:
  [[Date]]: [[Feb 20th, 2022]] 
  [[Author]]:Kevin Song
  [[Reference links]]:None
  [[Status]]: [[DONE]] 
  [[Tags]]: #技术
  [[NOTES]]:
	- [[Question]]：如何安装 homebrew？
collapsed:: true
		- 具体见： [github](https://zhuanlan.zhihu.com/p/90508170) 。
	- [[Question]]：如何为ssh 添加账号？
collapsed:: true
		- [github]([https://blog.csdn.net/weixin_40910372/article/details/89886553])
	- [[Question]]：在输入`git push -u origin main`回车后，出现`remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead...remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information.fatal: 'https://github.com/sksuai/knowledge-garden-1.git/' 鉴权失败”`，如何解决？
collapsed:: true
		- >大概意思就是你原先的密码凭证从2021年8月13日开始就不能用了，必须使用个人访问令牌（personal access token），就是把你的密码替换成token！
		- 具体见 [github](https://blog.csdn.net/weixin_41010198/article/details/119698015)
	- [[Question]]:在输入`git push origin master`时显示`error: 源引用规格 master 没有匹配`,如何解决？
collapsed:: true
		- >因为从 2021 年 11 月开始，新项目 github 默认的主分支从 master 变成了 main，而在 2021 年之前创建的项目 (老项目)，主分支仍使用 master。当使用 git push origin master 对新项目(2021 年之后的项目) 上传代码时，就会报 "源引用规格 master 没有匹配" 错误。
		- 解决方法：本地分支的名称与远程分支的名称要保持一致，新项目要推送 main 分支，老项目要推送 master。即新项目要从`git push origin master`变成`git push origin main`。
		  id:: 621343fc-7eeb-4360-9e50-b4cdf03329de
		- 具体见 [github](https://blog.csdn.net/sanqima/article/details/122201855)
	- [[Question]]:
collapsed:: true
	  ```推送到 github 
	  git push origin main
	  ```
	  显示：`更新被拒绝，因为远程仓库包含您本地尚不存在的提交。这通常是因为另外...提示：一个仓库已向该引用进行了推送。再次推送前，您可能需要先整合远程变更`，如何解决？
		- 思路：通过删除本地隐藏的 git 文件夹重置解决。
		- ```根据提示设置分支名：
		   git config --global init.defaultBranch main;git branch -m main 
		  ```
		- ```添加了远程版本库：
		  git remote add origin git@github.com:sksuai/knowledge-garden.git
		  ```
		- 具体见 [github](https://blog.csdn.net/qq_42067550/article/details/122122872)
		- [[Feb 21st, 2022]]再次出现时，通过先同步远程数据库，后推送本地到远程解决了。
	- [[Question]]:如何在macos 下显示隐藏文件？
collapsed:: true
	  ```显示隐藏文件：
	  defaults write com.apple.finder AppleShowAllFiles TRUE（回车）killall Finder（回车）
	  ```
	  ```隐藏隐藏文件：
	  defaults write com.apple.finder AppleShowAllFiles FALSE（回车）killall Finder（回车）
	  ```
		- 具体见： [github](https://www.zhihu.com/question/24635640)
	- [[Question]]:`出现更新被拒绝，因为您当前分支的最新提交落后于其对应的远程分支。提示：再次推送前，先与远程变更合并（如 'git pull ...'）。详见`如何解决？
collapsed:: true
		- 忽略历史：
		  ```
		  git pull origin main --allow-unrelated-histories
		  ```
		- 具体见： [github](https://www.cnblogs.com/pansidong/p/8287937.html)
		- 解决冲突：通过修改冲突文件 README.txt 解决了。
		- 具体见： [github](https://www.cnblogs.com/lianzhilei/p/7117372.html)
	- [[Question]]:如何将本地文件上传到 github？
collapsed:: true
		- 具体见： [github](https://www.jianshu.com/p/63b64ce3ffd7)
	- [[Question]]:如何将本地文件上传到 github？
collapsed:: true
		- ```同步远程：
		  git pull origin main
		  ```
		  ```本地上传：
		  git push -u origin main
		  ```
		- 具体见： [github](https://zhuanlan.zhihu.com/p/467192292?utm_source=pocket_mylist)
	- [[Question]]:如何在 vi 命令行下退出？
collapsed:: true
		- 按 `esc`后`:wq`
		- 具体见： [github](https://www.cnblogs.com/fromus/p/6759477.html)
	- [[Question]]：github的 token 保存在本地哪儿？
collapsed:: true
		- 见`/Users/kevin/Documents`的`github 密匙.rtf`文件。
	- [[Question]]：github的 token 多久过期，能否到期提醒我？
collapsed:: true
		- 我设置的到期时间为 2023年 2 月 22 日到期，到期提醒
		  SCHEDULED: <2023-02-23 Wed 11:11 .+1m>
	- [[Question]]:[[logseq 如何美化主题并发布到 github？]]
	- [[Question]]:logseq 如何添加提醒计划？
		- 输入:提醒的内容+`/scheduled`,配置相关日期,到期会有个在 **Linked Reference** 上方的**提醒栏**,**不会闹铃**,只能在打开 logseq 时看到.
	- [[Question]]:[[如何将本地图片上传图床？]]
	- [[Question]]: [[logseq 的用法和问题]]
	- [[Question]]:发布到 github 后如何打开?
		- https://sksuai.github.io/knowledge-garden/#/page/Contents
	-