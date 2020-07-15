## 需要测试***

git pull origin master直接覆盖掉本地的了  本地文件被删除了直接

还是硬回退才恢复



应该怎么处理







## 流程图

![image-20200428100516462](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428100703629.png)

 

![image-20200428100607603](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428100516462.png)





## 语义化的版本

![image-20200428100703629](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428100607603.png)

<img src="https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428100917451.png" alt="image-20200428100719657" style="zoom: 67%;" />



```js
2.6.0-->2.6.10 都是BUG版本的修复

主版本:根本性的接口变化或者API重写

次版本:
```

<img src="https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428102006976.png" alt="image-20200428100917451" style="zoom:50%;" />

![image-20200428101611048](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428101611048.png)







## GIT

![image-20200428101651049](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428101651049.png)

```js

git ee 是码云
git ea也是国内的
```

码云的介绍

![image-20200428102006976](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428102237397.png)

![image-20200428102047438](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428102047438.png)



### SSH

![image-20200428102203894](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428102203894.png)



```js
使用http来克隆协议
https已经做了加密

但是克隆的时候必须要输入个人的用户名和密码

问题，useSSH--》就是一种免密的方式

```

![image-20200428102237397](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428103108605.png)



步骤

```js
https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

passphrase的作用
多个人协同的时候，使用同一组密钥对
为了防止泄密，使用passphrase
每次克隆的时候，需要pasephrase，相当于一个密码

回车两次
```

![image-20200428103108605](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428103325929.png)

产生两个文件key和pub

![image-20200428103325929](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428103427866.png)

打开pub，复制粘贴里面的内容到github

![image-20200428103427866](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428103626743.png)



在个人文件夹下面有一个隐藏的文件夹.ssh

![image-20200428103626743](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428105555422.png)



当我们不再使用这个默认的密钥对的时候id_rsa，或者使用多个密钥对来进行git的交互的时候



新增一个config文件，没有后缀

![image-20200428104006258](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428104006258.png)

别名，如果改变了host别名，需要修改remote远程git

这里填全名，user是git自己的user

File是绝对路径



------

如果本地有多个密钥对

![image-20200428104200171](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428104200171.png)

这个名称可以更换成自己上面定义HOST的时候的别名，比如HOST qiuhang  这里就改成qiuhang

对应多个密钥对的配置路径

```js

一个仓库，如果初始化完成

直接克隆到本地的话，默认就带了远程仓库地址
```

![image-20200428104631322](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428104909003.png)





如果已经有一个密钥对的话怎么办，从远程已经有的密钥对，复制到本地进行配置？？





## git基础

![image-20200428104909003](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428104631322.png)

```js
pull requests
PR，合并到自己的保护性分支并且检查
```



![image-20200428105555422](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428111215861.png)

```js
推送的第二种方式，是已经有了一个仓库，来多添加一条记录，这样的话，本地提交的时候，可以进行选择，
就会提交到选择好的那个仓库当中

注意的是，在已经配置好远程仓库的情况下，再进行添加另一个远程库地址，origin需要改成其他名字，比如o2等等

一次推送到多个仓库：需要注意的是，可以配置到一条origin当中，需要git remote set url命令，自查
可以实现一次推到多个仓库
```

```js
加上-u命令  相当于设置了一个默认的推送的远程分支的名字，第一次加上-u的话，之后再直接git push  就直接可以推送
```



## 核心概念，快照

```js
stage临时区域
已经开始监视文件
正式commit之后，就创建了一个快照


```

![image-20200428111215861](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428111237475.png)

![image-20200428111237475](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428192208279.png)



```js
pull:拉取到本地并且进行合并

git stash 保存缓存区的文件，不做任何提交，非常常用，但是不熟悉
这样可以切换到其他的任意分支，
想找回来，使用git apply

git add . 添加所有文件

git log

git reflog主要是本地的一些提交
包含删除的提交，可以进行回退撤销

查看用户和邮箱
git config --global --list

git reflog查看完hash值  比如22c7f3a

进行回退，
git reset --hard 22c7f3a

git reset --hard head^
    				~1
    一次

回退完成，
git log 只会记录回退点之前的记录，没有分支的切换

git reflog会记录所有的操作，包括分支的切换，删除操作
```



