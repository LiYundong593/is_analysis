# 实验3：图书管理系统领域对象建模
|学号|班级|姓名|
|:-------:|:-------------: | :----------:|
|201710414208|软件(本)17-2|李云东|
## 1. 图书管理系统的类图
### 1.1 类图PlantUML源码如下：
```cpp
@startuml
class 馆藏目录
class 馆藏资源品种
class 预定记录
class 资源项
class 碟片品种
class 图书品种
class 借书记录
class 读者
class 图书管理员2
class 逾期记录
class 罚款细则

馆藏目录 "1"--"1..*" 馆藏资源品种
馆藏资源品种 "1"--"*" 预定记录 : 被预定
馆藏资源品种 "1"*--"*" 资源项 : 拥有
碟片品种 --|> 馆藏资源品种
图书品种 --|> 馆藏资源品种
资源项 "1"--"0..1" 借书记录
逾期记录 "0..1"--"1" 借书记录
读者 -- 借书记录
读者 "1"--"*" 预定记录
图书管理员2 "1"--"*" 借书记录 : 登记
逾期记录 "*"--"0..1" 罚款细则 : 使用

馆藏资源品种 : 资源名称
馆藏资源品种 : 国际出版号
馆藏资源品种 : 价格
馆藏资源品种 : 简介
馆藏资源品种 : 馆藏数量
馆藏资源品种 : 可借数量

资源项 : 馆藏流水号
资源项 : 状态

碟片品种 : 碟片类型
碟片品种 : 碟片数
碟片品种 : 制作公司

图书品种 : 作者
图书品种 : 出版社
图书品种 : 出版日期

借书记录 : 借书日期
借书记录 : 归还日期

读者 : 姓名
读者 : 身份证号
读者 : 借书卡号
读者 : 图书限额
读者 : 已借图书书
读者 : 碟片限额
读者 : 已借碟片数

图书管理员2 : 职工号
图书管理员2 : 姓名

逾期记录 : 逾期天数

预定记录 : 预定日期
@enduml
```

### 1.2. 类图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200406135234467.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)
### 1.3. 类图说明：
1.识别出全部的概念类分别为：
馆藏目录、馆藏资源品种、预定记录、资源项、碟片品种、图书品种、借书记录、读者、图书管理员2、逾期记录、罚款细则

 2.添加概念类的属性：例如：馆藏资源品种 : 资源名称
馆藏资源品种 : 国际出版号
馆藏资源品种 : 价格
馆藏资源品种 : 简介
馆藏资源品种 : 馆藏数量
馆藏资源品种 : 可借数量

3.将所有的概念类关联起来：（关系的声明）
| 关系 | 符号|说明|
| :------ | :------ | :------ |
| 接口与实现关系 |<1..或者..1> | 带空心三角型的虚线表示 |
| 依赖(Dependency)关系 |<..或者..>|  带箭头的虚线表示 |
| 单向关联(Association) |<-- 或者 -->	 | 带箭头的实线表示 |
| 双向关联 |--| 直线表示 |
| 多重性关联 |“1..*”<--"0..*"或者 “0..*”--“1..*”|  关联直线上用一个数字或者一个数字的范围表示 |
| 聚合(Aggregation)关系 |o--或者--o	|  英语O 1带空心菱形的直线表示 |
| 组合(Composition)关系	 |*--或者--* | 带实心的菱形的直线表示|
| 泛化关系(继承[Inheritance]) | <1-- 或者 --1>| 带空心三角型的直线表示 |

4.泛化处理形成领域模型


## 2. 图书管理系统的对象图
### 2.1 读者的对象图
#### 源码如下：
```cpp
@startuml
object 读者 {
姓名 : 李大帅
身份证号 : 5110************20
借书卡号 : 201710414208
图书限额 : 50
已借出图书数目 : 12
碟片限额 : 20
已借出碟片数 : 6
}
@enduml
```
#### 对象图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020040614301174.png)
### 2.2 图书管理员的对象图
#### 源码如下：
```cpp
@startuml
object 图书管理员 {
职工号 :20171234566
姓名 : 张大帅
}
@enduml
```
#### 对象图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200406142357284.png)
