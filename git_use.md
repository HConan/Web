## 配置上传项目

查看html文件，在开头开入`http://htmlpreview.github.io/?`

[教你如何一步步将项目部署到Github](https://www.cnblogs.com/fengxiongZz/p/6477456.html)

**第一步：**

登录到Github上，新建一个repository，命名为demo1
**勾选** initialize this repository with a README，点击create repository。

**第二步：**

打开settings，有一个Github Pages 的设置，点击 source 中的本来的 None ，使其变成 master 分支，然后点击 save。

**第三步：**

页面刷新之后，再看 github pages 设置框处，多了一行网址，就是你的 github pages 的网址了

**第四步：**

右键打开git bash here
输入`cd /d`进入D盘
输入`mkdir web`创建web文件夹

**第五步：**

将网页上面的项目克隆到web文件夹中
`git clone https://github.com/用户名/项目名.git`
之后就会在web文件夹中看到README.md文件

**第六步：**

将自己的内容拷贝到这个文件夹里面

**第七步：**

执行 `cd/项目名`
即进入项目的根目录中
执行
`git status`
添加全部内容
`git add .`
再
`git status`

**第八步：**

`git commit -m "此次修改内容的说明"`

**第九步：**

`git pull`

`git push`

## 问题
**问题1：**

[解决方案](https://blog.csdn.net/sdkdlwk/article/details/78761163 )

使用git push origin master是出现如下问题；

Username for ‘https://github.com‘:

解决办法：

git remote set-url origin git+ssh://git@github.com/username/reponame.git

**问题2：**

ssh: Could not resolve hostname ssh.github.com: Name or service not known

[问题解决链接](https://blog.csdn.net/piaotiejun/article/details/48734175)


**问题3：**

[Github 的搭建和配置github中的SSH key值](https://blog.csdn.net/huang3513/article/details/52837075)