```js
git stash

在暂存区干了一件事，进行了修改，这个时候，要干其他事，并且不想提交到快照，

这个时候使用git stash  可以保存当中暂存区的状态，然后使用status进行查看，查看发现已经变成纯净的状态了，并且没有任何提交和修改

恢复：git stash apply  就可以恢复到一定的状态

比如在master分支上开发一个功能没有开发完成，又不想提交到版本库当中去，处女座

这个时候可以随机切换到其他分支

如果不stash  切换分支的话，会提示，修改了但是没有提交

另一个场景，改了一堆功能，改出来一堆BUG，这个时候怎么回退到干净的版本
另一个场景，改了一堆功能，改出来一堆BUG，这个时候怎么回退到干净的版本
另一个场景，改了一堆功能，改出来一堆BUG，这个时候怎么回退到干净的版本
改出来Bug的时候
可以创建多次
apply 弹出所有改变
pop 最近的一次改变


```



```js
git diff命令
可以直接使用

```



## git flow

## 1.就一个前端



## 2.太多分支

![image-20200428192208279](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428192444446.png)



针对用户测试的环境

测试的环境

开发的环境

release发布的环境

这些都是分支

问题1.必须使用dev,先checkout一个dev分支,然后在dev分支上面修改,然后提交到dev分支

问题2.复杂度太高 , 维护太麻烦

问题3,多次merge,从feature



gitflow的缺点

https://baijiahao.baidu.com/s?id=1661688354212771172&wfr=spider&for=pc





## 推崇的,适合持续集成的场景

多次提交

多次合并

多次发布

持续集成

上游分支向下游发展

在master分支开发  master推送到预生产就是测提

在pre-production预发布

在production就自动化构建



![image-20200428192444446](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428213335257.png)



这样的话直接在master上面进行操作合并

cicd工具,检测的是pre的提交和合并 ,发现有预发布的更新  进行测试提交

cicd自动发布到生产环境上面去

主要减少了合并





## vue和react模型

这个不是特别理解

![image-20200428192727538](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428210844948.png)

最大的好处是有一个稳定的版本

在master检出一个稳定版本

如果版本不用  那么删除掉最后打一个tag



a和b都在自己的dev分支上面开发

一般的人是没有master分支的推送权限的



步骤

拉取到本地

新建dev分支

推送到远程的自己的分支



然后在项目里面,自己的分支,提交一个pull request

PR



代码

```js
git checkout -b dev
创建并且切换到新的分支

切换分支的时候有没有提交,如果有提交的话,是不让切换分支的
这个时候
git status
```

<img src="https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428212626645.png" alt="image-20200428210844948" style="zoom:67%;" />

推送到dev分支

## 删除远程的分支

![image-20200428213335257](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428213116721.png)

本地空:远程



这样这是删除远程的  本地的 是 git branch -d 本地分支





## 发生冲突

![image-20200428211031015](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428213232421.png)

先使用git pull origin dev

合并远程分支到本地

然后修改冲突,

git add . 

git commit

git push origin dev





git pull = git fetch + git merge





可以使用fetch  先查看远程的

git fetch origin some-branch:dev

合并到本地的dev分支?



A : git push origin 本地分支:远程分支 完成了自己的开发

B:先使用  git fetch  查看一下远程和本地有什么不一样

然后发现了一个新分支

然后

git fetch origin some-branch:dev1

会自动创建dev1新分支

ok就返回dev进行合并







## 工作流

![image-20200428212626645](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428211031015.png)



现在 dev是预发布分支

fecture是开发分支

master是生产环境分支

先切换到dev分支进行合并

再切换到master进行合并dev



## tag

给当前的分支打上一个tag

![image-20200428213116721](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428214157265.png)





删除远程的tag

![image-20200428213232421](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428213742660.png)









## 如果没做完该怎么办,做了一半没有完

1.git stash

2.git reset --hard head  这种方式会放弃所有已经添加到暂存区的文件不太好

3.从暂存区当中撤出来

![image-20200428213742660](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428192727538.png)







## 已经添加到暂存区的文件再修改然后可以丢弃或者再次add

![image-20200428214157265](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428214931709.png)



丢弃的话,所有的改变都没了







## gitlab的好处

1.突破协作人数的限制

2.设置那些人才可以注册邮箱

定制化需求



gitlab



<img src="https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428215842554.png" alt="image-20200428214931709" style="zoom:50%;" />





## 产生gitignore

<img src="https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428220533608.png" alt="image-20200428215842554" style="zoom:67%;" />

![image-20200428220235416](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428220235416.png)

http://gitignore.io/





gitignore  不能忽略已经add的文件

已经提交了1.txt

想忽略

解决方式

![image-20200428220533608](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428220756101.png)

1.先清除快照

2.然后再git status 发现已经忽略了



方式3

![image-20200428220756101](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428221022399.png)

注意路径







## GUI

注册+sourcetree

![image-20200428221009637](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428221009637.png)

![image-20200428221022399](https://qiuhangmarkdown.oss-cn-hangzhou.aliyuncs.com/markdowm/image-20200428100719657.png)