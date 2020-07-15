## gitlab 服务端/ 开发者自己





分支

进公司以后要账户名和密码



## gitlab 服务端

centos 7 

管理员用户

拥有创建项目,创建组,创建分支,创建保护分支



## 创建仓库/项目

私有仓库 选中ssh协议才能克隆

对项目要进行成员和组的分配



## 分支git

github和gitlab有一点不一样

就是 默认创建的gitlab master分支是默认受到保护的

默认保护分支的含义:任何人都不能push文件到仓库当中



## 组,相当于GitHub的组织

前端组

后端组

第一组

第二组



一般一个项目对应一个组??

创建完用户  就要把用户分配到组里面







--------------

## 前端进公司  拿到账户名密码进行开发



### .ssh

1.免密克隆 推送 登录

2.安全



github和gitlab生成ssh方式一模一样

但是gitlab需要多做一步



```js
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

生成的文件目录

```js
/c/Users/Artificial/.ssh/ceshi/ceshi_key
```

passphrase

```js
passphrase 
gitlab 如果克隆项目是ssh协议
那么如果全组用一套SSH密钥来管理项目  那么就需要配置这个passphrase

empty for no passphrase
直接回车
```



```js
Host gitlab.example.com
	HostName 192.168.232.155 
	User qiuhang
	PreferredAuthentications publickey
	IdentityFile /c/Users/Artificial/.ssh/ceshi/ceshi_key


Host
          gitlab.example.com 别名  要配置到HOST的位置
          git clone git@gitlab.example.com:root/65ceshi.git

 HostName gitlab服务器的地址

```





### 开始正式工作

```js

在分支上进行操作

克隆gitlab远程仓库
git clone git@gitlab.example.com:root/65ceshi.git

查看origin地址
git remote -v

查看本地分支
git branch

拉取远程分支到本地分支
git pull origin 本地分支(没有会自动新建):远程分支
git pull origin hot_fix:hot_fix
//或者直接拉取到本地分支git pull origin master:hot_fix


切换到分支进行开发
git switch hot_fix
   
开发完成,返回master分支 
git switch master
    
合并分支
git merge hot_fix
    
add
git add
commit
git commit -m ""
    
push到远程的分支
    git push 远程地址别名(origin) 本地分支:远程分支
git push origin master:hot_fix
    




```







部署在Linux下面的私有github



https协议也可以

但是gitlab端创建项目的时候,必须设置成public



## 进公司以后自己拿到的



### 1.IP地址  是gitlab服务器的IP地址

192.168.232.155



### 2.账号名和密码,相当于GitHub的账号密码

