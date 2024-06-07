#### 一,认识github

##### 1.1Github标签

Explore 探索页

Topics 技术分类

Trending 推送

events 事件

##### 1.2搜索栏

关键字查询 （搜索标签）awesome（有趣的）sample（样例）tutorial（资料）

模糊查询 （搜索词）

#### 二，github三要素

##### 2.1 仓库

仓库是Github的**项目管理单元**，每个用户都可以创建属于自己的仓库将项目代码资源上传到仓库中保存。项目传到github中可以云存储 保存与备份。便于管理工程，每个仓库中存储一个工程。每个用户都可以有多个仓库。

####  仓库子标签

Code：项目工程资源，包含代码、资源、库、许可证（license）、阅读文档（MD）等

Issues：问答

README.md，工程的自述文件，使用markdown语言编写

LICENSE 开源许可证：GPL3.0 MIT APCHE2.0 BSD

##### 2.2 提交

 用户在上传代码时，可以用过提交来备份代码信息。

提交可以备份代码片段，并且统计展示用户的修改。通过提交记录找到以前的代码片段（良好的提交习惯）。

可以通过提交记录，回溯任意代码位置。提交可以记录开发的详细过程（文件的创建，即代码的修改）便于用户学习工程的开发过程。

##### 2.3 分支

**资源存储单位**，用于存储代码数据，一个仓库由若干分支构成。

每个仓库创建后都有一个默认主分支（Matser/Main），代码上传都存储在分支里。可以用于多人协作开发。



#### 三.git的配置与使用

Git分布式版本控制系统

Github网站仓库中的工程、已上线发布的工程，开发者可以随时使用git软件，对项目进行更新、访问、控制与管理，用于同步管理线上工程

3.1绑定远程仓库

1.完成账号与设备绑定(关联)

1）查看本地配置文件



```bash
git config --list
```

