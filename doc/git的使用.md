# git的使用

## 1.git的安装

```
使用库安装：
sudo apt update
sudo apt-get install git
```

测试：git --version

## 2.git概念和工作流程

![image-20211124172541713](/home/osuser/.config/Typora/typora-user-images/image-20211124172541713.png)

概念：

- **工作区：**就是你在电脑里能看到的目录。

- **暂存区：**英文叫 stage 或 index。一般存放在 **.git** 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。

- **版本库：**工作区有一个隐藏目录 **.git**，这个不算工作区，而是 Git 的版本库。
  
  ![image-20211124173608633](/home/osuser/.config/Typora/typora-user-images/image-20211124173608633.png)

![image-20211128161623943](image-20211128161623943.png)

## 3.git常用命令

1）git项目创建

新建一个目录，在此目录下执行：git init

执行后，会创建一个隐藏的.git目录:![image-20211124173048564](/home/osuser/.config/Typora/typora-user-images/image-20211124173048564.png)

2）add

![image-20211128163000947](image-20211128163000947.png)

3）commit

提交文件到本地库。

提交所有在staging area中的文件到registory：

```
git commit -m [message]
```

message是提交时的备注。

![image-20211128164433542](image-20211128164433542.png)

![image-20211128164553446](image-20211128164553446.png)

4)push

上传远程代码到远程仓库并合并。

前提：远程有仓库。

![image-20211128170007913](image-20211128170007913.png)

url栏里就是远程仓库地址。

先添加远程仓库：

git remote add 别名 远程仓库url

![image-20211128170713415](image-20211128170713415.png)

错误的原因是没有指定远程的branch，需要制定为master。

注意：github页面上将master分支名改成了"main"，但push时还是需要用master，master对应web页面上的main。

![image-20211128170758286](image-20211128170758286.png)

push时命令正确，认证失败：

![image-20211128171431256](image-20211128171431256.png)

获取token的方法：

![image-20211128171642648](image-20211128171642648.png)

点击右上角代表自己的图标，选择settings:

![image-20211128171902266](image-20211128171902266.png)

选Developer settings:

![image-20211128171949307](image-20211128171949307.png)

选Personal access tokens:

![image-20211128172041930](image-20211128172041930.png)

点击右侧的蓝色![image-20211128172125190](image-20211128172125190.png)

在页面上填写相关信息后：

![image-20211128172413883](image-20211128172413883.png)

点击Generate token:

![image-20211128172800156](image-20211128172800156.png)

关闭页面之前，需要把token拷贝出来，以后当成密码使用：

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

再次push:

![image-20211128173119582](image-20211128173119582.png)

password需要输入token。

5）clone

将远程仓库clone到本地：

git clone 远程仓库url

clone后操作步骤：

（1）修改文件（project正常进程）

（2）add

（3）commit

（4）远程同步：

分支问题：从本地开始创建的项目，主分支是master；从远程开始，主分支是main。

a）添加远程仓库：

git remote add 别名 远程仓库url

![image-20211201164728419](image-20211201164728419.png)

注意：password不能输入github的用户密码，而要输入token。

6）diff

查看工作区文件和staging area文件的区别。

7）查看提交历史log

8）恢复reset

git reset --hard HEAD^1

回退到上一个版本，--hard 将直接修改工作区文件内容。

## 4.在scode中使用git

1）用命令行进行git初始化

在scode打开项目之前，已经执行了：git init，git add

在此目录下打开，可以直接用scode的版本管理。

2）用scode进行初始化

