# 实验6：基于GitHub的实验管理平台的分析与设计
|学号|班级|姓名|
|:-------:|:-------------: | :----------:|
|201710414208|软件(本)17-2|李云东|

***
## 1.概述
- 基于GitHub的实验管理平台的作用是在线管理实验成绩的Web应用系统。学生和老师的实验内容均存放在GitHUB 页面上。
- 学生主要功能：
    1. 登录登出。
    2. 学生选课。
    3. 选择课程查看成绩。
    4. 管理GitHub个人基本信息（查看修改）。


- 老师主要功能：
    1. 登录登出。
    2. 老师选课。
    3. 选择课程管理实验（查看修改）。
    4. 查看学生成绩。
    5. 评定学生成绩。
    6. 管理GitHub个人基本信息（查看修改）。
- 老师和学生都能通过本系统的链接方便地跳转到学生的每个GitHUB实验目录，以便批改实验或者查看实验情况。
- 实验成绩按数字分数计算，每项实验的满分为100分，最低为0分。
- 系统自动计算每个学生的所有实验的平均分。


***

## 2. 系统总体结构
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526095117289.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526095133290.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526095139238.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)

界面设计参见：  https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/index.html
***


## 3. 用例图设计
![\[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-wLwGW7qA-1590427376050)(./UseCase.png )\]](https://img-blog.csdnimg.cn/20200526095147349.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)

用例图源码:[UseCase.puml](src/UseCase.puml)

***

## 4. 类图设计
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526095222345.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)

用例图源码:[class.puml](src/class.puml)

***

## 5. 数据库设计

- ### [参见数据库设计文档](./数据库设计.md)

***


## 6. 用例及界面详细设计

- ### [“修改密码”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/修改用户信息(密码).md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/修改密码.html)
- ### [“修改用户信息”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/修改用户信息(密码).md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/修改用户信息.html)
- ### [“查看成绩（学生）”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/查看成绩_学生.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/查看成绩（学生）.html)
- ### [“查看成绩（老师）”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/查看成绩_老师.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/查看成绩（老师）.html)
- ### [“查看用户信息”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/查看用户信息.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/查看用户信息.html)
- ### [“登出”用例](./用例/登出.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/登出.html)
- ### [“登录（学生）”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/登录.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/登录（学生）.html)
- ### [“登录（老师）”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/登录.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/登录（老师）.html)
- ### [“评定成绩”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/评定成绩.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/评定成绩.html)
- ### [“选课（学生）”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/选课_学生.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/选课（学生）.html)
- ### [“选课（老师）”用例](https://github.com/LiYundong593/is_analysis/tree/master/test6/用例/选课_老师.md),[界面](https://github.com/LiYundong593/is_analysis/tree/master/test6/ui/选课（老师）.html)
   
***