[![d37e36db35a9b1509d324c499a3b35d.png](https://i.postimg.cc/CLvV1Yk8/d37e36db35a9b1509d324c499a3b35d.png)](https://postimg.cc/svZL6knf)



2）修改或添加config配置项

```bash
git config --global user.name 用户名
git config --global user.email 注册邮箱
```

 \3) 生成本机设备密文

```bash
ssh-keygen -t rsa -C 注册邮箱
```


[![fd05864eda098ba6040cb6b83b12f3b.png](https://i.postimg.cc/HnxBPGnG/fd05864eda098ba6040cb6b83b12f3b.png)](https://postimg.cc/8J2Rj0Lw)

\4)查看生成的 SSH 公钥

```
cat /c/Users/lenovo/.ssh/id_rsa.pub
```

[![3840090368278ea4ab61e6c1d78b92c.png](https://i.postimg.cc/ZRfLNfcw/3840090368278ea4ab61e6c1d78b92c.png)](https://postimg.cc/XGCFSkt5)

\5) 在Github上添加ssh公钥

```bash
C:\Users\用户名\.ssh\id_rsa.pub 

Settings -> SSH and GPG keys-> New SSH key
```



[![bcf64a7b854a6aa9adce5768d9628e4.png](https://i.postimg.cc/Xv4KzM12/bcf64a7b854a6aa9adce5768d9628e4.png)](https://postimg.cc/RWpnWYBf)



\6) 测试关联是否完成

```bash
ssh -T git@github.com    #ssh远程登录
```

[![b9606f5807649a564eb9f791ba480bc.png](https://i.postimg.cc/cCpw7P8B/b9606f5807649a564eb9f791ba480bc.png)](https://postimg.cc/30ZkYS1k)




2、为目标仓库设置别名，创建一个云端仓库的SSH地址别名

1. ```bash
   1. git remote add orgin(别名) SSH地址(云端仓库地址) 
   2. git remote origin remove    *#删除地址别名
   
   ```

![Uploading 90709dc517aa52eecc644597b97e121.png…]()


##### 3.2 本地资源上传

![Uploading 65478670aa8f6bda5ce5f7f0149efcb.png…]()

![24568ec1fdc22ff9c29067a7babce48](https://github.com/xxtenction/new_colin/assets/129744215/d3d5b80a-d236-43d0-a731-ced183765938)


1.创建本地仓库.git

```bash
git init
```

![Uploading 57df345d3b6799d23956f254216c736.png…]()
2.将数据添加到缓冲区

![image-20240606144637557](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240606144637557.png)

```bash
git add filename    #将数据资源添加到git缓冲区

git status    #查看git缓冲区
```

![image-20240606142457461](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240606142457461.png)

![image-20240606142516501](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240606142516501.png)

3、将缓冲区数据提交到本地仓库

```bash
git commit    #提交到本地仓库


git commit -m "备注信息"    #生成提交记录
```



![image-20240606142810502](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240606142810502.png)

![image-20240606142903672](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240606142903672.png)

4、将本地仓库内容推到云端仓库

```bash
git push origin(云端仓库地址) master    

#将本地分支上传到云端，如果分支重名则合并；否则远端创建新的分支保存上传内容
```

![image-20240607125008209](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240607125008209.png)

![image-20240607125002296](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240607125002296.png)



3.3删除

1,还原/删除本地文件

```bash
git restore filename

```

![image-20240607125916331](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240607125916331.png)

```bash
git rm filename    *#删除本地仓库的同时删除本地文件，无法还原*
```







##### 3.4 获取云端数据

###### 3.4.1 下载源码

```bash
git clone https项目地址
```

![image-20240607161029745](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240607161029745.png)

![image-20240607161112475](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240607161112475.png)



###### 3.4.2 拉取仓库

```bash
git pull #获取云端仓库数据
```

![image-20240607161345265](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20240607161345265.png)

**为什么不在云端直接修改，而是要通过git提交?**

如果在云端进行修改，此时云端比本地新，依赖关系被改变，本地无法再进行上传

此时可以先拉取更新云端，再推送本地资源

rebase：可以对某一段线性提交历史进行编辑、删除、复制、粘贴；因此，合理使用rebase命令可以使我们的提交历史干净、简洁！

```bash
git pull --rebase origin master

git rebase --abort    #忽略新版，此时还不能上传 终止变基
git rebase --skip     #需略旧版，更新本地后可以上传 跳过冲突的提交
git rebase --continue #版本合并，解决冲突后可以直接上传 继续变基数
```

![4887e414343408239d2fb6c121267dd](https://github.com/xxtenction/new_colin/assets/129744215/940a7c4a-61df-4d0b-a4c8-19130b1c14fd)



![cd79c502ed5742fff2148319a963489](https://github.com/xxtenction/new_colin/assets/129744215/2cdb987a-2a5a-4849-9d72-67c563b3126f)










markdown 文本修饰语言，用特殊符号修饰正文效果<br>
## 标题修饰符\#

# 一级标题 
## 二级标题 
### 三级标题 
#### 四级标题 
##### 五级标题 
###### 六级标题 

##正文内容 
输入正文内容，但是如果需要换行 用<\br\>标签


## 修饰正文
*特殊字体 斜体 * 
**特效字体 粗体** 
***特效字体 粗斜体****>
   ~~测试文本~~


##分割线
	用\-\-\-表示分割线
	
-------
##引用效果\>表示

> 一级引用
>> 二级引用
>>> 三级引用


## 列表修饰符
### 无序列表 \*
* 无序列表
  * 子集
    * 子集
* 无序列表 
   * 子集

1. 有序列表
   1. 子集
   2. 子集
## 混合列表
1. 测试一级
   2. 测试二级
  * 子集
  
### 表格
名称|技能|排行
--|:--:|--:
蝙蝠侠|有钱|32
蜘蛛侠|勇敢|15
绿巨人|力气大|10

### 代码片段
``` C	
#include<stdio.h>
   int main(){
	printf("hello");
	return 0;
   }

```


### 超链接技术

 [Github](https://www.github.com “点击访问")

### 插入图片
![图片](C:\Users\lenovo\Desktop\1.png"图片演示")
   
   
[![1.png](https://i.postimg.cc/7Z7T4BJp/1.png)](https://postimg.cc/9DmftYpp)

